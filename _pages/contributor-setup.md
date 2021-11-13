---
title: Setup
meta: For contributors
# lead: This is the page lead text
---

Before you begin developing new content, you'll need to get a few things setup first.

## 1. Get a copy of the app

You'll need to get a copy of the app. Currently the app is available in beta for macOS and Windows platforms.

- [Download](https://historyxr.umn.edu/projects/virtual-fort-snelling-beta)

Once you have acquired the app, you should open it up and get comfortable with it.

## 2. Make a Github account

You will also need a [Github](https://www.github.com/) account.

Note that this is a regular `github.com` account, not a `github.umn.edu` account.

## 3. Fork the data repository

The data for the Virtual Fort Snelling experience is hosted on a public repository, at [http://github.com/UMN-LATIS/virtual-fort-snelling-data](http://github.com/UMN-LATIS/virtual-fort-snelling-data).

When the app first opens, it reads the XML files from the data repository to construct the menu pages.

In order to develop new content for the app, you will need to make a fork of this repository. A fork is like a copy of the repository that you are able to modify freely, without affecting the original repository.

**Step 1. Go to the data repository**

[http://github.com/UMN-LATIS/virtual-fort-snelling-data](http://github.com/UMN-LATIS/virtual-fort-snelling-data)

**Step 2. Press the fork button**

![1]({{ site.baseurl | append: '/assets/img/fork_guide/1.png' }})

**Step 3. Select your Github username as the destination**

![2]({{ site.baseurl | append: '/assets/img/fork_guide/2.png' }})

It will take a few seconds, and then bring you to your forked copy of the repository.


## 4. Enable Github Pages for your fork

Now that you have your own copy of the repository forked, you need to make sure it is setup to be published on the web, so that the app can read content from it.

**Step 1. Click on the "Settings" tab**

![3]({{ site.baseurl | append: '/assets/img/fork_guide/3.png' }})

**Step 2. Click on the "Pages" tab**

![4]({{ site.baseurl | append: '/assets/img/fork_guide/4.png' }})

**Step 3. Set the source to the main branch root, and press save**

![5]({{ site.baseurl | append: '/assets/img/fork_guide/5.png' }})

**Step 4. Verify that the site is published**

After a few minutes, refresh the page and look for the indicator that the site is published. Take a note of this url, as it will be important later.

![5]({{ site.baseurl | append: '/assets/img/fork_guide/6.png' }})

Now you are ready to begin developing content!
