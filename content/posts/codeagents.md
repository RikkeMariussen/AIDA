---
title: Code agents
categories: ["Code agents"]
tags: ["Code agents"]
date: 2026-04-20
draft: false
featureimage: ""
authors:
  - rikke
---

# Introduktion til Kodeagenter

Denne post vedrører den fjerde undervisningsgang i AIDA vi havde den 20/4-'26.

## Buzzwords/centrale begreber

### Assistent vs. agent

**Assistent:** 
- Kan blive spurgt om ting  
- Giver svar, forslag og forklaringer  
- Du styrer hele processen  

**Agent:**
- Kan gøre ting (tage handling)  
- Kan selv planlægge og udføre opgaver  
- Har en grad af autonomi  

*Control flow*
- Assistent: You control the loop
- Agent: It controls the loop 

*Time horizon*
- Assistent: One-shot (eller korte samtaler)
- Agent: Long-running tasks 

*State management*
- Assistent: Context -> prompt window
- Agent: Context -> environment (files, memory, logs)


### Kode agenter

- Codex
- Claude code  
    - I forbindelse med forløbet blev vi bedt om at vælge at bruge en af disse og jeg valgte claude code.
    
En kode agent kan godt finde på at lyve, for at gøre dig glad.

*Tips fra Jesper*
- 90 % i Plan mode og 10 % lad den kode
- Husk at få den til at lave en readme så når man efter fire måneder kommer tilbage, at man kan se hvordan det er sat op, hvad det kan og hvordan man kører programmet.
- Lav en todo fil - hvad mangler programmet

En kodeagent er en AI, der ikke kun kan foreslå kode, men også:
- skrive og ændre filer  
- navigere i projekter  
- debugge kode  
- tage beslutninger baseret på kontekst  


**Horizontal agents vs. Vertical agents:**

*Horizontal:*
- Bred funktionalitet  
- Kan bruges på tværs af mange domæner  
    - Eksempel: ChatGPT  

*Vertical:*
- Specialiseret til ét domæne  
- Ofte mere præcise inden for deres område  
- Eksempel: en kodeagent eller en kundeservice-bot  

---

### Hvad er en kodeagent:

En kodeagent er en AI-drevet agent, der kan:
- analysere kodebaser  
- planlægge ændringer  
- implementere funktionalitet  
- teste og justere løsninger  

**Hvordan vælger man det rigtige værktøj**

Når man vælger en kodeagent, bør man overveje:

- Kompleksitet af opgaven  
  → Skal den bare hjælpe, eller arbejde selvstændigt?

- Kontrol vs. automation  
  → Vil du selv styre alt, eller lade agenten tage over?

- Pålidelighed  
  → Hvor kritisk er det, at koden er korrekt?

- Integrationer  
  → Skal den kunne arbejde med filer, GitHub, API’er osv.?

I mit tilfælde valgte jeg Claude Code, fordi:
- Skriv noget her  

**Hvordan arbejder en kodeagent**

Det fungerer typisk sådan:

1. Du giver en opgave (prompt)  
2. Agenten laver en plan  
3. Den udfører handlinger (skriver kode, ændrer filer)  
4. Den evaluerer resultatet og itererer  

Dette minder meget om en udviklers arbejdsproces.


## Hvad har vi lært

- Forskellen mellem en assistent og en agent  
- Hvordan kodeagenter kan automatisere udviklingsopgaver  
- Vigtigheden af planlægning før eksekvering  
- Hvordan man skriver bedre prompts til agenter  


## Hvad var svært

- At stole på agenten uden at miste kontrol  
- At skrive præcise nok prompts
- Fejlfinding kan være svært hvis man ikke tjekker koden igennem  


## Teknologier og værktøjer

- Claude Code  
- Codex  
- LLM’er  
- Prompt engineering


## Mine "første" oplevelser

Skriv noget her...


## Opsummering

Denne undervisningslektion har vi arbejdet med kodeagenter og brugen af dem til udvikling.
Jeg benyttede lidt mere udførelige prompts, og planning. Min side har nogle små ting der kan fikses, men den er live: https://rikkemariussen.github.io/AGENTPROJECT/  