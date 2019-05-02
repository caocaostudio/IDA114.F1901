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
console.log("div3");
```

Befindet sich jedoch kein Element mit der Klasse __item3__ auf der Seite, ergibt sich in der Konsole des Web-Inspektors folgender Fehler:

```js

```