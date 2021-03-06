TOPICS: CSS length unit
        px
        em
        rem
        %
        cm
        mm
        ch
        ex
        vw
        vh
        vmin
        vmax
        in
        pt
        pc

# CSS Length Unit

There are two types of CSS length units: **relative length** and **absolute length**.
**Absolute Length Unit** is a fixed value that reflects a real physical size. The absolute length
unit depends on the output medium and is independent of the environment (display, resolution,
operating system, etc.). **Relative Length Unit** specifies the properties of one length relative
to another. For different devices, the relative length is more suitable.

There must be no spaces between **number** and **unit**. If the length value is **`0`**,
**can omit the unit**.

## Absolute Length Unit

| Unit | Description |
| :--- | :--- |
| **`cm`** | **cm** |
| **`mm`** | **mm** |
| **`in`** | **Inches** |
| **`pt`** | **Points** |
| **`pc`** | **Picas** It is equivalent to the size of China's new No. 4 typeface. |
| **`px`** | **Pixel** is determined by the resolution of the screen display (so different devices may display the same pixel value with different results) |

### CSS absolute length unit conversion

1in = 2.54cm = 25.4mm = 72pt = 6pc = 96px

## Relative length unit

| Unit | Description |
| :--- | :--- |
| **`ch`** | (Infrequently used) Relative to **width** of number **`0`** (`ZERO`, `U+0030`) glyph in the element’s font. |
| **`ex`** | (Infrequently used) Relative to character **`x`** **height** of the element's font. |
| **`%`** | **Percentage** is generally used to inherit the width and height of the parent element, or to adapt based on the browser's width and height. |
| **`em`** | Relative to the font size of the *parent element*. The default value of browsers' font size is *`16px`*, then `1em == 16px` |
| **`rem`** | Relative to the font size of the [*`<html>`*](/en/webfrontend/<html>) root element. If the root element is not set, relative to the browser's default font size, the default browser font size is *`16px`*, then `1rem == 16px`.|
| **`vw`** | Relative to **1%** of **viewport’s width**. |
| **`vh`** | Relative to **1%** of **viewport's height**. |
| **`vmin`** | The smaller one between of *`vw`* and *`vh`*. |
| **`vmax`** | The larger one between of *`vw`* and *`vh`*. |

### Examples of relative length units

```html
<div>
  <p>This is a paragraph A</p>
  <p class="b">This is a paragraph B</p>
  <p class="c">xx<span>x</span></p>
  <p class="d">00<span>0</span></p>
  <p class="e">This is a paragraph E</p>
  <p class="f">This is a paragraph F</p>
</div>
```

```css
/* The default browser font size is 16px */
html { font-size: 16px; }

/* Define font size using absolute and relative length units */
p.b { font-size: 0.5cm; }  /* Use absolute length unit cm cm */
p.c > span { font-size: 2ex; }  /* Height equivalent to 2 letters x */
p.d > span { font-size: 2ch; }  /* Equivalent to a width of 2 numbers 0 */

/* The difference between rem and em */
/* Regardless of the parent element's defined font, `rem` is defined relative to the <html> root element */
div { font-size: 10px; }  /* Parent element font size */
p.e { font-size: 1.5em; }  /* Equivalent to 1.5 parent element font size, ie 1.5 x 10px = 15px (1em = 10px) */
p.f { font-size: 1.5rem; }  /* Equivalent to 1.5 <html> element font sizes, ie 1.5 x 16px = 24px (1rem = 16px) */

/* % Example of percent length units */
div {  /* The parent element uses absolute length units */
  height: 150px;
  width: 150px;
  background: black;
}
p {  /* Child elements use relative length units, relative to the parent element */
  height: 80%;
  width: 80%;
  background: red;
}
```

### Example window unit

```html
<h1>Hello</h1>
<h2>Hello</h2>
<h3>Hello</h3>
<h4>Hello</h4>
```

```css
/* Example of vw and vh length units */
/* For example: Browser height is 950px, width is 1920px, 1vh = 950px / 100 = 9.5px, 1vw = 1920px / 100 = 19.2px. */
h1 { font-size: 20vw; } /* 20vw equals 20/100 window width */
h2 { font-size: 20vh; } /* 20vh equals 20/100 window height */

/* Examples of vmin and vmax length units */
/*
For example: browser width is 1100px, height is 700px, 1vmin = 700px / 100 = 7px, 1vmax = 1100/100 = 11px.
    Browser width is 800px, height is 1080px, 1vmin = 800px / 100 = 8px, 1vmax = 1080px / 100 = 10.8px
*/
h3 { font-size: 15vmin; } /* Try reducing or enlarging the browser (height and width) to see how h3's font size changes. */
h4 { font-size: 15vmax; } /* Try reducing or enlarging your browser (height and width) to see how h4's font size changes. */
```

## More

- [Pixel on Wikipedia](https://en.wikipedia.org/wiki/Pixel)

## Browser compatibility

The numbers in the table below indicate the minimum browser version that supports this length unit.

| ULength unit | Google | Firefox | Safari |
| :--- | :--- | :--- | :--- |
| `em`, `ex`, %, `px`, `cm`, `mm`, `in`, `pt`, `pc` | 1.0 | 1.0 | 1.0 |
| `ch`| 27.0| 1.0 | 7.0 |
| `rem` | 4.0 | 3.6 | 4.1 |
| `vh`, `vw` | 20.0 | 19.0 | 6.0 |
| `vmin` | 20.0 | 19.0 | 6.0 |
| `vmax` | 26.0 | 19.0 | Not support |
