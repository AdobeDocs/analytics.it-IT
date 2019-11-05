---
description: Il codice di tracciamento mobile viene inserito nella pagina sotto forma di tag immagine generati dal server.
keywords: Implementazione di Analytics;tracciamento mobile;protocolli mobili;impedire la memorizzazione nella cache;tag alt;tipo di immagine predefinito
seo-description: Il codice di tracciamento mobile viene inserito nella pagina sotto forma di tag immagine generati dal server.
seo-title: Assegnazione di tag alle pagine per i protocolli mobile
solution: Analytics
title: Assegnazione di tag alle pagine per i protocolli mobile
topic: Sviluppatore e implementazione
uuid: 5788beaf-f309-4918-a99c-a3e591668205
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Assegnazione di tag alle pagine per i protocolli mobile

Il codice di tracciamento mobile viene inserito nella pagina sotto forma di tag immagine generati dal server.

Il codice di tracciamento mobile viene inserito nella pagina sotto forma di tag immagine generati dal server. Poiché linguaggi di script come JavaScript e WMLScript non sono generalmente supportati nei dispositivi mobili, il beacon di tracciamento non può essere generato dinamicamente tramite un linguaggio di script.

・ Mentre l'immagine del beacon mobile è di 2 x 2 pixel, per garantire il supporto per tutti i dispositivi mobili, è necessario impostare le proprietà relative a altezza e larghezza su 5. Ad esempio:

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## Usa un numero casuale per impedire la memorizzazione nella cache {#section_BF5C344A16034C439C8704632CF673A7}

Mentre i server Adobe ordinano ai browser di non memorizzare nella cache il beacon di tracciamento, non tutti i browser devono seguire tali istruzioni. Per impedire ulteriormente il caching del beacon, si consiglia al server Web di generare in modo dinamico un numero casuale nel percorso dell’URL dell’immagine. In questo modo si garantisce una maggiore precisione dei rapporti. Il numero casuale deve trovarsi nell’ultima sezione del percorso, come illustrato di seguito:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## Includi un tag ALT {#section_FBD8B2FD1EA0429580C2B933DA300B07}

Alcuni browser mobili richiedono che tutte le immagini includano testo alternativo nel tag immagine. Di seguito viene illustrato l’aspetto dell’attributo ALT nel tag immagine:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

È importante che il /5/ venga sempre visualizzato correttamente nel percorso. Questo viene utilizzato dai server Adobe per identificare i dispositivi mobili. Se viene utilizzato lo standard /1/, i server Adobe tentano di impostare un cookie sul dispositivo mobile.

## Modifica del tipo di immagine predefinito {#section_2F969909010D4A64BF6E092A32ABADB7}

Se il tipo di immagine predefinito non è supportato su un particolare dispositivo, non viene restituito alcun dato. Per evitare questa situazione, puoi forzare il server di raccolta dati Adobe a restituire un particolare tipo di grafica supportato dal dispositivo mobile. Il codice che segue il nome della suite di rapporti specifica il tipo di immagine:

* `/5/` restituisce il tipo di immagine predefinito.
* `/5.1/` oppure restituisce `/1/` sempre un'immagine GIF.

* `/5.5/` restituisce sempre un’immagine WBMP.

Consultate [Identificazione dei visitatori tramite protocolli](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md)mobili.
