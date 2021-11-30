---
title: Basic
description: 'You can configure @nickfrosty/nuxt-seo with the "seo" property in your nuxt.config.js.'
category: Options
position: 1
---

You can configure your global options with the `seo` property in your `nuxt.config.js`

You may also set page specific options via the Nuxt `head` or `asyncData` methods.

```js{}[nuxt.config.js]
export default {
  seo: {
    // Your custom configuration
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

## Options

### `baseUrl`

Your website's base url (e.g. `https://example.com`). This will automatically prefix all generated `canonical` urls.

- Default: ``
- Type: `String`

### `name`

The name of your website or Nuxt app

- Default: `false`
- Type: `String`

### `title`

The specifc title for the individual page being loaded

- Default: `Title`
- Type: `String`

### `templateTitle`

Simple string template to dynamically set the page `<title>` 

- Default: `%title%`
- Type: `String`

#### Supported template variables:
- `%title%`: will be replaced with `$seo.title`
- `%name%`: will be replaced with `$seo.name`

#### Example

```js [nuxt.config.js]
{
  seo: {
    name: 'My Site',
    title: 'Home page',
    templateTitle: '%name% - %title%'
  }
}
```

Result: `My Site - Home page`


### `description`

Meta description for the page

- Default: `false`
- Type: `String`

### `keywords`

Meta keywords for the page

- Default: `[]`
- Type: `String` || `Array[...keywords]`


### `canonical`

Set the canonical url for the page

- Default: `auto`
- Type: `String`

<alert type="info">
When set to `auto`, the page canonical url will automatically generate according to the route.
</alert>

### `isForcedTrailingSlash`

Allows forcing a trailing slash in the `canonical` url

- Default: `true`
- Type: `Boolean`

### `author`

Set the author meta tag of the website, or a specific page. 

- Default: `false`
- Type: `String` || `Array[name, email || site]`

<alert type="info">
You can read more about the "author meta tag" on <a target="_blank" href="https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML#adding_an_author_and_description">mozilla.org</a>
</alert>

#### String example

```js [nuxt.config.js]
{
  seo: {
    author: 'Nick Frostbutter'
  }
}
```

Resultant meta tag: 
```html
<meta data-hid="author" key="author" property="author" name="author" content="Nick Frostbutter">
```

### `charset`

Set the default character set for your website

- Default: `utf-8`
- Type: String

### `lang`

Set the short version of your website's language. Used together with `language`

- Default: `en`
- Type: String

### `language`

Set the full text version of your website's language. Used together with `lang`

- Default: `English`
- Type: String

## Social options

The `nuxt-seo` module has default support for several standards for embedding rich content on social media platforms. 


### `url`

The page url used while sharing your page on social media platforms.

- Default: `false`
- Type: `URL String`

> #### openGraph.url default
> When set, this `url` value will become the default for the `openGraph.url` option. See [OpenGraph options](/options/opengraph) for more details.

### `image`

The image used while sharing your page on social media platforms.

- Default: `false`
- Type: `URL String`

> #### openGraph.image default
> When set, this `image` value will become the default for the `openGraph.image` option. See [OpenGraph options](/options/opengraph) for more details.

### `openGraph`

See the [OpenGraph specific](/options/opengraph) options

### `twitter`

See the [Twitter specific](/options/twitter) options

## More options

`copyright`, `subtitle`, `replyTo`, `noindex.ids.0`, `noindex.ids.1`, `noindex.ids`, `noindex.value.0`, `noindex.value.1`, `noindex.value`, `noindex`, `robots.ids.0`, `robots.ids.1`, `robots.ids`, `robots`, 

`openGraph.name`, `openGraph.title`, `openGraph.description`, `openGraph.locale`, `openGraph.url`, `openGraph.type`, `openGraph.profile.firstName`, `openGraph.profile.lastName`, `openGraph.profile.username`, `openGraph.profile.gender`, `openGraph.profile`, `openGraph.article.publishedTime`, `openGraph.article.modifiedTime`, `openGraph.article.expirationTime`, `openGraph.article.author.multi`, `openGraph.article.author`, `openGraph.article.section`, `openGraph.article.tag.multi`, `openGraph.article.tag`, `openGraph.article.authors.multi`, `openGraph.article.authors`, `openGraph.article.tags.multi`, `openGraph.article.tags`, `openGraph.article`, `openGraph.image.multi`, `openGraph.image.url`, `openGraph.image.width`, `openGraph.image.height`, `openGraph.image.alt`, `openGraph.image`, `openGraph.book.author.multi`, `openGraph.book.author`, `openGraph.book.isbn`, `openGraph.book.releaseDate`, `openGraph.book.tag.multi`, `openGraph.book.tag`, `openGraph.book.authors.multi`, `openGraph.book.authors`, `openGraph.book.tags.multi`, `openGraph.book.tags`, `openGraph.book`, `openGraph.price.currency`, `openGraph.price.amount`, `openGraph.price`, `openGraph.images.multi`, `openGraph.images.url`, `openGraph.images.width`, `openGraph.images.height`, `openGraph.images.alt`, `openGraph.images`, `openGraph`, 

`facebook.appId`, `facebook.pageId`, `facebook`, 

`article.publishedTime`, `article.modifiedTime`, `article.expirationTime`, `article.author.multi`, `article.author`, `article.section`, `article.tag.multi`, `article.tag`, `article.authors.multi`, `article.authors`, `article.tags.multi`, `article.tags`, `article`, 

`book.author.multi`, `book.author`, `book.isbn`, `book.releaseDate`, `book.tag.multi`, `book.tag`, `book.authors.multi`, `book.authors`, `book.tags.multi`, `book.tags`, `book`, 

`image.multi`, `image.url`, `image.width`, `image.height`, `image.alt`, `image`, `images.multi`, `images.url`, `images.width`, `images.height`, `images.alt`, 
`images`, 