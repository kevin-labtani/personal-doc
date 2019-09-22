# CSS

## Selectors

- [CSS dinner game](http://flukeout.github.io/)
- [CSS selectors reference](https://www.w3schools.com/cssref/css_selectors.asp)

## Extra Tips

- `visibility: hidden` vs `display: none`: it keeps the element in the DOM and space is allocated for it on the page

- to override another style, we can use the `!important` flag

- `margin-top: -30px;` to move up the element 30px

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
