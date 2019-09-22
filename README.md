```js
let save;
hotkeys('ctrl+s', function(event) {
    event.preventDefault();
    save();
});
window.addEventListener('DOMContentLoaded', (event) => {
    let notepad = document.getElementById("notepad");
    let indicator = document.getElementById("status");
    let oldvalue;

    let setIndicatorStatus = function(status) {
        if (status == "saved") {
            indicator.innerHTML = "<strong>Note Saved!</strong>";
            indicator.classList.replace("unsaved", "saved");
        }
        if (status == "unsaved") {
            indicator.innerHTML = "<strong>Note Unsaved</strong>. Press <i>Ctrl + S</i> to save.";
            indicator.classList.replace("saved", "unsaved");
        }
    };
    
    save = function() {
        fs.writeFile('/note', notepad.innerHTML, (err) => {
            if (err) return;
            setIndicatorStatus("saved");
            oldvalue = notepad.innerHTML;
        });
    };

    notepad.addEventListener("input", event => {
        if (oldvalue != notepad.innerHTML) {
            setIndicatorStatus("unsaved");
        } else {
            setIndicatorStatus("saved");
        }
    });
    
    fs.readFile('/note', 'utf8', function (err, data) {
        if (err) {
            let str = "Welcome to my notepad!";
            notepad.innerHTML = str;
            oldvalue = str;
        }
        else if (data) {
            notepad.innerHTML = data;
            oldvalue = data;
        }
    });
});
```
