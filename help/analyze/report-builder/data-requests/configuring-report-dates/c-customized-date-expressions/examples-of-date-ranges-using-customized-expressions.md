---
description: Esempi, note e note di sintassi sull'uso degli intervalli di date nelle espressioni personalizzate.
solution: Analytics
title: Esempi di intervalli di date utilizzando espressioni personalizzate
topic: Report builder
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Esempi di intervalli di date utilizzando espressioni personalizzate

Esempi, note e note di sintassi sull'uso degli intervalli di date nelle espressioni personalizzate.

La tabella presuppone che la data odierna sia lunedì 10 novembre 2011, utilizzando il calendario gregoriano.

| Esempio  | Intervallo date | Personalizza espressione | Intervallo date del rapporto |
|---|---|---|---|
|  |  | **Da** | **A** |  |
| 1 | Due settimane fa | cw-2w | cw-1w-1d | Da 26 ott a 1 nov |
| 2 | I primi 3 giorni del quinto mese dello scorso anno | cy-1y+4 m | cy-1y+4m+2d | dal 1o maggio al 3 maggio 2010 |
| 3 | Una settimana intera, a partire da 4 settimane fa | cw-4w | cw-3w-1d | 12 ott-18 ott |
| 4 | Ultima settimana dell'anno precedente | cw-53w | cw-52w-1d | Nov. - 9 Nov. 2010 |
| 5 | Un mese a partire da 2 mesi fa | cm-2m | cm-1m-1d | 1 settembre al 30 settembre |
| 6 | 12 mesi fa | cm-12m | cm-11m-1d | dal 1 o novembre al 30 novembre 2010 |

## Note sugli esempi {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Esempio 1**

Se oggi è lunedì 10 novembre 2011, prendere la data corrente e sottrarre una settimana per ottenere l'ultima settimana completa di ottobre.

**Esempio 2**

aggiungere quattro mesi all'inizio dell'anno (il mese di gennaio) per ottenere il mese di maggio; aggiungere due giorni al primo giorno del mese per ottenere il terzo giorno del mese.

## Note sulla sintassi {#section_555D6563B2D94FA3BDD801DC0B8C289D}

È possibile creare espressioni personalizzate che coprono la maggior parte degli intervalli di date collegando due termini a un operatore. Un termine è una combinazione di un moltiplicatore di numeri interi e di un'abbreviazione di punto. Un esempio di termine è 18d. Un esempio di operatore è +.

* Spazio vuoto non consentito tra operatori e termini.
* Utilizzate solo le seguenti abbreviazioni: cd cw cm cq d w m q y
* È consigliabile utilizzare lo stesso riferimento data nella data di inizio e nella data di fine: cd, cd o cw, cw o cy. I riferimenti alle date di mixaggio possono portare a date non valide in determinati periodi dell'anno.
* I multipli validi delle abbreviazioni d w m q y sono formati da numeri interi ( 1 2 3 ... ) anteposto all'abbreviazione, ad esempio 53d 3w 5q 9m 2y

   * I numeri non interi non sono consentiti.
   * Non anteporre l'abbreviazione a un solo zero. Ad esempio, 0w non è consentito.

* Per concatenare le abbreviazioni vengono utilizzati gli operatori seguenti: + -
* Poiché gli intervalli di date devono essere considerati relativi al periodo corrente, il primo termine in un'espressione inizia sempre con c.

