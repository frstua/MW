## Best Practices We Follow

1. Keep your CSS selectors short.
2. Your CSS classes should describe the content, not the look.
3. Select using classes not id's (id might be a dynamical, might be a issues with priority).
4. Nested selectors looks like:
    ```css
    .selector {
      width: 100%;            // <--- selector's rules immediately after the selector
      height 100%;
                              // <--- empty line before the nested selector
      .nested-selector {
          width: 50%;
          heihgt: 50%;
      }
    }
    ```
5. Presentation-Specific and Layout-Specific styles differentiation.
Presentation-Specific styles are those that only alter the visual design of the element, but don't change its dimensions or position in a meaningful way. Example:
    ```css
    .foo {
      position: fixed;          // <--- better start with position then display
      top: 8px;
      right: 8px;
      display: inline-block;
      width: 100%;
      height: 100%;
      padding: 2px;
      z-index: 100;

      font-weight: bold;
      background-color: #333;
      color: #f00;
    }
    ```
6. If the value of a property is 0, do not specify units. Use short declaration of parameters.
7. Use a single space after the colon, always end property declarations with a semicolon, put spaces after `:` in property declarations, put spaces before `{` in rule declarations.