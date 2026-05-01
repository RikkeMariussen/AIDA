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
