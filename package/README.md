# nuxt-seo

SEO / HTML meta tags module for NuxtJS

## Features

- Easy to use, on page SEO
- Page title templating
- Set default global SEO settings/tags
- Customize all SEO options for each page 
- Canonical tag automatically generated
- Supports the OpenGraph protocol
- Twitter card support

[![nuxt-seo](/docs/static/preview.png)](https://nuxt-seo.frostbutter.com)

<p align="center">
  <a href="https://nuxt-seo.frostbutter.com">Read Documentation</a>
</p>

[📖 **Release Notes**](./CHANGELOG.md)

## Local development and testing

To work on a local version of the `nuxt-seo` package (e.g. feature/bug development or testing):

1. Download the `nuxt-seo` repo from GitHub (either via `git clone` or the zip archive)
2. On your local computer, change directory into the `packages` directory
3. Install the dependencies via `npm install`
4. Run `npm link` to create a local linked package on your for your currently logged in user account

From inside a Nuxt project that you desired to test your local changes, associate your local `nuxt-seo` package version by performing the following:

1. Change directory to your root project directory (likely the directory with your `node_modules` directory)
2. Run `npm link nuxt-seo` to create the local package association
3. Now, any changes to the local `nuxt-seo` package, will be utilized in this current project on your local machine.

> Note: After saving local changes to the `nuxt-seo` package, you may need to restart your Nuxt project's development server (or rebuild your project via saving the `nuxt.config.js` file again). Sad, I know.

## License

[MIT](LICENSE) © [Nick Frostbutter](https://frostbutter.com)

## Original credits

Original credits go to [TiagoDanin](https://github.com/TiagoDanin/Nuxt-SEO) for the "Nuxt-SEO" package. In [old issue #109](https://github.com/TiagoDanin/Nuxt-SEO/issues/109), the project was archived.

Original License: 
[MIT](https://github.com/TiagoDanin/Nuxt-SEO/blob/master/LICENSE) © [Tiago Danin](https://TiagoDanin.github.io)