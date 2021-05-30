# Third Hemisphere Hugo Theme

This [Hugo](https://gohugo.io/) theme create websites optimised for search engines.

## Features

- Simple one-column design
- Uses [Bulma CSS](https://bulma.io/), based on the work by [Päktech](https://www.pakstech.com/blog/create-hugo-theme/)
- Optimised for technical SEO, mimicking the functionality of the [Yoast SEO Wordpress plugin](https://yoast.com/)
- Optimised for use with [Org-Mode](https://lucidmanager.org/productivity/create-websites-with-org-mode-and-hugo/)

The following pages use this theme:

- [The Lucid Manager](https://lucidmanager.org/)
- [The Horizon of Reason](https://horizonofreason.com/)

## Getting started
At the root of your Hugo project, run:

```bash
git submodule add https://github.com/pprevos/hugo-thirdhemisphere themes
```

## Hero images
The `index.html` and `404.html` pages use hero images. 

The hero image for the index page is set in the `heroindex` site parameter.

The hero image for the 404 page is set in the `hero404` site parameter.

## Taxonomies
The theme uses the category and tag taxonomies. Ideally, each category and tag should have an index file that specifies a title, a featured image and a description.

All taxonomy pages are set as private and will not appear in the sitemap or any RSS files.

The index page shows a summary of all category pages. You can add an icon to this summary by setting the `icon` variable in the index file.

## Shortcodes
### Contact form
To enable the contact form, create a `contact.md` or `contact.org` page in the `content` folder with the appropriate title and set the layout to `page`, a plain page with only a header and footer. You can use this template for other pages that don’t require a featured image and author information.

The contact from shortcode enables a form by assigning an endpoint that processes the data. The example below uses [Formspree](https://formspree.io/), but this can be any other endpoint.

`{{< contact-form "https://formspree.io/abcdefgh" >}}`

### Pinterest
The Pinterest shortcode displays a board. The first parameter contains the URL, the second and third parameter the width and height of the frame and the last parameter contains the image size. For example:

`{{< pinterest "https://www.pinterest.com.au/HorizonOfReason/pacific-island-hopping/" 600 600 300>}}`

### Image Slider
This shortcode provides a simple image slider. Place all images for the slider in one folder and call the shortcode as follows: 

`{{< slider "image folder location" >}}`

The activate the Javascript for the slider, also set the `slider` variable to `true` in your config file.

## Search-Engine Optimisation
Google'sGoogle's mission is to "to organise the world's information and make it universally accessible and useful". This means that each page needs to have:
- Quality content
- Good UX & UI
- Flawless security
- Effective PR and social
- Technical excellence

This purpose of this theme is to help achieve these goals.

### robots.txt
Any files that have the `private` option set to `true` are disallowed. You need to set the `enableRobotsTXT` site parameter to `true` to enable this functionality.

### Sitemap
Any files that have the `private` option set to `true` are excluded from the sitemap.

### Robots meta tags
The robots meta tag for all files is set to `index, follow`. For any files that have the `private` option set to `true`, the tag is set to `noindex, nofollow`.

### Canonical links
Each page contains a self-referencing [canonical link](https://yoast.com/rel-canonical/). Index pages contain an alternate link to the relevant RSS file.
  
### Structured Data
The theme uses the built-in Open Graph and Twitter card templates. Content pages also have the [article schema](https://developers.google.com/search/docs/data-types/article) in JSON-LD format. This schema uses the:

- Title or SEO title of the page
- Page description
- Featured images
- Published date
- Last modified date
- Site author or page author
- Publishing organisation
- Site logo
  
### Internationalisation
Each page contains an alternate self-referencing link wit the site language code.
  
### Content optimisation
This theme contains a partial template that assesses the content of a page. This module implements some of the features of the popular WordPress Yoast plugin.

The SEO assessment only appears when running the site on localhost, and when the `seo` parameter is set to `true`.

![Example of SEO assessment.](file:exampleSite/static/images/seo-example.png)

#### Keyphrase
The key phrase should be [[https://yoa.st/34i][between 1 and 4 words]]. You will need to do some research to find the ideal phrase. You should only use [each keyphrase once](https://yoa.st/33x) on your site.

#### Slug
The [page slug](https://yoa.st/33o) of the page should ideally contain the keyphrase.

#### Meta description
The [meta description](https://yoa.st/34d) is a summary of the page, between 120 and 156 characters long. The keyphrase should [appear in the meta description](https://yoa.st/33k).

#### Title
Each page can have two titles, the one displayed on the page in the `h1` header and an optional separate version for the title tag. To set a separate title for a page, use the `seotitle` option. The ideal [title width](https://yoa.st/34h) is between 50 and 60 characters, and it should contain the [keyphrase](https://yoa.st/33g).

#### Featured image
You can define a featured image with the `images` parameter. This image should be at least 800 pixels wide with an aspect ratio of 3:2. The image is used in the structured data page summary on index pages. The template assigns the meta description to the [alt and title tags](https://yoa.st/33c).

#### Content
The [content length](https://yoa.st/34n) need to be at least 300 words and contain the [[https://yoa.st/33e][keyphrase]] appears in first paragraph. Ideally, the key phrase should be mentioned a few times throughout the text. At least one [[https://yoa.st/33m][heading]] needs to contain the keyphrase.

## Branding
The logo image is a square png file that is used in the navigation bar and as the favicon. The location of the logo file is identified in the params section of the config file, e.g. `logo = "/favicon.png"`.

## RSS - Really Simple Syndication
The RSS template has been enhanced to remove the author e-mail. The RSS feed shows the full content of each regular page instead of only the summary. Each index category and tag) has its own feed. Pages with the `private` parameter set to `true` are excluded from the feed.

## Mathematical formulas
If you like to typeset mathematical equations on your website, the set the `math` parameter to `true`. This setting loads [MathJax](https://www.mathjax.org/) so you can display beautiful mathematics.

## Sharing Buttons
Each page shows simple sharing buttons for either Facebook, Twitter, Reddit or LinkedIn. 

To enable these buttons, set the relevant site parameters to `true`. For Twitter, you need to set the username without the @-symbol, e.g. `"pprevos"`

## Social Media links
The social media menu in the `config.toml` provides icons and links to your profiles in the footer. You can find the relevant icons on the [Font Awesome](https://fontawesome.com/icons?d=gallery) website, e.g. "`fab fa-github`".

## Copyright statement
A copyright statement appears in the central footer column with the appropriate icon. The `copyright` variable holds the copyright statement text, which can include HTML.
