# Solaredge-Battery-Canbus-Protocol
Reverse Engeneering of the proprietary SolarEdge Battery Protocol used with the RWB 
CAN-Bus ID	Bedeutung	Byte 0	Byte 1	Byte 2	Byte 3	Byte 4	Byte 5	Byte 6	Byte 7			Datenart:	
305	Heartbeat												
330	Batteriestatus	Batterienr. 01 bis 05	Batteriekonfiguration: "P16S100" 16 Zellen serielll, 100Ah								ok	ASCII	
331	Batteriestatus		Konstant "A-1757-"										
332	Batteriestatus		Firmwareversion des Batteriemoduls: "1.1402" + 0x00									ASCII	
333	Batteriestatus		Konstant "2201688"										
334	Batteriestatus		Konstant "52CB017"										
335	Batteriestatus		wechselnde feste Daten										
336	Batteriestatus		"Seriennummer der Batterie im Format
SP5122-XXXXXXXXX-XX gefolgt von zwei Blanks.
Codierung: ASCII"									ASCII	
337	Batteriestatus												
338	Batteriestatus												
340	Einzelbatteriedaten	Batterienr. 01 bis 05	0	leer	Leer	Leer	Leer		Cycles?	2D/2E	45/46		
341	Einzelbatteriedaten		0	Spannung Bat unsigned		Ladestrom signed		Leer					
342	Einzelbatteriedaten		0	Identifier?		SOH Batterie 98%		SOC Batterie					
343	Einzelbatteriedaten		0			Niedrigste Zelle Nummer		Höchste Zelle Nummer					
344	Einzelbatteriedaten		0	E8 03		SOC lang/genau, SOC Batterie springt bei 0,2 über x auf x+1		SOH genau 987 aka 98,7					
345			0					0	0				
346	Einzelbatteriedaten		0	Temperaturdaten									
347	Einzelbatteriedaten		0	Temperaturdaten ?		Wiederholung Byte 2+3		Wiederholung Byte 2+3					
348	Einzelbatteriedaten		0	siehe  oben 		siehe oben		siehe oben					
349	Einzelbatteriedaten		0	durchschnittliche Spannung? Kurz oder tiefste Spannung kurz		Zellenspannung max 16 bit unsigned??		Zellenspannung min 16 bit unsigned??					
34A	Einzelbatteriedaten		0	Spannung Zelle 1		Spannung Zelle 2		Spannung Zelle3				16 bit Unsigned	
34B	Einzelbatteriedaten		0	Spannung Zelle 4		Spannung Zelle 5		Spannung Zelle 6				16bit unsigned	
34C	Einzelbatteriedaten		0	Spannnung Zelle 7		Spannung Zelle 8		Spannung Zelle 9				16bit unsigned	
34D	Einzelbatteriedaten		0	Spannung Zelle 10		Spannung Zelle 11		Spannung Zelle 12				16 bit Unsigned	
34E	Einzelbatteriedaten		0	Spannung Zelle 13		Spannung Zelle 14		Spannung Zelle 15				16 bit unsigned	
34F	Einzelbatteriedaten		0	Spannung Zelle 16		leer		leer				16 bit unsigned	
351	Gesamtwert	Max.Ladespannung Konstant 56,6 V		Max Ladestrom 250 A (U16) 5 Batterien a 50A (2850W/56,6V)		Max Entladestrom 400A (U16) ???		Max Entladespannung 40 Volt (U16)????				16 bit unsigned	
355	Gesamtwert	SOC (Abweichung mit Arndt geklärt SE rechnet um)		SOH hier wird immer 98% gesendet,Vermutung auch hier rechnet Se um, um die Fremdbatterien zu disqualifizieren)		10 27 = 10000 permanent? Zu klären		Leer					
356	Gesamtwert	Aktuelle Spannung über alles unsigned integer		Aktueller Ladestrom signed Integer		Temperatur(Umgebung?)		Leer					
357	???	leer im Betrachtungszeitraum		leer im Betrachtungszeitraum		leer im Betrachtungszeitraum		leer im Betrachtungszeitraum					
359	Alarms												
35C	Forced Charge bits												
![grafik](https://github.com/user-attachments/assets/e60c5b48-4a09-4a91-9ab5-3557bfc8ac10)
