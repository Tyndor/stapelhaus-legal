# Stapelhaus — Rechtliches

Öffentlich erreichbare Rechtstexte zur App **Stapelhaus** (Android und iOS):
Datenschutzerklärung und Impressum. Ausgeliefert über GitHub Pages, damit die
Store-Konsolen eine dauerhaft erreichbare URL ohne Anmeldung prüfen können.

Der Quelltext der App liegt in einem eigenen, privaten Repository. Hier stehen
ausschließlich die beiden Rechtstexte — Änderungen daran sind sofort öffentlich
wirksam.

## Woher die Texte kommen

Die Quelle sind die Markdown-Dateien im App-Repo, nicht diese Seiten:

| Seite | Quelle im App-Repo |
|---|---|
| `datenschutz.html` | `apps/stapelhaus/legal/privacy_de.md` |
| `impressum.html` | `apps/stapelhaus/legal/imprint_de.md` |

**Übertragen wird von Hand, nicht erzeugt.** Wer den Text dort ändert, ändert
ihn hier mit — sonst laufen App-Fassung und Web-Fassung still auseinander. Vor
jedem Store-Upload gehören die beiden nebeneinandergelegt.

**Ein Abschnitt steht nur hier:** „12. Diese Website". Er erklärt, was GitHub
beim Aufruf dieser Seiten verarbeitet. In der Markdown-Datei ist er mit
`<!-- nur-web -->` geklammert; die App entfernt solche Blöcke beim Lesen, denn
wer die Erklärung im Einstellungen-Tab liest, ruft keine Website auf.

## Wie die Seiten gebaut sind

Fünf Dateien, kein Framework, kein Bauschritt: `index.html`,
`datenschutz.html`, `impressum.html`, `stil.css`, `robots.txt`.

**Die Seiten laden NICHTS nach** — keine Schriften, keine Skripte, keine
Cookies, keine Analyse. Auf einer Datenschutzseite wäre eine Schrift von
fremdem Server der falsche Anfang: Der Besuch stünde dann in einem zweiten
Protokoll. Das Aussehen kommt deshalb aus Farben und Rundungen der App, die
Schrift aus dem System — Nunito steht im Stapel vorn, wer sie hat, sieht sie.

Die Farbwerte in `stil.css` stammen aus
`apps/stapelhaus/lib/core/theme/app_theme.dart`, die Radien aus `tokens.dart`
daneben. Verbunden sind die beiden nur durch diesen Satz.

**Die Favicons entstehen aus der Icon-Lieferung**, nicht von Hand:
`dart run tool/make_web_favicons.dart` aus `apps/stapelhaus` skaliert
`design/stapelhaus/icon/png/icon-ios-light-1024.png` auf 32, 180 und 512 px.
`icon-quelle.png` hier ist eine Kopie derselben Vorlage, damit die Seiten auch
ohne das App-Repo nachgezogen werden können.

## Nicht in Suchergebnisse

Jede Seite trägt `noindex, nofollow`. Die Anschrift muss erreichbar sein, aber
nicht über Suchmaschinen auffindbar. Bewusst **keine** pauschale Sperre in
`robots.txt`: Die würde nur das Lesen verhindern, das Indexieren über fremde
Verweise aber nicht — und die `noindex`-Angabe in den Seiten würde dann nie
gelesen. Die `robots.txt` weist stattdessen die bekannten KI-Sammler ab.
