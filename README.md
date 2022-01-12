![Screenshot of a website using Huey](https://github.com/alloydwhitlock/huey/blob/main/images/tn.png)

# Huey
A minimal Hugo blog template using Bulma CSS

## Questions

### Why is it Named Huey?
The name "Huey" was taken from the musician "Baby Huey". The record was on the mantle when the theme author was trying to come up with a name. The album cover for "The Baby Huey Story: The Living Legend" is used as the default `favicon.ico` for this theme.

### Why Use Bulma for CSS?
Bulma is a great framework for starting off sites. It's pure CSS, meaning you don't need to bring in Javascript (unless you want to). This was also meant as an exercise for the author to learn Bulma CSS and how Sass works.

### Why Doesn't Huey use "X" Bulma feature?
This is meant to be "minimal". Only add features needed for a slim site and when necessary. If you want a full-featured Bulma theme meant to provide everything Bulma offers, check out [hugo-bulma](https://github.com/wayn3h0/hugo-bulma).

### How Can I Contribute?
File a pull request in the Huey theme repository. Preferably create a Github Issue which addresses a problem that needs to be solved, then submit a PR fixing it.


## How Can I Get New Features?
If you need or want new functionality, please create a new issue on Github in the Huey project.


## Installation

### Prerequisites

- A Hugo site has been initialized or cloned. Example: `hugo new site <site name>`
- Git installed in development environment
- Github access available

### Method 1: Clone in Themes Directory

The simplest method of installing Huey is cloning the Huey directly into the site `themes/huey` directory. Below is a command that can be copied & pasted into a terminal to clone the Huey theme.


```git clone https://github.com/alloydwhitlock/huey/ --depth=1```

If you use Huey cloned directly, you will need to run `git pull` within `themes/huey` for updating to the most recent version.


### Method 2: Use Git Submodule

Git Submodule allows you to have one git repository located within another. This lets you separate what your working site directory will be from the Huey theme, as an example. It's a great choice when you have an external component you don't fully control, since it locks the repository reference to the specific commit you used.

```git submodule add https://github.com/alloydwhitlock/huey/ themes/huey --depth=1```

If you use Huey as a submodule, you will need to run `git submodule update --remote --merge` when updating the most more recent version.



## Theme Configuration
Huey comes with a number of configuration options. Read through this section for more details, along with a boilerplate configuration that can be used to get started.

### Font Awesome
Font Awesome icons are included as part of the Bulma CSS framework, though their use is optional. Using the icons in Huey is also optional. If you want to have icons next to page titles or social media icons in your page footer it's necessary to enable Font Awesome. To use Font Awesome, you will first need to [register with Font Awesome](https://fontawesome.com/start) and get a token. Once you have a token, add it to the `[Params]` table as `fontawesomeToken`. Example configuration is provided below (with additional keys/values removed):

```
[params]
    fontawesomeToken = "018de52a07"
```

### Subtitle
This theme doesn't use a subtitle. To add a subtitle, edit `layouts/partials/header.html` to include a {{ .Params.Subtitle }} along with adding `subtitle` to your `config.toml` `[params]` table.

### Social Media Icons and Links

If you want to use social media icons in your page footer, you can add them through the `[[menu.social]]` table array. The example below shows a full configuration, where three social media locations are set. Any link and icon can be used, though if you don't use Font Awesome it will show the name specified instead of an icon.

```
[[ menu.social]]
  identifier = 'linkedin'
  name = 'LinkedIn'
  pre = "<i class='fab fa-linkedin fa-lg'></i>"
  url = "https://linkedin.com/in/yourlinkedinprofile"
  weight = 10

[[ menu.social]]
  identifier = 'github'
  name = 'Github'
  pre = "<i class='fab fa-github fa-lg'></i>"
  url = "https://github.com/yourgithubname"
  weight = 20

[[ menu.social]]
  identifier = 'twitter'
  name = 'Twitter'
  pre = "<i class='fab fa-twitter fa-lg'></i>"
  url = "https://twitter.com/yourtwittername"
  weight = 30
```

The `pre` key defines the Font Awesome icon code you would use. If you do a search on Font Awesome, you should be able to paste the icon code as the value. You can also use this to specify a location for an icon, if you don't want to use Font Awesome.

The `weight` key is used to determine the location of icons. Adjusting the weight from low-to-high will order left-to-right.


### Configuration Example

This is a configuration boilerplate you can use with minimal changes.

```
baseURL = "https://www.yourbaseurl.com"
languageCode = "en-us"
title = "Put a site title here"
theme = "huey"
canonifyurls = true

[params]
  # General site metadata, used in header and other places
  author = "Author's name goes here"
  dateFormat = "January 2, 2006"
  description = "This is a description of your site. This is also used in your site header metadata."
  keywords = ""
  email = "adam@adamwhitlock.com"

  # Use your Font Awesome token here. Example token is fake, so please get your own.
  fontawesomeToken = "018de52a07"

  # Use content from _index.md on homepage
  # useIndexContent = true # default is false

  # Navigation, use Bulma options here
  # navbarStyle = "is-transparent" # Default is "is-transparent"
  # navbarTitleStyle = "has-text-black" # Default is "has-text-black"

  # # Override Bulma schemes with values
  # schemeMain = "" # Change background color, default is white
  # link = "#000" # Bulma default is blue, though theme is black
  # linkHover = "#888" # Bulma default is grey-darker, though theme is #888
  # footerBackgroundColor = "false" # Bulma default is #fafafa. You can use "false" or #hex
  # navbarItemHoverColor = "#444" # Bulma default is blue, though theme is #444
  # navbarItemColor = "#888" # Bulma default is grey-dark, though theme is #888

  # Set static directory locations and favicon
  favicon = "favicon.ico"
  staticDir = ['static']


[menu]

# Top Navigation
[[menu.nav]]
  identifier = 'home'
  name = 'Home'
  title = 'Home'
  url = '/'
  weight = 10

[[menu.nav]]
  identifier = 'archive'
  name = 'Archive'
  title = "Archive"
  url = '/archive/'
  weight = 20

# Contacts

[[ menu.social]]
  identifier = 'linkedin'
  name = 'LinkedIn'
  pre = "<i class='fab fa-linkedin fa-lg'></i>"
  url = "https://linkedin.com/in/yourlinkedinprofile"
  weight = 10

[[ menu.social]]
  identifier = 'github'
  name = 'Github'
  pre = "<i class='fab fa-github fa-lg'></i>"
  url = "https://github.com/yourgithubname"
  weight = 20

[[ menu.social]]
  identifier = 'twitter'
  name = 'Twitter'
  pre = "<i class='fab fa-twitter fa-lg'></i>"
  url = "https://twitter.com/yourtwittername"
  weight = 30

[outputs]
  home = ['HTML', 'RSS']
  pages = ['HTML']

```

## Page Configuration


### Layout for Individual Pages

Huey pages require that you specify a `type: pages` and `layout: page` for any page that's standalone (Examples: Contact, About Me). This will remove the "date" field from those pages, along with letting you specify an optional Font Awesome icon next to the page title. Unlike how Font Awesome icons are used in the configuration, you only need to put the short Font Awesome codes on your page front matter (the metadata at the top of a post).S

Specifying the `menu:nav` and `weight: weight-value`, as seen in the example, will ensure additional pages you create appear in navigation. If declared properly, the active page should be darker in the menu.

Example Layout for Individual Page

```
---
title: "About"
date: 2021-12-22T22:31:55-06:00
draft: false
url: /about/
type: pages
layout: page
fa_icon: "fas fa-user"
menu: nav
weight: 20

---

Content text goes here...

```

To add an icon next to a page title, use `fa_icon:` key where the value is the Font Awesome icon code. Example: `fa_icon: fas fa-user`


### Layout for Blog Posts

#### Post Front Matter

Blog posts only need the type `blog` specified in a page front matter, which allows new posts to appear on the main home page. If you don't want a post to appear on the home page, it's possible to hide them by ignoring the type or setting it to another (Example: post).

Use the `lastmod` key in your page front matter to specify the last modified date. This is useful if you make changes to a post and want to highlight something new is present.

`archive` is used throughout Huey as the blog post location, but you can specify your own. Rename `layouts/pages/archive.html` file accordingly.


Example Layout for Blog Posts:

```
---
title: "Example Post"
date: 2021-12-30
# lastmod: 2021-12-29
draft: false
url: /archive/examplepost
type: blog
description: "Every post should have a great description!"
---

Content text goes here...
```


There is not an option for Font Awesome codes with blog posts. If you need/want this functionality please create a new issue on Github in the Huey project.

#### Header Images & Content

When using Huey as a theme, it's suggested to use page bundles. These allow for a content author to include all relevant content within a folder. Pages can reference bundle content directly. Below is an example of a page bundle layout:


```
hugo-site
├── content/
│ ├── posts/
│ │ ├── new_post/
│ │ │ ├── header.png
│ │ │ ├── image1.png
│ │ │ └── index.md
│ │ ├── _index.md
...

```

Post bundles require an `index.md` for the bundle folder, which will contain the content of the post. See [Page Bundles](https://gohugo.io/content-management/page-bundles/) on Hugo for more information.


##### Header Image (Front Page & Posts Page)

Huey will use any picture named "header.jpg" or "header.png" that's included within a page bundle. This picture is used on the front home page and the posts (blog posts) page. If you do not include an image meeting the naming convention, then no image will be used for the header.


##### Images & Other Content

You can reference any content in the page bundle, such as additional images, in your markdown files using a relative path. Example:

```
![Image alt text](image1.png)
```

##### Shortcodes

###### Centered Text

Example:

{{% center %}}Text to be centered{{% /center %}}


###### Centered Image

{{% center-image
src="x400_board.png"
alt="This is sample image" %}}


## Additional Scripts

Huey supports loading scripts after the footer loads (Example: Javascript for site analytics). Adding new code directly to Huey's existing `huey/layouts/partials/scripts.html` is the fastest method to get started. However, to maintain core site code separate from your theme create a `layouts/partials/scripts.html` file in the base site directory. When generating a new site, Hugo will load the base folder `scripts.html` accoording to the order of precedence.

Example Layout Showing New scripts.html:

```
hugo-site
├── layouts/
├── partials/
│└── scripts.html
... more files ...
├── themes/
│└── huey/
...

```


## Site Local Assets and Online Dependencies

Bulma CSS is stored as part of the project theme, in `assets/css/bulma`. This ensures you can move your site around without needing network access. If a newer version of Bulma is necessary, either replace the Bulma CSS directory completely or use a public Bulma CSS location. The location is specified in `layouts/partials/head.html`.

Font Awesome is not stored within the theme, so network access to the Font Awesome CDN is required. If you need local icons, store them in the `static` folder (Example: `static/icons`) and reference their location directly. This may require theme modification depending on where you are adding or needing icons.


## Theme Customization

If you want to change the colors that Huey uses, the best location is `assets/css/base/base.scss`. Huey uses Bulma, which itself uses Sass for generating CSS. This file will apply changes to Bulma CSS and generate what is ultimately created in your `public` folder. However, there are a number of Bulma variables already configurable in the `[Params]` table, which means you don't need to edit this file directly. Only edit it directly if you need to make changes.

If you want to add new CSS definitions that don't exist in Bulma, add them to `assets/css/extra/extra.css` or copy CSS files to the `assets/css/extra` folder. Huey will read any CSS files in that folder.


## TODO
This is the author's current TODO list for Huey. It won't impact your use of Huey. If you run into an issue and it's in the list, be assured it's being looked into.

- Children pages will show active for parent in menu
