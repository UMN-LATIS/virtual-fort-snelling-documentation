---
title: Adding New Pages
# meta: This is the page meta text
# lead: This is the page lead text
---

This guide goes over the process of creating a new page of content for the Virtual Fort Snelling experience.

In the Virtual Fort Snelling experience, all of the pages are represented by XML files. XML is a type of markup language, similar to HTML.

The XML files for the Virtual Fort Snelling experience must follow a set of guidelines in order to be interpreted in the app.

This guide will cover the process of creating a new page of content, from start to finish.

## A warning

Please be **very careful** about renaming, and especially deleting existing files.

Pages are directly linked to by their file names, so by renaming a file you will break all links to it and must fix them manually.

Additionally, when the app first starts it automatically loads the `main-menu.xml` page first, so you **may not** rename that one! All other pages can be renamed if need be (but be aware that you will need to update all links pointing to them).

## 1. Create a new XML file in your fork of the data repository

Navigate to the `_pages` directory of your fork.

![1]({{ site.baseurl | append: '/assets/img/xml_guide/1.png' }})

## 2. Press the "Add File > Create New File" button

![2]({{ site.baseurl | append: '/assets/img/xml_guide/2.png' }})

## 3. Give the new file a unique name

It should satisfy the following criteria: 
- Unique from every other file in the `_pages` directory
- Ends in `.xml`
- Is comprised of only lowercase characters and dashes
- Does not start with `reserved`

A good example: `my-new-page.xml`

A bad example: `reserved-my-New Page.oops`

![3]({{ site.baseurl | append: '/assets/img/xml_guide/3.png' }})

## 4. Write the file contents

Please see the [Understanding XML]({{ site.baseurl | append: '/pages/guides/understanding-xml' }}) guide for an in-depth look at what each page can contain.


### 4.1 Add a link to the page 

If you are creating a new page (rather than modifying an existing one), you will need to add a way to navigate to it from within the existing menu structure.

The first page of the menu is described in `main-menu.xml`, and all other pages should be accessible from that common starting point. Please add a link to your page where appropriate.

For example, if you were adding a page describing some structure in the diamond area of the fort, it would go in `diamond-area.xml`, referenced from `main-menu > landmarks > diamond-area`.

## 5. Press the "Commit New File" button

![4]({{ site.baseurl | append: '/assets/img/xml_guide/4.png' }})

Github will regenerate your site within a few minutes, and you will be able to see your new page in the app!