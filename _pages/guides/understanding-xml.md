---
title: Understanding XML
# meta: This is the page meta text
# lead: This is the page lead text
---

## 1. Front-matter

All `.xml` files must contain the following as the first lines of the file.

```
---
---
```

These lines are referred to as the "front-matter", and they tell Github to process the page so it can be loaded in the app.

## 2. \<page\> Tag

After the front matter, all future content must be wrapped in a `<page>` tag.

```html
---
---
<page>
    <!-- all content goes in here -->
</page>
```

## 3. Text Tags

### 3.1 \<title\>

The `<title>` tag produces text in a large, bold font. It is similar to the `<h1>` tag in HTML.

### 3.2 \<subtitle\>

The `<subtitle>` tag produces text in a slightly smaller font than the title. It is similar to the `<h2>` tag in HTML.

### 3.3 \<body\>

The `<body>` tag produces text in a regular font suitable for reading. It is similar to the `<p>` tag in HTML.

### 3.4 \<caption\>

The `<caption>` tag produces smaller text in a lighter font.

### 3.5 Examples

For example, the following file

```xml
---
---
<page>
    <title>The Aliens Invade!</title>

    <subtitle>One Local Man Has The Scoop</subtitle>

    <body>"Yeah, they came down last night I reckon" says local farmer J. T.</body>

    <body>"I hope they're friendly," he adds.</body>

    <caption>(We have since learned, they are).</caption>
</page>
```

will produce

![text]({{ site.baseurl | append: '/assets/img/xml_guide/text.png' }})

## 4. Multimedia Tags

### 4.1 \<image\>

The `<image>` tag produces an image.

It must contain the following attribute(s):
- `src`: a link to the image to display

And can optionally contain the following attribute(s):
- `title`: a title to display under the image
- `description`: a subtitle to display under the image

### 4.2 \<audio\>

The `<audio>` tag produces a playable audio clip.

It must contain the following attribute(s):
- `src`: a link to the audio clip to play when clicked

And can optionally contain the following attribute(s):
- `icon-src`: a link to an icon to display on the button (e.g. the album art)
- `title`: a title to display on the button (e.g. the song title)
- `description`: a subtitle to display on the button (e.g. the artist name)

### 4.3 Examples

For example, the following file

```xml
---
---
<page>
    <image
        src="/assets/example/scoobydoo.jpg"
        title="Scooby Doo"
        description="Where are you?"
    />

    <audio
        src="/assets/example/audio.mp3"
        icon-src="/assets/example/audioicon.png"
        title="Groovy Tunes"
        description="Mystery Inc"
    />
</page>
```

will produce

![multimedia]({{ site.baseurl | append: '/assets/img/xml_guide/multimedia.png' }})

### 4.4 Notes

**a. Links**

The `src` and `icon-src` attributes are relative to the `assets` directory of the data repository. You **cannot** link to any old content hosted on the web, it must be hosted in the assets directory of the data repository.

**b. Formats**

Images must be in either `.jpg`, or ideally `.png` format.

Audio must be in either `.wav`, or ideally `.mp3` format.


## 5. Interactive Tags

### 5.1 \<button\>

The `<button>` tag produces a button that users can click to control functionality in the app.

It must contain the following attribute(s):
- `title`: a title to display on the button

And can optionally contain the following attribute(s):
- `description`: a description to display on the button
- all of the action-argument attributes

The action-argument system is outlined later on in section `5.6`.

### 5.2 \<icon-button\>

The `icon-button` tag produces a square button with an icon that users can click to control functionality in the app.

It must contain the following attribute(s):
- `src`: a link to an icon to display on the button

And can optionally contain the following attribute(s):
- all of the action-argument attributes

The action-argument system is outlined later on in section `5.6`.

### 5.3 \<input\>

The `<input>` tag produces a text field and button that users can type into and click.

It must contain the following attributes:
- `placeholder`: placeholder text to display before the user has typed anything in
- `action-0`: the action to execute when the button is clicked (the value of the input field is used as `action-0-argument-0`)

The action-argument system is outlined later on in section `5.6`.

### 5.4 \<timeline\>

The `<timeline>` tag produces a list of buttons, each representing a year.

It can optionally contain the following attribute(s):
- `collapsible`
- `title`
- `description`
- all of the action-argument attributes

The action-argument system is outlined later on in section `5.6`.

If `collapsible` is set to `true`, then the timeline will be rendered as a button and only expanded into a full timeline view after the button is clicked. (The `title` and `description` attributes are unused if `collapsible` is false).

The `<timeline>` tag can only contain comments and `<timeline-button>` tags as children.

### 5.5 \<timeline-button\>

The `<timeline-button>` tag produces a button within a `<timeline>` tag.

It must contain the following attribute(s):
- `year`: the year this button represents in the timeline

And can optionally contain the following attribute(s):
- `title`
- `description`
- all of the action-argument attributes

The action-argument system is outlined later on in section `5.6`.

### 5.6 Actions


<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Action</th>
            <th>Argument(s)</th>
            <th>Functionality</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>application:open-url</td>
            <td>any url</td>
            <td>leaves the app and opens the given url in the device's web browser</td>
        </tr>
        <tr>
            <td>options:swap-hand</td>
            <td></td>
            <td>Swaps which side the UI appears on in the app</td>
        </tr>
        <tr>
            <td>options:swap-theme</td>
            <td></td>
            <td>Swaps between light and dark colors</td>
        </tr>
        <tr>
            <td>menu:toggle</td>
            <td></td>
            <td>Toggles the menu state (opens it if it's closed, and closes it if it's open)</td>
        </tr>
        <tr>
            <td>menu:close</td>
            <td></td>
            <td>Closes the menu</td>
        </tr>
        <tr>
            <td>menu:open</td>
            <td></td>
            <td>Opens the menu</td>
        </tr>
        <tr>
            <td>menu:next-page</td>
            <td>the name of a page (as it appears in the <code>_pages</code> directory, without the <code>.xml</code> at the end)</td>
            <td>Opens the specified page</td>
        </tr>
        <tr>
            <td>menu:previous-page</td>
            <td></td>
            <td>Opens the previously opened page</td>
        </tr>
        <tr>
            <td>history:set-year</td>
            <td>any integer (e.g. <code>1820</code>)</td>
            <td>Sets the current year that the fort is viewed in</td>
        </tr>
        <tr>
            <td>player:teleport</td>
            <td>either 3 floats (position x, y, and z), or 5 floats (position x, y, and z, pitch, and yaw)</td>
            <td>Teleports the player to the specified position, and optionally points the camera in the specified direction</td>
        </tr>
        <tr>
            <td>player:set-mode</td>
            <td>either no arguments, <code>first-person</code>, or <code>overview</code></td>
            <td>sets the camera mode to the specified mode (if no argument is provided, the mode is toggled)</td>
        </tr>
        <tr>
            <td>developer:clear-cache</td>
            <td></td>
            <td>Clears out the cached content stored on device</td>
        </tr>
        <tr>
            <td>developer:refresh-content</td>
            <td>either no argument, or a url</td>
            <td>reloads all the content from the given url (or the production data repository if no url is specified)</td>
        </tr>
        <tr>
            <td>developer:toggle-info</td>
            <td></td>
            <td>Toggles a debug overlay containing the FPS, player position, etc.</td>
        </tr>
    </tbody>
</table>

### 5.7 Examples

The following code would teleport a player to (5, 4, 3) and set their pitch and yaw to (0, 90)

```xml
<button
    title="Teleport"
    action-0="player:teleport"
    action-0-argument-0="5"
    action-0-argument-1="4"
    action-0-argument-2="3"
    action-0-argument-3="0"
    action-0-argument-4="90"
/>
```

![button]({{ site.baseurl | append: '/assets/img/xml_guide/button.png' }})


The following code would open the url in the input field. (Note that the content of the input field is implicitly used as `action-0-argument-0`)

```xml
<input
    placeholder="Enter a url to open..."
    action-0="application:open-url"
/>
```

![input]({{ site.baseurl | append: '/assets/img/xml_guide/input.png' }})


The following code would open the commander's house menu page, and set the year to 1820

```xml
<icon-button
    src="/assets/example/arrow.png"
    title="Commander's House"
    action-0="history:set-year"
    action-0-argument-0="1820"
    action-1="menu:next-page"
    action-1-argument-0="commanders-house"
/>
```

![icon-button]({{ site.baseurl | append: '/assets/img/xml_guide/icon-button.png' }})

The following code sets the year, and closes the menu after **any** of the buttons in the timeline are clicked

```xml

<timeline
    collapsible="true"
    title="Timeline"
    description="A set of years"
    action-0="menu:close"
>
    <timeline-button
        year="1820"
        title="1820"
        action-0="history:set-year"
        action-0-argument-0="1820"
    />

    <timeline-button
        year="1910"
        title="1910"
        description="Something happened in 1910"
        action-0="history:set-year"
        action-0-argument-0="1910"
    />

    <timeline-button
        year="2021"
        title="2021"
        description="Something REALLY happened in 2021"
        action-0="history:set-year"
        action-0-argument-0="2021"
    />
</timeline>
```

![timeline]({{ site.baseurl | append: '/assets/img/xml_guide/timeline.png' }})

## 6. Other Tags

### 6.1 \<divider\>

The `<divider>` tag just inserts a dividing line between content

### 6.2 Examples

For example, the following file

```xml
---
---
<page>
    <body>Here's some text</body>
    <divider />
    <body> Here's more text</body>
</page>
```

will produce

![divider]({{ site.baseurl | append: '/assets/img/xml_guide/divider.png' }})



