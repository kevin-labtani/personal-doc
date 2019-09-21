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

## HTML

![semantic elements](/assets/img_sem_elements.gif)

- only 1 `<h1>` per page

- figure semantic tag

  ```html
  <figure>
    <img src="" alt="  " />
    <figcaption></figcaption>
  </figure>
  ```

- description meta tag

  ```html
  <head>
    <meta
      name="description"
      content="This is an example of a meta description. This will often show up in search results."
    />
  </head>
  ```

- robots meta tag to tell robots not to index

  ```html
  <head>
    <meta name="robots" content="NOINDEX, NOFOLLOW" />
  </head>
  ```

- An article is intended to be independently distributable or reusable.

- A section is a thematic grouping of content, typically with a heading.

- The `<aside>` element is intended for content that is not part of the flow of the text in which it appears, however still related in some way.

- The `<header>` element specifies a header for a document or section.  
  The `<header>` element should be used as a container for introductory content.  
  You can have several `<header>` elements in one document.

- The `<main>` tag specifies the main content of a document.  
  The content inside the `<main>` element should be unique to the document. It should not contain any content that is repeated across documents such as sidebars, navigation links, copyright information, site logos, and search forms.

- The `<details>` tag specifies additional details that the user can view or hide on demand.  
  The `<summary>` tag defines a visible heading for the `<details>` element.

  ```html
  <details>
    <summary>Copyright 1999-2014.</summary>
    <p>- by Refsnes Data. All Rights Reserved.</p>
    <p>
      All content and graphics on this web site are the property of the company
      Refsnes Data.
    </p>
  </details>
  ```

  <details>
    <summary>Copyright 1999-2014.</summary>
    <p> - by Refsnes Data. All Rights Reserved.</p>
    <p>All content and graphics on this web site are the property of the company Refsnes Data.</p>
  </details>

- Table

  ```html
  <table>
    <thead>
      <tr>
        <th>Lorem</th>
        <th>Lorem</th>
        <th>Lorem</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Ipsum</td>
        <td>Ipsum</td>
        <td>Ipsum</td>
      </tr>
      <tr>
        <td>Ipsum</td>
        <td>Ipsum</td>
        <td>Ipsum</td>
      </tr>
      <tr>
        <td>Ipsum</td>
        <td>Ipsum</td>
        <td>Ipsum</td>
      </tr>
    </tbody>
  </table>
  ```

  <table>
    <thead>
      <tr>
        <th>Lorem</th>
        <th>Lorem</th>
        <th>Lorem</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Ipsum</td>
        <td>Ipsum</td>
        <td>Ipsum</td>
      </tr>
      <tr>
        <td>Ipsum</td>
        <td>Ipsum</td>
        <td>Ipsum</td>
      </tr>
      <tr>
        <td>Ipsum</td>
        <td>Ipsum</td>
        <td>Ipsum</td>
      </tr>
    </tbody>
  </table>

- Form

  ```html
  <form action="/signup" method="post">
    <p>
      <label>Title</label><br />
      <label>
        <input type="radio" name="title" value="mr" />
        Mr
      </label>
      <label>
        <input type="radio" name="title" value="mrs" />
        Mrs
      </label>
      <label>
        <input type="radio" name="title" value="miss" />
        Miss
      </label>
    </p>
    <p>
      <label>First name</label><br />
      <input type="text" name="first_name" />
    </p>
    <p>
      <label>Last name</label><br />
      <input type="text" name="last_name" />
    </p>
    <p>
      <label>Email</label><br />
      <input type="email" name="email" required />
    </p>
    <p>
      <label>Phone number</label><br />
      <input type="tel" name="phone" placeholder="999-999-999" />
    </p>
    <p>
      <label>Password</label><br />
      <input type="password" name="password" />
    </p>
    <p>
      <label>Country</label><br />
      <select>
        <option>China</option>
        <option>India</option>
        <option>United States</option>
        <option>Indonesia</option>
        <option>Brazil</option>
      </select>
    </p>
    <p>
      <label>
        <input type="checkbox" value="terms" />
        I agree to the <a href="/terms">terms and conditions</a>
      </label>
    </p>
    <p>
      <button>Sign up</button>
      <button type="reset">Reset form</button>
    </p>
  </form>
  ```

  <form action="/signup" method="post">
    <p>
      <label>Title</label><br>
      <label>
        <input type="radio" name="title" value="mr">
        Mr
      </label>
      <label>
        <input type="radio" name="title" value="mrs">
        Mrs
      </label>
      <label>
        <input type="radio" name="title" value="miss">
        Miss
      </label>
    </p>
    <p>
      <label>First name</label><br>
      <input type="text" name="first_name">
    </p>
    <p>
      <label>Last name</label><br>
      <input type="text" name="last_name">
    </p>
    <p>
      <label>Email</label><br>
      <input type="email" name="email" required>
    </p>
    <p>
      <label>Phone number</label><br>
      <input type="tel" name="phone" placeholder="999-999-999">
    </p>
    <p>
      <label>Password</label><br>
      <input type="password" name="password">
    </p>
    <p>
      <label>Country</label><br>
      <select>
        <option>China</option>
        <option>India</option>
        <option>United States</option>
        <option>Indonesia</option>
        <option>Brazil</option>
      </select>
    </p>
    <p>
      <label>
        <input type="checkbox" value="terms">
        I agree to the <a href="/terms">terms and conditions</a>
      </label>
    </p>
    <p>
      <button>Sign up</button>
      <button type="reset">Reset form</button>
    </p>
  </form>


