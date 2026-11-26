---
name: "ernaehrungstagebuch"
description: "Ernährungstagebuch im Google Sheet führen: sofort nutzen bei \"trag ein\", \"ich hab gerade XYZ gegessen\", \"lege Rezept an\", Beschwerden oder Fragen nach Tageswerten."
---

# Ernährungstagebuch

Die Person sagt (oft per Sprache, ungeordnet), was gegessen wurde. Werte ermitteln, direkt ins Google Sheet eintragen, kurz antworten. Deutsch. Ausreden lassen.

## Tabelle finden (einmal pro Gespräch)
Google-Tabelle, deren Name mit „Ernährungstagebuch“ beginnt (eigene oder „Geteilt mit mir“). Über die Drive-Suche finden (title contains 'Ernährungstagebuch', Typ Tabelle; „Backup“/„Vorlage“ ignorieren), ID merken. Mehrere/keine: kurz fragen. Locale de_DE.
Beim ersten Mal auch Anweisungen!A1:A40 lesen: Name, Ansprache, Wünsche (z. B. Unverträglichkeiten). Diese gehen vor.

## Grundhaltung
- Nie vorher nachfragen. Unklares (Menge, Stückgewicht, Marke, Zubereitung, Uhrzeit, Mahlzeit) sinnvoll entscheiden, eintragen, danach knapp nennen. Korrekturen kommen von selbst.
- Löschen nur nach kurzer Bestätigung.
- Werte nachschlagen (Quellen unten), nicht aus dem Gedächtnis.

## Stichwörter
- Ohne Stichwort: normaler Eintrag. Marke/Geschäft + Gramm = genau dieses Produkt.
- Foto mit weißer Textleiste „Auftrag an Claude: …“ (kommt aus der App, oft ohne weiteren Text): den Auftrag in der Leiste so ausführen, als hätte die Person ihn geschrieben; das Essen auf dem Foto erkennen und Mengen schätzen.
- Foto mit weißer Textleiste unten („📝 Trag ein: …“) kommt aus der App: der Text in der Leiste ist der Auftrag, genau so ausführen (Essen auf dem Foto erkennen, Mengen schätzen, eintragen).
- „Kurz: …“ = Sparmodus: höchstens eine Websuche für alles, Unsicheres mit „vorläufig“, nichts weiter recherchieren.
- „wie gewohnt / wie immer / wie gestern“ = Zeile aus Tab Zuletzt übernehmen (neues Datum, neue Uhrzeit).
- „Packung: Produkt, kcal/Eiweiß/KH/Fett pro 100 g“ = Werte übernehmen, Quelle „Verpackung“, keine Suche.
- „Nachtrag [Tag, Uhrzeit]: …“ = anderer Tag / frühere Uhrzeit. „Korrektur: …“ = Zeilen ändern, alle Spalten neu rechnen.
- „Stand“ = nur Status lesen und antworten. „Gewicht: 82,4“ = Zeile an Tab Gewicht anhängen (Datum | Uhrzeit | kg | Notiz).
- „Beschwerde: was, Stärke 1–10, Uhrzeit“ = an Beschwerden anhängen (Datum | Uhrzeit | Beschwerde | Stärke | Notiz).
- Rezept anlegen oder ändern („Rezept: …“, „Rezept anlegen …“, „lege Rezept an“, „Wieder: Rezept, X Portionen“ oder Portionsangaben wie „gibt 6 Portionen“) → erst `references/rezepte.md` lesen, dann genau danach vorgehen.
- „Abgleich“, „Nachpflegen“ oder Status B19 > 0 (Eingang „Schnell hinzufügen“) → erst `references/eingang.md` lesen.

## Zeile im Tagebuch (A–P, nichts leer außer J)
Datum (ISO) | Uhrzeit (HH:MM) | Mahlzeit | Zutat | Menge | kcal | Eiweiß | KH | Fett | Rezept | Zucker | Ballaststoffe | Salz (g) | Süßstoff | Laktose (g) | Koffein (mg)
- Mahlzeit nur: Frühstück, Mittagessen, Abendessen, Snacks / Sonstiges. Datum fehlt = heute, Uhrzeit fehlt = jetzt, Mahlzeit aus der Uhrzeit.
- Eine Zeile pro Zutat. Wert pro 100 g × Gramm / 100; kcal ganzzahlig, Rest auf 0,1.
- Zusatzwerte K–P immer füllen: nachschlagen, sonst typisch schätzen (Salz = Natrium × 2,5; Laktose 0 bei Nicht-Milchprodukten; Koffein 0). Süßstoff „nein“ oder „ja (Art)“.
- Menge kurz (≤ 40 Zeichen) mit Gramm und Quelle, z. B. „2 Scheiben (16 g, fddb)“. Unsicheres mit dem Wort „vorläufig“.
- Zutaten ohne kcal (Salz, Gewürze) eigene Zeile. Rein manuelle Angaben („120 kcal, 5 g Eiweiß“): eine Zeile, Rest schätzen.

## Quellen (in dieser Reihenfolge, sparsam)
1. Eigene Datenbank über Tab Suche (nie Lebensmittel direkt lesen). Ohne Marke reicht fast immer der BLS-Eintrag mit passender Zubereitung (roh/gekocht/abgetropft).
2. Markenprodukt fehlt: EINE WebSearch je Produkt mit allowed_domains ["fddb.info"], parallel für mehrere. WebFetch nur, wenn Werte fehlen.
3. Nichts Brauchbares: eine Suche ohne Filter, dann nächstbesten Wert mit „vorläufig“.
- Alles aus Stufe 2/3 und angenommene Stückgewichte (Quelle „Annahme“) als Zeile in Lebensmittel anhängen (A–P: Name | Marke/Variante | kcal | Eiweiß | KH | Zucker | Fett | Ballaststoffe | Portion | g pro Portion | Quelle | Stand ISO | Salz | Süßstoff | Laktose | Koffein; pro 100 g).
- Eigenmarken: Kaufland = K-Classic, Lidl = Milbona/Pilos, Aldi = Milsani, Rewe = ja!, Edeka/Netto = Gut & Günstig.

## Ablauf (3 Runden, alles in einer Runde parallel)
1. Status!A4:B25 lesen und alle Zutaten als EINEN Suchbegriff in Suche!B1 schreiben (klein, Wortstamm, mit |, z. B. „hühnerei|ketchup|knusperbrot“).
2. Suche!A4:P40 und Zuletzt!A2:Q11 lesen. Schon Gegessenes gleich rechnen wie zuletzt. Fehlendes parallel suchen (Quellen).
3. EIN Schreibvorgang je Tab: alle Zeilen an Tagebuch!A1:P1 anhängen, neue Lebensmittel an Lebensmittel!A1:P1 – parallel. Status NICHT erneut lesen: übrig = B13 bzw. B14 aus Runde 1 minus dieser Eintrag.

## Antwort
„Okay [Name aus Anweisungen], [Mahlzeit] eingetragen: X kcal, Y g Eiweiß. Heute noch übrig: Z kcal, W g Eiweiß.“ (Z negativ: „über dem Ziel um … kcal“)
Zweite Zeile nur bei Neuem, in Stichworten: „Angenommen: Ei 54 g. Nicht gefunden: …, Ersatz …“. Keine Zutatenlisten, Quellen oder Rechenwege, außer gefragt.

## Tabelle (Kurzfassung)
- Status!A4:B25: B5–B7 Ziele (kcal/Tag, Eiweiß/Tag, kcal/Woche), B11 kcal heute, B12 Eiweiß heute, B13 kcal übrig, B14 Eiweiß offen, B19 offene Eingangszeilen, B20 letzte Tagebuchzeile, B21 unvollständige Zeilen, B23 letzte Rezeptzeile, B24 letzte Lebensmittelzeile, B25 vorläufige Zeilen.
- Zuletzt!A2:Q11 füllt sich aus Suche!B1 (A = Tagebuchzeile, B–Q = Tagebuch A–P).
- append_values nur für Tagebuch, Lebensmittel, Beschwerden, Gewicht. Ansichten und Formeln nie anfassen, nie formatieren oder sortieren. Tab-Namen und Spalten nicht ändern (eine App liest mit).
- Mehr Details nur bei Bedarf (auch Fragen zum Training): `references/tabelle.md`.
