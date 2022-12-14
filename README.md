# USB

USB 1.0 und USB 1.1 unterscheiden sich nur durch die maximale Stromstärke (100 mA bzw 500 mA). USB 2.0 
verwendet genau dieselben Stecker und Buchsen wie USB 1.x und kann bis 900 mA liefern; der Hauptunterschied
ist aber der neue Hi-Speed Modus, der bis zu 40 MByte/s (480 MBaud) liefern kann - im Gegensatz zu den alten beiden
Modi Low-Speed (150 kByte/s, 1,5 MBaud) und Full Speed (1 MByte/s, 12 MBaud). 

USB 3.0 erforderte dann eine Änderung der Stecker - es gibt mehr Kabel, die Datenrate steigt mit USB 3.0 SuperSpeed auf
5 GBaud brutto. Das sind die blauen Stecker.
USB 3.1 "Superspeed" verdoppelte die Geschwindigkeit auf 10 GBaud brutto und mit einem effizienteren Leitungscode 1,2 GByte/s netto.
USB-3.0 ging in USB 3.1 auf und heißt nun USB 3.1 Gen 1.

USB 3.2 verdoppelt die Datenrate auf 20 GBaud mit einem USB-C Stecker an jedem Kabelende. Es hat 3 Datenraten, USB3.2Gen1 mit 5 GBaud
(identisch zu USB 3.0 was auch USB 3.1 Gen 1 genannt wird), USB3.2 Gen2 mit 10 GBaud (identisch zu USB 3.1 was auch USB 3.1 Gen 2 genannt wird),
und USB 3.2 Gen2x2 mit den 20 GBaud.

USB Geräteklassen. Klasse 0 ist das composite device, 1 ein Audiodevice (Lautsprecher, Mikrofon, Soundkarte), 3 ein HID (Tastatur, Maus...),
8 ein Massenspeicher wie eine Festplatte oder ein USB-Stick.

Es gibt bis zu 15 In- und 15 Out-Endpunkte, und den Control-Endpunkt 0 (der I/O ist).

Der isochrone Transfer wird für Audio verwendet. In Full-Speed können je Millisekunde bis zu 1023 Byte je Endpunkt übertragen werden,
Hi-Speed je Mikroframe (125 us) bis zu 1024 Byte. Im Prinzip könnten mehrere Endpunkte gleichzeitig genutzt werden, aber bei Full Speed ist
man mit einem einzigen Endpunkt schon bei 81% der maximalen Gesamtdatenrate. Isochroner Transfer ist für Full-Speed und Hi-Speed Geräte
möglich.
Bei 16 bit Audiodaten und 192 kS/s hat man 384 kByte/s pro Kanal, oder 384 Byte/ms. Selbst Stereo lässt sich also noch über Full-Speed
übertragen. Hi-Speed oder USB 3.0 braucht man also so schnell nicht; bei 48 kHz SR kann ich theoretisch 10 Mikrofone parallel über Full Speed
anschließen.

USB Audio hat mindestens 2 Klassen, UAC1 und UAC2 oder Class 1 und Class 2. Alte Windowsversionen unterstützten nur Class 1, Class 2 gibt es
erst seit einer bestimmten Windows-10 (!) Version. Class 1 kann 24 bit bis zu 96 kHz, aber höhere Sampleraten gehen nur mit 16 bit. Class 2
unterstützt auch 192 kHz SR bei 24 bit Genauigkeit. Android kann kein Class 2. Generell unterstützt UAC1 nur Full Speed (mehr nicht) und ein
1 ms Frame (was anderes macht Full Speed ja auch nie). UAC2 kann High Speed - ab USB 2.0 steht High Speed zur Verfügung also gibt es keine
sinnvolle Anwendung von UAC2 auf USB1.x Geräten. UAC2 ist nicht rückwärtskompatibel zu UAC1, d.h. ein Gerät muss sich entweder als UAC2 oder als
UAC1 Gerät anmelden. Beides geht nicht. UAC1 ist schnell genug für 192 kHz SR, 16 bit stereo (pro Endpoint), nicht aber für mehr. 


USB links
https://www.esp32.com/viewtopic.php?t=8732
https://www.hackster.io/news/create-custom-usb-devices-with-the-esp32s2stick-458bf370a522
https://hackaday.com/2021/03/26/usb-comes-to-the-esp32/
https://www.kampis-elektroecke.de/mikrocontroller/avr8/at90usb1287-usb/usb-device/
https://www.mikrocontroller.net/articles/USB-Tutorial_mit_STM32
https://arduino.stackexchange.com/questions/81749/how-to-get-the-esp32s2-recognized-as-usb-device
https://www.reddit.com/r/esp32/comments/n0cevt/esp32_as_spoofed_usb_audio_inputoutput/
https://www.fambach.net/esp32-s2/

