[![Build Status](https://travis-ci.org/advanced-rest-client/polymer-styles-analyzer.svg?branch=stage)](https://travis-ci.org/advanced-rest-client/polymer-styles-analyzer)  

# polymer-styles-analyzer

CSS variables and mixin discovery element for Polymer powered web components.

It looks for a custom elements in the DOM and uses Polymer APIs to read styles
declaration for the element and extracts CSS variables and mixins from it.
The element looks inside custom element to search for additional imports than
the one defined in main document.

### Example

```html
<polymer-styles-analyzer id="analyzer"></polymer-styles-analyzer>
<script>
document.getElementById('analyzer').analyze()
.then(result => console.log(result));
</script>
```

## Parsing results

A result of parsing the data is an array of styles definitions:

```javascript
{
  "name": "custom-element-name",
  "mixins": ["--mixin-name"],
  "variables": [{
    "name": "--variable-name",
    "defaultValue": "#e0e0e0"
  }],
  "hasVariables": true, // true if variables length > 0
  "hasMixins": true, // true if mixins length > 0
  "hasStyles": true // true if hasVariables or hasMixins is true
}
```

