# learn-hugo
a repository for learning hugo

# How to make a change that you made display on the site

## Make and check the changes that you are going to make

1. Run the pages locally to make sure that they look okay 

  * Type `hugo server -D` from the folder where your website files are stored. on the command line to run the website on your computer
  * Navigate to `http://localhost:1313/learn-hugo/` in your browser to see the site locally. **What you see here is NOT what is currently on the website**
  * You can make changes in the files and (for most changes) when you save them in your files, the changes will be reflected on your local branch

2. When you are satisfied with your additions and changes, make sure that all of your changes have been committed to the master branch. (It's a great idea to do this from a separate branch, and make a pull commit to contribute these changes to the site.)

## Deploy the site

_NOTE: this piece should only be done by someone that is experienced with deploying changes to the production website. These commands will push the changes to the site._

3. From within the repository folder for the site, run the deploy script: On the command line, type `./publish_to_ghpages.sh` (you will need to have contributor rights to the github repository.)
4. If there are changes that haven't been committed, you will get messages to clear these changes before moving forward
5. The script will rebuild the site and push the changes to the gh-pages branch.
6. When the process is completed, confirm that the changes are present in the `gh-pages` branch on github. The site at `https://lpaglione.github.io/learn-hugo/` will be refreshed in a few min.

# Updating metadata

## Site subfooter

The information displayed in the site sub-footer is contained in the `data > contact.yaml` file. If any item is left blank (empty inside of the quotes), it will not display in the footer.

To add things to this subfooter, the `Layouts > Partials > sub-footer.html` file must be edited to include these items.

_NOTE: the Business Name is displayed in the copyright in the main footer and in the address if one exists._

# Updating the site

## General components

### Logos

These are stored in the `static/images` folder

* The site logo must be called `logo.svg`
* There must be a mobile version of the logo which must be called `logo-mobile.svg`
* If either logo needs to be changed, its file can just be replaced in this folder.

### Site favicon

* This image is stored in the static folder and must be called `favicon.png`

## Home page

### Hero

The home page hero is specified in the `content/_index.md` file which contains the following parameters:

* **date**: The date & time that this section was last updated. This date is not displayed anywhere, but updating it can be handy for others who may be editing this part of the page
* **heroHeading**: This is the header text displayed in the hero
* **heroSubHeading**: This is the sub header text displayed in the hero
* **heroBackground**: This is the background image displayed. This image is automatically colored by the general site color settings (see above). The image must be added to the folder `static/images` and the file name in this markdown file should reflect the name of the file that you want displayed (note: the file name is in quotes, and is in the format `'images/<file-name>'`)

### The rest of the home page

The rest of the home page is configured in the `content/homepage` folder. Each markdown file describes a section of the home page. The `index.md` file will not need to be edited.

For each section of the site, you will create a new markdown page (with the exception of one section which is described below.) Each markdown file has a header and a body.

In the header:

* **title**: The header text in the section
* **weight**: A number representing the order that this section should appear on the home page
* **background** _(optional)_: The background image that should be displayed, if any. As will the hero background, the file should be stored in the `static/images` folder, and the file name is listed here.  (note: the file name is in quotes, and is in the format `'images/<file-name>'`). If there should be no background image, use the value `''`.
* **button** _(optional)_: The text that should be displayed on a button.
* **buttonLink** _(included if there is a button value)_: Where the reader should be directed when they click the button.

In the body of the markdown file, you should include the text that you want to display under the header.

## The Service

_This content is stored in the `content > services` folder_

The content included in the services folder are used in multiple places:

* As single pages
* As summaries, such as on the home page
* As a list of services, for example, on the services landing page

From a content perspective, each page should have the following header elements:

Name | Description | Example
---- | ----------- | -------
title | the title for the page. Displayed on the browser title bar | title: 'SeamlessAccess for Researchers'
date | the publication date for the page. This field is optional, but useful to get search engines to re-index the page if it changes | date: 2018-11-18T12:33:46+10:00
icon | an image to be displayed for the service in summary and list views. The image should be included in the `static > services` folder | icon: 'services/service-icon-1.png'
draft | indication if this page is a draft or not. It is possible that this feature is not implemented on this site - not tested | draft: false
featured | Indication if this page should display in the summary view. Only the featured items are included in the summary view with a link to see all services | featured: true
weight | the order that this item should be displayed in the list and summary views. Note, this is a dumb indicator. You are going to want to be careful about assigning different numbers to each page to avoid conflicts | weight: 1
heroHeading | on the page there is text that can be displayed over the hero image. This optional text will be displayed as a header | heroHeading: 'SeamlessAccess for Researchers'
heroSubHeadingLead | Additional text that can be displayed over the hero image. This optional text will be displayed as lead-in text to the sub header and will be styled differently | heroSubHeadingLead: 'Catchy Lead-in! '
heroSubHeading | Additional text that can be displayed over the hero image. This optional text will be displayed as a sub header | heroSubHeading: 'Include a useful subheader here'
heroBackground | the image that is displayed as a hero image. Note that this image is automatically overlayed with an overlay background to make all images look more similar to each other | heroBackground: 'services/service1.jpg'

## In Action section

_This content is stored in the `content > work` folder. There is no menu pick for this content - it is displayed on the home page and at the bottom of the services page._

### Use Cases

Use cases are displayed from the "In Action" section on the home page. There is no top-level link to this content. The In Action section provides links to demos, videos, etc; lists of implementations; and use cases that one can use to get a sense of how SeamlessAccess works, and who is using it.

The content for this section is stored in the `content > work` folder. The `_index.md` page provides the front matter for the In Action section, and each additional page listed serves as a use case. For each use case, you will need the following header elements:

Name | Description | Example
---- | ----------- | -------
title | the title for the page. Displayed on the browser title bar | title: 'SpringerNature'
date | the publication date for the page. This field is optional, but useful to get search engines to re-index the page if it changes | date: 2018-11-18T12:33:46+10:00
draft | indication if this page is a draft or not. It is possible that this feature is not implemented on this site - not tested | draft: false
weight | the order that this item should be displayed in the list and summary views. Note, this is a dumb indicator. You are going to want to be careful about assigning different numbers to each page to avoid conflicts | weight: 1
heroHeading | on the page there is text that can be displayed over the hero image. This optional text will be displayed as a header | heroHeading: ''
heroSubHeading | Additional text that can be displayed over the hero image. This optional text will be displayed as a sub header | heroSubHeading: ''
heroBackground | the image that is displayed as a hero image. Note that this image is automatically overlayed with an overlay background to make all images look more similar to each other. While this image can be referenced by URL, it is a little safer to store the image in the `static > work` folder and reference it here `'work/fileName.jpg'` | heroBackground: 'https://source.unsplash.com/tjX_sniNzgQ/1600x400'
thumbnail | this is the image that displays on the summary and list version. You can make it the same as the header image, or something different (including the same image with different dimensions | thumbnail: 'https://source.unsplash.com/tjX_sniNzgQ/400x300'
images | a list of images for the gallery. Note the format shown in the example | images: ['https://source.unsplash.com/random/400x600/?nature', 
'https://source.unsplash.com/random/400x300/?travel','https://source.unsplash.com/random/400x300/?architecture','https://source.unsplash.com/random/400x600/?buildings','https://source.unsplash.com/random/400x300/?city','https://source.unsplash.com/random/400x600/?business']

## About section

_This content is stored in the `content > about` folder._

### Intro text

This is written in markdown in the `index.md` file. There is a header that affects the background image:

Name | Description | Example
---- | ----------- | -------
title | The title for the page. Displayed on the browser title bar | title: 'About'
date | the publication date for the page. This field is optional, but useful to get search engines to re-index the page if it changes | date: 2018-12-06T09:29:16+10:00
layout | indicates that the layout that should be used is the "about layout". Don't change this value | layout: 'aboutlayout'
hero | as with the other pages, you can include a hero image and text here. the usual fields are included | hero: false; heroHeading: ''; heroSubHeading: ''
background | the image that is behind the text that is shown behind the text in markdown. If you have an image that is light on the left side, with an image on the right, it will look best (without update of the layout) |background: 'https://source.unsplash.com/zglUlG8k47I/1600x500'

### Subsections

Each subsection is a separate page in the `about` folder. They are displayed in order by their weight. The intro paragraph is "highlighted" with emphasized text. The headers for these pages should be as follows:

Name | Description | Example
---- | ----------- | -------
title | The title for the page. Displayed on the browser title bar | title: 'Community'
date | the publication date for the page. This field is optional, but useful to get search engines to re-index the page if it changes | date: 2018-12-06T09:29:16+10:00
icon | this image is shown in the list on the about landing page. the image should be square, and will automatically be resized to be the same size. | icon: 'features/noun_The Process_1885341.svg'
featured | This value needs to be true to be shown on the about landing page | featured: true
draft | indication if this page is a draft or not. It is possible that this feature is not implemented on this site - not tested | draft: false
type | indicates the layout type for the page - this should remain as "about" | type: about
description | this text is displayed on the about landing page | description: "Short description here. New image is needed."
weight | the order that this item should be displayed in the list and summary views. Note, this is a dumb indicator. You are going to want to be careful about assigning different numbers to each page to avoid conflicts | weight: 2
hero | as with the other pages, you can include a hero image and text here. the usual fields are included | heroHeading: 'SeamlessAccess.org Community'; heroSubHeading: 'Who is SeamlessAccess?'; heroBackground: 'https://source.unsplash.com/_v-EHHKKW3w/1600x700'
---
