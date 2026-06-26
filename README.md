# Agentenbasiertes Infektionsmodell (SEIR)

Interaktives Seminarwerkzeug für die Lehre (Infektionsepidemiologie, Universität des Saarlandes).
Jeder Punkt ist eine Person; bei Kontakt überträgt sich der Erreger mit einer Wahrscheinlichkeit,
Angesteckte durchlaufen **S → E → I → R**. Die Epidemiekurve entsteht live aus dem Verhalten der
Einzelnen (Mikro → Makro) — die anschauliche Ergänzung zum
[SEIR-Kompartimentmodell](https://clinical-pharmacy-saarland-university.github.io/seir-simulator/).

**Live:** https://clinical-pharmacy-saarland-university.github.io/abm-infektion/

## Didaktische Stellschrauben
- **Erreger:** Übertragungsrate β, Latenzzeit (1/σ), infektiöse Periode (1/γ)
- **Interventionen:** Impfung/Anfangsimmunität, Kontaktreduktion (Social Distancing), Quarantäne/Isolation
- **Gemessenes Rₜ:** die mittlere Zahl der Folgeinfektionen je kürzlich genesener Person — R₀/Rₜ ist
  hier *emergent*, keine Stellgröße.

Kontaktreduktion und Quarantäne lassen sich auch **mitten in der Welle** aktivieren, um den Effekt
einer Intervention zum laufenden Geschehen zu zeigen.

## Technik
Eine einzelne, eigenständige `index.html` — kein Build, kein Server, **keine externen JS-Abhängigkeiten**
(Simulation und Diagramm sind selbst gezeichnet; nur Google Fonts werden geladen). Die Simulation läuft
in festen logischen Koordinaten, damit die Dynamik unabhängig von der Bildschirmgröße ist. Läuft auf
Desktop und Handy (responsiv) und sammelt keine Daten.

Die Modell-Engine ist gegen Szenario-Tests verifiziert (Epidemie bei Default, Herdenimmunität bei hoher
Impfquote, Kurvenabflachung bei Kontaktreduktion, Reduktion durch Quarantäne; Erhaltung S+E+I+R = N).

## Aktualisieren
`index.html` ändern, dann `git add` / `commit` / `push`. GitHub Pages baut automatisch neu.
