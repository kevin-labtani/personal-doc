# CSS

## Selectors

- [CSS dinner game](http://flukeout.github.io/)
- [CSS selectors reference](https://www.w3schools.com/cssref/css_selectors.asp)

## Tips & tricks

- `visibility: hidden` vs `display: none`: it keeps the element in the DOM and space is allocated for it on the page

- to override another style, we can use the `!important` flag

- `margin-top: -30px;` to move up the element 30px

- `background #333 url('https://source.unsplash.com/random') no-repeat center center/cover;` image (with fallback color) that won't repeat be centered and cover our content

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

- `flex-wrap` and `flex-basis` work together in that flx-basis wil only work on the item

## Responsive Design

- Set the viewport tag (default with Emmet)
- Use fluid width (max-width instead of width)
- Media queries
- Rem units
- Mobile first design, do all base styling targetting mobile and use media queries for big screens

Use device toolbar in chrome dev tools to test

### Media Queries

[W3Schools Tutorial](https://www.w3schools.com/css/css_rwd_mediaqueries.asp)

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
