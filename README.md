# Silver Eagle's Letterbox Aerie
The URL of the website is: https://sileagle1.github.io

## Technology

The website uses [Jekyll](https://jekyllrb.com/) to help simplify content creation.
Content is still written using HTML, but Jekyll does a lot of heavy lifting to make things
easy to use and link together.

## Adding New Content

### New Page

To add a new page that shows up in the sidebar, create a new HTML file in the project.
If the page is going to be in the sidebar, you should create the page in the root of the project.
Otherwise, create the new page in the appropriate folder such as `series`.

Copy the header from the top of `index.html` so that the layout is defined.
It should look like this:
```yaml
---
layout: default
title: Home
nav_order: 1
permalink: /
---
```

* `title` is the title of the web page.
* `nav_order` is the order the page will show up in the sidebar with `1` at the top.
  If you do not want the page to show up in the sidebar, replace this with `nav_exclude: true`
* `permalink` should be the path to the page, so if the page is `test.html`, the value should be `/test`

Below this section you can add HTML.
You do not need to put the basic `<html>` or `<body>` tags: the content you put here will
automatically be inserted into the correct place in the final page.

### New Photo Album

This website is set up to automatically create photo albums based on the files that are present.
To create a new album, create a new folder under the `photos` folder.
The name of this folder will be the name of the photo album.

To add captions to photos, you will need to edit the file `_data/image_captions.yaml`.
The top-level key is the name of the folder you created.
The child keys are the names of the individual photograph files within that folder.

So, this would be the content you would add to the file in order to add a caption
to the photos `photo1.jpg` and `photo2.jpg` in the folder `photos/TALE21-event`:
```yaml
TALE21-event:
  photo1.jpg: The first photograph
  photo2.jpg: The second photograph
```

After adding all the photos, run the command `bundle exec jekyll build` in the terminal to generate
the new thumbnail images on your machine.

## Adjusting Style

The style related files live in the `lib` folder.
The `just-the-doc` Jekyll theme does most of the default styling, but there are things that
are overriden in the css files of that folder.
Images used for backgrounds are in the `lib/images` folder.

## Local Development

### Setup

* You will need to [install prerequisites for Jekyll](https://jekyllrb.com/docs/installation/windows/)
* You will need to [install ImageMagick](https://imagemagick.org/script/download.php)
* In the root of the project, run `bundle install`

### Preview Changes Locally

* In the root of the project, run `bundle exec jekyll serve trace`
* You can view the website at http://127.0.0.1:4000
* Changes made to html files should automatically be reflected when you refresh the page in the browser.
  If not, simply stop the `bundle` command and re-run it.

### Commit and Push Changes
* Once you are satisfied with your changes, commit and push the files to GitHub.
* It will take a few minutes for the changes to be built and published.
