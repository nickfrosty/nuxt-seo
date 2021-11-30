---
title: Usage
description: 'Setup a the nuxt-seo module to improve on page SEO for any Nuxt website or application'
category: Getting started
position: 4
---

This `nuxt-seo` module allows you to set page specific SEO settings in three ways:

- global defaults
- the Nuxt `head` method
- or using `asyncData`


## Global defaults

Your site's "_global defaults_" are set via the  `nuxt.config.js` file. Those options will be written into every page's head data automatically.

<alert type="info">

You may locally override any global `$seo` options while setting page specific options. When doing so, the changes will only take effect for that specific page. 

</alert>

For more information on the recommended global defaults, see [Configuration](/configuration)

## head method

The most common way to set page specific SEO settings is though the Nuxt `head()` method. Here, you will have access to `$seo` from the global context.

- `head() { return this.$seo(options) }`
- `head({ $seo }) { return $seo(options) }`

```vue
<template>
  <h1>Hello World</h1>
</template>

<script>
  export default {
    head({ $seo }) {
      return $seo({
        title: 'Home Page',
        description: 'Hello World Page',
        keywords: 'hello, world, home',
      })
    }
  }
</script>
```

While accessing `$seo` in the Nuxt `head()` function, you will have access to the `context` object ncluding all `props`, `data`, and `computed` values. Even any prefetched/prerendered data from `asyncData`.

## asyncData method

You may also set page specific SEO settings via `asyncData`.

<alert type="warning">

Setting your SEO options via the `asyncData` should <b><u>NOT</u></b> be done in Server-Side Rendering (SSR) mode.
For SSR, you should use the Nuxt head method above.

</alert>

- `asyncData({ seo }) { seo(options) }`
- `asyncData({ $seo }) { $seo(options) }`
- `asyncData() { this.seo(options) }`
- `asyncData() { this.$seo(options) }`

```vue
<template>
	<h1>Hello World</h1>
</template>

<script>
	export default {
		asyncData({ $seo }) {
			$seo({
				title: 'Home Page',
				templateTitle: '%name% - %title%',
				description: 'Hello World Page'
			})
		}
	}
</script>
```