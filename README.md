# Markdown Editor

```js
window.addEventListener('DOMContentLoaded', (event) => {
    fs.readFile('/note', 'utf8', function(err, data) {
        if (err)
            editor.setText("...");
        if (data)
            editor.setContents(JSON.parse(data));
    })
});
```
