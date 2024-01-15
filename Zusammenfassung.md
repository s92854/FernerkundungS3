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

### Digitale Bildverarbeitung (digital image processing)
* digital vorliegende Bilder werden rechnergestützt weiterverarbeitet (keine Aussage um welche Verarbeitung es sich handelt)

### Digitale Bildbearbeitung (image enhancement, image restauration)
* digital vorliegende Bilder werden durch spezielle Methoden aufbereitet bzw. verbessert, da die Qualität i.d.R. durch Störungen gelitten hat
* i.d.R. wegen eines bestimmten Auswerteziels

#### Ziele
* visuelle Bildinterpretation
* automatische Bildauswertung

#### Visuelle Bildinterpretation
* Menschen interpretieren Bilder
    * Filterung (Kantenverstärkung zur Schärfung des Bildinhalts, Glättung des Bildinhalts zur Reduktion von Bildrauschen)
    * Helligkeits- und Kontrastverbesserung
    * Kanalkombinationen (z.B. Ratios,  Pan-Sharpening)
    * Künstliches Einfärben monochromer Bilder (Falschfarbenbilder)
    * Dekorrelation (z.B. Hauptkomponentenanalyse (principal component analysis, pca))

#### Automatische Bildauswertung
* Computerverfahren, die ohne menschliche Beobachter auskommen (maschinelles Sehen (computer vision), Mustererkennung (pattern recognition))
    * Filterung
    * Beseitigung systematischer Fehler des Sensors (z.B. radio- und geometrische Abbildungsfehler)
    * Beseitigung systematischer Fehler der Aufnahme (z.B. Atmosphärenkorrektur, Beleuchtungskorrektur)
    * bestimmte Bildinformationen zusammenfassen (z.B. Segmentierung, Clusteranalyse, k-nearest-neighbor (KNN))

#### Frequenzbereich
* Transformation eines Bildes in seine Frequenzanteile

#### Ortsbereich
* Darstellung der Position im Raum

#### Fouriertransformation und Inverse Fouriertransformation
* Frei hin und her transformieren zwischen Orts- und Frequenzbereich
* Orts- in Frequenzbereich: Fouriertransformation
* Frequenz- in Ortsbereich: Inverse Fouriertransformation
    * nach Jean Baptiste de Fourier

##### Bearbeitung im Ortsbereich
Die Beziehung bezieht sich auf die räumliche Anordnung von Pixeln in einem digitalen Bild. Bildbearbeitungsfunktionen im Ortsbereich werden generell beschrieben als:

$$f2(x,y)=T[f1(x,y)]$$

* f<sub>1</sub>(x,y) ist Grauwert des Eingabe- und f<sub>2</sub>(x,y) Grauwert des Ausgabebildes
* T ist ein Bildoperator im Bezug auf f<sub>1</sub>

### Digitale Bildauswertung (digital image processing, feature extraction, pattern recognition, image classification)
* Ableiten semantischer Informationen aus Bildern

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

## Bildoperatoren
### Punktoperatoren
* pixelorientiert; betreffen nur einzelne Bildelemente (Grauwerttransformation)
* arbeiten isoliert auf einzelnen Pixeln, wissen nichts über die Umgebung des Pixels (arbeitet grauwertorientiert)
* jeder neue Pixelwert hängt ausschließlich vom alten Pixelwert ab, unabhängig von anderen Pixelwerten im Bild (keine Nachbarschaft wird berücksichtigt)
* Anwendungen:
    * Kontraständerung
        * Multiplikation, damit Streckung oder Stauchung des Histogramms
    * Helligkeitsänderung
        * Addition bzw. Subtraktion (+a oder -a), damit Veränderung der Amplitude des Histogramms
    * Anwendung beliebiger Helligkeitskurven (Transferfunktionen)
    * Invertieren von Bildern
    * Schwellenwertbildung (Binarisierung, treshold)
        * Anzahl der Grauwerte eines Bildes wird auf 2 reduziert (0,1)
        * wird häufig im 1. Schritt der Objekterkennung (Segmentierung) genutzt, um Objekte vom Bildhintergrund zu trennen
    * Rauschen reduzieren
        * Nicht-Information, die der nutzbaren Information überlagert ist
        * Signal-Rauschverhältnis: Verhältnis zwischen nutzbarer Bildinfo und Rauschen
        * z.B. durch Addition der Bilder; Achtung: Bittiefe kann sich ändern
    * Histogrammausgleich (histogram equalization)
        * Konstrastverbesserung &rarr; häufig: wenige Bildpunkte nutzen großen und viele Bildpunkte einen kleinen Grauwertbereich
        * durch homogene Punktoperationen gleichverteiltes Histogramm erzeugen
    * Look-Up-Table (LUT)
        * Wertetabelle mit zwei Spalten: Original- und Zielwert
        * schnelle Wertsuche
        * weniger Speicherplatz

#### Homogene Punktoperatoren
* Position des Pixels hat auf den neuen Grauwert keinen Einfluss, sondern nur der ursprüngliche Grauwert des Pixels

#### Inhomogene Punktoperatoren
* Lage des Pixels wird mit verrechnet
* neue Grauwert hängt vom ursprünglichen Grauwert und der Position des Pixels innerhalb des Bildes ab
* z.B. Aufhellung des Bildes an den Rändern

### Lokale Operatoren
* regionenorientiert &rarr; Berechnung aus einer Menge von benachbarten Pixeln
* durch Punktoperatoren lassen sich keine Glättung oder Schärfungen erzeugen
* Problem: Randpixel können nicht berechnet werden, da außerhalb des Bildes Informationen fehlen &rarr; mgl. Lösung: Ränder im Ergebnisbild leer (undefined) lassen oder Ränder nach außen spiegeln (Bild künstlich vergrößern)

#### Parameter
* Größe der Region (Filtermatrix)
* Form der Filterregion
* Gewichtung der Quellpixel (konstant vs. ortsabhängig)

#### Bildfilterung
* Bildverbesserungen:
    * Unterdrückung bzw. Verminderung vorhandenen Rauschens
    * Unterdrückung von Störungen (Pixelausfälle)
    * Restaurierung von Bildern
    * Hervorhebung von Details (z.B. Kantenverstärkung)

##### Lineare Filter
* Wert des Zielpixels wird in linearer Form als gewichtete Summe der Quellpixel berechnet
* Größe und Form der Filterregion und Gewichte des Filters werden durch eine Matrix spezifiziert **Filtermatrix** H<sub>ij</sub>
* Koordinaten meist relativ zum Zentrum ('hot spot') angegeben
* Filterregion muss nicht quadratisch oder zusammenhängend sein
* Beispiele:
    * Glättungsfilter (Tiefpassfilter)
        * Abschwächung/ELimination der hochfrequenten Teile eines Bildes
        * visueller Eindruck: Bild wird weicher
        * Grauwertkanten werden verwischt
        * Details und Rauschen eines Bildes werden abgeschwächt
        * in homogenen Teilen eines Bildes (nicht hochfrequenten) haben Tiefpassfilter so gut wie keine Auswirkung
            * Boxfilter
            * Gaußfilter
    * Differenzfilter
        * gewichtete Differenz zwischen zentralem Pixel und umliegenden Werten
        * Verstärkung lokaler Intensitätsspitzen
        * negative Ergebnis-Werte sind möglich
            * Laplacian of Gaussian (LoG) Filter (Mexican Hat Filter)
    * Hochpassfilter
        * Hervorhebung von hochfrequenten Teilen des Bildes
        * der visuelle Bildeindruck wird härter
        * feine Strukturen/ hochfrequente Anteile werden hervorgehoben
        * Kanten werden verstärkt/ extrahiert
        * homogene Bildbereiche werden gelöscht
        * Bildrauschen wird verstärkt
    * Kantenfilter/ Gradientenfilter
        * Kanten entstehen durch lokale Änderungen von Intensität oder Farbe
        * mathematisch gesehen ist eine Kante die erste Ableitung der Bildfunktion
        * Übergänge zwischen hell und dunkel (Intensitätsunterschiede) werden vom menschen Sehsystem verstärkt
        * Kantendetektion
            * Prewitt-Operator (Gradientenfilter + Box-Glättung)
            * Sobel-Operator (Gradientenfilter + Orthogonaler Gauß-Filter)
            * Roberts-Operator (nicht sehr richtungsselektiv)

<img title="Gradiationsfilter" src="https://github.com/s92854/FernerkundungS3/assets/134683810/fe0b3fd4-62ee-454d-b5d1-d28e0b6c38c0">

**Prewitt-Operator**

<img title="Prewitt-Operator" src="https://github.com/s92854/FernerkundungS3/assets/134683810/4c9751a7-339b-4ba4-8c94-750fc0afaed3">

**Sobel-Operator**
* wie Prewitt, nur mit Orthogonalem 1D-Gauß-Filter

<img title="Sobel-Operator" src="https://github.com/s92854/FernerkundungS3/assets/134683810/79351ac6-e679-46c4-af2b-66316c704a2f">


**Roberts-Operator**
* nicht richtungsselektiv

<img title="Roberts-Operator" src="https://github.com/s92854/FernerkundungS3/assets/134683810/2269b692-a19c-4bc2-a836-15253cd949f3">


##### Nicht lineare Filter

### Globale Operatoren
* gesamtes Bild

