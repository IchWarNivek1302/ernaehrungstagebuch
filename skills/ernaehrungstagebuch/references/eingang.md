# Eingang „Schnell hinzufügen“, Abgleich, Nachpflegen

- „Abgleich“ (aus der App): Status!A4:B25 und 'Schnell hinzufügen'!A4:J30 lesen, alle Einträge und Aufträge erledigen, kurz melden.
- Zeile 4 = Kopfzeile, Einträge ab Zeile 5: Datum | Mahlzeit | Uhrzeit | Was | Menge | kcal | Eiweiß | KH | Fett | Status. Claude schreibt dort nie Einträge.
- Zeilen mit Inhalt in D wie diktierte Einträge behandeln; vorhandene Werte übernehmen, nur Fehlendes ermitteln.
- Erledigte Zeilen nur in A:I leeren (batch_clear_values), J bleibt (Formel). Steht die Kopfzeile nicht in Zeile 4: leere Zeilen darüber löschen.
- In der Antwort nur „plus N aus dem Eingang“.

## Aufträge in Spalte D
- „Auftrag: Rezept vervollständigen „X““: im Rezepte-Block X alle Zutatenzeilen mit „offen“ in B bearbeiten (grob geschrieben, z. B. „TK Lachs“, „1 Pack“). Produkt bestimmen, Packungs-/Stückgewicht nachschlagen. Dann A = sauberer Name, C = Menge mit Gramm („1 Pack (250 g)“), D–G = Gesamtwerte, B leeren (update_values, nur diese Zeilen). Neue Lebensmittel wie üblich. Auftragszeile leeren. Antwort: „Rezept X vervollständigt: N kcal, M g Eiweiß pro Portion.“
- „Auftrag: Bild suchen für Rezept „X““: per WebSearch ein echtes Foto (kein generiertes, kein Wasserzeichen). Direkte https-Bildadresse (.jpg/.png/.webp) in Bilder!D der Zeile mit Rezept X schreiben. Das Script lädt es selbst. Auftragszeile leeren. Antwort: „Bild für X gesucht.“
- „Auftrag: Rezept anlegen – …“: Rezept wie bei „lege Rezept an“ aus dem Text anlegen (Rezepte-Block, Werte, Anleitung, falls Schritte genannt). Nichts ins Tagebuch. Auftragszeile leeren.
- „Auftrag: Anleitung schreiben für Rezept „X““: kurze Zubereitung (4–8 Schritte) passend zu den Zutaten von X im Tab Anleitungen anlegen (Titel = Rezeptname). Auftragszeile leeren.
- Andere Aufträge ausführen (Löschungen nach Bestätigung).

## „Nachpflegen“
Alle Zeilen aus Status B25 (vorläufig) und B21 (unvollständig) normal nachschlagen und korrigieren (alle Spalten). Gefunden: „vorläufig“ aus Menge entfernen; nur geschätzt: „vorläufig“ → „geschätzt“. Danach Auftragszeile leeren.
App-Einträge (Menge endet auf „(App)“) mit leeren K–P: ohne Rückfrage ergänzen, sobald B21 sie nennt. Quelle „Open Food Facts (EAN …)“ = Barcode, wie Packungswerte behandeln.
