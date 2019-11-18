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
