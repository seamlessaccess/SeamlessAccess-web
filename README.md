# learn-hugo
a repository for learning hugo

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
