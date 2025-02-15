---
layout: plain
sitemap: false
---

# CHANGELOG
{:.no_toc}

* this list will be replaced by the toc
{:toc .large-only}

## v9.2.1
Sep 14 2024
{:.heading.post-date}

* Fixed missing Dart Sass deprecation warning

## v9.2.0
Sep 08 2024
{:.heading.post-date}

* Added new social media icons
* Added dark mode to free version
* Changed default Twitter icon to "𝕏"
* Disabled Google Fonts by default
* Changed the default font weight for headings to 900 (you can undo this by setting `font_weight_heading: 700` in `_data/variables.yml`).
* Fixed a bug that caused a scrollbar to appear on the copy button on code blocks
* Fixed a bug that caused a glitch on the copy button during light/dark mode transition 
* Fixed a bug that caused newlines to get lost when using the copy button

## v9.1.9
Sep 05 2024
{:.heading.post-date}

* Fixed Dart Sass deprecation warnings in a way that is compatible with the legacy GitHub Pages pipeline

## v9.1.8
Sep 04 2024
{:.heading.post-date}

* Reverted "Fixed deprecation warnings" which broke compatibility with the legacy GitHub Pages pipeline

## v9.1.7
Sep 04 2024
{:.heading.post-date}

* Fixed deprecation warnings
* Updated Ruby dependencies
* Fixed browser chrome (e.g. scrollbar) not matching dark mode

## v9.1.6
Feb 07 2022
{:.heading.post-date}

* Removed unused clap button HTML tags
* Fixed an issue with using `featured` projects on the `welcome` layout
* Minor style adjustments
* Updated dependencies

## v9.1.5
Nov 30 2021
{:.heading.post-date}

* Now works with Ruby 3.0
* Fixed theme color issue when using multiple theme colors
* Fixed UTF-8 characters not rendering correctly in breadcrumbs
* Fixed empty string warning in resume layout
* Removed clap button info box

## v9.1.4
Mar 30 2021
{:.heading.post-date}

* Fixed scroll position restoration in webkit.
* Fixed an issue that caused clap button to use canonical url incorrectly.

## v9.1.3
Mar 28 2021
{:.heading.post-date}

### Added
* Allow setting custom Google Fonts providers via `google_fonts_url` ([#264](https://github.com/hydecorp/hydejack/issues/264)). Defaults to `https://fonts.googleapis.com`. 

### Fixes
* Merged [#266](https://github.com/hydecorp/hydejack/pull/266) --- Fixed a bug that caused incorrect links to be rendered.
* Merged [#267](https://github.com/hydecorp/hydejack/pull/267) --- Fixed a bug that caused incorrect sub-titles when using multiple categories/tags.
* Fix [#262](https://github.com/hydecorp/hydejack/issues/262) --- Fixed a bug that causes warnings when not providing a skill level / fluency level in the resume.
* [PRO] Fixed a bug preventing scrolling when using sticky ToC with certain aspect ratios.

### Design
* [PRO] Adjusted calculation to dark mode background color to prevent red tint of grey colors
* Hide underline in tooltips
* Show clap button on collection pages
* Show dingbat in `plain` layout

## v9.1.2
Feb 11 2021
{:.heading.post-date}

* Fix [#258](https://github.com/hydecorp/hydejack/issues/258)
* Fix [#259](https://github.com/hydecorp/hydejack/issues/259)

 
## v9.1.1
Feb 9 2021
{:.heading.post-date}

* Added tooltips to post subtitles and last-modified-at lines.
* Added tooltips to abberavations (`<abbr>` tags), e.g. IIAFE. See [Example Content](/blog/hyde/2012-02-07-example-content/#inline-html-elements){:.flip-title} on how to use them in markdown.
* Added tooltips to social media icons (inside main column only)
* Fixed KaTeX font rendering
* [PRO] Setting `clap_button: false` will hide the clap button preview, even in development
* [PRO] A overscrolling ToC will scroll itself to keep the active element in view.

*[IIAFE]: Instantly Invoked Asynchronous Function Expression
*[ToC]: Table of Contents

## v9.1.0
Feb 5 2021
{:.heading.post-date}

Version 9.1 provides minor design changes, new features, and closes multiple issues:

### Added

*   Code blocks now can have headers:

    ~~~js
    // file: 'hello-world.js'
    console.log('Hello World!');
    ~~~

    To add the headers, simply make the first line a comment of the form `file: "dir/filename.ext"`.

    * Code blocks now have a copy-to-clipboard button
  
*   Resumes can now have download buttons.

    ![Download Buttons](/assets/img/blog/9.1.0-3.png){:.border.lead width="1776" height="258" loading="lazy"}

    Add the following to the front matter. Note that the PDF needs to be pre-generated. 
    See [the docs](docs/basics.md#downloads) for more.

    ```yml
    # file: "resume.md"
    buttons:
      print: true
      pdf: /assets/Resume.pdf
      vcf: http://h2vx.com/vcf/<!--url-->
      json: /assets/resume.json
    ```

*   Added breadcrumbs above page title:

    ![Breadcrumbs](/assets/img/blog/9.1.0-2.png){:.border.lead width="1588" height="164" loading="lazy"}

    Note that this requires a [directory-like URL pattern](https://qwtel.com/posts/software/urls-are-directories/) like `/blog/:categories/:year-:month-:day-:title/` (default for Hydejack).

    Disable with `hydejack.no_breadcrumbs`.

*   Added "Last modified at" to post layout:

    ![Last modified at](/assets/img/blog/9.1.0-1.png){:.border.lead width="1254" height="218" loading="lazy"}

    To enable this feature, the post needs to have a `last_modified_at` property with a valid date. You can either set it manually in the frontmatter (not recommended), or use the [`jekyll-last-modified-at` plugin](https://github.com/gjtorikian/jekyll-last-modified-at) to set it for you (Not available on GitHub Pages!). 

    You can remove this element by setting `hide_last_modified` in the front matter. You can disable it for all posts by setting `hydejack.hide_last_modified` in the config file. Setting `hydejack.hide_dates` (PRO version only) will also remove it, together with all other time-related UI elements.

    You can customize the hover text, icon, and date format in `_data/strings.yml` using the following keys: `last_modified_at` (hover text), `last_modified_at_icon` (icon name, default: `icon-history`) and `date_formats.last_modified_at` (date format, default: `%Y-%m-%d`).

* Added option to "invert" / darken the font colors in the sidebar. This enables use of bright sidebar images. 
  Set `invert_sidebar: true` in the font matter to enable. Use `defaults` in the config file to enable this for all pages.

* Added a demo of [Clap Button](https://getclaps.app/) during development.
* Added option to configure border radius
* Added dingbat to `page` layout
* Added `plain` layout that comes without a dingbat
* Added `smaller` and `larger` CSS classes that set the font size to the respective values.
* Added options to change the file paths to favicon and apple touch icon in the confog file. Use `favicon` and `apple_touch_icon` respectively.

### Changed
* Added border radius to many elements
* Modernized table design
* [PRO] Setting `hydejack.advertise: false` will now remove the banner from the HTML and the JavaScript console.
* Changed the box shadow of cards (projects, posts) to reduce the amount of painting the browser has to do on when mouse hovering them.
* The layout when using the theme without the `no_break_layout` setting is now


### Fixes
* Allow transparent project and post images
* Removing/leaving out the `logo` key in the config file will now correctly remove the logo from the sidebar
* [PRO] Fixed a bug that caused blog posts to be included the the search even when set to `sitemap: false` in the front matter.

## v9.0.5
Sept 8 2020
{:.heading.post-date}

* Added GitHub Pages Starter Kit to PRO version
* Added chapter on how to deploy PRO on GitHub Pages
* JavaScript source files now included in PRO zip again
* Updated default config file
* Changed default code font
* Improved fallback image in dark mode

## v9.0.4
July 15 2020
{:.heading.post-date}

* Fixed image fade in animation for images with `srcset`
* Slightly increased size of post and project cards
* Added page margin to print layout
* Fixed KaTeX when JavaScript is disabled 
* Fixed a layout bug in the `resume` layout when changing the content width in variable
* Fixed table of contents sticky breakpoint

## v9.0.3
July 9 2020
{:.heading.post-date}

* Updated print resume style  
* Updated docs for GitHub Pages
* Slightly decreased size of dark mode icon
* Fixed a bug that caused a GitHub Pages build to fail with an empty configuration file
* Changed default icon so that it less resembles slashdot.org\~\~ 

## v9.0.2
July 7 2020
{:.heading.post-date}

* Fixed a bug that prevented the search from updating when offline is enabled
* Fixed a bug that caused search terms to get lost during initialization
* Fixed a bug that prevented `site.legal` from getting stored for offline during service worker installation
* Added support to for `no-cache` param to service worker.

## v9.0.1
July 6 2020
{:.heading.post-date}

* Changing app icons has been revamped. See [this section](./docs/config.md#adding-custom-favicons-and-app-icons) in the docs.
* Changed default icons
* Changed default sidebar background
* Added `jekyll-compose` defaults to config file
* Slightly adjusted dark mode colors
* Fixed resume layout breakpoint

## v9.0.5
Sept 8 2020
{:.heading.post-date}

* Added GitHub Pages Starter Kit to PRO version
* Added chapter on how to deploy PRO on GitHub Pages
* JavaScript source files now included in PRO zip again
* Updated default config file
* Changed default code font
* Improved fallback image in dark mode

## v9.0.4
July 15 2020
{:.heading.post-date}

* Fixed image fade in animation for images with `srcset`
* Slightly increased size of post and project cards
* Added page margin to print layout
* Fixed KaTeX when JavaScript is disabled 
* Fixed a layout bug in the `resume` layout when changing the content width in variable
* Fixed table of contents sticky breakpoint

## v9.0.3
July 9 2020
{:.heading.post-date}

* Updated print resume style  
* Updated docs for GitHub Pages
* Slightly decreased size of dark mode icon
* Fixed a bug that caused a GitHub Pages build to fail with an empty configuration file
* Changed default icon so that it less resembles slashdot.org\~\~ 

## v9.0.2
July 7 2020
{:.heading.post-date}

* Fixed a bug that prevented the search from updating when offline is enabled
* Fixed a bug that caused search terms to get lost during initialization
* Fixed a bug that prevented `site.legal` from getting stored for offline during service worker installation
* Added support to for `no-cache` param to service worker.

## v9.0.1
July 6 2020
{:.heading.post-date}

* Changing app icons has been revamped. See [this section](./docs/config.md#adding-custom-favicons-and-app-icons) in the docs.
* Changed default icons
* Changed default sidebar background
* Added `jekyll-compose` defaults to config file
* Slightly adjusted dark mode colors
* Fixed resume layout breakpoint

## v9.0.0
July 3 2020
{:.heading.post-date}

### Major
*   Added Built-In Search Functionality

    Hydejack now has its own built-in search solution, that integrates well with the existing page style and the new navbar. 
   
    The solution is entirely browser-based which means it even works while offline and doesn't depend on an 3rd party. 
    This works, because Hydejack is designed for personal sites that generally have less than 1000 pages. 
    In my testing, Jekyll build times have been a problem long before search query times.
   
    The results of the search are surprisingly good