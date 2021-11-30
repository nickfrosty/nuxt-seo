---
title: Setup
description: 'Setup and install @nickfrosty/nuxt-seo your Nuxt project.'
category: Getting started
position: 2
---


## Install via NPM or Yarn

Add `@nickfrosty/nuxt-seo` dependency to your project:

<code-group>
  <code-block label="NPM" active>

  ```bash
  npm install @nickfrosty/nuxt-seo
  ```

  </code-block>
  <code-block label="Yarn">

  ```bash
  yarn add @nickfrosty/nuxt-seo
  ```

  </code-block>
</code-group>

## Setup

Then, add `@nickfrosty/nuxt-seo` to the `modules` section of `nuxt.config.js`:

```js[nuxt.config.js]
{
  modules: [
    '@nickfrosty/nuxt-seo'
  ],
  seo: {
    // Module Options
  }
}
```