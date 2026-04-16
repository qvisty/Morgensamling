# Morgensamling

Korte, kreative morgensamlinger til efterskoleelever — med saerligt fokus paa ordblinde.

## Om

Et simpelt statisk site med daglige morgensamlinger. Hver morgensamling har sin egen side. Forsiden giver overblik over alle samlinger.

- Hostet gratis paa GitHub Pages
- Dysleksivenligt design (klar typografi, hoej kontrast)
- Bygget med Jekyll

## Brug

Besøg: https://qvisty.github.io/Morgensamling/

## Tilfoej ny morgensamling

Opret en ny `.md`-fil i `_samlinger/` mappen:

```markdown
---
layout: samling
title: "Titel paa samlingen"
dato: 2026-04-16
tema: mindfulness
---

Indhold her...
```

## Lokal udvikling

```bash
bundle install
bundle exec jekyll serve
```
