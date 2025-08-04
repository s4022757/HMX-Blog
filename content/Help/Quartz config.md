---
title: Example title
description: 
date: 
draft: true
tags: 
permalink: 
aliases:
---
## General Configuration

This part of the configuration concerns anything that can affect the whole site. The following is a list breaking down all the things you can configure:

- `pageTitle`: title of the site. This is also used when generating the [RSS Feed](https://quartz.jzhao.xyz/features/RSS-Feed) for your site.
- `pageTitleSuffix`: a string added to the end of the page title. This only applies to the browser tab title, not the title shown at the top of the page.
- `enableSPA`: whether to enable [SPA Routing](https://quartz.jzhao.xyz/features/SPA-Routing) on your site.
- `enablePopovers`: whether to enable [popover previews](https://quartz.jzhao.xyz/features/popover-previews) on your site.
- `analytics`: what to use for analytics on your site. Values can be
    - `null`: don’t use analytics;
    - `{ provider: 'google', tagId: '<your-google-tag>' }`: use Google Analytics;
    - `{ provider: 'plausible' }` (managed) or `{ provider: 'plausible', host: 'https://<your-plausible-host>' }` (self-hosted, make sure to include the `https://` protocol prefix): use [Plausible](https://plausible.io/);
    - `{ provider: 'umami', host: '<your-umami-host>', websiteId: '<your-umami-website-id>' }`: use [Umami](https://umami.is/);
    - `{ provider: 'goatcounter', websiteId: 'my-goatcounter-id' }` (managed) or `{ provider: 'goatcounter', websiteId: 'my-goatcounter-id', host: 'my-goatcounter-domain.com', scriptSrc: 'https://my-url.to/counter.js' }` (self-hosted) use [GoatCounter](https://goatcounter.com/);
    - `{ provider: 'posthog', apiKey: '<your-posthog-project-apiKey>', host: '<your-posthog-host>' }`: use [Posthog](https://posthog.com/);
    - `{ provider: 'tinylytics', siteId: '<your-site-id>' }`: use [Tinylytics](https://tinylytics.app/);
    - `{ provider: 'cabin' }` or `{ provider: 'cabin', host: 'https://cabin.example.com' }` (custom domain): use [Cabin](https://withcabin.com/);
    - `{provider: 'clarity', projectId: '<your-clarity-id-code' }`: use [Microsoft clarity](https://clarity.microsoft.com/). The project id can be found on top of the overview page.
- `locale`: used for [i18n](https://quartz.jzhao.xyz/features/i18n) and date formatting
- `baseUrl`: this is used for sitemaps and RSS feeds that require an absolute URL to know where the canonical ‘home’ of your site lives. This is normally the deployed URL of your site (e.g. `quartz.jzhao.xyz` for this site). Do not include the protocol (i.e. `https://`) or any leading or trailing slashes.
    - This should also include the subpath if you are [hosting](https://quartz.jzhao.xyz/hosting) on GitHub pages without a custom domain. For example, if my repository is `jackyzha0/quartz`, GitHub pages would deploy to `https://jackyzha0.github.io/quartz` and the `baseUrl` would be `jackyzha0.github.io/quartz`.
    - Note that Quartz 4 will avoid using this as much as possible and use relative URLs whenever it can to make sure your site works no matter _where_ you end up actually deploying it.
- `ignorePatterns`: a list of [glob](https://en.wikipedia.org/wiki/Glob_\(programming\)) patterns that Quartz should ignore and not search through when looking for files inside the `content` folder. See [private pages](https://quartz.jzhao.xyz/features/private-pages) for more details.
- `defaultDateType`: whether to use created, modified, or published as the default date to display on pages and page listings.
- `theme`: configure how the site looks.
    - `cdnCaching`: if `true` (default), use Google CDN to cache the fonts. This will generally be faster. Disable (`false`) this if you want Quartz to download the fonts to be self-contained.
    - `typography`: what fonts to use. Any font available on [Google Fonts](https://fonts.google.com/) works here.
        - `title`: font for the title of the site (optional, same as `header` by default)
        - `header`: font to use for headers
        - `code`: font for inline and block quotes
        - `body`: font for everything
    - `colors`: controls the theming of the site.
        - `light`: page background
        - `lightgray`: borders
        - `gray`: graph links, heavier borders
        - `darkgray`: body text
        - `dark`: header text and icons
        - `secondary`: link colour, current [graph](https://quartz.jzhao.xyz/features/graph-view) node
        - `tertiary`: hover states and visited [graph](https://quartz.jzhao.xyz/features/graph-view) nodes
        - `highlight`: internal link background, highlighted text, [highlighted lines of code](https://quartz.jzhao.xyz/features/syntax-highlighting)
        - `textHighlight`: markdown highlighted text background