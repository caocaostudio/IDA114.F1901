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
Seht euch folgendes (sehr simples Plugin) [WelcomeJS](https://github.com/stml/welcomejs) an. Versucht es auf einer Website einzubinden und die __console.log__ Nachricht mit simplen CSS Befehelen zu gestalten.



