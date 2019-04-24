# SVG Graphiken animieren

[SVG](https://svgontheweb.com) steht für Scalable Vector Graphics. Es ist ein XML-basiertes Vektorformat für zweidimensionale Graphiken welche animiert und interaktiv fürs Web verwendet können.

Eine (rote) Linie als SVG könnte so aussehen: 

```xml
<svg>
    <line stroke="#ff0000" x1="0.4" y1="78.2" x2="78.2" y2="0.4" />
</svg>
```

Dieser Code kann direkt ins HTML eingefügt werden. Es handelt sich deshalb um eine Inline SVG. Mehr zu den Grundformen vom SVG Format hier unter diesem [Link](https://www.w3schools.com/html/html5_svg.asp).

Illustrator (bzw. [Inkscape](https://inkscape.org/)) arbeiten ebenso mit Vektorgraphiken. Diese können bis zu einer gewissen Komplexität direkt in den HTML Code eingebunden werden. v

Hier ein einfacher Stern als Vektorgraphik, welche im Illustrator selektiert wurde:

<img src="img/star.png" width="300"/>

Und hier dieselbe Vektorgraphik im Browser animiert:

<img src="img/star_animated.gif" width="300"/>

Die Vektorgraphik kann in ein XML Format konvertiert werden, indem sie aus dem Illustrations-Programm kopiert wird und anschliessend in den Text-Editor eingefügt wird (Copy/Paste).

Eine eingefügte Graphik könnte so aus aussehen:

```xml
<!-- Generator: Adobe Illustrator 22.1.0, SVG Export Plug-In  -->
<svg version="1.1"
	 xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:a="http://ns.adobe.com/AdobeSVGViewerExtensions/3.0/"
	 x="0px" y="0px" width="76.8px" height="73.1px" viewBox="0 0 76.8 73.1" style="enable-background:new 0 0 76.8 73.1;"
	 xml:space="preserve">
<defs>
</defs>
<g>
	<path d="M36.5,1.6c1-2.1,2.7-2.1,3.8,0L49,19.3c1,2.1,3.8,4.1,6.1,4.4l19.5,2.8c2.3,0.3,2.8,1.9,1.2,3.6L61.6,43.9
		c-1.7,1.6-2.7,4.9-2.3,7.2l3.3,19.5c0.4,2.3-1,3.3-3,2.2l-17.5-9.2c-2.1-1.1-5.5-1.1-7.5,0l-17.5,9.2c-2.1,1.1-3.4,0.1-3-2.2
		L17.4,51c0.4-2.3-0.7-5.5-2.3-7.2L1,30.1c-1.7-1.6-1.2-3.2,1.2-3.6l19.5-2.8c2.3-0.3,5.1-2.3,6.1-4.4L36.5,1.6z"/>
</g>
</svg>
```

Die erste Zeile ist lediglich ein Kommentar. Danach kommt das Element <__svg__> , welches das <__g__> Element beinhaltet. Innerhalb eines <__g__> Elementes können mehrere SVG Elemente zu einer Gruppe zusammengefasst werden.

Das Element <__path__> beschreibt nun die Vektorgraphik mittels x,y Koordinaten und Pfaden. Um es mit CSS zu animieren bzw. zu steuern, kann eine Klasse für dieses Element definiert werden:

```xml
	<path class="star" d="M36.5,1.6c1-2.1,2.7-2.1,3.8,0L49,19.3c1,2.1,3.8,4.1,6.1,4.4l19.5,2.8c2.3,0.3,2.8,1.9,1.2,3.6L61.6,43.9
		c-1.7,1.6-2.7,4.9-2.3,7.2l3.3,19.5c0.4,2.3-1,3.3-3,2.2l-17.5-9.2c-2.1-1.1-5.5-1.1-7.5,0l-17.5,9.2c-2.1,1.1-3.4,0.1-3-2.2
		L17.4,51c0.4-2.3-0.7-5.5-2.3-7.2L1,30.1c-1.7-1.6-1.2-3.2,1.2-3.6l19.5-2.8c2.3-0.3,5.1-2.3,6.1-4.4L36.5,1.6z"/>
```

Im CSS kann die Klasse genauer beschrieben werden (Farbe, Position, Grösse) und die Animation definiert werden:

```css
.star {
	fill: #ff0000;
	animation: rotate 2s infinite;
}

@keyframes rotate {
	from {}
	to {
		transform: rotate(360deg);
	}
}
```

Der Stern rotiert allerdings nicht um die Mitte, sondern der Rotationspunkt liegt an der linken oberen Ecke. Hierfür kann [__transform-origin__](https://developer.mozilla.org/en-US/docs/Web/CSS/transform-origin) hilfreich sein:

```css
transform-origin: center center;
```

Es fällt noch auf, dass die Vektorgraphik "geclipped" wird, d. h. sie wird an den Grenzen des SVG Rahmens abgeschnitten. Um dieses Problem zu lösen, hilft der [__overflow__](https://www.w3schools.com/cssref/pr_pos_overflow.asp) Parameter. 

```css
svg {
	overflow: visible;
}
```
