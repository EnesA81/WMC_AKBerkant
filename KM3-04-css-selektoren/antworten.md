# KM3-04 – Meine Antworten

## Beispiel 1

**a) Speisekarte**

1. Kopfzeile: `main > section:last-child thead`
2. Jede zweite Zeile: `main > section:last-child tbody tr:nth-child(even)`
3. Letztes Gericht: `main > section:last-child tbody tr:last-child td:first-child`

**b) Liste**

- Zweiter Schritt: `main > section:last-child ol li:nth-child(2)`
- Vorletzter Schritt: `main > section:last-child ol li:nth-last-child(2)`

**c) Kästen**

Verwendeter Selektor: `main > section:last-child .kasten:has(img)`

Mit `:has(img)` wird überprüft, ob im Kasten ein Bild vorhanden ist. `:is()` fasst nur verschiedene Selektoren zusammen und prüft nicht, was im Kasten liegt.

## Beispiel 2

**a) Richtige Aussagen:**

- [x] 1. `p.hinweis` trifft nur Absätze mit der Klasse `hinweis`.
- [x] 2. `h2 ~ p` trifft passende folgende Geschwister-Absätze derselben Ebene.
- [ ] 3. `:nth-child(2)` und `:nth-of-type(2)` treffen immer dasselbe Element.
- [x] 4. Bei gleicher Spezifität gewinnt normalerweise die später notierte Regel.

**Begründung zu Aussage 3:** `:nth-child(2)` zählt alle Kinder eines Elternelements. `:nth-of-type(2)` zählt nur Kinder mit demselben HTML-Tag.

**b) Selektoren**

| Gesucht | Selektor |
|---|---|
| Links, die auf `.pdf` enden | `a[href$=".pdf"]` |
| Absätze ohne Klasse `hinweis` | `p:not(.hinweis)` |
| Erstes `li` in jeder `ul` | `ul > li:first-child` |
| Elemente mit einem `img` darin | `:has(img)` |
| Angekreuzte Checkbox direkt vor einem Label | `input[type="checkbox"]:checked + label` |

*Beim letzten Selektor wird das `label` nach der angekreuzten Checkbox ausgewählt.*

**c) Fehler und Korrektur**

`p:nth-child(1)` funktioniert nur, wenn der Absatz wirklich das erste Kind seines Elternelements ist. Steht zum Beispiel eine Überschrift davor, klappt es nicht.

```css
p:first-of-type {
    font-weight: bold;
}
```

## Beispiel 3

Die Regeln für **a), b) und c)** stehen in `loesung.css`. Mit `testbereich.html` kann man sie ansehen.

**d) Erklärung (2 Sätze):** Das Attribut `data-topic` ist schon im HTML vorhanden, deshalb kann ich es direkt im CSS auswählen. Mit einer neuen Klasse müsste ich das HTML verändern, und das ist hier nicht erlaubt.
