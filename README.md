# Cactus White

A responsive, white and simple [Hexo](http://hexo.io) theme for a personal website. Based on the original [Cactus Dark](https://github.com/probberechts/cactus-dark) theme by [Pieter Robberechts](https://github.com/probberechts) and the [Cactus-White](https://github.com/sergodeeva/cactus-white) theme by [Sergodeeva](https://github.com/sergodeeva).

:cactus: [Demo](https://chenkxin.github.io/cactus-white/)

## Summary

- [General](#general)
- [Features](#features)
- [Install](#install)
- [Configuration](#configuration)
- [License](#license)

## General

- **Version** : 2.0
- **Compatibility** : Hexo 3 or later

## Features

- Fully responsive
- Disqus
- Google analytics
- Font Awesome icons
- Pick your own code highlighting scheme
- Configurable navigation menu
- Support for local search
- Projects list
- Simplicity

## Install
1. In the `root` directory:

    ```git
    $ git clone https://github.com/chenkxin/cactus-white.git themes/cactus-white
    $ npm install hexo-pagination --save
    ```

2. Change the `theme` property in the `config.yml` file.

    ```yml
    # theme: landscape
    theme: cactus-white
    ```
3. Run: `hexo generate` and `hexo server`

## Configuration

### Navigation

Setup the navigation menu in the theme's `_config.yml`:

  ```
  nav:
    Home: /
    About: /about/
    Writing: /posts/
    Projects: http://github.com/chenkxin
  ```

### Blog posts list on home page

You have two options for the list of blog posts on the home page:

  - Show only the 5 most recent posts (default)

  ```
  customize:
    show_all_posts: false
    post_count: 5
  ```

  - Show all posts 

  ```
  customize:
    show_all_posts: true
  ```

### Projects list

Create a projects file `source/_data/projects.json`.

  ```json
  [
      {
         "name":"Hexo",
         "url":"https://hexo.io/",
         "desc":"A fast, simple & powerful blog framework"
      },
      {
         "name":"Font Awesome",
         "url":"http://fontawesome.io/",
         "desc":"The iconic font and CSS toolkit"
      }
  ]
  ```

### Social media links

Cactus White can automatically add links to your social media accounts. Therefore, update the theme's `_config.yml`:

  ```
  customize:
    social_links:
      github: your-github-url
      twitter: your-twitter-url
      NAME: your-NAME-url
  ```

where `NAME` is the name of a [Font Awesome icon](http://fontawesome.io/icons/#brand).

### RSS

Set the `rss` field in the theme's `_config.yml` to one of the following values:

1. `rss: false` will totally disable rss (default).
2. `rss: atom.xml` sets a specific feed link.
3. `rss:`leave empty to use the [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) plugin. 

### Analytics

Add you Google Analytics `tracking_id` to the theme's `_config.yml`.

  ```
  plugins:
      google_analytics: 'UA-49627206-1'            # Format: UA-xxxxxx-xx
  ```

### Comments

First, create a site on Disqus: [https://disqus.com/admin/create/](http://disqus.com/admin/create/).

Next, update the theme's `_config.yml` file:

  ```
  plugins:
      disqus_shortname: SITENAME
  ```

where `SITENAME` is the name you gave your site on Disqus.

### Code Highlighting

Pick one of [the available colorschemes](https://github.com/sergodeeva/cactus-white/tree/master/source/css/_highlight) and add it to the theme's `_config.yml`:

  ```
  customize:
      highlight: COLORSCHEME_NAME
  ```

### Tags and categories

Tags and categories can be included in the front-matter of your posts. For example:

```markdown
title: Tags and Categories
date: 2017-12-24 23:29:53
tags:
- Foo
- Bar
categories: 
- Baz
---

This post contains 2 tags and 1 category.
```

You can create a page with a tag cloud by running:

```sh
$ hexo new page tags
```

Next, add `layout: tags` to the front-matter of `source/tags/index.md`.

Similarly, you can create a page with an overview of all categories by running:

```sh
$ hexo new page categories
```

and adding `layout: categories` to the front-matter of `source/categories/index.md`. 

Finally, don't forget to create a link to these pages, for example in the navigation menu:

```yml
nav:
  tag: /tags/
  category: /categories/
```

You can show a category and tag section on the home page by editing the hexo `_config.yml` file.

```yml
# Show a Tags section on the home page
show_tags_section: true

# Show a Category section on the home page
show_category_section: true
```

### Local search

First, install the [hexo-generate-search](https://www.npmjs.com/package/hexo-generator-search) plugin, which will generate a search index file.

  ```git
  $ npm install hexo-generator-search --save
  ```

Next, create a page to display the search engine:

  ```sh 
  $ hexo new page Search
  ```
and put `search: true` in the front-matter.

Finally, edit the theme's `_config.yml` and add a link to the navigation menu.

  ```
  nav:
    ...
    Search: /Search/
    ...
  ```

## License
MIT
