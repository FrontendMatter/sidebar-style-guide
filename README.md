# sidebar-style-guide

[![npm version](https://badge.fury.io/js/sidebar-style-guide.svg)](https://badge.fury.io/js/sidebar-style-guide)

A style guide (CSS and Sass) providing a convenient base for styling common sidebar/drawer elements like menus, brand, etc. 

This package complements the [drawer](https://github.com/themekit/material-design-kit/tree/master/src/drawer) component from [material-design-kit](https://github.com/themekit/material-design-kit).

## Installation

Install sidebar-style-guide via npm.

```bash
npm install sidebar-style-guide
```

## Usage

```sass
// Customize variables
$sidebar-font-size: 16px !default;

@import 'node_modules/sidebar-style-guide/sass/variables';
@import 'node_modules/sidebar-style-guide/sass/style';
```

## Sidebar skins

There are two base skin variants that you get out of the box for making a sidebar with a light background color and dark text color or a sidebar with dark background color and light text color.

<table>
  <thead>
    <tr>
      <th>CSS Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>.sidebar-light</code></td>
      <td>Defines the basic style for a sidebar with a light background color and dark text color.</td>
    </tr>
    <tr>
      <td><code>.sidebar-dark</code></td>
      <td>Defines the basic style for a sidebar with a dark background color and light text color.</td>
    </tr>
  </tbody>
</table>

Note that none of the skin classes include a background color, so the following example assumes you are adding the background with the additional `.bg-primary` and `.bg-white` custom classes.

```html
<!-- .sidebar-light -->
<div class="sidebar-light bg-white">
  ... 
</div>

<!-- .sidebar-dark -->
<div class="sidebar-dark bg-primary">
  ... 
</div>
```

## Sidebar position

Note that the positioning classes don't actually change your sidebar's position, but they can add styling which depends on the sidebar position. For example, when the sidebar is positioned to the left, you could apply a border to the right of the sidebar, separating the page content from the sidebar with a line.

<table>
  <thead>
    <tr>
      <th>CSS Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>.sidebar-left</code></td>
      <td>Applies style on a sidebar positioned to the left</td>
    </tr>
    <tr>
      <td><code>.sidebar-right</code></td>
      <td>Applies style on a sidebar positioned to the right</td>
    </tr>
  </tbody>
</table>

```html
<div class="sidebar-light bg-white sidebar-left">
  ... 
</div>
```

## Sidebar menu

<table class="table table-sm">
  <thead>
    <tr>
      <th>CSS Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>.sidebar-menu</code></td>
      <td>The sidebar menu wrapper <code>ul</code></td>
    </tr>
    <tr>
      <td><code>.sidebar-menu-item</code></td>
      <td>The sidebar menu item <code>li</code></td>
    </tr>
    <tr>
      <td><code>.sidebar-menu-button</code></td>
      <td>The sidebar menu button <code>a</code></td>
    </tr>
  </tbody>
</table>

To create a basic sidebar menu:

- add `ul` wrapper using the `.sidebar-menu` class
- add `li` menu items using the `.sidebar-menu-item` class
- add `a` menu buttons use the `.sidebar-menu-button` class
- add the `.active` class to `.sidebar-menu-item` elements

```html
<!-- Basic sidebar menu -->
<ul class="sidebar-menu">

  <!-- Active menu item -->
  <li class="sidebar-menu-item active">
    <a href="#" class="sidebar-menu-button">Active menu item</a>
  </li>

  <!-- Regular menu item -->
  <li class="sidebar-menu-item">
    <a href="#" class="sidebar-menu-button">Regular menu item</a>
  </li>

</ul>
```

You can customize sidebar menus with the following Sass variables.

### Spacing

<table>
  <thead>
    <tr>
      <th width="250">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-spacing-x</code></td>
      <td>Defines the horizontal spacing for sidebar menus</td>
      <td><code>$sidebar-spacing-x</code></td>
    </tr>
    <tr>
      <td><code>$sm-spacing-y</code></td>
      <td>Defines the vertical spacing for sidebar menus</td>
      <td><code>$sidebar-spacing-y</code></td>
    </tr>
  </tbody>
</table>

### .sidebar-menu-button

<table>
  <thead>
    <tr>
      <th width="250">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-button-font-size</code></td>
      <td>Defines the base font size in <code>px</code> for <code>.sidebar-menu-button</code></td>
      <td><code>$sidebar-font-size</code></td>
    </tr>
    <tr>
      <td><code>$sm-button-font-weight</code></td>
      <td>Defines the font weight for <code>.sidebar-menu-button</code></td>
      <td><code>400</code></td>
    </tr>
    <tr>
      <td><code>$sm-button-height</code></td>
      <td>Defines the height in <code>px</code> for <code>.sidebar-menu-button</code></td>
      <td><code>42px</code></td>
    </tr>
    <tr>
      <td><code>$sm-active-button-font-weight</code></td>
      <td>Defines the font weight for <code>.sidebar-menu-button</code> when using <code>li.sidebar-menu-item.active</code></td>
      <td><code>$sm-button-font-weight</code></td>
    </tr>
  </tbody>
</table>

## Sidebar menu icons

Add icons to sidebar menus.

<table>
  <thead>
    <tr>
      <th>CSS Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>.sidebar-menu-icon</code></td>
      <td>The sidebar menu icon</td>
    </tr>
    <tr>
      <td><code>.material-icons</code></td>
      <td>Required on <code>.sidebar-menu-icon</code> elements when using <a href="https://design.google.com/icons/">Material icons</a></td>
    </tr>
  </tbody>
</table>

### Dependencies

The following example is using Material icons, so make sure to load the icons library into the `<head>` section of your page before using the example.

```html
<!-- Material Design Icons -->
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

### Usage

To add an icon to the sidebar menu button, add an element using the `.sidebar-menu-icon` base icon class within the `.sidebar-menu-button` element. Also, to use the [Material icons](https://design.google.com/icons/) add the `.material-icons` class to the `.sidebar-menu-icon` element.

```html
<!-- Sidebar menu icons -->
<ul class="sidebar-menu">
  <li class="sidebar-menu-item">
    <a class="sidebar-menu-button" href="#">
      <i class="sidebar-menu-icon material-icons">home</i> 
      Menu button text
    </a>
  </li>
</ul>
```

You can customize sidebar menu icons with the following Sass variables.

<table>
  <thead>
    <tr>
      <th width="250">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-icon-font-size</code></td>
      <td>Defines the base font size in <code>px</code> for sidebar menu icons</td>
      <td><code>24px</code></td>
    </tr>
    <tr>
      <td><code>$sm-icon-margin</code></td>
      <td>Defines the margin for sidebar menu icons</td>
      <td><code>$sm-spacing-x * 0.4</code></td>
    </tr>
  </tbody>
</table>

> #### See also
> Sidebar menu icons in the context of [sidebar submenus](#sidebar-submenus).

## Sidebar menu utilities

You can modify the style of sidebar menus and sidebar submenus by using CSS helper classes. All the following classes should be applied on `.sidebar-menu` and `.sidebar-submenu` elements.

<table>
  <thead>
    <tr>
      <th>CSS Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>.sm-condensed</code></td>
      <td>Applies a smaller spacing to sidebar menu buttons</td>
    </tr>
    <tr>
      <td><code>.sm-bordered</code></td>
      <td>Applies a border bottom to a <code>.sidebar-menu</code> or <code>.sidebar-submenu</code></td>
    </tr>
    <tr>
      <td><code>.sm-item-bordered</code></td>
      <td>Applies a border bottom to <code>.sidebar-menu</code> or <code>.sidebar-submenu</code> items</td>
    </tr>
    <tr>
      <td><code>.sm-active-button-bg</code></td>
      <td>Applies a background color to active sidebar menu items</td>
    </tr>
    <tr>
      <td><code>.sm-icons-right</code></td>
      <td>Aligns the sidebar menu icons to the right</td>
    </tr>
    <tr>
      <td><code>.sm-icons-block</code></td>
      <td>Wrap the sidebar menu icons into a square block with background color</td>
    </tr>
    <tr>
      <td><code>.sm-indent</code></td>
      <td>Increase the horizontal spacing of <code>.sidebar-menu</code> or <code>.sidebar-submenu</code> buttons</td>
    </tr>
  </tbody>
</table>

You can customize sidebar utilities with the following Sass variables.

### .sm-condensed

<table>
  <thead>
    <tr>
      <th width="270">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-condensed-button-height</code></td>
      <td>Defines the height in <code>px</code> for sidebar menu buttons when using <code>.sm-condensed</code></td>
      <td><code>$sm-button-height - ($sm-button-height/4)</code></td>
    </tr>
    <tr>
      <td><code>$ssm-condensed-button-height</code></td>
      <td>Defines the height in <code>px</code> for sidebar submenu buttons when using <code>.sm-condensed</code></td>
      <td><code>$ssm-button-height - ($ssm-button-height/4)</code></td>
    </tr>
  </tbody>
</table>

### .sm-bordered

<table>
  <thead>
    <tr>
      <th width="270">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sidebar-dark-border-color</code></td>
      <td>Defines the default border color for sidebar elements when using the <code>.sidebar-dark</code> skin</td>
      <td><code>rgba(0, 0, 0, .15)</code></td>
    </tr>
    <tr>
      <td><code>$sidebar-light-border-color</code></td>
      <td>Defines the default border color for sidebar elements when using the <code>.sidebar-light</code> skin</td>
      <td><code>#e5e5e5</code></td>
    </tr>
  </tbody>
</table>

### .sm-item-bordered

<table>
  <thead>
    <tr>
      <th width="270">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-dark-item-border-color</code></td>
      <td>Defines the border color for sidebar menu items when using the <code>.sidebar-dark</code> skin</td>
      <td><code>$sidebar-dark-border-color</code></td>
    </tr>
    <tr>
      <td><code>$ssm-dark-item-border-color</code></td>
      <td>Defines the border color for sidebar submenu items when using the <code>.sidebar-dark</code> skin</td>
      <td><code>$sm-dark-item-border-color</code></td>
    </tr>
    <tr>
      <td><code>$sm-light-item-border-color</code></td>
      <td>Defines the border color for sidebar menu items when using the <code>.sidebar-light</code> skin</td>
      <td><code>$sidebar-light-border-color</code></td>
    </tr>
    <tr>
      <td><code>$ssm-light-item-border-color</code></td>
      <td>Defines the border color for sidebar submenu items when using the <code>.sidebar-light</code> skin</td>
      <td><code>$sm-light-item-border-color</code></td>
    </tr>
  </tbody>
</table>

### .sm-active-button-bg

<table>
  <thead>
    <tr>
      <th width="270">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-dark-active-button-bg</code></td>
      <td>Defines the background color for active sidebar menu buttons when using the <code>.sidebar-dark</code> skin</td>
      <td><code>rgba(255, 255, 255, .12)</code></td>
    </tr>
    <tr>
      <td><code>$sm-dark-activebuttonbg-button-color</code></td>
      <td>Defines the text color for active sidebar menu buttons when using the <code>.sidebar-dark</code> skin</td>
      <td><code>#fff</code></td>
    </tr>
    <tr>
      <td><code>$sm-dark-activebuttonbg-icon-color</code></td>
      <td>Defines the icon text color for active sidebar menu buttons when using the <code>.sidebar-dark</code> skin</td>
      <td><code>$sm-dark-activebuttonbg-button-color</code></td>
    </tr>
    <tr>
      <td><code>$sm-light-active-button-bg</code></td>
      <td>Defines the background color for active sidebar menu buttons when using the <code>.sidebar-light</code> skin</td>
      <td><code>$brand-primary</code></td>
    </tr>
    <tr>
      <td><code>$sm-light-activebuttonbg-button-color</code></td>
      <td>Defines the text color for active sidebar menu buttons when using the <code>.sidebar-light</code> skin</td>
      <td><code>#fff</code></td>
    </tr>
    <tr>
      <td><code>$sm-light-activebuttonbg-icon-color</code></td>
      <td>Defines the icon text color for active sidebar menu buttons when using the <code>.sidebar-light</code> skin</td>
      <td><code>$sm-light-activebuttonbg-button-color</code></td>
    </tr>
  </tbody>
</table>

### .sm-active-button-bg and .sm-icons-block

<table>
  <thead>
    <tr>
      <th width="270">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$sm-dark-active-iconsblock-activebuttonbg-icon-bg</code></td>
      <td>Defines the icon background color for active sidebar menu buttons when using the <code>.sidebar-dark</code> skin</td>
      <td><code>$sm-dark-active-iconsblock-icon-bg</code></td>
    </tr>
    <tr>
      <td><code>$sm-light-active-iconsblock-activebuttonbg-icon-bg</code></td>
      <td>Defines the icon background color for active sidebar menu buttons when using the <code>.sidebar-light</code> skin</td>
      <td><code>$sm-light-active-iconsblock-icon-bg</code></td>
    </tr>
  </tbody>
</table>

### Dependencies

The following example is using [Material icons](https://design.google.com/icons/), so make sure to load the icons library into the `<head>` section of your page before using the example.

```html
<!-- Material Design Icons -->
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
```

### Usage

```html
<!-- Sidebar menu style modifiers -->
<ul class="sidebar-menu sm-active-button-bg sm-bordered sm-icons-right">
    <li class="sidebar-menu-item">
        <a class="sidebar-menu-button" href="#">
            <i class="sidebar-menu-icon material-icons">home</i> 
            Menu button
        </a>
    </li>
    <li class="sidebar-menu-item active">
        <a class="sidebar-menu-button" href="#">
            <i class="sidebar-menu-icon material-icons">menu</i> 
            Another button
        </a>
    </li>
</ul>
```

## Sidebar submenu

<table>
  <thead>
    <tr>
      <th width="230">CSS Class</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>.sidebar-submenu</code></td>
      <td>The sidebar submenu wrapper <code>ul</code> placed after <code>a.sidebar-menu-button</code> elements</td>
    </tr>
    <tr>
      <td><code>.sidebar-menu-item</code></td>
      <td>The sidebar submenu item <code>li</code></td>
    </tr>
    <tr>
      <td><code>.sidebar-menu-button</code></td>
      <td>The sidebar submenu button <code>a</code></td>
    </tr>
    <tr>
      <td><code>.open</code></td>
      <td>Makes the sidebar submenu visible when applied to a <code>li.sidebar-menu-item</code> parent</td>
    </tr>
  </tbody>
</table>

### Usage

To create a basic sidebar submenu:

- add `ul` wrapper using the `.sidebar-submenu` class, after a `.sidebar-menu-button` element
- add `li` submenu items using the `.sidebar-menu-item` class
- add `a` submenu buttons using the `.sidebar-menu-button` class
- add the `.open` class to the parent `.sidebar-menu-item` element to display a submenu

```html
<!-- Sidebar menu -->
<ul class="sidebar-menu">

  <!-- Open menu item -->
  <li class="sidebar-menu-item open">
    <a href="#" class="sidebar-menu-button">Dashboard</a>

    <!-- Submenu -->
    <ul class="sidebar-submenu">
      <li class="sidebar-menu-item active">
        <a href="#" class="sidebar-menu-button">Active menu item</a>
      </li>
      <li class="sidebar-menu-item">
        <a href="#" class="sidebar-menu-button">Regular menu item</a>
      </li>
    </ul>
  </li>

  <!-- Menu item -->
  <li class="sidebar-menu-item">
    <a href="#" class="sidebar-menu-button">Reports</a>

    <!-- Submenu -->
    <ul class="sidebar-submenu">
      <li class="sidebar-menu-item">
        <a href="#" class="sidebar-menu-button">Another menu item</a>
      </li>
      <li class="sidebar-menu-item">
        <a href="#" class="sidebar-menu-button">Regular menu item</a>
      </li>
    </ul>
  </li>

</ul>
```

You can customize sidebar submenus with the following Sass variables.

### .sidebar-menu-button

<table>
  <thead>
    <tr>
      <th width="250">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$ssm-button-height</code></td>
      <td>Defines the height in <code>px</code> for sidebar submenu buttons</td>
      <td><code>$sm-button-height</code></td>
    </tr>
    <tr>
      <td><code>$ssm-button-font-size</code></td>
      <td>Defines the base font size in <code>px</code> for sidebar submenu buttons</td>
      <td><code>$sm-button-font-size</code></td>
    </tr>
  </tbody>
</table>

### .sidebar-menu-icon

<table>
  <thead>
    <tr>
      <th width="250">Sass variable</th>
      <th>Description</th>
      <th width="200">Default value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>$ssm-icon-font-size</code></td>
      <td>Defines the base font size in <code>px</code> for sidebar submenu icons</td>
      <td><code>$sm-icon-font-size</code></td>
    </tr>
  </tbody>
</table>