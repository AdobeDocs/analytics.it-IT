---
description: Esempi, note e note di sintassi sull'utilizzo di intervalli di date nelle espressioni personalizzate.
title: Esempi di intervalli di date utilizzando espressioni personalizzate
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 7%

---


# Esempi di intervalli di date utilizzando espressioni personalizzate

Esempi, note e note di sintassi sull&#39;utilizzo di intervalli di date nelle espressioni personalizzate.

La tabella presuppone che la data odierna sia lunedì 10 novembre 2011, utilizzando il calendario gregoriano.

| Esempio | Intervallo date | Personalizza espressione | Intervallo di date del rapporto |
|---|---|---|---|
|  |  | **Da** | **Su** |  |
| 1 | Due settimane fa | cw-2w | cw-1w-1d | 26 ottobre - 1 novembre |
| 2 | I primi 3 giorni del quinto mese dello scorso anno | cy-1y+4m | cy-1y+4m+2d | dal 1o maggio al 3 maggio 2010 |
| 3 | Una settimana intera, a partire da 4 settimane fa | cw-4w | cw-3w-1d | dal 12 ottobre al 18 ottobre |
| 4 | La settimana scorsa nell&#39;anno precedente | cw-53w | cw-52w-1d | Nov. - 9 Nov. 2010 |
| 5 | Un mese a partire da due mesi fa | cm-2 m | cm-1m-1d | dal 1° settembre al 30 settembre |
| 6 | 12 mesi fa nell&#39;anno precedente | cm-12m | cm-11m-1d | dal 1o novembre al 30 novembre 2010 |

## Note sugli esempi {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Esempio 1**

Se oggi è lunedì 10 novembre 2011, prendere la data corrente e sottrarre una settimana per ottenere l&#39;ultima settimana completa di ottobre.

**Esempio 2**

Aggiungere quattro mesi all&#39;inizio dell&#39;anno (il mese di gennaio) per ottenere il mese di maggio; aggiungi due giorni al primo giorno del mese per ottenere il terzo giorno del mese.

## Note sulla sintassi {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Puoi creare espressioni personalizzate che coprono la maggior parte degli intervalli di date collegando due termini con un operatore . Un termine è una combinazione di un moltiplicatore di numeri interi e di un&#39;abbreviazione di periodi. Un esempio di termine è 18d. Un esempio di operatore è +.

* Spazio vuoto non consentito tra operatori e termini.
* Utilizzare solo le seguenti abbreviazioni: cd cw cm cq d w m q y
* La best practice prevede l’utilizzo dello stesso riferimento di data nella data di inizio e nella data di fine: cd, cd o cw, cw o cy, cy. La combinazione di riferimenti a date può portare a date non valide in alcuni momenti dell’anno.
* I multipli validi delle abbreviazioni d w m q y sono formati da numeri interi ( 1 2 3 ... ) preceduti dall&#39;abbreviazione, come 53d 3w 5q 9m 2y
* I numeri non interi non sono consentiti.
* Non anteporre l&#39;abbreviazione con un solo zero. Ad esempio, 0w non è consentito.
* I seguenti operatori vengono utilizzati per concatenare le abbreviazioni: + -
* Poiché gli intervalli di date devono essere conteggiati rispetto al periodo corrente, il primo termine in un’espressione inizia sempre con c.

