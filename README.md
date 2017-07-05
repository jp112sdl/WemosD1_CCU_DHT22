# Wemos D1 als HomeMatic Temperatur- / Luftfeuchtesensor  

## Folgende Bauteile werden benötigt:
- Wemos D1 Mini
- DHT22 oder AM2302 Sensor
- 1 Taster
- Stromversorgung (z.B. ein Batteriehalter mit 3x AA Batterien)

![Anschlussplan](https://github.com/jp112sdl/WemosD1_CCU_DHT22/blob/master/Images/Anschlussplan.png)

Wenn alles nach obigem Bild verdrahtet wurde, kann das Image ```WemosD1_CCU_DHT22.ino.d1_mini.bin``` auf den Wemos geflasht werden.

## Voraussetzungen: 
- installiertes CUxD-Addon auf der CCU und ein Thermostat-Device 
![NewCUXDDevice](https://github.com/jp112sdl/WemosD1_CCU_DHT22/blob/master/Images/CUxD_Device_erzeugen.png)
mit folgenden Einstellungen in der WebUI:
![NewCUXDDevice](https://github.com/jp112sdl/WemosD1_CCU_DHT22/blob/master/Images/CCU_Geraeteeinstellung.png)

## Konfiguration des Wemos D1
Um den Konfigurationsmodus zu starten, muss der Wemos D1 mit gedrückt gehaltenem Taster gestartet werden.
Die blaue LED blinkt kurz und leuchtet dann dauerhaft. 

Der Konfigurationsmodus ist nun aktiv.

Auf dem Handy oder Notebook sucht man nun nach neuen WLAN Netzen in der Umgebung. 

Es erscheint ein neues WLAN mit dem Namen "WemosD1-xx:xx:xx:xx:xx:xx"

Nachdem man sich mit diesem verbunden hat, öffnet sich automatisch das Konfigurationsportal.

Geschieht dies nicht nach ein paar Sekunden, ist im Browser die Seite http://192.168.4.1 aufzurufen.

![PortalStart](https://github.com/jp112sdl/WemosD1_CCU_DHT22/blob/master/Images/Konfiguration_Startseite.png)

**WLAN konfigurieren auswählen**

![KonfigurationLeer](https://github.com/jp112sdl/WemosD1_CCU_DHT22/blob/master/Images/Konfiguration_Leer.png)

**SSID**: WLAN aus der Liste auswählen, oder SSID manuell eingeben

**WLAN-Key**: WLAN Passwort

**IP der CCU2**: selbsterklärend

**CUxD Device Seriennumer**: Seriennummer des CUxD Devices, meist ```CUX9002001``` für das erste Thermostat-Device

**Übertragung alle x Minuten**: Sende-Intervall. Zwischen den Übertragungen verbleibt der Wemos D1 im DeepSleep Modus, um Energie zu sparen. Je größer die Sendeabstände, desto länger ist die Lebensdauer der Batterien

![KonfigurationBeispiel](https://github.com/jp112sdl/WemosD1_CCU_DHT22/blob/master/Images/Konfiguration_Beispiel.png)

**Beispiel**

**Nach dem "Speichern" startet der Wemos neu und es findet eine Übertragung statt. In der HomeMatic WebUI sollten nun Werte bei dem Temperatursensor zu sehen sein**
