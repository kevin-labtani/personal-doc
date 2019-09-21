# HTML

## Emmet

- by default class expansion will create a div but there's some contextual awareness
- `>` for direct descendant
- `+` for sibling
- `^` for climbing up a level
- `()` for grouping
- `*` to get a multiple of an element
- `{text $}` braces to add text to the body of an element, `$` to iterate over numbers  
  `ul.col>li.col-item*5{Item $}` =>
  ```html
  <ul class="col">
    <li class="col-item">Item 1</li>
    <li class="col-item">Item 2</li>
    <li class="col-item">Item 3</li>
    <li class="col-item">Item 4</li>
    <li class="col-item">Item 5</li>
  </ul>
  ```
- Emmet is also useful for css
