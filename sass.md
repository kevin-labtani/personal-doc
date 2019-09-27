# Sass

- Sass uses .scss or .sass extensions
- Sass files must be compiled into .css
- Install **Live Sass Compiler** extension for VScode and configure it
  ```json
  {
    "liveSassCompile.settings.formats": [
      {
        "format": "expanded",
        "extensionName": ".css",
        "savePath": "/assets/css"
      },
      {
        "extensionName": ".min.css",
        "format": "compressed",
        "savePath": "/dist/css"
      }
    ],
    "liveSassCompile.settings.excludeList": [
      "**/node_modules/**",
      ".vscode/**"
    ],
    "liveSassCompile.settings.generateMap": true,
    "liveSassCompile.settings.autoprefix": ["> 1%", "last 2 versions"]
  }
  ```
- `// this is a Sass silent comment.`

## Variables

```scss
$primary-color: steelblue;
$font-stack: Arial, Helvetica, sans-serif;

body {
  background: $primary-color;
  font-family: $font-stack;
  line-height: 1.5;
}
```

## Nesting

```scss
header {
  background: $dark-color;
  color: $light-color;
  padding: 1rem;

  h1 {
    text-align: center;
  }
}
```

You can extend a parent tag by using the `&` reserved symbol.

```scss
.section {
  padding: 3rem;

  h3 {
    font-size: 2rem;
  }

  &-a {
    // equivalent to .section-a
    background: $primary-color;
    color: white;
  }

  &-b {
    background: $secondary-color;
    color: white;
  }
}
```

```scss
a {
  color: #333;
  &:hover {
    color: coral;
  }
}
```

You can nest properties

```scss
.foo {
  font: {
    family: arial;
    weight: bold;
    size: 2em;
  }
}
```

## Partials & Imports

- `_variables.scss` is a partial, notice the `_`, it won't be compiled, then use `@import "variables";` in our .scss file

```scss
// in _variables.scss
$light-color: #f4f4f4;

// in style.css
@import "variables";

body {
  background: $light-color;
}
```

## Functions & Mixins

- A function returns something, compared with a mixin.

```scss
// in _functions.scss
@function set-text-color($color) {
  @if (lightness($color) > 50) {
    @return #000;
  } @else {
    @return #fff;
  }
}

// in style.scss
@import "variables";
@import "functions";

header {
  background: $dark-color;
  color: set-text-color($dark-color);
}
```

- Mixin

```scss
// in _functions.scss
@mixin transform($property) {
  transform: $property;
}

// in style.scss
.btn {
  &-light {
    @extend %btn-shared;
    background-color: $light-color;
    color: set-text-color($light-color);
    &:hover {
      @include transform(rotate(20deg));
    }
  }

  &-dark {
    @extend %btn-shared;
    background-color: $dark-color;
    color: set-text-color($dark-color);
    &:hover {
      @include transform(rotate(-20deg));
    }
  }
}
```

## Inheritance

```scss
%btn-shared {
  display: inline-block;
  padding: 0.7rem 2rem;
  border: none;
  cursor: pointer;
  text-decoration: none;
  margin-top: 1rem;
}

.btn {
  &-light {
    @extend %btn-shared;
    background-color: $light-color;
    color: $dark-color;
  }

  &-dark {
    @extend %btn-shared;
    background-color: $dark-color;
    color: #fff;
  }
}
```

## Operators & Calculations

```scss
html {
  font-size: (12 / 16) * 1em;
}
```

## Color Functions

```scss
.btn {
  &-light {
    @extend %btn-shared;
    background-color: $light-color;
    color: set-text-color($light-color);
    &:hover {
      @include transform(rotate(20deg));
      background-color: darken($light-color, 10%);
    }
  }

  &-dark {
    @extend %btn-shared;
    background-color: $dark-color;
    color: set-text-color($dark-color);
    &:hover {
      @include transform(rotate(-20deg));
      background-color: lighten($dark-color, 10%);
    }
  }
}
```
