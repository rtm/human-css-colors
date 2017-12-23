HUMAN CSS COLORS
======

`human-css-colors` provides a set of micro-attributes to easily specify and control CSS color styling.
It is a sister repo to `human-css-numbers` and `human-css-classes`
(and used by the latter).

It exposes a single custom property on designated elements named `--color` which you may use as you see fit.

Summary
-------

```
<span dark red color>
```

Colors are specified using the flexible HSL model.
This allows you to easily think of colors in terms of their hue, lightness, and saturation.
The standard hues are red, orange, yellow, lime, green, aquamarine, cyan, azure, blue, purple, magenta, and pink.
The hues can then be adjusted with additional micro-classes for saturation,
including `pure`, `x-bright`, `bright`, `dull`, `x-dull`, and `gray`,
and with additional micro-classes for lightness,
including `white`, `x-light`, `light`, `dark`, `x-dark`, and `black`.

In addition, any HTML color, such as `steelblue`, can be used as an attribute to specify the desired color.
To distinguish HTML colors from hues of the same name, add the attribute `html`, as in `html red`.

Global HSL values
-----------------

The actual application of a color to a specific element is triggered by the presence of the `color` attribute.
Without that, you are setting the hue, saturation, lightness, or alpha value for child elements.
For example, in conjunction with a micro-class/attribute library  such as `human-css-classes`,
the following will yield a red bordered div, with lighter red text:

```
<div hue red>
  <div thick border color>
    <div lighter text color>
```

The global HSL values may be modified for a particular element by the attributes
`purer` or `brighter`, `duller` or `grayer`, `whiter` or `lighter`, and `darker` or `blacker`,
or corresponding versions prefixed with `x-`.

usage
------------

    npm install --save-dev rtm@human-css-colors
    yarn add rtm@human-css-colors

Then, in some file that a CSS processor will process:

    @import "@rtm/human-css-colors";

### Caveat

This repo uses CSS custom properties, also known as CSS variables, in its implementation.
This excludes IE11 from consideration.
