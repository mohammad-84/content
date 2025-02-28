---
title: Blob.type
slug: Web/API/Blob/type
tags:
  - API
  - Blob
  - File API
  - Property
  - Reference
browser-compat: api.Blob.type
---
{{APIRef("File API")}}

The **`type`** property of a {{domxref("Blob")}} object returns the {{Glossary("MIME type")}} of the file.

## Value

A {{domxref("DOMString")}} containing the file's MIME type, or an empty string if the
type could not be determined.

## Examples

This example asks the user to select a number of files, then checks each file to make
sure it's one of a given set of image file types.

### HTML

```html
<input type="file" id="input" multiple>
<output id="output">Choose image files...</output>
```

```css hidden
output {
  display: block;
  margin-top: 16px;
}
```

### JavaScript

```js
// our application only allows GIF, PNG, and JPEG images
const allowedFileTypes = ["image/png", "image/jpeg", "image/gif"];

const input = document.getElementById('input');
const output = document.getElementById('output');

input.addEventListener('change', (event) => {
  const files = event.target.files;

  if (files.length === 0) {
    output.innerText = 'Choose image files...';
    return;
  }

  if (Array.from(files).every((file) => allowedFileTypes.includes(file.type))) {
    output.innerText = 'All files clear!';
  } else {
    output.innerText = 'Please choose image files only.';
  }
});
```

### Result

{{EmbedLiveSample("Example")}}

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- {{domxref("Blob")}}
- [Using files
  from web applications](/en-US/docs/Web/API/File/Using_files_from_web_applications)
