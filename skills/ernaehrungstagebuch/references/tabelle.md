# Tabelle im Detail (nur bei Bedarf lesen)

- Tabs: Schnell hinzufügen, Tagesansicht, Wochenansicht, Monatsansicht, Verlauf, Tagebuch, Rezepte, Anleitungen, Lebensmittel, Suche, Beschwerden, Auswertung, Status, Zuletzt, Gewicht, Anweisungen. Versteckte Tabs der App (nur lesen): Wochenplan, Vorlagen, Bilder, Rezeptinfo.
- Status!A4:B25 komplett: B5–B7 Ziele (nur hier ändern), B10 heute, B11 kcal gegessen, B12 Eiweiß gegessen, B13 kcal übrig, B14 Eiweiß offen, B15 kcal Woche, B16 Woche übrig, B19 offene Eingangszeilen, B20 letzte Tagebuchzeile, B21 unvollständige Zeilen, B22 Zeilen mit unbekannter Mahlzeit, B23 letzte Rezeptzeile, B24 letzte Lebensmittelzeile, B25 vorläufige Zeilen.
- Nachtrag für einen anderen Tag: Tagessumme aus Wochenansicht!A8:K14 (aktuelle Woche), sonst nur die Mahlzeitwerte nennen.
- Änderungen an Menge/Portionen/Rezept-Zutat: ALLE Spalten der betroffenen Zeilen neu rechnen, bei Rezepten auch schon eingetragene Tagebuchzeilen.
- Fehlen bei einem Lebensmittel Stückgewicht oder Zusatzwerte: neue Zeile mit gleichem Namen, Marke/Variante „ergänzt“, alle Werte. Bei doppelten Treffern die vollständigere nehmen. Packungswerte („Verpackung“) haben Vorrang.
- Nur wenn B20 > 5100 oder B24 > 7450: 500 Zeilen anfügen (appendDimension) und Format einer Datenzeile per copyPaste PASTE_FORMAT übertragen.
- Wochenplan (Datum | Mahlzeit | Art | Name | Portionen | kcal | Eiweiß | Eingetragen | ID): lesen, wenn nach dem Plan gefragt wird.
- Ziele für KH, Fett und Zielgewicht stehen nur in der App.
- Immer kontrastreiche dunkle Schrift. Keine ungefragten Umbauten.
- Training (aus der App, nur lesen, außer ausdrücklich gewünscht): Tab „Training“ (Datum | Plan | Gerät | Gewicht (kg) | Sätze | Wiederholungen | Polster 1–3 | Stufe | Dauer (min) | Notiz | Geräte-ID; pro Tag, Plan und Gerät eine Zeile), versteckt „Trainingspläne“ (ID | Name | Übungen als JSON). Gemeinsame Geräte stehen im Tab „Geräte“ der Besitzer-Tabelle. Fragen zum Training („wie viel habe ich an der Beinpresse?“) daraus beantworten.
