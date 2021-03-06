---
title: Off-canvas
description: Off-canvas menus are positioned outside of the viewport and slide in when activated. Setting up an off-canvas layout in Foundation is super easy.
sass: scss/components/_off-canvas.scss
js: js/foundation.offcanvas.js
tags:
  - navigation
---

<div class="callout alert">
  <h4>Known Issues</h4>
  <ul>
    <li>The right off-canvas menu jitters when it opens.</li>
    <li>The right off-canvas menu is not properly hiding on mobile on init.</li>
    <li>Menus should not force a <code>scrollTop()</code>?</li>
    <li>Open menus should trap focus.</li>
  </ul>
</div>

<button class="button" type="button" data-toggle="offCanvasLeft">Toggle Off-canvas</button>

## Setup

Create an off-canvas menu with the class `.off-canvas` and the attribute `data-off-canvas`. The menu also needs a positioning class, which can be `.position-left` or `.position-right`. Make sure the off-cavnas also has a unique ID so it can be targeted.

Along with the menu, the main content of your page will be housed in its own container with the class `.main-content` and attribute `data-off-canvas`.

```html
<body>
  <div class="off-canvas position-left" id="offCanvas" data-off-canvas data-position="left"></div>
  <div class="main-content" data-off-canvas-content></div>
</body>
```

### Click Triggers

To create a click trigger that opens the menu, add the attribute `data-open` or `data-toggle` to any element. That element will then open or toggle the menu when clicked on. The value of the data attribute should be the ID of the off-canvas.

```html
<button type="button" class="button" data-toggle="offCanvas">Open Menu</button>
```

---

## Multiple Menus

A design can have two menus: one on the left, and one on the right. Be sure that both menus come *before* the `.main-content` wrapper&mdash;this is required for the CSS to apply correctly.

```html
<body>
  <div class="off-canvas position-left" id="offCanvas" data-off-canvas></div>
  <div class="off-canvas position-right" id="offCanvas" data-off-canvas></div>
  <div class="main-content" data-off-canvas-content></div>
</body>
```

<button class="button" type="button" data-toggle="offCanvasLeft">Open Left Menu</button>
<button class="button" type="button" data-toggle="offCanvasRight">Open Right Menu</button>

---

## Title Bar

If you need a simple title bar to toggle the off-canvas, `.title-bar` is here to help. It supports left- and right-aligned sections.

```html_example
<div class="title-bar">
  <div class="title-bar-left">
    <button class="menu-icon" type="button" data-open="offCanvasLeft"></button>
    <span class="title-bar-title">Foundation</span>
  </div>
  <div class="title-bar-right">
    <button class="menu-icon" type="button" data-open="offCanvasRight"></button>
  </div>
</div>
```

---

## Reveal on Larger Screens

The left- and right-hand off-canvas panes can be set to be persistent on larger screens. Add the class `.reveal-for-medium` or `.reveal-for-large` to the off-canvas menu.

The main content area (`.main-content`) will be padded to the left or right equal to the width of the container.

<div class="warning callout">
  <p>The slide in/out of the plugin still works when these classes are active. If you use this feature on a larger screen, be sure to hide any click triggers on those larger breakpoints as well. Foundation's <a href="visibility.html">visibility classes</a> can help you with that.</p>
</div>

```html
<div class="off-canvas position-left reveal-for-large" data-off-canvas>
  <!-- ... -->
</div>
```

<button type="button" class="button" data-docs-example-ofc>Toggle Reveal Class</button>
