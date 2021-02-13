# Research site

>By Siobhon Egan

A place to house general info related to my research.
Mainly a place for me to store lots of links and short bits of information that don't warrant their own project specific site.
Topics covered include project organisation, referencing, coding, data analysis, RStudio and RMarkdown, statistics, sequencing, phylogenetics...plus more.

http://siobhonlegan.com/research_site

----------------

> Site built using [`rundocs/starter-slim`]
[GitHub repo](https://github.com/rundocs/starter-slim/)


1. [Generate with the same files and folders](https://github.com/rundocs/starter-slim/generate) from this repository
2. Set up your GitHub Pages to source(`/`)
3. Now you can view your documentation in your site

## site.pages

<!-- prettier-ignore-start -->

| source          | link                                                           |
| --------------- | -------------------------------------------------------------- |
{% for page in site.pages -%}
| {{ page.path }} | [{{ page.url | relative_url }}]({{ page.url | relative_url }}) |
{% endfor %}

<!-- prettier-ignore-end -->

## Documents

https://jekyll-rtd-theme.rundocs.io

## Local debug

```sh
gem install jekyll bundler

bundle install

JEKYLL_GITHUB_TOKEN=blank PAGES_API_URL=http://0.0.0.0 bundle exec jekyll server --livereload
```

## The license

The theme is available as open source under the terms of the MIT License
