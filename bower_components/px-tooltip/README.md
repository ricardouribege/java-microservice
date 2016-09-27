# Px-Tooltip

## Overview

Px-Tooltip is a Predix Experience component which opens a tooltip message,
allowing the user to get a better view and or understanding of the content.

## Usage

### Prerequisites
1. node.js
2. npm
3. bower
4. [webcomponents-lite.js polyfill](https://github.com/webcomponents/webcomponentsjs)

Node, npm and bower are necessary to install the component and dependencies. webcomponents.js adds support for web components and custom elements to your application.

### Getting Started

First, install the component via bower on the command line.

```
bower install https://github.com/PredixDev/px-tooltip.git --save
```

Second, import the component to your application with the following tag in your head.

```
<link rel="import" href="/bower_components/px-tooltip/px-tooltip.html"/>
```

Finally, use the component in your application:

```
<px-tooltip tooltip-message="Hello World"></px-tooltip>
```

<br />
<hr />

## Attributes

####delay
*Type:* **Number** - (*Optional*) - *Default:* "1000"
The delay in milliseconds until the tooltip is displayed.

```
<px-tooltip
  ...
  delay="500">
</px-tooltip>
```

####for
*Type:* **Object** - (*Optional*) - *Default:* ""
The element to which the tooltip provides additional information.  
Optional, tooltip will be attached to parent element if a 'for' id is not provided.

'for' can be either an String for the ID of the element, or the element itself.

If an ID is passed, this element must be a sibling of the tooltip.

```
<px-tooltip
  ...
  for="exampleDiv">
</px-tooltip>

<px-tooltip
...
id="myTooltip">
</px-tooltip>
<script>
  document.addEventListener("WebComponentsReady", function() {
    var target = Polymer.dom(document).querySelector('#hoverDiv'),
        tt = Polymer.dom(document).querySelector('#myTooltip');

    tt.set('for',target);
  });
</script>
```

####orientation
*Type:* **String** - (*Optional*) - *Default:* "auto"
The position of the tooltip relative to the 'for' element. Currently supports 'top', 'bottom', 'left', 'right' and 'auto'.

```
<px-tooltip
  ...
  orientation="top">
</px-tooltip>
```

####smartOrientation
*Type:* **Boolean** - (*Optional*) - *Default:* "false"
If smartOrientation is turned on then the tooltip will override the default orientation to try to better fit on the page. Smart Orientation will be chosen in a clockwise manner. (example: for a tooltip with "right" orientation it will be below if tooltip will go off right side of the screen, but left if it goes off right *and* bottom side of the screen)

```
<px-tooltip
  ...
  smartOrientation="true">
</px-tooltip>
```

####tooltip-message
*Type:* **String** - (*Required*) - *Default:* ""
The text message that will be displayed in the tooltip. Also support HTML elements.

```
<px-tooltip
  ...
  tooltip-message="Hello World">
</px-tooltip>
```

<br />
<hr />


## Local Development

From the component's directory...

```
$ npm install
$ bower install
$ grunt sass
```

From the component's directory, to start a local server run:

```
$ grunt depserve
```

Navigate to the root of that server (e.g. http://localhost:8080/) in a browser to open the API documentation page, with link to the "Demo" / working examples.

### LiveReload

By default grunt watch is configured to enable LiveReload and will be watching for modifications in your root directory as well as `/css`.

Your browser will also need to have the LiveReload extension installed and enabled. For instructions on how to do this please refer to: [livereload.com/extensions/](http://livereload.com/extensions/).

Disable LiveReload by removing the `livereload` key from the configuration object or explicitly setting it to false.


### concurrent
concurrent runs `grunt depserve` and `grunt watch` concurrently so that when you make a change to your source files and save them, your preview will be updated in any browsers you have opened and turned on LiveReload.
From the component's directory run:

```
$ grunt concurrent
```

### GE Coding Style Guide
[GE JS Developer's Guide](https://github.com/GeneralElectric/javascript)

<br />
<hr />

## Known Issues

Please use [Github Issues](https://github.com/PredixDev/px-tooltip/issues) to submit any bugs you might find.
