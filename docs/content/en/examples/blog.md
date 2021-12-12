---
title: Blog
description: 'How to can configure "nuxt-seo" for a blog website'
category: Examples
position: 1
---

A common use for the `nuxt-seo` module is to create a personal blog, using the [`nuxt/content`](https://content.nuxtjs.org) module.

The example site has the `nuxt/content` module setup and installed, allowing us to have a content blog powered by markdown files.

## What is in this example?

This "blog website" example demonstrates:

- default SEO settings in `nuxt.config.js` for every page
- unique SEO setting on the site's home page, changing the `templateTitle`
- a blog listing page
- unique blog post page with custom social images

<alert type="info">

This example will <b>NOT</b> go into the full details of how to use the `nuxt/content` module. If you are unfamiliar, check out <a href="">this tutorial</a>.

</alert>

## Default SEO settings

Set your default global SEO settings using the `seo` property in your `nuxt.config.js` file.

```js{}[nuxt.config.js]
export default {
  seo: {
    baseUrl: 'https://frostbutter.com',
    name: 'Site Name',
    templateTitle: '%name% — %title%',
    description: "Hi! I'm Nick, an indie developer.",
    keywords: 'indie, developer, nuxt',
    canonical: 'auto',
    isForcedTrailingSlash: false,
    author: 'Nick Frostbutter',
    openGraph.image: {
      url: 'https://frostbutter.com/img/nick.jpg',
    },
    twitter: { 
      site: '@nickfrosty', 
      creator: '@nickfrosty',
      card: 'summary',
    },
  }
}
```

## Site's home page

Our website can have a home page (`pages/index.vue`) that updates the `seo.templateTitle` option for this page only. As well as setting unique SEO meta data for this page.

```vue[/pages/index.vue]
<template>
  <h1>Hello World</h1>
</template>

<script>
  export default {
    asyncData({ $seo }) {
      $seo({
        title: 'No place like home',
        templateTitle: '%title%',
        description: 'This is the meta description for the home page only',
        keywords: 'index, home, page',
      })
    }
  }
</script>
```

Since we overrode the global `seo.templateTitle` on the homepage, it will now have a title that is `No place like home`

## Blog posts listing

With the `nuxt/content` module setup and installed, we can set create a blog post listing page that is very similar to the home page.

```vue[/pages/blog/index.vue]
<template>
  <div>
    <h1>Blog post listing page</h1>
    <section>
      <div v-for="post in posts" :key="post.title">
        <nuxt-link :to="'/blog/'+post.slug"></nuxt-link>
      </div>
    </section>
  </div>
</template>

<script>
  export default {
    async asyncData({ params, error, $content }) {
      const posts = await $content("blog", { deep: true }).fetch();
      return { posts };
    },
    head({ $seo }) {
      return $seo({
        title: 'Blog',
        description: 'Check out these posts',
        keywords: 'blog, listing, articles',
      });
    }
  }
</script>
```

This "blog" index page will have meta tags for `description` and `keywords`. With a page `title` of `Site Name - Blog` (being set using the **global** `templateTitle`)

## Markdown based blog post

Let's say we have a markdown blog post inside the `/content/blog/` folder name `post1.md`

```md[/content/blog/post1.md]
---
title: 'Post 1 Title'
description: 'This is the description for blog post 1. and only blog post 1'
keywords: 'test, example, custom'
image: https://example.com/image.jpg
tags:
- devlog
- boomerang
---
This is the blog post page content. Write something good :)
```

Note that this markdown file has YAML head information saved, including:

- post `title`
- custom post `description` and `keywords`
- and an `image` url to use for social media.

## Individual blog post

Lastly, we have our blog post viewing page, located at `/pages/blog/_slug.vue`. Allowing us to access the Nuxt `params.slug` parameter to find the actual blog post to display.

Using `asyncData`, we can retrieve the specific blog post's mardown file. Saving it into the `post` variable.

```vue[/pages/blog/_slug.vue]
<template>
  <article>
    <h1>{{ post.title }}</h1>
    <img :src="post.image" :alt="post.title" />
    <nuxt-content :document="post" />
  </article>
</template>

<script>
  export default {
    async asyncData({ params, error, $content }) {
      const [post] = await $content("blog", { deep: true })
        .where({ slug: params.slug })
        .fetch();
      return { post };
    },
    head({ $seo }) {
      return $seo({
        title: this.post.title,
        description: this.post.description || 'fallback description',
        keywords: keywords,
        image: this.post.image || '',
        twitter.card: 'summary_large_image'
      });
    },
    computed: {
      keywords(){
        return this.post.keywords ? this.post.keywords : this.$seo.keywords;
      }
    }
  }
</script>
```

Once we have the specific blog post's markdown file, we can access all the post's info. Including the YAML head data we set earlier. Like the post's `descriotion`, `title`, `image`, etc.

Using the `head` method, we set the any of the page's `seo` options, based on the post's contents. 

In this specific example, we set a unique page `title`, `description`, `keywords`, `image`, and `twitter.card`. But you can of course set any of the `seo` options here.

### SEO title

The page's title becomes the `post.title`, after it has been processed by the global `templateTitle` set in our `nuxt.config.js`.

### SEO description

Here we are setting the page's meta description via `seo.description`. First we try to set it to `post.description`. If no post description is saved in the markdown file, then we default to a string of `fallback description`.

<alert type="info">
This examples uses a JavaScript <a target="_blank" href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Logical_OR">logical OR statement</a>. That's the "||" symbol.
</alert>

### SEO keywords

Next we set the keywords using a computed property named `keywords`, allowing us to keep any logic for parsing our post keywords. 

This is not _really_ necessary in the case, but just to demonstrate using computed properties with the module.

<alert type="info">
When setting your `seo` options via `head` method, you will have access to all the <a target="_blank" href="https://vuejs.org/v2/guide/computed.html">computed properties</a> like normal in Vue/Nuxt.
</alert>

### Twitter card and image

Since our blog post will have a primary "hero" style image, we override the global `twitter.card` option we set prior with a the larger image card type accepted by Twitter. 

Lastly, we set the `image` option of the primary image from the blog post itself.

<alert type="info">

Reminder: the `image` property is an alias for the <a href="/options/opengraph#image-options">OpenGraph image</a>, which is also accepted by Twitter in their card system.

</alert>