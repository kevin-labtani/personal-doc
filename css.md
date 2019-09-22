# CSS

## Selectors

- [CSS dinner game](http://flukeout.github.io/)
- [CSS selectors reference](https://www.w3schools.com/cssref/css_selectors.asp)

## Flexbox

- [Guide to flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
- [Flexbox froggy game](https://flexboxfroggy.com)

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
