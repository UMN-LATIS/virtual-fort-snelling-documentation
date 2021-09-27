---
title: Work
meta: For contributors
# lead: This is the page lead text
---

Now that you're setup, it's time to get to work on actually making content and testing it.

## 1. Modify the content

At this point, you can add and/or modify content as you see fit!

Please see the [Adding New Pages]({{ site.baseurl | append: '/pages/guides/adding-new-pages' }}) guide for a detailed tutorial on how to add new content to the app.

Once you've made your changes, your fork should update itself and you are ready to test it. Note that Github takes a few minutes to update the site after you make changes, so give it a few minutes before you test.

## 2. Load your fork in the app

Once your fork of the data repository has updated itself, you can test it in the app.

- Open the menu
- Open the "Options" page
- Open the "Developer Options" page
- Scroll down to the "Developer server url" input
- Type in the full url of your fork of the data repository
- Press the submit button
- Wait a few seconds for the content to load

<video src="{{ site.baseurl | append: '/assets/vid/work/devserver.mp4' }}" controls></video>

If the content failed to load for some reason, it will show you the "error" screen when you try to open the menu. From there, you can either try again or check the messages page to see the reason for the failure.

<video src="{{ site.baseurl | append: '/assets/vid/work/devservererror.mp4' }}" controls></video>

## 3. Verify everything works as intended

Open the new pages you added, and verify that all the text, buttons, images, etc work as you intend them to.

Additionally, check the log page for any errors or warnings that might have popped up while reading your content. This page can be accessed from the main menu in `Options > Developer Options > Log`.