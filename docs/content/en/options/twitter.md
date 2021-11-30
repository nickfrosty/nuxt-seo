---
title: Twitter
description: 'You can configure Twitter specific options using @nickfrosty/nuxt-seo with the "seo.twitter" property in your NuxtJS site'
category: Options
position: 3
---

You can configure your global twitter options within the `seo` property in your `nuxt.config.js`

You may also set page specific twitter options via the Nuxt `head` or `asyncData` methods.

In general, most website will want to set some specific default Twitter options in the `nuxt.config.js` file. Then set page specific options, like `title` and `description`. 

For most websites, these values will likely change for each page.

## Twitter Resources

If you are new to using Twitter cards, you can read the official getting started guide on [developer.twitter.com](https://developer.twitter.com/en/docs/twitter-for-websites/cards/guides/getting-started) or the listing of all card [markup options](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/markup)

### Test your Twitter Card

Ensuring your Twitter SEO settings are correctly configured is important. Without doing so, your website's Twitter info may not show up properly while links in tweets.

Be sure to test your page settings with the [official Twitter Card Validator](https://cards-dev.twitter.com/validator)

### Official Twitter Docs

You can find more about the specifics of each type of Twitter card from the official Twitter docs:

- [summary cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/summary)
- [summary card with large image](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/summary-card-with-large-image)
- [player card](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/player-card)
- [app card](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/app-card)

## Options

All Twitter options can be accessed via the `seo.twitter` property.

```js{}[nuxt.config.js]
export default {
  seo: {
    twitter: {
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

### `site`

The Twitter username for the website or app. This should include the "@" symbol

- Default: `false`
- Type: `String`

<alert type="info">
For websites that have only one person creating and posting content, the `site` and `creator` will likely be set the the same Twitter username.
</alert>

### `creator`

The Twitter username for the creator of the page's content. This should include the "@" symbol

- Default: `false`
- Type: `String`

<alert type="info">
For websites that have multiple people creating and posting content, all under the same "organization", the `site` and `creator` will likely be <b>different</b>. The `site` may be the company's Twitter handle, and the `creator` may be the specific person who created the content.
</alert>

### `title`

The specific page title to be displayed by the Twitter card

- Default: value set by `seo.title`
- Type: `String`

### `description`

The specific page description to be displayed by the Twitter card

- Default: value set by `seo.description`
- Type: `String`

### `card`

The string name of the type of Twitter card for the page to use 

- Default: `false`
- Type: `String`
- Values: `summary` | `summary_large_image` | `app` | `player`

### `type`

Alias of `card`
