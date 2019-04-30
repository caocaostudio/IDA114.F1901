# Grids und Responsive Design

Der viewport des Browsers ist der Bereich des Fensters, in dem Webinhalte zu sehen sind. Dies ist oft nicht die gleiche Größe wie die komplette gerenderte Seite. Eine typische optimierte Website für "mobil-view" beinhaltet folgende Zeile in der __<head>__ Sektion:

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

Die width-Eigenschaft steuert die Größe des Viewports. Es kann auf eine bestimmte Anzahl von Pixeln  oder auf den speziellen Wert __device-width__ (e.q. Grösse des Bildschirms) gesetzt werden

Die Eigenschaft __initial-scale__ steuert die Zoomstufe beim ersten Laden der Seite. Die Eigenschaften __maximum-scale__, __minimum-scale__, and __user-scalable__ steuern, wie Benutzer die Seite ein- oder auszoomen dürfen. Mehr Infos dazu bei [CSS-Tricks](https://css-tricks.com/snippets/html/responsive-meta-tag/).

## Media Queries

Mit Media Queries lassen sich verschiedene CSS Parameter anpassen in Abhängigkeit von Bildschirmauflösung und Orientierung der aktuellen Browsergrösse (z.B. Smartphone-Bildschirm vs. Computerbildschirm). Es wurde im Juni 2012 zum vom W3C empfohlenen Standard und ist unbedingt notwendig für das Responsive Design. Das Ziel von Responsive Design ist es, Webseiten zu erstellen, die die Bildschirmgröße und Ausrichtung erkennen und das Layout entsprechend ändern. 

Eine Media Query besteht aus einem Medientyp und einem oder mehreren Ausdrücken die wahr bzw. falsch sein können, je nach Endgerät. Das Ergebnis der Media Query ist wahr, wenn der in der Medienabfrage angegebene Medientyp mit dem Gerätetyp übereinstimmt. Wenn die Bedingung der Media Query wahr ist (true), dann werden die darinstehenden CSS Regeln angewandt.

Um z. B. ein bestimmtes CSS zu laden wenn ein Querformat vorliegt:

```css
@media all and (orientation: landscape) {
  /* der Code wird nur auf Querformat angewandt (Länge grösser als Breite */
}
```

Das zweite Wort nach __@media__ regelt welche Devices von der Media Query adressiert werden sollen. Es gibt __all__, __screen__, __print__ und __speech__. Hier die ganze [Liste](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries) und ihre Bedeutungen.

```css
@media all and (orientation: landscape) {
  /* der Code wird nur auf Querformat angewandt (Länge grösser als Breite */
}

@media screen and (min-width: 640px) {
  /* das CSS wird nur geladen wenn das Gerät mind. 640px Breite hat */
}
```

Mit dem Wort __and__ kann man Media Queries auch verknüpfen:

```css
@media all and (min-width: 640px) and (max-width: 800px){
  /* das CSS wird nur geladen wenn das Gerät mind. 640px
  und maximal 800px breit ist */
}
```

Oder z. B. die Screengrösse und die Ausrichtung:

```css
@media all and (min-width: 640px) and (orientation: landscape) { 
   /* das CSS wird nur geladen wenn das Gerät mind. 640px Breite 
   und im Querformat ist */ 
}
```

## Grids
Bislang hatten wir die Positionierung der einzelnen Block-Elemente mit __float__ kontrolliert. Für aufwändigere Layouts welche sich auf unterschiedlichen Screensizes ausrichten müssen, ist die Arbeit mit __float__ eher [mühsam](https://imgur.com/gallery/Q3cUg29). Anfangs musste man Tabellen, dann Floats, Inline-Block usw. verwenden, aber alle diese Methoden waren im Wesentlichen Hacks und Funktionen wie z.B. vertikale Zentrierung waren äusserst aufwendig. 

[Grid CSS](https://www.w3schools.com/css/css_grid.asp) ist ein zweidimensionales System, d.h. es kann sowohl Spalten als auch Zeilen verarbeiten, im Gegensatz zu [Flexbox](https://www.w3schools.com/css/css3_flexbox.asp), welches weitgehend für eindimensionale Layouts verwendet werden -> sprich für einzeilige horizontale oder vertikale Layouts. 

https://css-tricks.com/snippets/css/complete-guide-grid/

```css

```