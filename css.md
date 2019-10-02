# CSS

## Tips & tricks

- `visibility: hidden` vs `display: none`: it keeps the element in the DOM and space is allocated for it on the page

- to override another style, we can use the `!important` flag

- `margin-top: -30px;` to move up the element 30px

- `background #333 url('https://source.unsplash.com/random') no-repeat center center/cover;` image (with fallback color) that won't repeat be centered and cover our content

- The `overflow` property specifies what should happen if content overflows an element's box.

  - `visible` The overflow is not clipped. It renders outside the element's box. This is default
  - `hidden` The overflow is clipped, and the rest of the content will be invisible
  - `scroll` The overflow is clipped, but a scroll-bar is added to see the rest of the content
  - `auto` If overflow is clipped, a scroll-bar should be added to see the rest of the content

- to target the input field on the `input` or `textarea` field of a form when a user is focused on it use the `:focus` selector

  ```css
  input:focus {
    border-color: yellow;
  }
  ```

- Add a smooth scrolling effect to the document with `html {scroll-behavior: smooth;}`

## Fonts

```css
p {
  font-family: "Times New Roman", Times, serif;
  font-style: normal; /* italic, oblique */
  font-size: 16px; /*  16px = 1em = default, em size unit is recommended */
  font-variant: small-caps;
  font-weight: bold; /* normal */
}
```

## Background

```css
body {
  background-color: lightblue;
  background-image: url("paper.gif");
  background-size: 300px 100px; /* auto, cover, contain */
  background-repeat: repeat-x; /* repeat-y (repeat vertically), no-repeat */
  background-attachment: fixed; /* scroll, specifies whether the background image should scroll or be fixed */
  background-position: right top;
}
```

## Border

```css
p {
  border-style: none; /* dotted, dashed, solid, ... & can pick a side, eg: border-left-style:*/
  border-width: 5px;
  border-color: red;
  border-radius: 5px; /* for rounder borders */
}
```

## Box Model

![Box Model](./assets/box-model.png)

```css
div {
  padding-top: 50px;
  padding-right: 30px;
  padding-bottom: 50px;
  padding-left: 80px;
}

p {
  margin-top: 100px;
  margin-bottom: 100px;
  margin-right: 150px;
  margin-left: 80px;
}
```

- `margin: 25px 50px 75px 100px;`

  - top margin is 25px
  - right margin is 50px
  - bottom margin is 75px
  - left margin is 100px

- `margin: 25px 50px;`
  - top and bottom margins are 25px
  - right and left margins are 50px

## Align

- Center Align Elements

  ```css
  .center {
    margin: auto;
    width: 50%; /* or set up a fixed width in px */
  }
  ```

  - Center Align Text

  ```css
  .center {
    text-align: center; /* right, left, justify */
  }
  ```

  - Center Align Image

  ```css
  img {
    display: block;
    margin-left: auto;
    margin-right: auto;
  }
  ```

- Left and Right Align - Using position

  ```css
  .right {
    position: absolute;
    right: 0px;
    width: 300px;
  }
  ```

- Left and Right Align - Using float

  ```css
  .right {
    float: right;
    width: 300px;
  }
  ```

- Center Vertically - Using padding

  ```css
  .center {
    padding: 70px 0;
    border: 3px solid green;
  }
  ```

  To center both vertically and horizontally, use `padding` and `text-align: center`:

- Center Vertically - Using line-height

  ```css
  .center {
    line-height: 200px;
    height: 200px;
    text-align: center;
  }

  /* If the text has multiple lines, add the following: */
  .center p {
    line-height: 1.5;
    display: inline-block;
    vertical-align: middle;
  }
  ```

## Link

```css
/* remove underline */
a {
  text-decoration: none;
}

/* unvisited link */
a:link {
  color: red;
  background-color: aliceblue; /* can add background color to link */
}

/* visited link */
a:visited {
  color: green;
}

/* mouse over link */
a:hover {
  color: hotpink;
}

/* selected link */
a:active {
  color: blue;
}

/* link button */
a:link,
a:visited {
  background-color: #f44336;
  border-radius: 5px;
  color: white;
  padding: 14px 25px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
}

a:hover,
a:active {
  background-color: red;
}
/* end link button */
```

## Display Property

The display property specifies the display behavior (the type of rendering box) of an element.

- change block level elements to inline

  ```css
  li {
    display: inline;
  }
  ```

- change inline level elements to block

  eg: want to add margin to an inline element

  ```css
  img {
    display: block;
    margin: auto;
  }
  ```

- `inline-block` Value

  Compared to `display: inline`, the major difference is that `display: inline-block` allows to set a width and height on the element.

  Also, with `display: inline-block`, the top and bottom margins/paddings are respected, but with `display: inline` they are not.

  Compared to `display: block`, the major difference is that `display: inline-block` does not add a line-break after the element, so the element can sit next to other elements.

## Position

- Absolute

  The element is positioned relative to its first positioned (not static) ancestor element

  ```css
  div {
    position: absolute;
    left: 10px;
    top: 100px;
  }
  ```

- Fixed

  The element is positioned relative to the browser window

- Relative

  The element is positioned relative to its normal position, so "left:20px" adds 20 pixels to the element's LEFT position

- Sticky

  The element is positioned based on the user's scroll position

  ```css
  .sticky {
    position: sticky;
    top: 0;
  }
  ```

## Flexbox

- [Guide to flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox froggy game](https://flexboxfroggy.com)

### Properties for the Parent (flex container)

- display

  defines a flex container; inline or block depending on the given value

  ```css
  .container {
    display: flex; /* or inline-flex */
  }
  ```

- flex-direction

  establishes the main-axis

  ```css
  .container {
    flex-direction: row | row-reverse | column | column-reverse;
  }
  ```

- flex-wrap

  By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.

  ```css
  .container {
    flex-wrap: nowrap | wrap | wrap-reverse;
  }
  /* give some width to the items to test*/
  ```

- justify-content

  This defines the alignment along the main axis. It helps distribute extra free space leftover when either all the flex items on a line are inflexible, or are flexible but have reached their maximum size. It also exerts some control over the alignment of items when they overflow the line.

  ```css
  .container {
    justify-content: flex-start; /* flex-end | center | space-between | space-around | space-evenly | start | end | left | right ... + safe | unsafe */
  }
  ```

  Using `safe` ensures that however you do this type of positioning, you can't push an element such that it renders off-screen

- align-items

  This defines the default behavior for how flex items are laid out along the cross axis on the current line. Think of it as the `justify-content` version for the cross axis

  ```css
  .container {
    align-items: stretch; /* flex-start | flex-end | center | baseline | first baseline | last baseline | start | end | self-start | self-end + ... safe | unsafe */
  }
  ```

  don't forget to give a `height` to the container

- align-content

  This aligns a flex container's lines within when there is extra space in the cross-axis, similar to how `justify-content` aligns individual items within the main-axis.

  ```css
  .container {
    align-content: stretch; /* flex-start | flex-end | center | space-between | space-around | space-evenly | start | end | baseline | first baseline | last baseline + ... safe | unsafe */
  }
  ```

### Properties for the Children (flex items)

- order

  By default, flex items are laid out in the source order.

  ```css
  .item {
    order: <integer>; /* default is 0, can use negative values */
  }
  ```

- align-self

  This allows the default alignment (or the one specified by `align-items`) to be overridden for individual flex items.

  ```css
  .item {
    align-self: auto | flex-start | flex-end | center | baseline | stretch;
  }
  ```

  Note that `float`, `clear` and `vertical-align` have no effect on a flex item.

- flex

  ```css
  .item {
    flex: none | [ < "flex-grow" > < "flex-shrink" >? || < "flex-basis" > ];
  }
  ```

  This is the shorthand for `flex-grow`, `flex-shrink` and `flex-basis` combined. The second and third parameters (`flex-shrink` and `flex-basis`) are optional. Default is 0 1 auto.

- flex-grow

  This defines the ability for a flex item to grow if necessary. It accepts a unitless value that serves as a proportion. It dictates what amount of the available space inside the flex container the item should take up.

  If all items have flex-grow set to 1, the remaining space in the container will be distributed equally to all children. If one of the children has a value of 2, the remaining space would take up twice as much space as the others (or it will try to, at least).

  ```css
  .item {
    flex-grow: <number>; /* default 0 */
  }
  ```

  Negative numbers are invalid.

- flex-shrink

  This defines the ability for a flex item to shrink if necessary.

  ```css
  .item {
    flex-shrink: <number>; /* default 1 */
  }
  ```

- flex-basis

  This defines the default size of an element before the remaining space is distributed. It can be a length (e.g. 20%, 5rem, etc.) or a keyword. The `auto` keyword means "look at my `width` or `height` property" (which was temporarily done by the `main-size` keyword until deprecated). The content keyword means "size it based on the item's content" - this keyword isn't well supported yet, so it's hard to test and harder to know what its brethren `max-content`, `min-content`, and `fit-content` do.

  ```css
  .item {
    flex-basis: <length> | auto; /* default auto */
  }
  ```

  If set to `0`, the extra space around content isn't factored in. If set to `auto`, the extra space is distributed based on its `flex-grow` value.

### Tips & Tricks

- Perfect Centering

  ```css
  .flex-container {
    display: flex;
    height: 300px;
    justify-content: center;
    align-items: center;
  }
  ```

- `flex-wrap` and `flex-basis` work together in that flex-basis will only work on the item

## Responsive Design

- Set the viewport tag (default with Emmet)
- Use fluid width (max-width instead of width)
- Media queries
- Rem units
- Mobile first design, do all base styling targetting mobile and use media queries for big screens

Use device toolbar in chrome dev tools to test

### Media Queries

[W3Schools guide](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)

If the browser window is 600px or smaller, the background color will be lightblue:

```css
body {
  background-color: lightgreen;
}

@media only screen and (max-width: 600px) {
  body {
    background-color: lightblue;
  }
}
```

Hide an element when the browser's width is 600px wide or less:

```css
@media screen and (max-width: 600px) {
  div.example {
    display: none;
  }
}
```

Use `max-height` for when the user phone or tablet is in landscape

We can made a separate style sheet and import it after our main style sheet: `<link rel="stylesheet" media="screen and (max-width: 600px" href="mobile.css">`

### `em` & `rem` units

- `em` unit is relative to the font size of the parent element

```css

body {
  font-size: 20px;
}
p {
  font-size; 1.5em; /* 30px */
  padding 1em; /* the padding will be 30px as we
  defined a font-size and it'll use that as a reference */
  /* same issue with nested elements */
}

```

- `rem` unit is relative to the font size of the root html element.
  - Set a `font-size` value the font for `html{}` to change for the entire document.
  - A value of 62.5% will set the size of the root to 10px which makes it easier to calculate later, when necessary.
  - `rem` also good to use for accessibility features, as the user can set a large font in the browser and rem will scale.

### vh and vw units

- _viewport height_ and _viewport width_
- `50vh` will take a slice across of 50 out of the `100vh`
- Same thing with `vw`, but the slices go down

We want a header to take 100% of the screen, we can't use `height: 100%` because the `body` is just a wrapper around the content, it doensn't actually take all of the height of the page, so we use `vh`

```css
header {
  height: 100vh;
}
```

## Selectors

- [CSS dinner game](http://flukeout.github.io/)

- [CSS selectors reference](https://www.w3schools.com/cssref/css_selectors.asp)

| Selector            | Example                                                    | Description                                                                       |
| ------------------- | ---------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `.class1 .class2`   | `<div class="name1"> <div class="name2">... </div> </div>` | Selects all elements with `name2` that is a descendant of an element with `name1` |
| `element>element`   | `div > p`                                                  | Selects all `<p>` elements where the parent is a `<div>` element                  |
| `element+element`   | `div + p`                                                  | Selects all `<p>` elements that are placed immediately after`<div>` elements      |
| `[attribute]`       | `a[target]`                                                | Selects all `a` elements with a `target` attribute                                |
| `[attribute=value]` | `[target=_blank]`                                          | Selects all elements with `target="_blank"`                                       |
| `:first-child`      | `p:first-child`                                            | Selects every `<p>` element that is the first child of its parent                 |
| `:nth-child(n)`     | `p:nth-child(2)`                                           | Selects every `<p>` element that is the second child of its parent                |
| `:nth-of-type(n)`   | `p:nth-of-type(2)`                                         | Selects every `<p>` element that is the second `<p>` element of its parent        |
| `:nth-child(3n+7)`  | `p:nth-child(3n+7)`                                        | Selects every 3rd `<p>` element that is the child of its parent, after the 7th    |
| `:nth-child(odd)`   | `p:nth-child(odd)`                                         | Selects every odd `<p>` element that is the child of its parent                   |
| `::before`          | `p::before`                                                | Insert something before the content of each `<p>` element                         |
| `::after`           | `p::after`                                                 | Insert something after the content of each `<p>` element                          |

use of `::after` (The `content` property is used with the `::before` and `::after` pseudo-elements, to insert generated content.)

```html
<style>
  .is-required::after {
    content: "*";
    color: red;
    padding-left: 2px;
  }
</style>
...
<body>
  <label class="is-required" for="name">Name</label>
  <input type="text" />
</body>
```

use of `::before` to insert an image behind a header and opacify it (to better see the header text) without opacifying the text of the header itself

```css
header::before {
  content: "";
  background: url("https://source.unsplash.com/random/1600x900/?nature,water")
    no-repeat center center/cover;
  opacity: 0.4;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}
```

## Box Shadow

```css
box-shadow: none|h-offset v-offset blur spread color |inset|initial|inherit;
```

`inset` changes the shadow from an outer shadow (`outset`) to an inner shadow

## Text Shadow

```css
text-shadow: h-shadow v-shadow blur-radius color|none|initial|inherit;
```

## CSS Variables

```css
:root {
  --first-color: #488cff;
  --second-color: #ffff8c;
}

#firstParagraph {
  background-color: var(--first-color);
  color: var(--second-color);
}
```

Notice the `:root` pseudo-class selector — we can declare our variables globally using it. We can also declare them using other selectors, and they will then be scoped in those.

## Keyframe Animation

```html
<head>
  <style>
    div {
      width: 100px;
      height: 100px;
      background-color: red;
      animation-name: example;
      animation-duration: 4s;
    }
    @keyframes example {
      0% {
        background-color: red;
      }
      25% {
        background-color: yellow;
      }
      50% {
        background-color: blue;
      }
      100% {
        background-color: green;
      }
    }
  </style>
</head>
<body>
  <div></div>
</body>
```

- The `animation-delay` property specifies a delay for the start of an animation.
- The `animation-iteration-count` property specifies the number of times an animation should run.
- The `animation-direction` property specifies whether an animation should be played forwards, backwards or in alternate cycles.
- The `animation-timing-function` property specifies the speed curve of the animation.
- The `animation-fill-mode` property specifies a style for the target element when the animation is not playing (before it starts, after it ends, or both).
  - `forwards` - The element will retain the style values that is set by the last keyframe (depends on animation-direction and animation-iteration-count)
  - `backwards` - The element will get the style values that is set by the first keyframe (depends on animation-direction), and retain this during the animation-delay period

## CSS Transitions

To create a transition effect, you must specify two things:

- the CSS property you want to add an effect to
- the duration of the effect

```html
<head>
  <style>
    div {
      width: 100px;
      height: 100px;
      background: red;
      transition: width 2s, height 4s;
    }

    div:hover {
      width: 300px;
      height: 300px;
    }
  </style>
</head>
<body>
  <div></div>
</body>
```

- The `transition-timing-function` property specifies the speed curve of the transition effect.
- The `transition-delay` property specifies a delay (in seconds) for the transition effect.

## CSS Transform

[W3School guide](https://www.w3schools.com/cssref/css3_pr_transform.asp)

```css
div.a {
  transform: rotate(20deg);
}

div.b {
  transform: skewY(20deg);
}

div.c {
  transform: scaleY(1.5);
}
```

Transition & Transform:

```html
<head>
  <style>
    div {
      width: 100px;
      height: 100px;
      background: red;
      transition: width 2s, height 2s, transform 2s;
    }

    div:hover {
      width: 300px;
      height: 300px;
      transform: rotate(180deg);
    }
  </style>
</head>
<body>
  <div></div>
</body>
```

`Transition: all`

```css
.element {
  width: 400px;
  height: 400px;
  transition: all 1s ease-in;
  /* equivalent to  transition: width 1s ease-in, height 1s ease-in; */
}

.element:hover {
  width: 500px;
  height: 500px;
}
```

## Grid

- [Guide to flexbox](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid garden game](http://cssgridgarden.com/)

### Properties for the Parent (Grid Container)

- display

  defines the element as a grid container

  ```css
  .container {
    display: grid | inline-grid;
  }
  ```

- grid-template-columns  
  grid-template-rows

  defines the columns and rows of the grid with a space-separated list of values. The values represent the track size, and the space between them represents the grid line.

  ```css
  .container {
    grid-template-columns: <track-size> ... | <line-name> <track-size> ...;
    grid-template-rows: <track-size> ... | <line-name> <track-size> ...;
  }

  /* example */
  .container {
    grid-template-columns: 40px 50px auto 50px 40px;
    grid-template-rows: 25% 100px auto;
  }

  .container {
    grid-template-columns: [first] 40px [line2] 50px [line3] auto [col4-start] 50px [five] 40px [end];
    grid-template-rows: [row1-start] 25% [row1-end] 100px [third-line] auto [last-line];
  }

  .container {
    grid-template-columns: repeat(3, 20px [col-start]);
  }

  .container {
    grid-template-columns: 1fr 2fr 1fr;
  }
  ```

  auto-sizing with `auto-fit` and `minmax`

  ```css
  .container {
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  }
  ```

  These keywords tell the browser to handle the column sizing and element wrapping for us, so that the elements will wrap into rows when the width is not large enough to fit them in without any overflow. The fraction unit we used also ensures that, in case the width allows for a fraction of a column to fit but not a full column, that space will instead be distributed over the column or columns that already fit, making sure we aren't left with any empty space at the end of the row

- grid-gap

  setting the width of the gutters between the columns/rows

  ```css
  .container {
    grid-gap: <grid-row-gap> <grid-column-gap>;
  }
  ```

- grid-template-areas

  Defines a grid template by referencing the names of the grid areas which are specified with the `grid-area` property. Repeating the name of a grid area causes the content to span those cells. A period signifies an empty cell.

  ```css
  .container {
    grid-template-areas:
      "<grid-area-name> | . | none | ..."
      "...";
  }

  /* example */
  .item-a {
    grid-area: header;
  }
  .item-b {
    grid-area: main;
  }
  .item-c {
    grid-area: sidebar;
  }
  .item-d {
    grid-area: footer;
  }

  .container {
    display: grid;
    grid-template-columns: 50px 50px 50px 50px;
    grid-template-rows: auto;
    grid-template-areas:
      "header header header header"
      "main main . sidebar"
      "footer footer footer footer";
  }
  ```

### Properties for the Children (Grid Items)

- grid-column-start  
  grid-column-end  
  grid-row-start  
  grid-row-end

  determines a grid item's location within the grid by referring to specific grid lines. `grid-column-start`/`grid-row-start` is the line where the item begins, and `grid-column-end`/`grid-row-end` is the line where the item ends.

  we can make an item span multiple rows & columns

  ```css
  .item {
    grid-column-start: <number> | <name> | span <number> | span <name> | auto;
    grid-column-end: <number> | <name> | span <number> | span <name> | auto;
    grid-row-start: <number> | <name> | span <number> | span <name> | auto;
    grid-row-end: <number> | <name> | span <number> | span <name> | auto;
  }
  /* example (count the lines for the numbers) */
  .item-a {
    grid-column-start: 2;
    grid-column-end: five;
    grid-row-start: row1-start;
    grid-row-end: 3;
  }

  .item-b {
    grid-column-start: 1;
    grid-column-end: span col4-start; /* from the beginning till col4-start */
    grid-row-start: 2;
    grid-row-end: span 2;
  }
  ```

- grid-column  
  grid-row

  Shorthand for grid-column-start + grid-column-end, and grid-row-start + grid-row-end, respectively.

  ```css
  .item-c {
    grid-column: 3 / span 2;
    grid-row: third-line / 4;
  }
  ```
