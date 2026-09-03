# Morgensamling

Korte, kreative morgensamlinger til en efterskole — med særligt fokus på ordblinde
elever. Et enkelt, statisk website hvor hver morgensamling har sin egen side, og
forsiden giver overblik over alle samlinger.

- **Live site:** https://qvisty.github.io/Morgensamling/
- **GitHub-repo:** https://github.com/qvisty/Morgensamling
- **Projektstatus (Paperclip):** `backlog` — parkeret siden 19. maj 2026 (se [Nuværende status](#nuværende-status))

---

## Formål og vision

Morgensamlinger er en fast del af dagen på mange efterskoler. Målet med dette projekt
er at gøre det nemt for en lærer eller kontaktperson at finde et færdigt, kort oplæg til
morgensamlingen — noget der kan læses op eller vises på skærm på få minutter.

Projektet har et **særligt fokus på ordblinde elever**. Derfor er sitet bygget med et
bevidst dysleksivenligt design: klar og stor typografi, høj kontrast, korte sætninger og
et roligt, overskueligt layout uden støj.

Visionen er et lille, gratis værktøj der sparer forberedelsestid og samtidig er
tilgængeligt for alle elever — også dem der har svært ved at læse.

## Slutmål

Projektet er en del af ClipCores **etape 1**: at finde og køre et første, konkret produkt
frem til et **stabilt månedligt overskud på ca. 1.000 kr.**

For Morgensamling betyder det på sigt:

1. Et brugbart bibliotek af morgensamlinger som efterskoler reelt vil bruge.
2. Dokumenteret trafik til sitet.
3. Valideret betalingsvillighed hos målgruppen (efterskoler / lærere), inden der
   bygges videre eller skaleres.

Det økonomiske mål er **ikke** nået, og betalingsvilligheden er **ikke** valideret. Se
[Mangler](#mangler-på-kort-sigt) nedenfor.

## Nuværende status

**Status: `backlog` (parkeret).**

Sitet er teknisk færdigt og har været **live på GitHub Pages siden 19. april 2026**. Det
indeholder **50 morgensamlinger** for perioden **14. april – 27. juni 2026** (skoleåret
frem til sommerferien).

Projektet blev **parkeret den 19. maj 2026** efter ejerens beslutning. Baggrunden var en
statusgennemgang (Paperclip-issues CLIA-766 og CLIA-2516): sitet fungerer og indholdet er
på plads, men der er ikke drevet trafik til det, og betalingsvilligheden er endnu ikke
undersøgt. Frem for at bygge mere blev projektet sat på pause i afventning af en beslutning
om næste skridt.

**Betingelse for genoptagelse:** Projektet genoptages, når ejeren/board beslutter at
investere i trafik og validering af betalingsvillighed — dvs. når der er en konkret plan
for at bevæge projektet mod det økonomiske slutmål (1.000 kr./md.). Indtil da vedligeholdes
kun det eksisterende (fejlrettelser og dokumentation).

Hvad der virker i dag:

- ✅ Jekyll-site med dysleksivenligt design
- ✅ 50 morgensamlinger publiceret (april–juni 2026)
- ✅ Automatisk deployment til GitHub Pages (GitHub Actions)
- ✅ Forside med kronologisk oversigt; hver samling på egen side
- ✅ 404-fejl på fremtidige datoer rettet (`future: true` i Jekyll-config)

## Planlægning og faser

| Fase | Indhold | Status |
|------|---------|--------|
| 1. Opsætning | Repo, koncept, målgruppe, forretningsmodel i README | ✅ Færdig |
| 2. Site-fundament | Jekyll-site, GitHub Pages, dysleksivenligt design, forside + 3 samlinger | ✅ Færdig |
| 3. Indhold | 47 ekstra morgensamlinger (i alt 50) for hele skoleåret frem til sommerferien | ✅ Færdig |
| 4. Fejlrettelser | Rettet 404 på links/fremtidige datoer | ✅ Færdig |
| 5. Trafik & validering | Drive besøgende til sitet, måle interesse, teste betalingsvillighed | ⏸️ Ikke påbegyndt (parkeret) |
| 6. Monetisering | Beslutte og bygge en betalingsmodel, hvis fase 5 giver grønt lys | ⏸️ Ikke påbegyndt (parkeret) |

Faserne 1–4 er gennemført. Projektet er parkeret **før** fase 5.

## Mangler på kort sigt

Disse punkter er forudsætningen for at genoptage projektet meningsfuldt:

- **Trafik:** Der drives i dag ingen besøgende til sitet. Der mangler en simpel plan for
  at nå målgruppen (fx direkte kontakt til efterskoler, deling i relevante netværk).
- **Validering af betalingsvillighed:** Det er ukendt, om efterskoler/lærere vil betale
  for adgang. Dette skal afklares, før der investeres mere.
- **Beslutning om genoptagelse:** Board/ejer skal tage stilling til, om projektet skal
  fortsætte, forblive parkeret eller lukkes.

## Mangler på lang sigt

Relevant først hvis projektet genoptages og validering er positiv:

- **Betalingsmodel:** Konkret model (fx abonnement, engangskøb, freemium) er ikke besluttet.
- **Løbende indhold:** Nyt indhold til kommende skoleår; i dag dækkes kun frem til
  sommerferien 2026.
- **Redaktionsflow:** Nemmere måde at tilføje/redigere samlinger på end at redigere
  Markdown-filer manuelt (fx et simpelt CMS eller skabelon-workflow).
- **Måling:** Analytics for at følge brug og effekt.
- **Tilgængelighed:** Videre arbejde med WCAG/tilgængelighed ud over det nuværende
  dysleksivenlige design.

## Teknik

Sitet er et **statisk Jekyll-site**, hostet gratis på **GitHub Pages** og deployet
automatisk via **GitHub Actions**.

### Projektstruktur

```
Morgensamling/
├── index.md                 # Forside med oversigt over alle samlinger
├── _layouts/
│   ├── default.html         # Grundlayout (header/footer/typografi)
│   └── samling.html         # Layout for en enkelt morgensamling
├── _samlinger/              # Én Markdown-fil pr. morgensamling (Jekyll collection)
│   └── ÅÅÅÅ-MM-DD-titel.md
├── assets/css/style.css     # Dysleksivenligt design (typografi, kontrast)
├── .github/workflows/pages.yml  # Automatisk build + deploy til GitHub Pages
├── Gemfile                  # Ruby-afhængigheder (github-pages)
└── README.md
```

### Sådan tilføjer du en ny morgensamling

Opret en ny `.md`-fil i `_samlinger/` med front matter:

```markdown
---
layout: samling
title: "Titel på samlingen"
dato: 2026-04-16
tema: mindfulness
---

Indhold her — kort og letlæst.
```

Filnavnet følger mønsteret `ÅÅÅÅ-MM-DD-kort-titel.md`. De 50 eksisterende samlinger
fordeler sig på temaerne: kreativ, diskussion, mindfulness, fortælling, samarbejde,
quiz, bevægelse, natur, humor og musik.

### Lokal udvikling

```bash
bundle install
bundle exec jekyll serve
```

Sitet kan derefter ses på `http://localhost:4000/Morgensamling/`.

### Deployment

Hvert push til `main` udløser workflowet i `.github/workflows/pages.yml`, som bygger
sitet med Jekyll og publicerer det til GitHub Pages. Ingen manuelle trin er nødvendige.

## Links

- **Live site:** https://qvisty.github.io/Morgensamling/
- **GitHub-repo:** https://github.com/qvisty/Morgensamling
- **Paperclip-projekt:** Morgensamling (status `backlog`)
- **Relaterede Paperclip-issues:**
  - CLIA-302 — Start projektet (done)
  - CLIA-364 — GitHub repository for Morgensamling (done)
  - CLIA-646 — Ret fejl på links på forsiden (done)
  - CLIA-766 — Statusgennemgang: Morgensamling (done)
  - CLIA-2516 — Morgensamling: Projekt parkeret (done, 19. maj 2026)
  - CLIA-4052 — Beskrivelser: krav om velbeskrevet README pr. projekt
  - CLIA-4061 — Skriv velbeskrevet README for Morgensamling (denne opgave)

---

*Denne README afspejler projektets faktiske tilstand pr. 3. september 2026. Projektet er
parkeret (`backlog`); indholdet er live og komplet for skoleåret frem til sommerferien 2026.*
