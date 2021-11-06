---
title: Understanding XML
# meta: This is the page meta text
# lead: This is the page lead text
---

**General**
- [Front-matter](#front-matter)
- [\<page\>](#page)
- [\<divider\>](#divider)

**Text**
- [\<title\>](#title)
- [\<subtitle\>](#subtitle)
- [\<body\>](#body)
- [\<caption\>](#caption)

**Multimedia**
- [\<image\>](#image)
- [\<gallery\>](#gallery)
    - [\<gallery-image\>](#gallery-image)
- [\<audio\>](#audio)

**Interaction**
- [Actions](#actions)
- [\<button\>](#button)
- [\<icon-button\>](#icon-button)
- [\<timeline\>](#timeline)
    - [\<timeline-button\>](#timeline-button)


## Front-matter

All `.xml` files **must** contain the following as the first lines of the file.

```
---
---
```

These lines are referred to as the "front-matter", and they tell Github to process the page so it can be loaded in the app.

## \<page\>

After the front matter, all further content must be wrapped in a `<page>` tag.

```xml
---
---
<page>
    <!-- all content goes in here -->
</page>
```

## \<divider\>

The `<divider>` tag inserts a dividing line between the prior and following content.

```xml
---
---
<page>
    <body>Here's some text</body>
    <divider />
    <body> Here's more text</body>
</page>
```

![divider]({{ site.baseurl | append: '/assets/img/xml_guide/divider.png' }})

## \<title\>

The `<title>` tag renders the text within in a large, bold font. It is similar to the `<h1>` tag in HTML.

## \<subtitle\>

The `<subtitle>` tag renders the text within in a slightly smaller font than the title. It is similar to the `<h2>` tag in HTML.

## \<body\>

The `<body>` tag renders the text within in a regular font suitable for reading. It is similar to the `<p>` tag in HTML.

## \<caption\>

The `<caption>` tag renders the text within in a small, light-colored font.

## \<image\>


The `<image>` tag renders an image based on the provided attributes. When clicked, the image will expand into a full-screen view.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>src</code></td>
            <td>required</td>
            <td>a link to the image file (relative to the <a href="https://github.com/UMN-LATIS/virtual-fort-snelling-data/tree/main/">root</a> directory of the data repository)</td>
        </tr>
        <tr>
            <td><code>title</code></td>
            <td>optional</td>
            <td>a title to display under the image</td>
        </tr>
        <tr>
            <td><code>description</code></td>
            <td>optional</td>
            <td>a subtitle to display under the image</td>
        </tr>
    </tbody>
</table>

The source image file **must** be either `.png`, or `.jpg`.

### Example

```xml
---
---
<page>
    <image
        src="/assets/example/scoobydoo.jpg"
        title="Scooby Doo"
        description="Where are you?"
    />
</page>
```

![image]({{ site.baseurl | append: '/assets/img/xml_guide/image.png' }})


## \<gallery\>

The `<gallery>` tag is similar to the `<image>` tag, in that it displays a single image. The difference is that, when the image is tapped, it expands into a full-screen view with "previous" and "next" controls to cycle through the galleries content.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>src</code></td>
            <td>required</td>
            <td>a link to the cover image file (relative to the <a href="https://github.com/UMN-LATIS/virtual-fort-snelling-data/tree/main/">root</a> directory of the data repository)</td>
        </tr>
        <tr>
            <td><code>title</code></td>
            <td>optional</td>
            <td>a title to display under the cover image</td>
        </tr>
        <tr>
            <td><code>description</code></td>
            <td>optional</td>
            <td>a subtitle to display under the cover image</td>
        </tr>
    </tbody>
</table>

The `<gallery>` tag can only contain `<gallery-image>` tags and comments as children.

### \<gallery-image\>

The `<gallery-image>` tag should only be used within a `<gallery>` tag. It is otherwise identical to the `<image>` tag.

The source image files **must** be either `.png`, or `.jpg`.

### Example

```xml
---
---
<page>
    <gallery
        src="/assets/example/coverphoto.png"
        title="A Gallery"
    >
        <gallery-image src="/assets/example/gallery1.png" title="Alpha">
        <gallery-image src="/assets/example/gallery2.png" title="Beta">
        <gallery-image src="/assets/example/gallery3.png" title="Gamma">
    </gallery>
</page>
```
![gallery]({{ site.baseurl | append: '/assets/img/xml_guide/gallery.png' }})

![galleryfull]({{ site.baseurl | append: '/assets/img/xml_guide/galleryfull.png' }})

## \<audio\>

The `<audio>` tag renders an audio player based on the provided attributes. When clicked, the audio player will start/stop playing.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>src</code></td>
            <td>required</td>
            <td>a link to the audio file (relative to the <a href="https://github.com/UMN-LATIS/virtual-fort-snelling-data/tree/main/">root</a> directory of the data repository)</td>
        </tr>
        <tr>
            <td><code>icon-src</code></td>
            <td>optional</td>
            <td>a link to an image file (relative to the <a href="https://github.com/UMN-LATIS/virtual-fort-snelling-data/tree/main/">root</a> directory of the data repository), to be displayed on the audio player</td>
        </tr>
        <tr>
            <td><code>title</code></td>
            <td>optional</td>
            <td>a title to display next to the icon</td>
        </tr>
        <tr>
            <td><code>description</code></td>
            <td>optional</td>
            <td>a subtitle to display next to the icon</td>
        </tr>
    </tbody>
</table>

The source audio file **must** be either `.mp3`, `.wav`. The source icon file **must** be either `.png`, or `.jpg`.

### Example

```xml
---
---
<page>
    <audio
        src="/assets/example/audio.mp3"
        icon-src="/assets/example/audioicon.png"
        title="Groovy Tunes"
        description="Mystery Inc"
    />
</page>
```

![audio]({{ site.baseurl | append: '/assets/img/xml_guide/audio.png' }})


## Actions

All of the interaction-related tags make use of an **action – argument** system. This is defined by a list of action(s)

`action-0="..." action-1="..."`

and their associated argument(s)

`action-0-argument-0="..." action-0-argument-1="..." action-1-argument-0="..."`

For example, to open the menu and set the app's calendar to 1820, the actions would be

```xml
action-0="menu:open"
action-1="history:set-year"
action-1-argument-0="1820"
```

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
            <td><code>application:open-url</code></td>
            <td>any url</td>
            <td>leaves the app and opens the given url in the device's web browser</td>
        </tr>
        <tr>
            <td><code>menu:toggle</code></td>
            <td></td>
            <td>Toggles the menu state (opens it if it's closed, and closes it if it's open)</td>
        </tr>
        <tr>
            <td><code>menu:close</code></td>
            <td></td>
            <td>Closes the menu</td>
        </tr>
        <tr>
            <td><code>menu:open</code></td>
            <td></td>
            <td>Opens the menu</td>
        </tr>
        <tr>
            <td><code>menu:next-page</code></td>
            <td>the name of a page (as it appears in the <code>_pages</code> directory, without the <code>.xml</code> at the end)</td>
            <td>Opens the specified page</td>
        </tr>
        <tr>
            <td><code>menu:previous-page</code></td>
            <td></td>
            <td>Opens the previously opened page</td>
        </tr>
        <tr>
            <td><code>history:set-year</code></td>
            <td>any integer (e.g. <code>1820</code>)</td>
            <td>Sets the current year that the fort is viewed in</td>
        </tr>
        <tr>
            <td><code>player:teleport</code></td>
            <td>either 3 floats (position x, y, and z), 5 floats (position x, y, and z, normalizedYaw, normalizedPitch), or 6 floats (position x, y, and z, normalizedYaw, normalizedPitch, and normalizedZoom)</td>
            <td>Teleports the player to the specified position, and optionally points the camera in the specified direction</td>
        </tr>
        <tr>
            <td><code>player:set-mode</code></td>
            <td><code>toggle</code>, <code>first-person</code>, or <code>overview</code></td>
            <td>sets the camera mode to the specified mode (if no argument is provided, or the argument is <code>toggle</code>, then the mode is toggled)</td>
        </tr>
        <tr>
            <td><code>developer:clear-cache</code></td>
            <td></td>
            <td>Clears out the cached content stored on device</td>
        </tr>
        <tr>
            <td><code>developer:refresh-content</code></td>
            <td>either no argument, or a url</td>
            <td>reloads all the content from the given url (or the production data repository if no url is specified)</td>
        </tr>
    </tbody>
</table>

## \<button\>

The `<button>` tag renders a button that users can click to control functionality in the app.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>title</code></td>
            <td>optional</td>
            <td>a title to display on the button</td>
        </tr>
        <tr>
            <td><code>description</code></td>
            <td>optional</td>
            <td>a subtitle to display on the button</td>
        </tr>
        <tr>
            <td><code>action-X</code></td>
            <td>optional</td>
            <td>an action to perform when the button is clicked</td>
        </tr>
        <tr>
            <td><code>action-X-argument-Y</code></td>
            <td>optional</td>
            <td>the Yth argument for the Xth action</td>
        </tr>
    </tbody>
</table>

### Example

```xml
---
---
<page>
    <!--
        Clicking this will teleport the player to (5, 4, 3)
        and set their normalized yaw and pitch to 0.5
    -->
    <button
        title="Teleport"
        action-0="player:teleport"
        action-0-argument-0="5"
        action-0-argument-1="4"
        action-0-argument-2="3"
        action-0-argument-3="0.5"
        action-0-argument-4="0.5"
    />
</page>
```

![button]({{ site.baseurl | append: '/assets/img/xml_guide/button.png' }})

## \<icon-button\>

The `<icon-button>` tag renders a square icon button that users can click to control functionality in the app.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>src</code></td>
            <td>required</td>
            <td>a link to the icon file (relative to the <a href="https://github.com/UMN-LATIS/virtual-fort-snelling-data/tree/main/">root</a> directory of the data repository)</td>
        </tr>
        <tr>
            <td><code>action-X</code></td>
            <td>optional</td>
            <td>an action to perform when the button is clicked</td>
        </tr>
        <tr>
            <td><code>action-X-argument-Y</code></td>
            <td>optional</td>
            <td>the Yth argument for the Xth action</td>
        </tr>
    </tbody>
</table>

The source icon file **must** be either `.png`, or `.jpg`.

### Example

```xml
---
---
<page>
    <icon-button
        src="/assets/example/left-arrow.png"
        action-0="menu:previous-page"
    />
</page>
```

![icon-button]({{ site.baseurl | append: '/assets/img/xml_guide/icon-button.png' }})

## \<timeline\>

The `<timeline>` tag renders a list of buttons, each representing a year. The correct year is highlighted based on the app calendar.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>collapsible</code></td>
            <td>optional</td>
            <td><code>true</code> or <code>false</code></td>
        </tr>
        <tr>
            <td><code>title</code></td>
            <td>optional</td>
            <td>a title to display on the timeline button (only visible if <code>collapsible</code> is true)</td>
        </tr>
        <tr>
            <td><code>description</code></td>
            <td>optional</td>
            <td>a subtitle to display on the timeline button (only visible if <code>collapsible</code> is true)</td>
        </tr>
        <tr>
            <td><code>action-X</code></td>
            <td>optional</td>
            <td>an action to perform when <b>any button in the timeline</b> is clicked</td>
        </tr>
        <tr>
            <td><code>action-X-argument-Y</code></td>
            <td>optional</td>
            <td>the Yth argument for the Xth action</td>
        </tr>
    </tbody>
</table>

The `<timeline>` tag should only contain `<timeline-button>` tags and comments as children.

### \<timeline-button\>

The `<timeline-button>` tag renders a button within a `<timeline>` tag. If the calendar year matches the buttons year, then the button is highlighted.

<table class="uk-table uk-table-divider uk-table-justify">
    <thead>
        <tr>
            <th>Attribute</th>
            <th>Requirement</th>
            <th>Argument</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>year</code></td>
            <td>required</td>
            <td>an integer (e.g. <code>1820</code>)</td>
        </tr>
        <tr>
            <td><code>title</code></td>
            <td>optional</td>
            <td>a title to display on the button</td>
        </tr>
        <tr>
            <td><code>description</code></td>
            <td>optional</td>
            <td>a subtitle to display on the button</td>
        </tr>
        <tr>
            <td><code>action-X</code></td>
            <td>optional</td>
            <td>an action to perform when the button is clicked</td>
        </tr>
        <tr>
            <td><code>action-X-argument-Y</code></td>
            <td>optional</td>
            <td>the Yth argument for the Xth action</td>
        </tr>
    </tbody>
</table>

### Example


```xml
---
---
<page>

    <!--
        Closes the menu when ANY button in the timeline is clicked,
        and sets the calendar to a different year depending on the button.
    -->
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
</page>
```

![timeline]({{ site.baseurl | append: '/assets/img/xml_guide/timeline.png' }})