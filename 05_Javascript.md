# Javascript

Eine allgemeine Einführung in die Syntax zu Javascript gibt es unter folgendem [Link](https://github.com/fleshgordo/introJS/blob/master/01_walkthrough.md).

Die Arbeit mit dem [Web-Inspektor](https://developers.google.com/web/tools/chrome-devtools/console/) und der Live-Console ist sehr hilfreich, um Bugs oder sonstige Fehler aufzufinden.

Javascript kann einerseits direkt im HTML eingebunden sein (aka inline) oder über ein externes File geladen werden:

__inline__

```js
<script>console.log('Hello world!');</script> 
```

Das __\<script>\</script>__ Tag kann entweder in der __\<head>__ Sektion der Seite eingebunden werden, oder (in den meisten Fällen) kurz bevor der __\</body>__ geschlossen wird.

__external__ (am Ende des HTML Files)

```html
<!-- html webseite .... -->
<script href="./link_zum_file.js"></script> 
</body>
</html>
```

### Mini-Aufgabe
Seht euch folgendes (sehr simples Plugin) [WelcomeJS](https://github.com/stml/welcomejs) an. Versucht es auf einer Website einzubinden und die __console.log__ Nachricht mit simplen CSS Eigenschaften zu gestalten.

## Selektoren

Javascript kann alle HTML Elemente sowie deren Attribute auf einer Seite ändern (dies wird auch DOM-Manipulation genannt). JS kann aber auch CSS Stile ändern, bestehende HTML Elemente entfernen, neue generieren bzw. auch neue Ereignisse (z. B. Popup bzw. Zeit-intervalle) erzeugen.

Um ein HTML Element zu manipulieren, muss es zunächst mittels eines Selectors ausgewählt werden. Dieser Selector kann über die __id__ oder über die Klasse (__class__) abgerufen werden. Der Befehl dazu heisst [querySelector("CSSSELEKTOR")](https://developer.mozilla.org/en-US/docs/Web/API/Document/querySelector). Diese Funktion gibt das erste Element innerhalb eines Dokuments zurück, welches dem angegebenen Selektor bzw. Selektoren entspricht. Nehmen wir an, es befindet sich ein Blockelement \<div class="item3"> im HTML Code: 

```js
let div3 = document.querySelector(".item3");
console.log(div3);
console.log("div3");
```

Was seht ihr in der Konsole? Befindet sich jedoch kein Element mit der Klasse __item3__ auf der Seite, ergibt sich in der Konsole des Web-Inspektors folgender Output:

```js
null
div3
```

Die Positionierung des Javascript Codes ist wichtig! Ist das Element noch nicht im DOM Tree geladen, ist die Variable __div3__ null! Wird der JS Code am Ende (kurz vor dem \<body> Tag) platziert, sollter der Output so aussehen:

```html
<div class="item item3">3</div>
div3
```

In der Variable __div3__ ist nun das HTML Element gespeichert. Nun kann der Inhalt des Elementes z. b. verändert werden:

```js
div3.innerHTML = "test";
```

Es kann auch über den Javascript Code eine CSS Klasse an das Element angehängt werden:

```js
div3.classList.add("hide");
/* über die Punkt Syntax kann das ganze auch in einer Zeile aneinandergereiht sein wie z.b: */
document.querySelector(".item3").classList.add("hide"); // wäre die variante ohne variable
```

Klassen können ebenso wieder entfernt werden:
```js
document.querySelector(".item3").classList.remove("hide"); 
```

Im CSS sollte die Klasse __hide__ noch definiert werden, z. B.:

```css
.hide {
    display: none; /* dies entfernt es komplett aus dem DOM. alternative wäre die opacity zu ändern */
    /* opacity: 0; */
}
```

Dies macht aber erst Sinn, wenn es z. B. an einen Event (wie Mausklick, Mouseover, Tastenklick, Timer, etc.) angebunden wird.

## Events

Alle User-Interaktionen können über Event-Listener mittels Javascript abgerufen werden. Die Methode [__addEventListener()__](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/addEventListener) registriert den angegebenen "Zuhörer" (Engl. "listener") an einem ausgewählten EventTarget (welcher durch __document.querySelector()__ beispielsweise ausgewählt wurde), auf welches es aufgerufen wird. 

```js
document.querySelector(".item3").addEventListener("mouseover", function() {
    console.log("yo");
});
```

Folgender Code erzeugt eine Message __yo__ im Konsolenfenster, sobald der __mouseover__ Event getriggert wird. Hier eine Liste aller [Events](https://www.w3schools.com/jsref/dom_obj_event.asp).

Um ein Element zu animieren, sobald sich der Mauszeiger darüber befindet könnte man wie folgt definieren:

```js
document.querySelector(".item3").addEventListener("mouseover", function() {
    document.querySelector(".item3").classList.add("hide");
});
document.querySelector(".item3").addEventListener("mouseleave", function() {
    document.querySelector(".item3").classList.remove("hide");
});
```

Die Klasse __hide__ sollte im CSS so definiert sein:

```css
.hide {
    opacity: 0;
    transition: all 1s;
}
```

Das Projekt [clickclickclick](https://clickclickclick.click/) von [Studio Moniker](https://studiomoniker.com/) nutzt viele Browser-spezifische Events, Eigenschaften und User-Inputs auf humorvolle Weise.

Nebem dem [document](https://www.w3schools.com/jsref/dom_obj_document.asp) Element gibt es auch noch das [window](https://www.w3schools.com/js/js_window.asp) Element, welches verschiedene Funktionen sowie Variablen beinhaltet, so sind z. B. in __window.innerHeight__ bzw. __window.innerWidth__ die Grösse des aktuellen Browser-Fensters gespeichert.

```js
console.log("Window width: " + window.innerWidth);
console.log("Window height: " + window.innerHeight);
```

Tastendrücke können ebenfalls als Trigger für Manipulation am DOM Element dienen (__keyup__ wenn die Taste losgelassen wird). 

```js
window.addEventListener("keyup",function(e) {
    console.log(e);
});
```




## Audio/Video steuern

# Weiterführende Links

  - [The Vanilla JS Toolkit](https://vanillajstoolkit.com/reference/)
  - [Vanilla Javascript Cheatsheet](https://gist.github.com/thegitfather/9c9f1a927cd57df14a59c268f118ce86)
  - 

----




```js
document.addEventListener("DOMContentLoaded", function() {
  // code...
});
```