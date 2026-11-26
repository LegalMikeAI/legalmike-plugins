---
name: check-citations
description: >
  Check the legal citations and claims in a text against the primary sources
  with LegalMike. Use when someone asks to check a draft, memo, pleading,
  contract clause, email or AI answer on Dutch or EU law: do the ECLIs and
  articles exist, and do they say what the text claims? Controleer de
  juridische bronnen en beweringen in een tekst tegen de primaire bronnen.
---

# Bronnen controleren met LegalMike

Een verzonnen ECLI of een artikel dat iets anders zegt dan de tekst beweert, is
de fout die een jurist het meest kost. Deze controle zoekt elke verwijzing op in
de bron zelf en zegt per verwijzing of die klopt.

## Werkwijze

1. **De verwijzingen.** Elke ECLI, elk wetsartikel (met wet en zo nodig lid),
   elk CELEX-nummer, elke genoemde uitspraak of roepnaam (*Haviltex*), en elke
   bewering over wat een bron zegt, met de zin uit de tekst waarin ze staat.
2. **Elke bron opzoeken,** één aanroep per bron:
   - met **`legalmike_document`** als die tool er is, met de verwijzing zoals
     ze in de tekst staat (`ECLI:NL:HR:2022:276`, `artikel 7:670 BW`,
     `32016R0679 artikel 6`);
   - anders met **`legalmike_search`**, met een vraag die de bron noemt:
     `Wat oordeelde de Hoge Raad in ECLI:NL:HR:2022:276?` of
     `Tekst van artikel 7:672 BW`. Een kaal nummer is geen vraag en wordt
     geweigerd.

   Bij meer dan tien bronnen: de eerste tien, en zeggen welke zijn
   overgeslagen.
3. **Vergelijken.** Zegt de gevonden passage wat de tekst beweert? Het oordeel
   rust op de passage, niet op wat over de bron bekend is.
4. **Een inhoudelijke bewering zonder bron** gaat, als de gebruiker die getoetst
   wil hebben, als vraag naar `legalmike_reason`.

## Het oordeel

Eén tabel, één rij per verwijzing, in de volgorde van de tekst:

| Verwijzing | Wat de tekst zegt | Oordeel | Bron |
|---|---|---|---|

Met precies deze oordelen:

- **Klopt**: de bron bestaat en zegt wat de tekst beweert.
- **Klopt niet**: de bron bestaat maar zegt iets anders, met een kort citaat van
  wat ze wel zegt.
- **Bestaat niet**: LegalMike vindt geen bron met dit nummer. Een bron die
  LegalMike niet heeft, kan toch bestaan; dit is een signaal, geen bewijs.
- **Niet te verifiëren**: de bron is gevonden maar de passage zegt er niets
  over, of een bron was niet bereikbaar.

In de kolom Bron staat de link uit het resultaat (`ecli_citations`,
`non_ecli_citations` of de passage). Een **Klopt** heeft altijd een link.

Daarna één zin: hoeveel verwijzingen kloppen, en welke als eerste hersteld
moeten worden.

## Grenzen

- Wat niet is opgezocht, is **Niet te verifiëren**.
- De tekst blijft zoals hij is, tenzij de gebruiker om een herstelde versie
  vraagt. Die bevat dan alleen bronnen die in deze controle zijn gevonden, met
  hun link.
- Foutcodes betekenen hetzelfde als in de skill `legal-research`.
