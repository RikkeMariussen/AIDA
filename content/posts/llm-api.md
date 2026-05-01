---
title: LLM-API
categories: ["LLM-API"]
tags: ["LLM, API"]
date: 2026-05-01
draft: false
featureimage: ""
authors:
  - rikke
---

# Introduktion til LLM API-integration

Denne post vedrører den femte undervisningsgang i AIDA vi havde den 24/4-'26.

Det her var introduktion til LLM-API integration og kodeagenter, hvor vi går fra at bruge det i et chat vindue og sender frem og tilbage fra forskellige vinduer, til direkte i vores IDE/editor. Denne blogpost er nok meget kort da det fortsætter i posten om praktikvurderingsopgaven. 

## Buzzwords/centrale begreber

### LLM-API integration

At integrere en LLM betyder, at man:
- sender en request til en model via API  
- modtager et svar  
- bruger svaret i sin egen applikation  

Det fungerer ved at:
1. Backend sender system + user prompt  
2. API’en behandler input  
3. Man modtager et svar  
4. Svaret bruges i frontend eller videre logik  

---

### Promptstruktur

En god prompt består typisk af:

- **Systemprompt** → definerer rolle og regler  
- **Userprompt** → selve inputtet  

Struktur er vigtigt, fordi:
- det giver mere stabile svar  
- det gør output lettere at bruge i kode  

---

### Struktureret output

I stedet for fri tekst kan man få modellen til at returnere:

- JSON
- Markdown  
- faste formater  
- bestemte felter  

Fordele:
- lettere at parse  
- kan bruges direkte i kode  
- mindre risiko for fejl  

---

### Asynkron programmering

Når man kalder et API, tager det tid.

Derfor arbejder man ofte asynkront:
- undgår at blokere systemet  
- bedre performance  
- bedre brugeroplevelse  

---

### ETL (Extract, Transform, Load)

LLM-integration minder meget om ETL:

1. **Extract** → hent data (user input / database)  
2. **Transform** → send til LLM og få svar  
3. **Load** → brug resultatet i systemet  

---

### Mental model og beslutningstræ

For at arbejde effektivt med LLM’er, er det vigtigt at have en mental model:

- Hvornår skal LLM’en bruges?  
- Hvornår skal klassisk kode bruges?  

Man kan tænke det som et beslutningstræ:
- Er opgaven deterministisk? → brug kode  
- Er opgaven sproglig/fortolkende? → brug LLM  

---

### Digital forestillingsevne

En vigtig del af arbejdet er at udvikle sin “digitale forestillingsevne”:

- Forestille sig hvad systemet kan gøre  
- Bruge snusfornuft og sjusning  
- Eksperimentere med prompts  

Det handler ikke kun om korrekthed, men også om at kunne tænke i muligheder.

---

## Hvad har vi lavet

Vi er blevet introduceret til det at bruge en LLM-API en i vores applikation.


Formålet var at forstå hele flowet fra:
bruger → backend → LLM → backend → bruger  

---

## Perspektivering

LLM-integration åbner op for:

- intelligente systemer  
- automatisering  
- bedre brugeroplevelser  

Men det kræver:
- god struktur  
- kritisk tænkning  
- forståelse for begrænsninger  

---

## Hvad har vi lært

- ETL 
- Relevansen bag den digitale forestillingsevne
- hvad et Beslutningstræ er


## Opsummering

Vi nåede ikke at påbegynde dagens opgave, men fik en introduktion til Jespers emailprogram, og Jons hjemmeside med AI vurdering for undervisere, og det at lave programmer ved hjælp af LLM'er og LLM-Api. 

Det vigtigste takeaway er, at:
- LLM’er ikke bare er chatbots  
- de kan bruges som en del af et system  