# Search syntax

SearXJP comes with a search syntax by which you can modify the categories,
engines, languages, and more. See the {{link('preferences', 'preferences')}} for
the list of engines, categories, and languages.

## `!` Select engine and category

To set category and/or engine names, use a `!` prefix. To give a few examples:

- Search Wikipedia for **Tokyo**:

  - {{search('!wp Tokyo')}}
  - {{search('!wikipedia Tokyo')}}

- Search in category **map** for **Tokyo**:

  - {{search('!map Tokyo')}}

- Image search

  - {{search('!images Mt. Fuji')}}

Abbreviations of the engines and languages are also accepted. Engine/category
modifiers are chainable and inclusive. For example, {{search('!map !ddg !wp
Tokyo')}} searches in the map category and searches DuckDuckGo and Wikipedia for **Tokyo**.

## `:` Select language

To select a language filter use a `:` prefix. To give an example:

- Search Wikipedia with a custom language (Japanese):

  - {{search(':ja !wp Samurai')}}

## `!!<bang>` External bangs

SearXJP supports the external bangs from [DuckDuckGo]. To directly jump to a
external search page use the `!!` prefix. To give an example:

- Search Wikipedia (Japanese Edition) directly:

  - {{search('!!wja Ninja')}}

Please note that your search will be performed directly in the external search
engine. SearXJP cannot protect your privacy with this.

[DuckDuckGo]: https://duckduckgo.com/bang

## `!!` automatic redirect

When including `!!` within your search query (separated by spaces), you will
automatically be redirected to the first result. This behavior is comparable to
the "I'm Feeling Lucky" feature from DuckDuckGo. To give an example:

- Search for a query and get redirected to the first result

  - {{search('!! Weather forecast')}}

Please keep in mind that the result you are being redirected to can't be
verified for trustworthiness and SearXJP cannot protect your personal privacy
when using this feature. Use it at your own risk.

## Special Queries

In the {{link('preferences', 'preferences')}} page you find keywords for _special queries_. To give a few examples:

- Generate a random UUID

  - {{search('random uuid')}}

- Find the average

  - {{search('avg 123 548 2.04 24.2')}}

- Show the _user agent_ of your browser (needs to be activated)

  - {{search('user-agent')}}

- Convert strings to different hash digests (needs to be activated)

  - {{search('md5 lorem ipsum')}}
  - {{search('sha512 lorem ipsum')}}
