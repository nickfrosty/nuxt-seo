---
title: Configuration
description: 'You can configure "nuxt-seo" with the "seo" property in your nuxt.config.js.'
category: "Getting Started"
position: 3
---

You can configure `nuxt-seo` with the `seo` property in your `nuxt.config.js`.

## Default options

```js{}[nuxt.config.js]
export default {
  seo: {
    // My custom configuration
    baseUrl: 'https://domain',
    name: '<name of site>',
    title: '<title default>',
    templateTitle: '%name% - %title%',
    description: '<description default>',
    canonical: 'auto',
    isForcedTrailingSlash: false
  }
}
```

Since these options are commonly set for every site, this configuration is considered the "default".

<alert type="info">

Check out the explanation of each of these [basic options](/options/basic)

</alert>

## Global default options

The options set vie the `seo` property in your `nuxt.config.js` file will be automatically added to every page. 


<alert type="info">

Your global default options may also overridden or removed while setting each page specific options. See [Usage](/usage) for more details on page specific options.

</alert>

Common "global" default options include:

- meta tags for every page, and their values (e.g. title, description, keywords, etc)
- social media handles (e.g. Twitter, Facebook, etc)
- author tags and "humans.txt"

## All options

For the full explanation of each available option:

- [Basic options](/options/basic)
- [Twitter options](/options/twitter)
- [OpenGraph options](/options/opengraph)