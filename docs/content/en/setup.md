---
title: Setup
description: 'Setup and install "nuxt-seo" on your Nuxt project.'
category: "Getting Started"
position: 2
---


## Install via NPM or Yarn

Add `nuxt-seo` dependency to your project:

<code-group>
  <code-block label="NPM" active>

  ```bash
  npm install nuxt-seo
  ```

  </code-block>
  <code-block label="Yarn">

  ```bash
  yarn add nuxt-seo
  ```

  </code-block>
</code-group>

## Setup

Then, add `nuxt-seo` to the `modules` section of `nuxt.config.js`:

```js[nuxt.config.js]
{
  modules: [
    'nuxt-seo'
  ],
  seo: {
    // Module Options
  }
}
```