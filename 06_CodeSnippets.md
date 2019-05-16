# Code Snippets

## Inaktivität des Users

Triggere etwas oder einen Event, wenn die Maus bzw. die Taste für eine bestimmte Zeit nicht bewegt werden:¨

```js
/* triggerSomething will be exectued after certain timeout (3000ms in this example) */
let inactivityTime = function () {
    let time;
    let timeout = 3000;

    window.onload = resetTimer;
    // DOM Events
    document.onmousemove = resetTimer;
    document.onkeypress = resetTimer;

    function triggerSomething() {
        console.log("Timeout")
    }

    function resetTimer() {
        clearTimeout(time);
        time = setTimeout(triggerSomething, timeout)
    }
};

// Funktion aufrufen
inactivityTime(); 

```

## Browserwindow öffnen

Mit Javaskript ein neues Fenster öffnen:

```js
// öffnet ein neuen browser window mit 100x100pixel und google.com
window.open ("http://www.duckduckgo.com", "WindowTitle","location=1,status=1,scrollbars=1, width=100,height=100");

// öffnet neues browser window in bildschirmgrösse
let source = "http://www.duckduckgo.com";
window.open(src, "newWin", "width="+screen.availWidth+",height="+screen.availHeight);

// öffnet url in neuem Tab
let source = "http://www.duckduckgo.com";
window.open(source,'_blank');
```

# Weiterführende Links

  - [30seconds of CSS](https://30-seconds.github.io/30-seconds-of-css/)
  - [Javascript 30 course by Wes Bos](https://javascript30.com)
  - 