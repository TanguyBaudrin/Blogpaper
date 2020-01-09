# Blogpaper

> A graphical newspaper like blog theme for Hugo.

[![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=NormandErwan_blogpaper&metric=alert_status)](https://sonarcloud.io/dashboard?id=NormandErwan_blogpaper)
[![GitHub Pages Status](https://github.com/NormandErwan/Blogpaper/workflows/GitHub%20Pages/badge.svg)](https://github.com/NormandErwan/Blogpaper/actions)

See the [live demo](https://normanderwan.github.io/Blogpaper/):
[![Example of a homepage](https://raw.githubusercontent.com/NormandErwan/Blogpaper/master/images/screenshot.png)](https://normanderwan.github.io/Blogpaper/)

See the [style guide](https://normanderwan.github.io/Blogpaper/posts/style-guide/):
[![Example of a post page](https://raw.githubusercontent.com/NormandErwan/Blogpaper/master/images/post-page.gif)](https://normanderwan.github.io/Blogpaper/posts/style-guide/)

## Install

1. Make sure you're using the [Hugo extended](https://gohugo.io/getting-started/installing/) version.
2. If you're using Hugo for the first time, follow the
[Hugo's quick start tutorial](https://gohugo.io/getting-started/quick-start/) first.
3. Copy the theme in your site:

    ```bash
    git submodule add https://github.com/NormandErwan/Blogpaper themes/Blogpaper
    ```

4. Edit your `config.yml`:

    ```yml
    theme: Blogpaper
    ```

5. Generate your site!

    ```bash
    hugo server -D
    ```

You should now a have a working site, but with a flat grey background instead of banner images on top your pages. See
the next section to configure your site and add banner images on your pages.

|                           After intall homepage                           |                           After intall post page                            |
|:-------------------------------------------------------------------------:|:---------------------------------------------------------------------------:|
| ![Example of a homepage after install](https://raw.githubusercontent.com/NormandErwan/Blogpaper/master/images/after-install-homepage.jpg) | ![Example of a post page after install](https://raw.githubusercontent.com/NormandErwan/Blogpaper/master/images/after-install-post-page.jpg) |

## Configure

1. Edit your `config.yml`:

    ```yml
    theme: Blogpaper
    title: # Your site title
    author:
      name: # Your name
    baseURL: # Hostname (and path) to the root, e.g. https://bep.is/
    copyright: # Optional, will be displayed on site's footer, if this line is removed an default copyright will be generated
    languageCode: en # The language code of your site, by default "en"
    menu:
      main: # Optional, the menu to display on top-right of your site, see https://gohugo.io/templates/menu-templates/#site-config-menus
        - name: About
          url: /about
    params:
      description: # The description of your site (used on a <meta> tag)
      subtitleLength: 25 # The number of words on the subtitle of a page
    ```

    See <https://gohugo.io/getting-started/configuration/> for more configuration settings (such as `datetimeFormat`,
    `mainSections` or `paginate`).
    See also how to configure [post summaries](https://gohugo.io/content-management/summaries/) on the homepage.

    Every page can have a subtitle, displayed bellow the title on the header of the page.
    It's generated by default from the first `subtitleLength` words of the page's content.
    It works the same as a [summary](https://gohugo.io/content-management/summaries/).

2. Add banner images on your pages, you can either:
    - Add a `banner.jpg` image next to a `index.md` or `_index.md` page.
    - Add a `<page-filename>.jpg` image next to a `<page-filename>.md` page.
    - Add no image to use the banner of the parent page.
    - Use a custom image by adding to the front matter of the page:

        ```yml
        banner:
          src: <banner-filename>.jpg # Optional, the filename of the banner, by default <page-filename>.md or banner.jpg
        ```

    - Set no banner by adding to the front matter of the page:

        ```yml
        banner: false
        ```

    For example, see the Blogpaper's [example site](https://github.com/NormandErwan/BlogpaperExampleSite):

      ```bash
      .
      └── content
          ├── posts
          |   ├── rich-content
          |   |   ├── banner.jpg
          |   |   └── index.md # Use banner.jpg
          |   ├── _index.md # No banner.jpg, use the parent banner: ../banner.jpg
          |   ├── emoji-support.md # Use emoji-support.jpg
          |   ├── emoji-support.jpg
          |   └── ...
          ├── _index.md # Use banner.jpg
          ├── about.md # Use about.jpg
          ├── about.jpg
          └── banner.jpg
      ```

    You can download free images on sites like [Lorem Picsum](https://picsum.photos/) or
    [other](https://alternativeto.net/software/unsplash/).

3. Add to the [front matter](https://gohugo.io/content-management/front-matter/) of your pages:

    ```yml
    subtitle: # Optional, will be displayed bellow the title of the page; remove this line to generate an automatic subtitle
    banner:
      src: <banner-filename>.jpg # Optional, the filename of the banner, by default <page-filename>.jpg or banner.jpg
      caption: # Optional, the caption of the banner
      href: # Optional, a link on the caption
    ```

## Troubleshooting / FAQ

- I can't generate the site.
  - Problem: I have the error: `Problem: Building sites … ERROR Transformation failed: TOCSS: failed to transform "blogpaper.scss" (text/x-scss)`.
  - Solution: [Reinstall Hugo](https://gohugo.io/getting-started/installing/), the *extended* version not the standard one.

- I want to customize the CSS.
  - Use your own CSS or SCSS files. Simply add the files in your `/assets/` folder.

    ```bash
    .
    └── assets
        └── css
            ├── custom1.css
            ├── custom2.scss
            └── ...
    ```

## Contribute

For any question or comment, please [open a new issue](https://github.com/NormandErwan/Blogpaper/issues/new).
I'm not a web designer so I'm open to any design suggestions! :-)

If you'd like to contribute, please [fork the repository](https://github.com/NormandErwan/Blogpaper/fork) and use a
feature branch. Pull requests are warmly welcome!

## Upgrade

From your site folder, execute:

```bash
git submodule update --remote themes/Blogpaper
```

## Build the example site

Clone this repository, then execute:

```bash
cd exampleSite
hugo server --themesDir ../..
```

Content is adapted from <https://github.com/gohugoio/hugoBasicExample>.
Images are credited on the page where they are used.

## License

The MIT License (MIT). Copyright (c) 2019-2020 Erwan Normand <normand.erwan@protonmail.com>.

See the [LICENSE.md](LICENSE.md) file for details.

Blogpaper uses the following third-party resources:

- [normalize.css](https://github.com/necolas/normalize.css): The MIT License (MIT).
[Copyright © Nicolas Gallagher and Jonathan Neal.](https://github.com/necolas/normalize.css/blob/master/LICENSE.md).

This theme is inspired by [Start Bootstrap - Clean Blog](https://github.com/BlackrockDigital/startbootstrap-clean-blog),
Jekyll's [Olania](https://olania-jekyll.netlify.com/) and Jekyll's [Curious](https://curious-jekyll.netlify.com/).
