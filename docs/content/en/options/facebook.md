---
title: Facebook
description: 'You can configure facebook specific options using nuxt-seo with the "seo.facebook" property in your NuxtJS site'
category: Options
position: 4
---

You can configure your global facebook options within the `seo` property in your `nuxt.config.js`

You may also set page specific facebook options via the Nuxt `head` or `asyncData` methods.

For most websites, these values are unlikely change for each page. So setting them once via the global config may be the best option.

## Options

All Facebook options can be accessed via the `seo.facebook` or `seo.fb` properties.

```js{}[nuxt.config.js]
export default {
  seo: {
    facebook: {
      appId: '',
      pageId: '' 
    },
  }
}
```

### `appId`

The facebook app id

- Default: `false`
- Type: `String`

### `pageId`

The facebook page id

- Default: `false`
- Type: `String`
