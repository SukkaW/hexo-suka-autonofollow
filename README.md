# hexo-filter-nofollow

Adds nofollow attribute to all external links in your hexo blog posts automatically.

## Features
* Add `rel="external nofollow noopener noreferrer"` to all external links for security, privacy and SEO. [Read more](https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types).
* Add `target="_blank"`, Open external links in new window or tab. This can be disabled, see below.

Hexo doesn't insert `target="_blank"` to all external links even if you set `external_link: true` (default value) in the _config.yml.
This plugin make sure all external links are processed.

For example,
```markdown
[example-link](https://example.com)
```
Becomes,
```html
<a href="https://example.com" rel="external nofollow noopener noreferrer" target="_blank">example-link</a>
```

## Install

``` bash
$ npm install hexo-autonofollow --save
```

## Options

You can configure this plugin in `_config.yml`.

```
nofollow:
  enable: true
  exclude:
    - exclude1.com
    - exclude2.com
```

- **enable** - Enable the plugin. Defaults to **false**.
- **exclude** - Exclude hostname.

## About

This plugin is originally based on [hexo-autonofollow](https://github.com/liuzc/hexo-autonofollow) (by [liuzc](https://github.com/liuzc)) and share its options, thus suitable as a drop-in replacement. By dropping [cheerio](https://github.com/cheeriojs/cheerio) and replacing it with native regex, this plugin can perform faster and avoid certain [cheerio's](https://github.com/cheeriojs/cheerio/issues/1198) [quirks](https://github.com/cheeriojs/cheerio/issues/1031).
