# Lambda Wärmepumpe in Homeassistant #
> Since this model of the heatpump is mainly distributed in german-speaking countries I will keep the documentation in German. Feel free to contact me if a translation is needed!

Hier soll die Integration einer Lambda/Zewotherm Wärmepumpe per Modbus (TCP) in Homeassistant dokumentiert werden. 
Aufgebaut wurde insbesondere auf folgende Arbeiten, vielen Dank an die Autoren!
 - <https://github.com/RalfWinter/lambda-heatpump-modbus-tcp-HA>
 - <https://homeassistant.com.de/homeassistant/modbus-einbindung-lambda-in-home-assistant/>


## Bedienpanel Lambda ##

Screenshots der eingebauten Steuerung (Zugang über VNC):

![Steuerung Lambda](/screenshots/lambda_main.png)
*Bild1: Hauptansicht Steuerung Lambda*


![Steuerung Lambda Detail](/screenshots/lambda_hp.png)
*Bild2: Detailansicht Wärmepumpe Steuerung Lambda*


## Homeassistant ##

Einbindung der Modbus-Register in Homeassistant:
- [configuration.yaml](/configuration.yaml)(bzw. folgendes dort hinzufügen:)
```
modbus: !include modbus.yaml
sensor: !include sensor.yaml
```
- [modbus.yaml](/modbus.yaml) (Auslesen/Schreiben Register)
- [sensor.yaml](/sensor.yaml) (Anzeige Stati als Text)  
  

Ergebnis:  
 :partying_face:  

![Homeassistant Lambda](/screenshots/HA-lambda.png)  
*Bild3: Ansicht in Homeassistant*  

![Homeassistant Lambda Detail](/screenshots/HA-lambda-detail.png)

*Bild4: Detailansicht Register in HA*

## Grafana ##

![Grafana Leistungen](/screenshots/grafana-power.png)  
*Bild5: Leistung (thermisch + elektrisch) in Grafana*



![Grafana Temperaturen](/screenshots/grafana-temp.png)  
*Bild6: Temperaturen (Heizung + Warmwasser) in Grafana*  


Die elektrische Leistung der Heizung (inkl. Steuerung/Pumpen) etc. wird über einen Shelly Pro 3EM gemessen, die Wärmeleistung aktuell noch aus der WP ausgelesen, separate Wärmemengenzähler folgen. 
COP = P<sub>therm</sub>/P<sub>el</sub>

Die Daten sind bei ca. 10°C Außentemperatur entstanden und werden weiterhin beobachtet.  

❄️❄️❄️
