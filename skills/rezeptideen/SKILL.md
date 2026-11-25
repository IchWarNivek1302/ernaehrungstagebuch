---
name: "rezeptideen"
description: "Rezept- und Essensvorschläge passend zum eigenen Vorrat, Abneigungen und restlichen Kalorien/Eiweiß: nutzen bei \"was soll ich kochen\", \"Idee:\", \"hab noch X daheim\", \"ist alle\", \"esse ich nicht\"."
---

# Rezeptideen

Die Person will Vorschläge, die zu dem passen, was sie daheim hat, was sie mag und was heute noch in ihre Ziele passt. Sprache Deutsch, kurz. Daten liegen im Google Sheet des Ernährungstagebuchs.

Tabelle: siehe „Tabelle finden“.


## Tabelle finden (zuerst)
Die Tabelle ist eine Google-Tabelle, deren Name mit „Ernährungstagebuch“ beginnt (z. B. „Ernährungstagebuch – Mama“). Sie kann der Person gehören oder für sie freigegeben sein („Geteilt mit mir“). Einmal pro Gespräch über die Drive-Suche finden (title contains 'Ernährungstagebuch', Typ Tabelle; Dateien mit „Backup“ oder „Vorlage“ im Namen ignorieren) und die ID für das ganze Gespräch merken. Gibt es keine oder mehrere passende Dateien: kurz fragen, welche gemeint ist. Locale de_DE, in Formeln Semikolon.
Beim ersten Mal im Gespräch auch Anweisungen!A1:A40 lesen: Dort stehen Name, Ansprache und persönliche Wünsche (z. B. Unverträglichkeiten). Diese gelten vor den Regeln hier.

## Tab Küche (sheetId 13)
Zeile 3 = Kopf, Einträge ab Zeile 4: A Art | B Lebensmittel | C Notiz.
Art nur: "Immer da", "Gerade da", "Esse ich nicht", "Mag ich gern", "Lieblingsgericht".

## Küche per Satz pflegen
- "Hab daheim: A, B, C" oder "hab noch X" = Zeilen mit Art "Gerade da" (Notiz: Menge, falls genannt).
- "Immer da: ..." = Art "Immer da".
- "Esse ich nicht: Pilze, ..." = Art "Esse ich nicht".
- "Mag ich: ..." / "Lieblingsgericht: ..." = entsprechende Art.
- "X ist alle" = Zeile von "Gerade da" bzw. "Immer da" löschen (bei "Immer da" kurz bestätigen lassen).
- Schreiben: Küche!A4:C300 einmal lesen, neue Zeilen per append_values an Küche!A3:C3, doppelte nicht anlegen. Antwort eine Zeile: "Küche aktualisiert: ...".

## Vorschlag machen
Auslöser: "was soll ich kochen", "Idee: ..." (Lust, z. B. "was Warmes, scharf, schnell"), "Rezept mit X", oder die Person nennt Zusatzvorrat ("hab außerdem X und Y": erst als "Gerade da" speichern).
1. Parallel lesen: Status!A4:B16 (B13 kcal übrig, B14 Eiweiß offen, B16 Woche übrig) und Küche!A4:C300.
2. Rahmen: Ziel pro Portion = kcal übrig für die Mahlzeit (Abends ganz, mittags etwa die Hälfte des Rests), Eiweiß möglichst hoch (mind. 35 g pro Hauptmahlzeit, wenn Eiweiß offen ist). Tageszeit aus der aktuellen Uhrzeit.
3. Regeln: "Esse ich nicht" nie verwenden, auch nicht als Spur oder Alternative. "Gerade da" zuerst verbrauchen, dann "Immer da". Höchstens 2 Zutaten zum Einkaufen, als "(kaufen)" markiert. "Mag ich gern" und "Lieblingsgericht" als Richtung nutzen. Die Lust der Person hat Vorrang. Hinweise aus Tab Anweisungen beachten (z. B. Unverträglichkeiten).
4. Werte nicht schätzen: alle Zutaten als einen Suchbegriff mit | in Suche!B1 schreiben, Suche!A4:P40 lesen, Mengen so wählen, dass die Portion ins Ziel passt. Fehlt etwas: nächstverwandten Eintrag nehmen.
5. Antwort (kompakt):
   - Name, Portionen, pro Portion: X kcal, Y g Eiweiß
   - Zutaten mit Gramm (gesamt)
   - 3 bis 6 kurze Schritte, Zeitangabe
   - letzte Zeile: "Sag 'gekocht, X Portionen gegessen', dann trage ich es ein."
6. Fragt die Person "noch was anderes" oder "mehrere Ideen": 3 Vorschläge mit je einer Zeile (Name, kcal, Eiweiß, Hauptzutaten), auf Wunsch einen ausführen.

## Übergabe ans Tagebuch
Sagt die Person danach "gekocht" oder "gegessen": den Ablauf "Rezepte" des Skills ernaehrungstagebuch ausführen (Rezept anlegen mit den genannten Zutaten und Mengen, Anteil eintragen). Verbrauchte "Gerade da"-Zutaten aus der Küche löschen, wenn die Person sagt, dass sie alle sind.

## Wichtig
- Nur Tab Küche und Suche!B1 beschreiben; alles andere nur lesen.
- Keine Nachfragen vor dem Vorschlag; fehlen Angaben, sinnvoll annehmen.