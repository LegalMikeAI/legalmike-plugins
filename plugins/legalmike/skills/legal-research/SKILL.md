---
name: legal-research
description: >
  Research a question of Dutch or EU law with LegalMike and present the answer
  with a working link to every ruling and article. Use when someone asks about
  Dutch or EU law and the sources matter: case law and ECLIs, statutes,
  disciplinary law, local regulations, EU law, the ECHR, dispute committees,
  parliamentary papers or legal literature; or asks to find a ruling or
  article, or to support a position with sources. Juridisch onderzoek naar
  Nederlands en Europees recht, met een link naar elke uitspraak en elk
  artikel.
---

# Juridisch onderzoek met LegalMike

LegalMike doorzoekt de primaire bronnen van het Nederlandse en Europese recht en
schrijft een antwoord waarin elke bron een link heeft. Met die link kan een
jurist een standpunt verantwoorden: de uitspraak of het artikel is te openen.

## De tools

- **`legalmike_reason`**: een geschreven antwoord, waarin elke bronvermelding is
  gecontroleerd tegen de gevonden passages.
- **`legalmike_search`**: de gevonden passages, zonder antwoord. Voor wie de
  bronnen zelf wil lezen of wil weten wat er over een onderwerp bestaat.
- **`legalmike_document`**: één bron volledig: een wetsartikel met het
  commentaar van LegalMike als dat er is, een uitspraak bij ECLI, of een
  EU-artikel of -arrest bij CELEX. Ook om een bron uit een eerder antwoord te
  openen.

## De aanroep

1. **Eén aanroep per vraag.** De server splitst een samengestelde vraag zelf op
   en zoekt de delen tegelijk.
2. **Een vraag die op zichzelf staat.** Zet de feiten uit het gesprek die ertoe
   doen in `question`: wie, wat, wanneer, welk contract of welke beslissing.
   Gespreksgeschiedenis hoeft niet mee.
3. **`context`** is de rol, als die uit het gesprek blijkt: `ik treed op voor de
   werknemer`, `wij zijn de verhuurder`. Blijkt de rol niet, dan blijft het
   veld leeg.
4. **`mode`** blijft leeg, zodat de server de diepgang kiest. `short` of `long`
   alleen als de gebruiker om een kort of een uitgebreid antwoord vraagt.
5. **`restrict_to_sources`** alleen als de gebruiker zegt in welke bronnen
   gezocht moet worden.
6. **Een antwoord duurt 30 tot 60 seconden.** Dat is de normale duur.

## Het antwoord

- **Het antwoord van `legalmike_reason` is af.** Het is geschreven voor de
  lezer, met elke bron op zijn plaats. Bij samenvatten verdwijnt de rechtspraak
  het eerst, dus het werkt het best volledig weergegeven.
- **Elke link blijft bij zijn verwijzing,** ook als dezelfde bron verderop
  terugkomt. `art. 7:669 BW` zonder link, waar het antwoord
  `[artikel 7:669 BW](https://wetten.overheid.nl/...)` gaf, leest nog als
  bronvermelding maar opent niets.
- **Wie zelf een uitspraak of artikel noemt,** vindt de link in
  `ecli_citations` of `non_ecli_citations` in het resultaat.
- **Wat niet uit het resultaat komt, heeft geen gecontroleerde vindplaats.**
  Wordt het toch toegevoegd, dan staat erbij dat het niet uit de bronnen van
  LegalMike komt.
- **Een bron die niet bereikbaar was,** noemt het antwoord in één zin. Die zin
  hoort erbij: een antwoord zonder rechtspraak is iets anders dan een antwoord
  waarin de rechtspraak is gewogen.
- **Taal.** Het antwoord is Nederlands. Met `language` op `en` komt het in het
  Engels; juridische begrippen en geciteerde wetstekst blijven Nederlands.

## Foutcodes

De fout heeft een `code`; die is leidend, niet de tekst.

| Code | Wat het betekent |
|---|---|
| `free_questions_used` | De gratis vragen zijn op. De melding bevat een link naar de abonnementen; opnieuw proberen helpt niet. |
| `subscription_required`, `quota_exceeded` | Geen abonnement, of de maandlimiet is bereikt. Opnieuw proberen helpt niet. |
| `rate_limited` | Te veel vragen tegelijk. De melding noemt na hoeveel seconden het weer kan. |
| `invalid_argument` | Een parameter klopt niet. De melding noemt de parameter en de toegestane waarden. |
| `sources_unavailable`, `upstream_timeout` | De bronnen zijn nu niet bereikbaar. Er is dan geen onderzoek gedaan. |
| `no_evidence` | LegalMike vond geen bronnen. Meer feiten of een andere formulering kan helpen. |
