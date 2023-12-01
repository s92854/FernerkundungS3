# Klassen
* Thematische Klasse: Rasterdatensatz bei dem die DN ein Thema repräsentieren (ID = ID für ein Thema).
* Spektrale Klasse: eine Zusammenfassung spektraler Merkmale in eine thematische Klasse, die ein vordefiniertes Homogenitätskriterium erfüllt.
    * Homogenitätskriterium: DN liegen im Merkmalsraum dicht bei einander (sie bilden eine Häufung bzw. ein Muster.
* Objektklasse: Zielklasse, das Ergebnis der Klassifikation; in diesem Sinne und eine thematische Klasse (s.o)
eindeutige Zuordnung zwischen spektraler- und Objektklasse gewünscht, aber nicht immer möglich

# Erstellung einer Normierung in ERDAS IMAGINE 2022
Folgendes Modell soll modelliert werden:

<img hight=871 title="Normierung" src="https://github.com/s92854/FernerkundungS3/assets/134683810/8de1d304-87c6-4fe6-ba11-8afbb2604ad7">

[Ergebnismodell](https://github.com/s92854/FernerkundungS3/files/13522596/Normierung.zip)

# Klassifizierung
Raster > Unsupervised > Unsupervised Classification

<img width=400 title="Unsupervised Classification" src="https://github.com/s92854/FernerkundungS3/assets/134683810/b6baae1c-4a33-4b38-be91-892d5ecede9f">

# Streudiagramm erstellen
Raster > Supervised > Feature Space Image

Korriliert: Kein starker Unterschied in Intensitätswerten von Pixeln zwischen zwei Kanälen

# Views verbinden
Home > Add Views > New 2D View

In einen View das Frankfurt image, in das andere das Streudiagramm

Raster > Supervised > Signature Editor > Feature > Link Cursors > Viewer: 2 (das mit dem Streudiagramm) > Link > Linksklick in Viewer 1

# AOI-Masken
* Rechtsklick in View > Create new AOI-Layer
* Masken von homogenen Objekten erstellen
* Signature Editor > Create New Signature (from AOI) (Icon mit Pfeil nach unten rechts mit einem Plus) > mehrere Objekte aus AOI Layer erstellen
* .sig abspeichern

<img src="https://github.com/s92854/FernerkundungS3/assets/134683810/09a1b4a5-b43b-4988-86f0-dc52ae5299f0">


# 
