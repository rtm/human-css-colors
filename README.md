HUMAN CSS COLORS
======

`human-css-colors` provides a set of micro-classes to easily specify and control CSS color styling.
It is a sister repo to `human-css-numbers` and `human-css-classes`
(and used by the latter).

It exposes a single custom property named `--color` which you may use as you see fit.

Summary
-------

```
<span class="dark red">
```

Colors are specified using the flexible HSL model.
This allows you to easily think of colors in terms of their hue, lightness, and saturation.
The standard hues are red, orange, yellow, lime, green, aquamarine, cyan, azure, blue, purple, magenta, and pink.
The hues can then be adjusted with additional micro-classes for saturation,
including `pure`, `x-bright`, `bright`, `dull`, `x-dull`, and `gray`,
and with additional micro-classes for lightness,
including `white`, `x-light`, `light`, `dark`, `x-dark`, and `black`.

In addition, any HTML color, such as `steelblue`, can be used as a class to specify the desired color.
To distinguish HTML colors from hues of the same name, add the class `color`, as in `color red`.

Global HSL values
-----------------

You may set "global" HSL values, which apply to all child elements,
using the `hue`, `lightness`, `saturation`, and `alpha` micro-classes.
For example, in conjunction with a micro-class library such as `human-css-classes`,
the following will yield a red bordered div, with red text:

```
<div class="hue red">
  <div class="thick border">
    <div class="lighter text">
```

The global HSL values may be modified for a particular element by the classes
`purer` or `brighter`, `duller` or `grayer`, `whiter` or `lighter`, and `darker` or `blacker`,
or corresponding versions prefixed with `x-`.

usage
------------

    npm install --save-dev rtm@human-css-colors

Then, in some file that postCSS will process:

    @import "@rtm/human-css-colors";

### Caveat

This repo uses CSS custom properties, also known as CSS variables, in its implementation.
This excludes IE11 from consideration.
Note that development of custom properties is underway for Edge.