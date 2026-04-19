## Projektziele
1. Der Lüfter läuft automatisch **vor**, bevor die Heizung angehen kann.
2. Der Lüfter läuft automatisch **nach**, wenn die Heizung ausgeschaltet wird.
3. Die Heizleistung soll stufenlos verstellbar sein.
4. Es soll einen automatik und einen manuellen Modus geben
    - Im manuellen Modus kann die Heizleistung eingestellt werden
    - Im automatik Modus kann direkt eine Temperatur eingestellt werden
5. Der aktuelle Status soll mit LEDs signalisiert werden
    - z.B. grün: alles in Ordnung, rot: Störung, gelb: Hochlauf
6. Mit einem Schalter soll der Heizlüfter angemacht werden.
7. Es soll nur noch ein Kabel auf den Heizlüfter gehen.
8. Der Ventilator wird ausschließlich mit einer konstanten Drehzahl betrieben

## Grobe Umsetzung
- Es soll eine Leistungsplatine und eine Steuerplatine entworfen werden
    - Leistungsplatine ist für die Schaltung der Spannung für die Leistungsregelung
    - Steuerplatine ist für die Sensorik, LEDs, Gate Treiber etc.
- Es müssen die Nulldurchgänge der Spannung zweier Phasen bestimmt werden, um dann zu schalten
- Arduino Uno als Entwicklungsplattform
- Im Automatikbetrieb Zweipunkt Regelung auf Temperatur einstellbar über Potenziometer
- Im Manuellbetrieb Einstellung der Leistung über dasselbe Potenziometer
### Überisicht über die Sensoren
| Nummer | Sensor |    Aufgabe   |
|:------:|:----------:|:-------------:|
|1|Temperatur|Innentemperaturfühler|
|2|Temperatur|Außerntemperaturfühler|
|3|Potenziometer|Temperatur-/Leistungseingabe|

### Überisicht über die Aktoren
| Nummer | Aktor |    Aufgabe   |
|:------:|:----------:|:-------------:|
|1|Heizwendeln|Heizung|
|2|Lüfter|Wärmeverteilung|
|3|LED grün| Statusangabe|
|4|LED gelb| Statusangabe|
|5|LED rot| Statusangabe|
|6|Lüfter| Kühlung der Leistungselektronik|
|7|Schalter| Ein-/Ausschalten der Anlage|
|8|Schalter| Manuell/Automatik Einstellung|