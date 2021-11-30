---
title: More OpenGraph
description: 'You can configure more OpenGraph specific options using @nickfrosty/nuxt-seo with the "seo.openGraph" property in your NuxtJS site'
category: Options
position: 5
---

Since the [OpenGraph protocol](https://ogp.me) supports a wide variety of SEO rich data, these less commonly used options have be segmented here.

Due to the unique nature of these options, it is likely these will be set only on unique specific pages via the `head` or `asyncData` methods. As such, the examples given will be in this context.

## Article Options

The OpenGraph protocol supports setting an "article" property for the page. 

This can be set using the `seo.openGraph.article` property, usually from a specific page like a single blog.

```vue
<script>
  export default {
    head({ $seo }) {
      return $seo({
        openGraph: {
          article: {
            publishedTime: '',
            modifiedTime: '',
            expirationTime: '',
            section: '',

            /* Author options */
            author: '',
            author.multi: '',
            authors: '',
            authors.multi: '',
            
            /* Tag options */
            tag: '',
            tag.multi: '',
            tags: '',
            tags.multi: '',
          }
        }
      })
    }
  }
</script>
```

### `publishedTime`

- Default: `false`
- Type: `String`

### `modifiedTime`

- Default: `false`
- Type: `String`

### `expirationTime`

- Default: `false`
- Type: `String`

### `section`

- Default: `false`
- Type: `String`

### `author`

- Default: `false`
- Type: `String`

### `author.multi`

- Default: `true`
- Type: `Boolean`

### `authors`

- Default: `false`
- Type: `String`

### `authors.multi`

- Default: `true`
- Type: `Boolean`

### `tag`

- Default: `false`
- Type: `String`

### `tag.multi`

- Default: `true`
- Type: `Boolean`

### `tags`

- Default: `false`
- Type: `String`

### `tags.multi`

- Default: `true`
- Type: `Boolean`


## Profile Options

The OpenGraph protocol supports setting a "profile" property for the page. 

This can be set using the `seo.openGraph.profile` property, usually from a specific page like a user's public profile.

```vue
<script>
  export default {
    head({ $seo }) {
      return $seo({
        openGraph: {
          profile: {
            firstName: '',
            lastName: '',
            username: '',
            gender: '',
          }
        }
      })
    }
  }
</script>
```

### `firstName`

- Default: `false`
- Type: `String`

### `lastName`

- Default: `false`
- Type: `String`

### `username`

- Default: `false`
- Type: `String`

### `gender`

- Default: `false`
- Type: `String`

## Book Options

The OpenGraph protocol supports setting a "book" property for the page. 

This can be set using the `seo.openGraph.book` property, usually from a specific page.

```vue
<script>
  export default {
    head({ $seo }) {
      return $seo({
        openGraph: {
          book: {
            author: '',
            isbn: '',
            releaseDate: '',
            tags: ''
          }
        }
      })
    }
  }
</script>
```

### `author`

- Default: `false`
- Type: `String`

### `author.multi`

- Default: `true`
- Type: `Boolean`

### `isbn`

- Default: `false`
- Type: `String`

### `releaseDate`

- Default: `false`
- Type: `String`

### `tag.multi`

- Default: `true`
- Type: `Boolean`

### `tag`

- Default: `false`
- Type: `String`

### `authors.multi`

- Default: `true`
- Type: `Boolean`

### `authors`

- Default: `false`
- Type: `String`

### `tags.multi`

- Default: `true`
- Type: `Boolean`


## Price Options

The OpenGraph protocol supports setting a "price" property for the page. 

This can be set using the `seo.openGraph.price` property, usually from a specific page.

```vue
<script>
  export default {
    head({ $seo }) {
      return $seo({
        openGraph: {
          price: {
            currency: '',
            amount: ''
          }
        }
      })
    }
  }
</script>
```

### `currency`

- Default: `false`
- Type: `String`

### `amount`

- Default: `false`
- Type: `String`