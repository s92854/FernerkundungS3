# Übung 1: Verrauschte Bilder
Input: 4 verrauschte Bilder mit ungleichem Rauschen

Ziel: Durch Addition der Bilder das Rauschen reduzieren/eliminieren

1. 4 .tif Dateien in IMAGINE laden
2. Toolbox > Spatial Model Editor > 4 .tif Dateien einzeln in den Modeler laden > Nach ADD suchen und Operation in den Modeler ziehen > durch Rechtsklick auf ADD weitere Knoten hinzufügen > Inputs mit ADD Operation verknüpfen > OUTPUT RASTER Operation in Modeler ziehen und ADD Operation mit OUTPUT Operation verknüpfen > Rechtsklick auf OUTPUT RASTER > .img Datei Namen und Location vergeben
3. Exportieren



# Übung 2: Reprojection
Multispectral/Panchromatic > Transform & Orthocorrect > Reproject

<img width="593" alt="image" src="https://github.com/s92854/FernerkundungS3/assets/134683810/11ed31cd-36f0-4dfe-b8af-bd9328a754aa">

<img width="593" alt="image" src="https://github.com/s92854/FernerkundungS3/assets/134683810/31325f7e-95a7-475e-bc13-7601f42d0cf4">

# Übung 3:
Raster > Subset & Chip > Subset > Rechtsklick ins Raster: Inquire Box > Quadrat mit 1km Kantenlänge durch Eingabe von Koordinaten die 1km auseinanderliegen erstellen

# Übung 4: Pansharpening
## RGB to IHS
Raster > Spectral > RBG to IHS

<img width="308" alt="image" src="https://github.com/s92854/FernerkundungS3/assets/134683810/541289be-0c5e-4886-9040-57c300e42633">

# Übung 5: NDVI
Raster > Unsupervised > NDVI

Input: Unsigned 8bit

Häckchen bei Stretch to Unsigned 8bit

## NDVI künstlich einfärben/ Heatmap erzegen
In Attributtabelle fehlt jetzt jedoch die Farbspalte, daher:

Layertype continous > auf thematic ändern:

Metadata > Edit Layertype > thematic

Layer wieder entfernen > Raster Layer öffnen > Raster Optionen > Pseudo Color

Eigentlicher Einfärbeschritt:

Raster > Table > Colors

# Übung 6: Green Leaf Index
## NDVI Modeler
Raster > Unsupervised > NDVI > View > Rechtsklick in Modeler > Save As > "EIFEL_Model_GLI.gmdx"

## Green Leaf Index GLI


# Hauptkomponenteninterpretation
1. Rechtsklick > Rasterlayer laden > Alle 15 Riverlayer auswählen > Multiple > Virtual Stack

2. Raster > Spectral > Layer Stack > .vsk Datei auswählen (alle 15 Layer hinzufügen)

3. Raster > Spectral > Principal Component > Einstellungen wie folgt:

<img width="467" alt="image" src="https://github.com/s92854/FernerkundungS3/assets/134683810/9dab3534-9c0d-4fbf-8d75-d9c9587e84e4">

Eigenwerte: Varianz der einzelnen Hauptkomponenten

$\sqrt{Varianz} = Standardabweichung$   $\sigma$

$Varianz = \sigma^2$

|Kanal|&sigma;|&sigma;<sup>2</sup>|
|---|---|---|
|1|0,396|0,157|
|2|0,063|0,004|
|3|0,035|0,001|
|...|...|...|

Eigenvektoren: Beitrag jedes Ursprungskanals zur jeweiligen Hauptkomponente


### Formatierung in Excel
Dazu öffnen der *.mtx und *.tbl Dateien in Editor und den Punkt (.) durch Komma (,) ersetzen > beide aktualisierten Dateien in Excel laden > *.mtx Tabelle beim Laden mit Leerzeichen trennen und mit bedingter Formatierung einfärben
