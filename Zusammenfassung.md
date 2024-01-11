# Zusammenfassung Fernerkundung Semester 3
## Bildverarbeitung
Transformation (Veränderung) eines Eingabebildes in ein Ausgabebild mithilfe von mathematischen Transformationsfunktionen

Unterschied zwischen Theorie und Praxis:
#### Theorie
* verschiedene Stufen der Bildverarbeitung (Eingangsbild & Bildverarbeitung & Ergebnisbild & Bildanalyse & abstrahierte Beschreibung)
#### Praxis/Realität
* fließender Übergang zwischen Verarbeitung und Analyse

&nbsp;

### Geometrische Transformation
* Bilder werden in ihrer Form verändert; radiometrische Eigenschaften bleiben erhalten (z.B. DN-/Grauwerte)

### Radiometrische Transformation
* Grauwerte werden verändert, während geometrische Eigenschaften erhalten bleiben

&nbsp;

### Ziele der Bildverarbeitung in der Fernerkundung
* Informationsextraktion, Bildanalyse, Auswertung, Visualisierung
* zunehmende Datenflut (Big Data), überwiegend visuelle Daten

  &rarr; Notwendigkeit der Automatisierung
  
  &rarr; Zuverlässigkeit der Algorithmen
  
  &rarr; Schnelligkeit
  
  &rarr; Übertragbarkeit der Auswertemethoden
  
  &rarr; Einfachheit (sofern möglich)


### Werkzeuge der Bildverarbeitung
* Verbesserung der Bildqualität
* Behebung von Fehlern (Über-/Unterbelichtung, Unschärfe, Kontrastschwäche, Bildrauschen)
* Hervorhebung von Bildmerkmalen (z.B. NDVI)

### Auswahl an Anwendungsbeispielen der Bildverarbeitung (auch außerhalb der Fernerkundung)
#### Medizin
* Tomographie
* Thermographie
* Radiologie
#### Produktion
* Sortierung
* Bestückung
* Überwachung
#### Kriminologie
* Fingerabdrücke
* Handschrifterkennung
* Porträtsauswertung
* Tatortanalyse
#### Verkehr
* Hinderniserkennung
* Fahrerassistenzsysteme
* autonome Fahrzeugführung
* Verkehrsmanagement

## Digitale Bilder
### Was ist ein digitales Bild?
* Bildpunkt/PIXEL (Picture Element) ist Elementareinheit des digitalen Bildes
* jeder Bildpunkt wird durch Zahl dargestellt (DN = digital number; bei 8 Bit 256: von 0 bis 255)
    * dieser Grauwert beschreibt die Helligkeit/Intensität eines Bildpunktes
    * bei einem RGB-Bild wird jeder Pixel durch drei Intensitätswerte beschrieben (jeweils einer für rot, grün und blau)
    * Synonyme: Brightness Value, Digital Count, Digital Level (DL), Digital Number (DN), Gray Level, Pixel Value

#### Die Grauwerte werden in einer s.g. Bildmatrix gespeichert

<img title="Veranschaulichung einer Bildmatrix" width="700" src="https://github.com/s92854/FernerkundungS3/assets/134683810/4bc3e195-6573-478b-9dc1-efc1a56a3889">

### Quantisierung
Die Quantisierung bezeichnet den Wertebereich der Grauwerte eines Bildes

<img title="Quantisierung eines Bildes von Binär bis 8-Bit" width="700" src="https://github.com/s92854/FernerkundungS3/assets/134683810/a8778833-97da-4e2f-8f29-64c00771fea7">

### Parameter eines digitalen Bildes
* Anz. Pixel
* Anz. Kanäle: pan, RGB, RGB + NIR, ...
* Datenformat: Rohdaten, Rohdaten + Header, spezielle Formate (BMP, GeoTIF, TIF, GIF, JPEG, IMG, ...)
* Bildgröße: Breite, Höhe
* Geometrische, radiometrische Auflösung
* Georeferenzierung
* Kartenprojektion
* Geodätisches Bezugssystem

## Histogramme
Histogramme sind Häufigkeitsverteilungen. Hier: Häufigkeitsverteilungen der Intensitäts- bzw. Grauwerte

$h(g) =$ die Anzahl der Pixel (Häufigkeit) mit dem Intensitätswert $g$

### Folgende Eigenschaften von Bildern können anhand des Histogramms beurteilt werden, u.a.:
* Kontrast (Bereich der Intensitätsstufen)
* Dynamik (Anzahl verschiedener Pixelwerte)
* Belichtung
* Sättigung (belegter Wertebereich)
* Kompression von Bilddaten

Ein Histogramm enthält nur Information über die Grauwertverteilung, nicht über die Position der jeweiligen Grauwerte im Bild. Zwei unterschiedliche Bilder können das gleiche Histogramm haben.

### Parameter eines Histogramms (Bildstatistik)
* kleinster Pixelwert (min value)
* größter Pixelwert (max value)
* arithmetisches Mittel (mean value)
* mittlerer Wert (Median)
* häufigster Wert (Modalwert)
* Standardabweichung (standard deviation)

### Histogramm eines RGB-Bildes
* Erstellung eines Histogramms für jeden einzelnen Kanal
* Mittelwertbildung der 3 Kanäle
* Mensch kann nicht gesamtes Farbspektrum sehen und nimmt unterschiedliche Farben untersch. stark wahr
    * Darstellung von RGB-Bildern mithilfe der Luminanz: gewichtete Helligkeit (60% Grün, 30% Rot, 10% Blau)
