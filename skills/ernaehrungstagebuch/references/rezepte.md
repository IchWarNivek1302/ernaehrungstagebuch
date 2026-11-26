# Rezepte und Anleitungen

Auslöser: „Rezept“ oder Portionsangaben („gibt 4 Portionen, 1,3 gegessen“). Erst Rezept anlegen, dann den Anteil ins Tagebuch.

1. Nährwerte jeder Zutat für die GESAMTE Rezeptmenge ermitteln, inkl. Zusatzwerte (über Suche/Quellen wie beim Eintrag).
2. Neuer Block ab Zeile Status B23 + 2 (eine Leerzeile Abstand), mit update_formulas, nie append_values.
3. Kopfzeile: A Rezeptname | B Portionen | C „pro Portion“ | D–G Formeln ohne Trennzeichen:
   D `=ROUND(SUM(D<erste>:D<letzte>)/$B<Kopf>)`, E–G `=ROUND(SUM(E<erste>:E<letzte>)/$B<Kopf>*10)/10` (entsprechend F, G).
   Darunter je Zutat: A Name | B leer | C Gesamtmenge | D–G Gesamtwerte.
4. Ein update_spreadsheet (sheetId des Tabs Rezepte): Kopfzeile A:G Hintergrund #FCE3C0, fett; Zutaten in A kursiv grau (#59606B); Zutatenzeilen gruppieren (addDimensionGroup) und einklappen.
5. Name allein in A (keine Portionen im Namen).
6. Tagebuch: je Zutat Gesamtwert × gegessene / Portionen, alle Spalten. J = Rezeptname, Menge z. B. „1,3 von 4 Portionen (Anteil von 220 g)“.
7. „Wieder: Rezept, X Portionen“: Rezepte!A5:G bis Zeile B23 lesen, Block nehmen, Zusatzwerte je Zutat über die Suche.

## Anleitung (nur wenn ausdrücklich gewünscht)
Tab Anleitungen A–C (Rezept | Schritt | Anleitung). Kopfzeile #FCE3C0 fett, in A GENAU der Rezeptname wie im Tab Rezepte (ohne Portionen/Klammern) – nur so ordnet die App zu. Darunter: erste Zeile B „Zutaten“, dann nummerierte Schritte, optional „Hinweis“, eine Leerzeile Abstand.
