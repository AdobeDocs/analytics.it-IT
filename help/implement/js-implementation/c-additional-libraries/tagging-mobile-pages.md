---
description: Il codice di tracciamento mobile viene posizionato sulla pagina sotto forma di tag immagine generato dal server.
keywords: Implementazione di Analytics; tracciamento dispositivi mobili; protocolli per dispositivi mobili; impedire la memorizzazione nella cache; alt, tag; tipo di immagine predefinito
seo-description: Il codice di tracciamento mobile viene posizionato sulla pagina sotto forma di tag immagine generato dal server.
seo-title: Assegnazione di tag alle pagine per i protocolli mobili
solution: Analytics
title: Assegnazione di tag alle pagine per i protocolli mobili
topic: Sviluppatore e implementazione
uuid: 5788 beaf-f 309-4918-a 99 c-a 3 e 591668205
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Assegnazione di tag alle pagine per i protocolli mobili

Il codice di tracciamento mobile viene posizionato sulla pagina sotto forma di tag immagine generato dal server.

Il codice di tracciamento mobile viene posizionato sulla pagina sotto forma di tag immagine generato dal server. Poiché linguaggi di script come javascript e wmlscript non sono generalmente supportati su dispositivi mobili, il beacon di tracciamento non può essere generato in modo dinamico tramite un linguaggio di script.

・ L'immagine del beacon mobile è in realtà di 2 x 2 pixel, per garantire il supporto per tutti i dispositivi mobili, impostando proprietà di altezza e larghezza su 5. Ad esempio:

```
<img sr c="https://metric.mydomain.com/b/ss/<Report_Suite_Name>/5/<random_number>?pageName=" alt="" width="5" height="5"/>
```

## Use a Random Number to Prevent Caching {#section_BF5C344A16034C439C8704632CF673A7}

Mentre i server Adobe segnalano ai browser di non memorizzare nella cache il beacon di tracciamento, non tutti i browser hanno la garanzia di seguire tali istruzioni. Per impedire ulteriormente la memorizzazione nella cache del beacon, si consiglia di generare dinamicamente un numero casuale nel percorso dell'URL dell'immagine. In tal modo si ottiene una precisione maggiore dei rapporti. Il numero casuale dovrebbe trovarsi nell'ultima sezione del percorso, come illustrato:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" />.
```

## Include an ALT Tag {#section_FBD8B2FD1EA0429580C2B933DA300B07}

Alcuni browser mobili richiedono che tutte le immagini abbiano testo alternativo incluso nel tag immagine. Di seguito viene illustrato come l'attributo ALT deve essere visualizzato nel tag immagine:

```js
<img src="https://rsid.112.2O7.net/b/ss/rsid/5/H.5--WAP/12345?pageName=" alt=""/>.
```

È importante che il /5/ venga sempre visualizzato correttamente nel percorso. Questa funzione viene utilizzata dai server Adobe per identificare i dispositivi mobili. Se utilizzate la /1/ standard, i server Adobe tentano di impostare un cookie sul dispositivo mobile.

## Change the Default Image Type {#section_2F969909010D4A64BF6E092A32ABADB7}

Se il tipo di immagine predefinito non è supportato su un particolare dispositivo, non viene restituito alcun dato. Per evitare questo problema, potete forzare il server di raccolta dati Adobe a restituire un particolare tipo di grafica supportato dal dispositivo mobile. Il codice che segue il nome della suite di rapporti specifica il tipo di immagine:

* `/5/` restituisce il tipo di immagine predefinito.
* `/5.1/` o `/1/` restituisce sempre un'immagine GIF.

* `/5.5/` restituisce sempre un'immagine WBMP.

See [Identifying Visitors using Mobile Protocols](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#concept_8C5557634014440AA3588FBB0CF6BB49).
