# vB5Support.com Website Read Me

This site is built using [Hugo](https://gohugo.io/) with the [Geekdocs](https://geekdocs.de/) theme.

> Hugo is one of the most popular open-source static site generators. With its amazing speed and flexibility, Hugo makes building websites fun again.

The Geekdocs theme provides a layout that is common with online documentation without using frames. The theme automatically supports Light and Dark themes and is customizable.

Follow the instructions on the [Hugo](https://gohugo.io/getting-started/installing/) and [Geekdocs](https://geekdocs.de/usage/getting-started/) sites to install these packages. The files included here are only the files needed to specifically build the vB5Support.com Documentation.

---
## Menus

These menus are provided by the theme used. They have been customized to fit this project.

### Main Menu

This menu is generated dynamically using the [file-tree](https://geekdocs.de/usage/menus/#file-tree-menu) menu system build into the theme. It is based on the layout of the sub-directories within the `content`. Individual articles will define their URL slug and weight within the Front Matter of the article. The main menu is configured so that each section can be collapsed to reduce scrolling.

### More Menu

This menu is provided to provide more resources to readers. It links to several vBulletin resources that can help people build custom sites. The configuration for this menu is located at `data\menu\more.yaml`. More information can be found within the Geekdocs [documentation](https://geekdocs.de/usage/menus/#more-menu).

### Extra Menu

This menu provides additional resources within the header of each page. You can see it in the upper right corner along with the theme switcher. The configuration for this menu is located at `data\menu\extra.yaml`. More information can be found within the Geekdocs [documentation](https://geekdocs.de/usage/menus/#extra-header-menu).

---
## Customizations

### Icon Sprites

Located at `assets/sprites`.

The Geekdoc template provides a limited source of icons that can be used in documentation with the icon shortcode. Additional icons are provided via the [FontAwesome](https://fontawesome.com/) Duotone and Brand SVG Sprites. These additional sprites only contain the icons used in order to keep file sizes low. The raw sprites are located at: `assets/sprites`

When building individual pages, Hugo will automatically embed the sprites within the header of the HTML output.

### Custom Layouts 

Layouts are [Go Template](https://blog.gopheracademy.com/advent-2017/using-go-templates/) files containing a that can be used to draw each page. These files are a combination of HTML, Hugo Variables, and Template structures. The majority of these layouts are added via the chosen theme. This project includes some custom layouts to add functionality to the current Geekdocs theme. 

#### Partials

Located at: `layouts/partials/`

- `_default/sections.html`: A new partial has been added to show links to sub-pages and a summary (if available) when visiting Branch index pages (i.e. _index.md). Within this project Branch Index pages are designed to lead into specific chapters and sub-chapters in the documentation.

#### Shortcodes

Located at: `layouts/shortcodes`

Using layouts in Hugo, custom shortcodes can be created. In addition to the shortcodes provided by the [Geekdocs theme](https://geekdocs.de/shortcodes/) and [Hugo](https://gohugo.io/content-management/shortcodes/), the following short codes have been added to this site.

- Alert: Copied from the [DOCSY Hugo Theme](https://www.docsy.dev/docs/adding-content/shortcodes/#alert). Used as a placeholder until all content is converted to the Geekdocs Hint shortcode.
- Color (ex. `{{< color "secondary" >}}...{{< /color >}}) : Creates a span of text with the class set to the specific CSS color class defined. 
- Video (ex. `{{< video src="videos/navigation.webm" type="video/webm" preload="auto" >}}`): Allows embedding local videos from inside the `static` directory. Can support webm or mp4. To use mp4 specify the type of `video/mp4`.

#### CSS

Located at: `layouts`

Provides some basic CSS to either override definitions and attributes defined by the Geekdocs theme or to provide custom definitions for items specific to this documentation.

---
## Content

Content is organized via Hugo's [Branch Bundle](https://gohugo.io/content-management/page-bundles/#branch-bundles) system. This is comprised of a hierarchy of directories for organization. Each directory pertains to a specific section of the vBulletin system contains one or more articles covering that section. Each article is written in markdown and weighted to control its location within the main menu of the site.

---
## Static

Some content is static or derived outside the Hugo system. This resides in the static directory. This content is currently images (`static/imgs`), video (`static/video`), legacy version manuals (`static/legacy`) and API documentation (`static/api`). API documentation is derived via the vBulletin source code and compiled using [phpDocumentor](https://www.phpdoc.org/).

---
Related: [Doc Generators](https://github.com/wayneluke/doc_generators)