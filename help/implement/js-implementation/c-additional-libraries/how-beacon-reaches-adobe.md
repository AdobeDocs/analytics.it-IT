---
description: Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web.
keywords: Implementazione di Analytics; gateway; wap; i-mode; wbmp
seo-description: Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web.
seo-title: Gateway di rete protocollo mobile
solution: Analytics
title: Gateway di rete protocollo mobile
topic: Sviluppatore e implementazione
uuid: a 2 c 92 ce 2-53 a 9-4 b 5 b-be 1 a -89 d 9 f 1 bf 776 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Gateway di rete protocollo mobile

Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web.

Quando un dispositivo mobile richiede una pagina da un server Web, la richiesta viene inviata tramite un gateway, che converte la richiesta mobile (in genere nel protocollo WAP o I-Mode) in una richiesta HTTP inviata a un server Web. Il server Web risponde al gateway, che inoltra la richiesta al telefono. Questo gateway agisce molto come un server proxy standard. Il gateway, tuttavia, trasmette la stringa agente utente del dispositivo mobile al server Web. Questo consente al server Web di rispondere a una pagina creata specificamente per il dispositivo che la richiede.

Poiché le dimensioni dello schermo sui dispositivi mobili WAP sono limitate, le pagine mobili sono molto chiare, spesso contenenti solo testo e un'immagine nella cache. Quando il tag immagine viene aggiunto alle pagine, viene inviata una richiesta in ogni pagina di un'immagine dai server Adobe. Quando viene restituita l'immagine, un WBMP, i server Adobe indicano al browser di non memorizzarlo nella cache. Di conseguenza, l'immagine viene nuovamente richiesta nelle pagine successive. Il numero casuale descritto sopra deve essere utilizzato per proteggere i browser che non rispettano le direttive non relative alla cache di Adobe.
