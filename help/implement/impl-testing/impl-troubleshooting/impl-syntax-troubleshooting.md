---
description: La tabella seguente mostra la differenza tra errori di codice corretti e non corretti.
keywords: Implementazione di Analytics
seo-description: La tabella seguente mostra la differenza tra errori di codice corretti e non corretti.
seo-title: Errori comuni di sintassi
solution: Analytics
subtopic: Risoluzione dei problemi
title: Errori comuni di sintassi
topic: Sviluppatore e implementazione
uuid: 9845dcb9-9f10-4f65-a43d-2af41edaa122
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Errori comuni di sintassi

La tabella seguente mostra la differenza tra errori di codice corretti e non corretti.

| Errato | Corretto |
|---|---|
| prop1 | s.prop1 (utilizza "s.") |
| s.evar1 | s.eVar1 (utilizza l'uso di maiuscole e minuscole corrette) |
| s.pagetype='errorpage'; | s.pageType='errorPage'; (utilizza l'uso di maiuscole e minuscole corrette) |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA'); (uso corretto di virgolette singole) |
| s.events='event1'; s.events='event2'; | s.events='event1,event2'; (formato corretto) |
| s.pageName="John" (citazioni smart su) | s.pageName="John" (virgolette intelligenti disattivate) |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99" (utilizza punto e virgola, non virgole) |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99" (non utilizza segni del dollaro) |
| s.products=";Nikon SB-600 Speedlight Flash per fotocamere reflex digitali Nikon;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash per fotocamere reflex digitali Nikon;1;229.95" (prezzi arrotondati o troncati) |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2" (nessuno spazio tra gli ID della suite di rapporti durante l'assegnazione di tag a più suite) |
| s.events="event1, event2" | s.events="event1,event2" (nessuno spazio tra gli ID evento durante l’assegnazione di tag per più eventi) |
| s.products="product name" | s.products=";product name" (punto e virgola utilizzato quando non è elencata alcuna categoria di prodotti) |

## Note aggiuntive {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Tenete il commento HTML di chiusura alla fine del codice Adobe (anche se state utilizzando la parte NOSCRIPT dello script).
