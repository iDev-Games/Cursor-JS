<p align="center">
  <img src="https://github.com/iDev-Games/Cursor-JS/blob/master/logo.png">
</p>


[![iDev-Games - Cursor-JS](https://img.shields.io/static/v1?label=iDev-Games&message=Cursor-JS&color=blue&logo=github)](https://github.com/iDev-Games/Cursor-JS "Go to GitHub repo")
[![stars - Cursor-JS](https://img.shields.io/github/stars/iDev-Games/Cursor-JS?style=social)](https://github.com/iDev-Games/Cursor-JS)

[![Stargazers repo roster for @iDev-Games/Cursor-JS](https://reporoster.com/stars/iDev-Games/Cursor-JS)](https://github.com/iDev-Games/Cursor-JS/stargazers)

[![GitHub tag](https://img.shields.io/github/tag/iDev-Games/Cursor-JS?include_prereleases=&sort=semver&color=blue)](https://github.com/iDev-Games/Cursor-JS/releases/)
[![License](https://img.shields.io/badge/License-MIT-blue)](#license)

Cursor.js powers dynamic, CSS-driven cursor-reactive effects using CSS variables and cursor position data, making mouse interactions effortless. Create custom animations in CSS or use cursor-animations.css for ready-made effects—full control or quick setup. Perfect for interactive websites.

<p align="center">
  <img src="https://github.com/iDev-Games/Cursor-JS/raw/master/creative.gif">
</p>


See it in action here: https://idev-games.github.io/Cursor-JS/

Find our codepen examples here: https://codepen.io/collection/RPLmpy

Keep up to date with tutorials, examples and information on my dev.to: https://dev.to/idevgames

Cursor-Animations.css documentation can be found here: https://idev-games.github.io/Cursor-JS/animations.html

You can download from Github.

Install with NPM

```css
npm i @idevgames/cursor-js
```

Use Cursor.js from a CDN
```
https://cdn.jsdelivr.net/npm/@idevgames/cursor-js/src/cursor.min.js
```

# What is Cursor.js?
Cursor.js is a super simple, efficient and lightweight way of making CSS cursor animations that react to the position of your mouse cursor on your HTML elements. You can also use Cursor.js to trigger CSS animations when the cursor hovers over an element.

Using nothing but the power of CSS, HTML and Cursor.js, you can make interactive cursor-reactive effects! Cursor.js is really lightweight and created with javascript and doesn't require any dependencies.

Cursor.js is really simple and quick to work with. You can use Cursor.js even if you aren't familiar with javascript.

Cursor.js is the perfect solution for CSS cursor animations in any project by developers of any skill level for both light or heavy usage. Perfect for creating magnetic effects, parallax on hover, tilt effects, and more! Pair with [https://github.com/iDev-Games/Cursor-JS](Cursor.js) for efficient scroll animations that work in the same way.

# Cursor-Animations.css
Configurable predefined cursor animations for your projects
https://idev-games.github.io/Cursor-JS/animations.html

# How To Install?
All you need to do is add the dist cursor.js file into your projects JS folder and add the following code with your cursor.js location as the src. Put this code in to your head HTML tags

```html
<script src="/js/cursor.min.js"></script>
```

Or just add a CDN instead
```html
<script src="https://cdn.jsdelivr.net/npm/@idevgames/cursor-js/src/cursor.min.js"></script>
```

# How To Use?
To activate cursor.js add the data attribute "data-cursor" or a class "enable-cursor" to your html element. To trigger animations cursor.js will place a class of "cursor" onto your element when the mouse hovers over it, as well as "cursor-enter-top", "cursor-enter-bottom", "cursor-enter-left", or "cursor-enter-right" depending from which direction the cursor entered.

```html
<div class="fadeIn" data-cursor> </div>
```
```css
.fadeIn{
    opacity:0;
}
.fadeIn.cursor{
    animation: fadeIn 1s normal forwards ease-in-out;
}
@keyframes fadeIn {
  0% {
    opacity:0;
  }
  100% {
    opacity:1;
  }
}
```

# Cursor Animations
Cursor.js calculates the percentage of cursor position on the element and creates CSS variables that you can use with CSS transform etc.

```html
<div class="element" data-cursor data-cursor-var="true"> </div>
```
```css
.element{
  transform: translateX( var(--cursor-x) );
}
```

The CSS variables you can use by adding **data-cursor-var="true", data-cursor-pixels="true" or data-cursor-degrees="true"** are:

- `--cursor-x` (0-100%)
- `--cursor-x-reverse` (-100-0%)
- `--cursor-y` (0-100%)
- `--cursor-y-reverse` (-100-0%)
- `--cursor-x-px` (pixel values)
- `--cursor-y-px` (pixel values)
- `--cursor-deg` (angle from center, 0-360deg)
- `--cursor-speed` (movement velocity)

The data attribute will also update in increments of 10 so you can use CSS attribute selectors like `[data-cursor-var-x="50"]{ }` for more control.

# Cursor Direction
Cursor.js creates classes of "cursor-moving-up", "cursor-moving-down", "cursor-moving-left", or "cursor-moving-right" onto the body of the document depending on the last cursor movement direction.

# Cursor States
Cursor.js creates classes of "cursor-active" or "cursor-idle" onto the body of the document depending on cursor activity (idle after 1 second of no movement).

When the mouse button is pressed, the class "cursor-down" is added to the body element.

# Data Attributes
You can use the below data attributes for additional features

```html
<div id="yourelement"
     data-cursor-min="-100"
     data-cursor-max="100"
     data-cursor-offset="0"
     data-cursor-negativeOffset="0"
     data-cursor-height="0"
     data-cursor-global="false"
     data-cursor>
</div>
```

## Global CSS Variables
If you want to use cursor position data globally (anywhere in your CSS), add `data-cursor-global="true"` and an `id` to your element:

```html
<div id="myElement" data-cursor data-cursor-var="true" data-cursor-global="true"></div>
```

This creates global CSS variables:
```css
:root {
  --cursor-myElement-x: 50%;
  --cursor-myElement-y: 50%;
  /* etc... */
}
```

# Example Effects

## Magnetic Button
```html
<button class="magnetic-btn" data-cursor data-cursor-var="true">Hover Me</button>
```
```css
.magnetic-btn {
  transition: transform 0.3s ease-out;
}
.magnetic-btn.cursor {
  transform: translate(
    calc((var(--cursor-x) - 50%) * 0.3),
    calc((var(--cursor-y) - 50%) * 0.3)
  );
}
```

## Dynamic Glow
```html
<div class="glow-box" data-cursor data-cursor-var="true" data-cursor-degrees="true"></div>
```
```css
.glow-box {
  transition: box-shadow 0.3s ease-out;
}
.glow-box.cursor {
  box-shadow: 0 0 30px hsl(var(--cursor-deg), 80%, 60%);
}
```

# Companion Library
Cursor.js is the perfect companion to [Trig.js](https://github.com/iDev-Games/Trig-JS) for complete control over both scroll and cursor interactions using the same elegant CSS-first philosophy!

**Together they provide:**
- **Trig.js**: Scroll position data (vertical)
- **Cursor.js**: Mouse position data (horizontal + vertical)
- Same API patterns and conventions
- Same performance optimizations
- Zero dependencies for both
- Minimal footprint

Perfect pair for modern, interactive web experiences!

# Browser Support
Cursor.js works in all modern browsers that support IntersectionObserver and CSS Variables.

# Performance
Cursor.js is highly optimized:
- Uses `requestAnimationFrame` for smooth updates
- Passive event listeners for better scroll performance
- Attribute caching to minimize DOM reads
- Selective CSS variable updates (only when values change)
- IntersectionObserver for efficient element tracking

# License
Released under [MIT](/LICENSE) by [@iDev-Games](https://github.com/iDev-Games).

# Credits
Created by iDev Games as a companion library to Trig.js, bringing the same elegant CSS-first philosophy to cursor interactions.
