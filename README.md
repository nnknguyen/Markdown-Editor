# Markdown Editor

```js
window.addEventListener('DOMContentLoaded', (event) => {
    fs.readFile('/note', 'utf8', function(err, data) {
        // editor is a Quill.js's instance for the div#text element
        if (err)
            editor.setText("...");
        if (data)
            editor.setContents(JSON.parse(data));
    })
});
```
