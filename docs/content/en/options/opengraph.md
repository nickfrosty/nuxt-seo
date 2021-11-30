---
title: OpenGraph
description: 'You can configure OpenGraph specific options using @nickfrosty/nuxt-seo with the "seo.openGraph" property in your NuxtJS site'
category: Options
position: 2
---

You can configure your global OpenGraph options within the `seo` property in your `nuxt.config.js`

You may also set page specific OpenGraph options via the Nuxt `head` or `asyncData` methods.

In general, most website will want to set some specific default OpenGraph options in the `nuxt.config.js` file. Then set page specific options, like `title` and `description`. 

For most websites, these values will likely change for each page.

## OpenGraph Resources

Read about the OpenGraph protocol on the [official website](https://ogp.me/).

### Test your OpenGraph Data

Ensuring your OpenGraph SEO settings are correctly configured is important. Without doing so, your website's social media posts may not show up properly in feeds.

## General Options

All OpenGraph options can be accessed via the `seo.openGraph` or `seo.og` properties.

```js{}[nuxt.config.js]
export default {
  seo: {
    openGraph: {
      site: '@nickfrosty', 
      creator: '@nickfrosty',
      card: '', 
      type: '', 
      title: '', 
      description: '', 
    },
  }
}
```

### `name`

The website's name to be displayed via the OpenGraph protocol

- Default: value set by `seo.name`
- Type: `String`

### `title`

The specific page title to be displayed via the OpenGraph protocol

- Default: value set by `seo.title`
- Type: `String`

### `description`

The specific page description to be displayed via the OpenGraph protocol

- Default: value set by `seo.description`
- Type: `String`

### `url`

The page url used while sharing your page on social media platforms.

- Default: value set by `seo.url`
- Type: `URL String`

### `locale`

The local code used by your website

- Default: value set by `seo.lang`
- Type: `String`

### `type`

The string `type` of primary content on the page

- Default: `false`
- Type: `String`

OpenGraph supports many different content types. And depending on the type selected, other data may be required. Some examples of types are listed below. This list is not all inclusive:

- `website` - the most basic form of type
- `article` - read more on the [OpenGraph article](/options/opengraph_more#article-options) property
- `book` - read more on the [OpenGraph book](/options/opengraph_more#book-options) property
- `profile` - read more on the [OpenGraph profile](/options/opengraph_more#profile-options) property

<alert type="info">
You can read more about OpenGraph types on their <a target="_blank" href="https://ogp.me/#types">website</a>
</alert>

## Image Options

The OpenGraph protocol supports setting an "image" property for the page. 

This can be set using the `seo.openGraph.image` property. Usually set for each specific page, but you can also set your default image options in the global `seo` property in `nuxt.config.js`

<alert type="info">
`<em>seo.openGraph.images</em>` is an alias of `<em>seo.openGraph.image</em>`
</alert>

```vue
<script>
  export default {
    head({ $seo }) {
      return $seo({
        openGraph: {
          image: {
            currency: '',
            amount: ''
          }
        }
      })
    }
  }
</script>
```

### `url`

- Default: `false`
- Type: `String`

### `alt`

- Default: `false`
- Type: `String`

### `multi`

- Default: `true`
- Type: `Boolean`

### `width`

- Default: `false`
- Type: `String`

### `height`

- Default: `false`
- Type: `String`