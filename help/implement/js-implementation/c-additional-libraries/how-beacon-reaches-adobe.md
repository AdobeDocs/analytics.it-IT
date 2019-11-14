---
description: Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web.
keywords: Analytics Implementation;gateway;wap;i-mode;wbmp
solution: Analytics
title: Gateway di rete per protocollo mobile
topic: Developer and implementation
uuid: a2c92ce2-53a9-4b5b-be1a-89d9f1bf776f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Gateway di rete per protocollo mobile

Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web.

Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web. Il server Web risponde al gateway, che inoltra la richiesta al telefono. Questo gateway funziona come un server proxy standard. Il gateway, tuttavia, trasmette la stringa agente utente del dispositivo mobile al server Web. Questo consente al server Web di rispondere con una pagina creata appositamente per il dispositivo che lo richiede.

Poiché le dimensioni dello schermo sui dispositivi mobili WAP sono limitate, le pagine mobili sono molto chiare, spesso contengono solo testo e un’immagine memorizzata nella cache. Quando il tag immagine viene aggiunto alle pagine, viene inviata una richiesta a ogni pagina per un’immagine dai server Adobe. Quando viene restituita l’immagine, un WBMP, i server Adobe informano il browser di non memorizzarla nella cache. Di conseguenza, l’immagine viene nuovamente richiesta nelle pagine successive. Il numero casuale descritto sopra dovrebbe essere utilizzato per proteggere contro i browser che non obbediscono alle direttive Adobe no-cache.
