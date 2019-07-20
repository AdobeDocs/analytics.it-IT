---
description: La tabella seguente mostra la differenza tra errori corretti e errori di codice errati.
keywords: Implementazione di Analytics
seo-description: La tabella seguente mostra la differenza tra errori corretti e errori di codice errati.
seo-title: Errori comuni di sintassi
solution: Analytics
subtopic: 'Risoluzione dei problemi   '
title: Errori comuni di sintassi
topic: Sviluppatore e implementazione
uuid: 9845 dcb 9-9 f 10-4 f 65-a 43 d -2 af 41 edaa 122
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Errori comuni di sintassi

La tabella seguente mostra la differenza tra errori corretti e errori di codice errati.

| Errato | Corretto |
|---|---|
| prop1 | s. prop 1 (usa "s.") |
| s.evar1 | s. evar 1 (usa le maiuscole corrette) |
| s. pagetype ='errorpagè; | s. pagetype ='errorpagè; (utilizza le maiuscole corrette) |
| s. tl (this, o, pagea) | s. tl (this,'o ','pagea '); (uso corretto di virgolette singole) |
| s. events ='event 1 '; s. events ='event 2 '; | s. events ='event 1, event 2 '; (formato corretto) |
| s. pagename = "John" (virgolette intelligenti) | s. pagename = "John" (virgolette smart) |
| s. products = "shoes, UX 4879,1,19.99" | s. products = "shoes; UX 4879; 1; 19.99 " (usa punto e virgola, non virgole) |
| s. products = "; Macbook Air; 1; $ 1999.99 | s. products = "; Macbook Air; 1; 1999.99 " (non utilizza segni di dollaro) |
| s. products = "; Nikon SB -600 Speedlight Flash per videocamere reflex digitali Nikon; 1; 229.9489183 " | s. products = "; Nikon SB -600 Speedlight Flash per videocamere reflex digitali Nikon; 1; 229.95 " (arrotondati o troncati) |
| var s_ account = "rsid 1, rsid 2" | var s_ account = "rsid 1, rsid 2" (nessun spazio tra gli ID suite di rapporti durante l'esecuzione di tag per più suite) |
| s. events = "event 1, event 2" | s. events = "event 1, event 2" (nessuno spazio tra ID evento durante l'esecuzione di tag per più eventi) |
| s. products = "product name" | s. products = "; nome prodotto " (punto e virgola utilizzato quando non è elencata alcuna categoria di prodotti) |

## Note aggiuntive {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

Mantenere il commento HTML alla fine del codice Adobe, anche se si utilizza la parte NOSCRIPT dello script.
