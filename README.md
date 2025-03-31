## Bachelorarbeit - Ergänzender Anhang zur Datenaufbereitung
### Geländedaten
*Aufbereitung des DGM1 aus dem Open GeopPortal des Landesamts für Geoinformation und Landentwicklung Baden-Württemberg unter Verwendung von Optionen des Befehls gdal_translate* 

Verwendet wurde zunächst gdal_translate zur Konvertierung des ursprünglichen Dateifor-mats .xyz in .tif. Da das Zusammenfügen der .tif-Dateien mit der Fehlermeldung einer vertauschten Nord-Süd Auflösung der Daten verweigert wurde, musste an dieser Stelle noch ein Zwischenschritt zur Invertierung der Nord-Süd Ausrichtung der Daten geschehen. Dies gelang mit gdalwap. Schlussendlich konnten die einzelnen .tif-Dateien zusammengefügt werden. Diese wurden dafür zunächst in einem virtual raster table (VRT) als Mosaik der Einzeldateien zusammengefasst (gdalbuildvrt) und anschließend als Gesamtdatei ausgeschrieben (gdal_translate). Durch Angabe der Auflösung von 10 m ∙ 10 m konnte an dieser Stelle die Datenkonvertierung beschleunigt werden, da diese davor bei 1 m ∙ 1 m lag. Eine Reduktion der Auflösung für schnellere Datenkonvertierung an dieser Stelle ist im Rahmen dieser Arbeit vertretbar, da die finale Aufbereitung für das Modellgitter mit Gitterzellenauflö-sung von 50 m ∙ 50 m erfolgt.

## Landnutzungsdaten
*Aufbereitung der ALKIS®-Landnutzungsdaten aus dem Open GeopPortal des Landesamts für Geoinformation und Landentwicklung Baden-Württemberg für ein Gitter mit Auflösung von 50 m ∙ 50 m*

