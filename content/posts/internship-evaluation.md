---
title: Internship-evaluation
categories: ["LLM-API, Internship-evaluation"]
tags: ["LLM, API, Tasks"]
date: 2026-05-01
draft: false
featureimage: ""
authors:
  - rikke
---

# Praktikvurderings-opgave

Denne post vedrører en opgave om at lave en praktikvurderingsprogram ved hjælp af en LLM. Hvor jeg har benyttet OpenAIs API. 

## Buzzwords/centrale begreber

### System-prompt
En systemprompt er en instruktion til modellen, der definerer dens rolle og adfærd.

I denne opgave brugte jeg systemprompten til at:
- definere modellen som en "bedømmer"
- forklare hvordan vurderingen skulle foregå
- sikre at output blev struktureret korrekt

Den fungerer ved at:
1. Definere rollen (fx "du er en underviser")  
2. Beskrive opgaven der skal vurderes  
3. Introducere rubric'en  
4. Bestemme formatet på output  

En god systemprompt gør, at modellen:
- svarer mere præcist  
- følger strukturen  
- undgår irrelevante svar  


---

### Userprompt
Userprompten er den konkrete input, som brugeren sender til modellen.

Her indeholdt den:
- elevens besvarelse
- relevante oplysninger om opgaven
- eventuelle ekstra instruktioner

---

### LLM-API
Et LLM API gør det muligt at sende prompts til en sprogmodel via kode.

Det betyder at man kan:
- automatisere vurderinger
- integrere AI i egne systemer
- bygge egne værktøjer

Jeg brugte OpenAI's API til at sende prompts og modtage svar.

Det fungerer ved at:
1. Man opretter en request i sin kode  
2. Man sender systemprompt + userprompt  
3. API'en behandler inputtet  
4. Man modtager et struktureret svar  

Dette gør det muligt at integrere vurderingssystemet direkte i en applikation.

---

### Rubric
En rubric er et vurderingsskema med kriterier og karakterer.

I denne opgave blev rubric'en brugt til at:
- strukturere vurderingen
- sikre ensartet bedømmelse
- gøre output mere forståeligt

---

## Hvad har vi lært

- Hvordan man arbejder med prompts i kode  
    - Forskellen på systemprompt og userprompt, og hvordan de bruges sammen  
- Hvordan man bruger en LLM gennem API i praksis (integrerer en LLM i en backend) 
- Hvordan man strukturerer output fra en model  
- Hvordan en rubric kan bruges sammen med AI  
- Hvordan man tænker i systemdesign med AI  


## Hvad var svært

- Få en detaljeret systemprompt og userprompt, uden at gøre den enten for generisk eller detaljeret
- At skrive en god systemprompt uden at gøre den for kompleks  
- At få modellen til at følge rubric'en korrekt  
- At få konsistente svar fra modellen  
- At balancere mellem fleksibilitet og struktur  

## Teknologier og værktøjer

- OpenAI LLM-API 
- Claude code
- Java
- Springboot

## Opsummering

I denne opgave har vi arbejdet med at bygge et system, der kan vurdere praktikopgaver ved hjælp af en LLM.

Det har givet indsigt i:
- hvordan man arbejder med prompts  
- hvordan man bruger API'er  
- hvordan man strukturerer AI-output  

Det vigtigste takeaway er, at kvaliteten af resultatet i høj grad afhænger af prompt-designet.


## Andre noter:

- Ved flere "projekter" som agenten skal have adgang til - eventuelt brug
    - Single repo
    - Submodule repo

- Overvejelser
    - Hvordan vil vi bruge LLM 
    - Brug javalin - jeg glemte at specificere dette, så claude brugte springboot
    - Behøver vi database

- Rubric struktur:
    - ned ad: kriterier
    - hen ad: karaktere

## Erfaringer

- Problemer med Python versioner i starten  
- Overvejede at bruge Render (men fravalgt)  
- Endte med at bruge Spring Boot i stedet for Javalin - ren dovenskab, gad ikke ændre det
- Maven i VS var underlig, så åbnede projektet i IntelliJ for at køre Maven og så tilbage.

--- 
# Processen jeg havde

I forbindelse med processen, har jeg til sidst fået claude code, til at lave en opsummering af den process den og jeg havde i forbindelse med opgaven:

# Prompt-design og procesdokumentation

Dette dokument beskriver, hvordan system- og userprompt til praktikrapport-vurderingen blev designet, hvilke valg der blev truffet undervejs, og hvorfor.

---

## Udgangspunkt

Tre kildefiler dannede grundlaget for rubricen:

| Fil | Indhold |
|-----|---------|
| `reference/krav-til-rapport.md` | Formelle krav til rapporten (obligatoriske elementer, omfang på max 12.000 tegn inkl. mellemrum ekskl. bilag) |
| `reference/dare-share-care.md` | EKs tre kerneværdier: DARE (mod og initiativ), SHARE (videndeling og fællesskab), CARE (ansvar og omsorg) |
| `reference/laeringsmaal.md` | Studieordningens læringsmål opdelt i Viden, Færdigheder og Kompetencer |

---

## Systemprompt – rubric-design

### Rolle og tone

AI'en gives rollen som en erfaren underviser på EK. Vurderingen skal være **faglig, konstruktiv og konkret** — hvert punkt begrundes med direkte referencer til rapporten.

### De 6 dimensioner

Rubricen dækker alle krav fra de tre kildefiler fordelt på seks dimensioner:

1. **Formelle krav** — er alle obligatoriske elementer til stede, og er omfanget overholdt?
2. **Læringsmål: Viden** — viser den studerende viden om virksomhedens daglige drift?
3. **Læringsmål: Færdigheder** — er tekniske metoder, problemvurdering, planlægning og formidling dokumenteret?
4. **Læringsmål: Kompetencer** — er der eksempler på selvstændig tilegnelse af ny viden og fagligt samarbejde?
5. **DARE / SHARE / CARE** — afspejles EKs tre kerneværdier i rapporten?
6. **Refleksionsdybde** — kobler rapporten praksis til teori, og rummer den ægte selvkritik?

### Niveauer og karakterer

Hvert niveau fik i en iteration tilknyttet en indikativ karakter på 7-trinsskalaen, så vurderingen er direkte anvendelig i en eksamenskontekst:

| Niveau | Karakter |
|--------|----------|
| Fremragende / Stærkt tilstede / Dyb / Opfyldt | 10–12 |
| Tilfredsstillende / Tilstede / Overfladisk | 7 |
| Under forventning / Fraværende / Beskrivende | 02–4 |
| Ikke opfyldt | 00 |

Formelle krav behandles separat da det primært er et godkendt/ikke-godkendt-kriterium.

### Outputformat

Outputformatet blev fastlagt til at indeholde fem sektioner i fast rækkefølge:

1. **Samlet vurdering** — 2–3 sætninger om rapportens overordnede styrker og svagheder
2. **Rubric-oversigt** — tabel med Dimension / Niveau / Karakter / Begrundelse
3. **Stærke punkter** — konkrete eksempler fra rapporten
4. **Udviklingsområder** — konstruktive forslag til forbedring
5. **Spørgsmål til mundtlig eksamen** — 3–5 spørgsmål der uddyber interessante eller uklare punkter

### Tilføjet undervejs: Konklusion

Efter den første testkørsel blev der tilføjet en sjette outputsektion:

6. **Konklusion** — samler rubric-scoren i én samlet karakterindikation og forklarer konkret hvilke dimensioner der trækker op og ned, samt hvad der ville have løftet rapporten mest.

---

## Userprompt – skabelon

### Design-principper

Userprompt'en er en **skabelon** der tilpasses per studerende. Den holder tre ting adskilt:

- **Reference til systemprompten** via `@prompts/system-prompt.md`
- **Eksaminator-noter** — rapport-specifikke oplysninger (tegntælling, antal bilag, anonymisering)
- **Selve rapporten** via `@data/studentX.md`
- **Instruktion om gemning** — output gemmes i `output/studentX-vurdering.md`

### Brug i Claude Code

Filerne er designet til at bruges med Claude Codes `@`-syntaks, som automatisk indsætter filindholdet:

```
@prompts/user-prompt.md
```

Denne ene reference trækker automatisk både systemprompten og rapporten ind.

### Brug i andre interfaces

Kopier indholdet af `system-prompt.md` til system-feltet og `user-prompt.md` (med rapportindhold indsat) til bruger-feltet i fx Claude.ai eller ChatGPT.

---

## Iterationer og begrundelser

| Iteration | Ændring | Begrundelse |
|-----------|---------|-------------|
| 1 | Grundlæggende rubric med 6 dimensioner og 3 niveauer | Dækker alle formelle krav og EK-værdier |
| 2 | Tilføjet karakter på 7-trinsskalaen ved hvert niveau | Direkte anvendelig til eksamenskarakter |
| 3 | Tilføjet Karakter-kolonne i outputtabellen | Giver hurtig overblik under eksamination |
| 4 | Tilføjet Konklusion-sektion i output | Samler vurderingen i én handlingsrettet opsummering |
| 5 | Rapportindhold erstattet med `@`-filreference i userprompt | Undgår at kopiere hele rapporten manuelt |
| 6 | Instruktion om at gemme output i `output/studentX-vurdering.md` | Sikrer sporbarhed og nem genfinding |

---

## Teknisk rejse – fra idé til kørende applikation

Udover prompt-designet blev der udviklet en webapplikation til at køre vurderingerne. Processen var ikke ligetil.

### Første plan: Python + FastAPI med deploy på Render

Den oprindelige plan var en Python-backend (FastAPI) med en React-frontend, deployeret på Render.com (backend) og GitHub Pages (frontend). API-nøglen skulle gemmes som GitHub Secret og sendes automatisk til Render via GitHub Actions ved hvert push til `main`.

**Problemer der opstod:**

- **Python 3.14 for ny:** Den installerede Python-version (3.14) var for ny til at OpenAI SDK'et (v1.51) fungerede korrekt. Fejlen var `TypeError: Client.__init__() got an unexpected keyword argument 'proxies'` — et inkompatibilitetsproblem mellem OpenAI SDK og den version af `httpx` der fulgte med Python 3.14.

- **Render Blueprint fandt ikke `render.yaml`:** Render kræver at `render.yaml` ligger i roden af repo'et. Filen lå fejlagtigt i `app/backend/`, og Render kunne derfor ikke finde den og afviste Blueprint-oprettelsen.

- **Render-dashboardet var forvirrende:** Forsøg på at navigere direkte til service-URL'er i Render resulterede i "Page not found"-fejl, fordi services endnu ikke var oprettet. Blueprint-flowet er det korrekte indgangspunkt, ikke manuel oprettelse af enkeltservices.

- **API-nøgle eksponeret i chat:** Under opsætningen blev en Render API-nøgle ved en fejl delt direkte i chatten. Nøglen blev straks invalideret og erstattet med en ny. Læring: API-nøgler må aldrig deles i chat, terminal-output eller andre usikrede kanaler — de gemmes udelukkende i `.env`-filer (lokalt) eller secrets-systemer (GitHub Secrets, Render environment).

### Løsning: Skift til Java + Spring Boot, kør lokalt

Da Python-versionsproblemet viste sig svært at løse hurtigt, og Render-opsætningen drillede, blev beslutningen taget om at:

1. **Skifte backend til Java + Spring Boot** — Java er mere stabilt på Windows, og IntelliJ IDEA håndterer Maven-projekter uden at kræve separat installation af byggeværktøjer.

2. **Droppe cloud-deployment og køre lokalt** — Kompleksiteten ved Render + GitHub Actions + secrets-pipeline var uforholdsmæssig stor for et internt undervisningsværktøj. Applikationen kører i stedet lokalt med `mvn spring-boot:run` (backend) og `npm run dev` (frontend).

**Yderligere tekniske udfordringer undervejs:**

- **Arbejdsmappen var forkert:** IntelliJ kørte Spring Boot fra projektroden (`praktikvurdering/`) i stedet for `app/backend/`. Det betød at relative stier til `data/`, `prompts/` og `output/` pegede forkert. Løsningen var at gøre stierne konfigurerbare via `application.properties` med niveauer tilpasset IntelliJs arbejdsmappe.

- **`.env`-filen blev ikke fundet:** `dotenv-java`-biblioteket ledte efter `.env` i arbejdsmappen (`praktikvurdering/`), men filen lå i `app/backend/`. Stien til dotenv-opslaget blev hardkodet til `app/backend/` relativt til arbejdsmappen.

- **Referencefiler dukkede op i dropdown:** `laeringsmaal.md`, `dare-share-care.md` og `krav-til-rapport.md` lå i `data/`-mappen og blev vist som valgbare rapporter. De blev flyttet til en separat `reference/`-mappe.

- **Frontend crashede ved backend-fejl:** Når backenden returnerede HTTP 500, parsede frontenden fejlsvaret som JSON og satte `reports`-state til `undefined`, hvilket crashede `ReportSelector`-komponenten. Fejlen blev rettet ved at tjekke `response.ok` inden JSON-parsing og anvende `?? []` som fallback.

### Hvad der ville have gjort det nemmere

- Installere Python 3.12 (LTS) frem for 3.14 fra start
- Placere `render.yaml` i roden af repo'et fra begyndelsen
- Afklare IntelliJs arbejdsmappe-konvention inden stier blev hardkodet

---

## Filer

```
prompts/
├── system-prompt.md   ← Rubric og instruktioner til AI'en
├── user-prompt.md     ← Skabelon til vurdering af én rapport
└── PROCES.md          ← Dette dokument
```

Referencematerialet der dannede grundlag for rubricen ligger i:

```
reference/
├── krav-til-rapport.md
├── dare-share-care.md
└── laeringsmaal.md
```
