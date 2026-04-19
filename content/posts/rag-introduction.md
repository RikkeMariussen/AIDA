---
title: RAG og DIFY
categories: ["RAG"]
tags: ["RAG"]
date: 2026-02-19
draft: false
featureimage: ""
authors:
  - rikke
---

# Introduktion til RAG og DIFY

Denne post vedrører de to undervisningslektioner vi havde den 13/4-'26 og den 17/4-'26.

## Buzzwords/centrale begreber

### Chatbot
Er et program der kan føre en samtale mellem en bruger og en "agent". De bliver ofte brugt som assistener/opslagsværktøjer, kundeservice og FAQ'er.

--- 

### LLM (Large language models)
En LLM er en AI-model der er trænet på "mange" tekster. 
En LLM kan:
- Læse og forstå tekst
- Generere svar med forklaringer

Da den er trænet på specifikke tekster, kan der opstå mangel i dens viden.

--- 

### RAG (Retrieval-Augmented Generation)
RAG er en metode til at forbedre en chatbot, da man giver den adgang til ekstra viden. RAG kan også bruges til at afgrænse viden, hvis man gør så botten KUN kan benytte viden fra den viden man selv fodrer den med.

Det fungerer ved at:
1. Brugeren stiller et spørgsmål
2. Programmet søger i en database (med den viden man har opsat)
3. Information bliver sendt til LLM'en
4. LLM'en bruger den information den er givet til at lave et svar til brugeren. 

---

### Vektordatabase
En vektor database er en database med 3 akser, hvor viden (tekst) bliver omformuleret til tal og indsat på denne. Der grupperes efter kontekst, f.eks. hund og kat er placeret relativt tæt på hinanden fordi de begge er dyr, men langt væk fra en banan.

Man kan således i stedet for at finde ord/tekst der betyder præcist det samme, lede efter noget der minder om hinanden.

---

### Semantisk søgning
Semantisk søgning er en søgning hvor man søger på betydningen af ord, i stedet for deres præcision. 
Denne type søgning er noget af det RAG benytter sig af, da kontekst kan være mere ledende og korrekt end antal matchende ord.

---

### Embeddings
I en vektordatabase benytter man embeddings, som er den måde teksten bliver lavet om til tal på.

Dette gør at der kan sammenlignes på indhold og tekst. 

---

### Reranking
Reranking betyder, som ordet lægger op til, at man omrangerer noget, og dette er søgeresultaterne fra f.eks. vektordatabasen, så man ser de svar der er mest relevante (højere relevansscore) kommer først. 

---

## Hvad har vi lært

- Hvad RAG er, og hvordan det gør svar mere præcise 
- Opbygning af en simpel chatbot med Dify
- Hvordan man benytter sine egne dokumenter som vidensbase (på Dify)
- Hvad embeddings og vektordatabase er, og hvordan de fungerer
- En smule om test og forbedring af svar fra en chatbot, ved at rykke på svar parametrene

---

## Hvad var svært

Dette "afsnit" for mig er kort, da jeg i min praktik var blevet introduceret til RAG og vektordatabaser.  

- At få gode svar
- At få dify sat ordentligt op
- At få dify/scripts sat op så vidensbasen bliver opdateret

---

## Teknologier og værktøjer

- Dify
- LLM
- Vektordatabase
- Embeddings API (openAI)

---

## Opsummering

I denne uge har vi arbejdet med RAG, opbygning af vores egen chatbot og justering af chatbottens LLM. 