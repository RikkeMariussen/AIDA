---
title: RAG workflow
categories: ["RAG"]
tags: ["RAG"]
date: 2026-04-19
draft: false
featureimage: ""
authors:
  - rikke
---

# RAG workflow automatisering

Denne post bygger videre på min post om introduktion til RAG og Dify. Heri fokusere jeg på at lave en automatiseret opdateringen af vidensbasen til min chatbot.

## Formål

Målet for denne problemstilling var at vidensbasen til min chatbot ikke skulle blive forældet ELLER "overcrowded". Dette gøre automatisere opdatering af vidensbasen, så den opdateres når der skubbes noget nyt til github, samtidig med at renser det gamle indhold på dify så der ikke forekommer duplikanter.

---

## Løsningen

Det automatiseret workflow som er bygget med Github Actions:
1. Bygger og deployer porteføljen, via hugo og github pages, ligesom før.
2. Samler indholdet fra porteføljen, så der kun skal læses et dokument
3. Sender dette til Dify som ny vidensbase
4. Slette det gamle data i Dify

Punkt 2-4 er tilføjet til processen for at automatisere opdateringen af chatbottens vidensbase.

Jeg har valgt at benytte github pages frem for et sekundært program med script i, da dette er en simpel og samlet måde. Endvidere behøves der ikke ske opdateringer til vidensbasen på nuværende tidspunkt uden der skubbes nyt indhold til github. 

Hvis der i fremtiden skal benyttes anden viden i min vidensbase såsom enkelt stående dokumenter jeg uploader, skal processen omskrives, således de ikke bare bliver slettet ved næste opdatering. Der kan også i sådanne tilfælde argumenteres for at et sekundært program med sit eget script vil være fordel agtigt. På nuværende tidspunkt kan jeg dog ikke se hvorfor denne specifikke chatbot kunne have behov for en anden viden end mine posts.

### Workflowets struktur
Består således af tre jobs:

#### 1. Build
- Installere dependencies
- Bygger den statiske side (porteføljen)
- Gemmer resultatet som en artefakt

#### 2. Deploy
- Udgiver siden via Github pages

#### 3. Sync-dify
I forbindelse med automatisering af opdateringen for min vidensbase, er dette det vigtigeste punkt.
- Kører efter deploy
- Opdatere min RAGs vidensbase

---

## Hvad har jeg lært?

- Automatisering af opdateringsworkflowet med github pages
- Opdatering af RAG vidensdatabase og hvorfor
- Dify API 

---

## Hvad har været svært?

- At få automatiseringen til at virke ved sekundært program, hvorfor jeg overgik til github pages måden
- Benyttelsen af den korrekte Dify API (knowledge ikke studio) 

---

## Teknologier og værktøjer

- Github actions
- Hugo
- Github pages
- Dify API
- Bash scripting (i min Hugo.yaml)
- RAG

---

## Opsummering

Jeg har fået min automatisering til at virke i forhold til opdatering af indhold i min vidensdatabase. Den bliver opdateret når der skubbes nyt til github actions. Dog kan dette være et problem hvis vidensdatabasen skal udvides til at indeholde dokumenter fra andre steder end min portefølje, da den på nuværende tidspunkt sletter alt der i vidensdatabasen og uploader det nye (opdateret) dokument til vidensdatabasen.