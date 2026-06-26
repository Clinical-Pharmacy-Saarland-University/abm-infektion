# Agentenbasiertes Infektionsmodell (SEIR)

Interaktives Seminarwerkzeug für die Lehre (Infektionsepidemiologie, Universität des Saarlandes).
Jeder Punkt ist eine Person; bei Kontakt überträgt sich der Erreger mit einer Wahrscheinlichkeit,
Angesteckte durchlaufen **S → E → I → R**. Die Epidemiekurve entsteht live aus dem Verhalten der
Einzelnen (Mikro → Makro) — die anschauliche Ergänzung zum
[SEIR-Kompartimentmodell](https://clinical-pharmacy-saarland-university.github.io/seir-simulator/).

**Live:** https://clinical-pharmacy-saarland-university.github.io/abm-infektion/

## Didaktische Stellschrauben
- **Erreger:** Übertragungsrate β, Latenzzeit (1/σ), infektiöse Periode (1/γ)
- **Bevölkerungsstruktur:** Aktivitätsgruppen — *Essential Worker* (viele Kontakte) vs. *Homeoffice*
  (wenige Kontakte) mit regelbar reduziertem Transmissionsrisiko
- **Interventionen:** Impfung/Anfangsimmunität, Quarantäne/Isolation
- **Optionales Modul „Hospitalisierung & adaptives Verhalten":** ein Teil der Fälle wird hospitalisiert
  (Zustand H, isoliert) mit **Kapazitätslinie**; zusätzlich eine **freiwillige Kontaktreduktion**, die
  mit dem aktuell hospitalisierten Bevölkerungsanteil hochfährt (Rückkopplung → mehrere Wellen)
- **Zwei Diagramm-Ansichten:** *Zusammensetzung* (gestapelt) und *Aktiv/Prävalenz* (nicht gestapelt) —
  Letztere macht den „flatten-the-curve"-Effekt und die Kapazitätsüberlastung deutlich sichtbar
- **Gemessenes Rₜ:** die mittlere Zahl der Folgeinfektionen je kürzlich genesener Person — R₀/Rₜ ist
  hier *emergent*, keine Stellgröße.

Alle Regler außer Bevölkerung und Impfquote wirken auch **mitten in der Welle**, um den Effekt einer
Intervention zum laufenden Geschehen zu zeigen.

## Technik
Eine einzelne, eigenständige `index.html` — kein Build, kein Server, **keine externen JS-Abhängigkeiten**
(Simulation und Diagramm sind selbst gezeichnet; nur Google Fonts werden geladen). Die Simulation läuft
in festen logischen Koordinaten, damit die Dynamik unabhängig von der Bildschirmgröße ist. Läuft auf
Desktop und Handy (responsiv) und sammelt keine Daten.

Die Modell-Engine ist gegen Szenario-Tests verifiziert (Epidemie bei Default, Herdenimmunität bei hoher
Impfquote, Kurvenabflachung bei Homeoffice-Anteil/reduziertem Risiko, frühere Welle bei Essential Workern,
Reduktion durch Quarantäne, Hospitalisierung samt Kapazitätsüberlastung, abgeflachter/gestreckter Verlauf
durch adaptives Verhalten; Erhaltung S+E+I+R+H = N).

## Aktualisieren
`index.html` ändern, dann `git add` / `commit` / `push`. GitHub Pages baut automatisch neu.
