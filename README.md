## Bachelorarbeit - Ergänzender Anhang zur Datenaufbereitung
### **1. Gelände**
*Aufbereitung des DGM1 aus dem Open GeopPortal des Landesamts für Geoinformation und Landentwicklung Baden-Württemberg unter Verwendung von Optionen des Befehls gdal_translate.*

**1.1 Konvertierung_DGM.txt**
> Verwendet wurde zunächst gdal_translate zur Konvertierung des ursprünglichen Dateifor-mats .xyz in .tif. Da das Zusammenfügen der .tif-Dateien mit der Fehlermeldung einer vertauschten Nord-Süd Auflösung der Daten verweigert wurde, musste an dieser Stelle noch ein Zwischenschritt zur Invertierung der Nord-Süd Ausrichtung der Daten geschehen. Dies gelang mit gdalwap. Schlussendlich konnten die einzelnen .tif-Dateien zusammengefügt werden. Diese wurden dafür zunächst in einem virtual raster table (VRT) als Mosaik der Einzeldateien zusammengefasst (gdalbuildvrt) und anschließend als Gesamtdatei ausgeschrieben (gdal_translate). Durch Angabe der Auflösung von 10 m ∙ 10 m konnte an dieser Stelle die Datenkonvertierung beschleunigt werden, da diese davor bei 1 m ∙ 1 m lag. Eine Reduktion der Auflösung für schnellere Datenkonvertierung an dieser Stelle ist im Rahmen dieser Arbeit vertretbar, da die finale Aufbereitung für das Modellgitter mit Gitterzellenauflö-sung von 50 m ∙ 50 m erfolgt.

### **2. Landnutzung**
*Aufbereitung der ALKIS®-Landnutzungsdaten aus dem Open GeopPortal des Landesamts für Geoinformation und Landentwicklung Baden-Württemberg für ein Gitter mit Auflösung von 50 m ∙ 50 m.*

**2.1 Einteilung_Versiegelungsklassen**
> Ermittlung der versiegelten Fläche in jeder 50 m ∙ 50 m Gitterzelle (=2500 m<sup>2</sup>).

**2.2 Einteilung_Landnutzungsklassen_SQL**
> Einteilung nach Nutzart, Bezeichnung und Versiegelung (Gebäude oder anderweitig versiegelte Flächen z.B. (Park)platz, Straßen) und Zuweisung eines spezifischen Zahlencodes. Zahlencode wurde frei gewählt, darf Anzahl von drei Werten nicht übersteigen, ansonsten fehlerhafte Interpretation in GRAMM.
