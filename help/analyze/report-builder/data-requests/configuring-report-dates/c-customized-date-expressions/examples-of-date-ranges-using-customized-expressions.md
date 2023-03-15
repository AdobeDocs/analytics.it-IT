---
description: Esempi, note e note di sintassi sull’utilizzo di intervalli di date nelle espressioni personalizzate.
title: Esempi di intervalli di date utilizzando espressioni personalizzate
uuid: 3f46816d-9eee-4b2d-83be-bf1c9fb97fcf
feature: Report Builder
role: User, Admin
exl-id: d936dd4e-d330-4ed9-a979-3273397d7d92
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 6%

---

# Esempi di intervalli di date utilizzando espressioni personalizzate

Esempi, note e note di sintassi sull’utilizzo di intervalli di date nelle espressioni personalizzate.

La tabella presuppone che la data odierna sia lunedì 10 novembre 2011, utilizzando il calendario gregoriano.

| Esempio | Intervallo date | Personalizza espressione | Intervallo date del rapporto |
|---|---|---|---|
|  |  | **Da** | **Su** |  |
| 1 | Due settimane fa | cw-2w | cw-1w-1d | 26 ottobre - 1 novembre |
| 2 | Primi 3 giorni del quinto mese dello scorso anno | cy-1y+4m | cy-1y+4m+2d | maggio-3 maggio 2010 |
| 3 | Una settimana intera, a partire da 4 settimane fa | cw-4w | cw-3w-1d | dal 12 ottobre al 18 ottobre |
| 4 | Ultima settimana nell&#39;anno precedente | cw-53w | cw-52w-1d | Dal 9 novembre al 9 novembre 2010 |
| 5 | Un mese a partire da 2 mesi fa | cm-2 m | cm-1m-1d | 1 settembre - 30 settembre |
| 6 | 12 mesi fa nell&#39;anno precedente | cm-12m | cm-11m-1d | 1 novembre - 30 novembre 2010 |

## Note sugli esempi {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Esempio 1**

Se oggi è lunedì 10 novembre 2011, prendere la data corrente e sottrarre una settimana per ottenere l&#39;ultima settimana completa di ottobre.

**Esempio 2**

Aggiungere quattro mesi all&#39;inizio dell&#39;anno (il mese di gennaio) per ottenere il mese di maggio; aggiungere due giorni al primo giorno del mese per ottenere il terzo giorno del mese.

## Note sulla sintassi {#section_555D6563B2D94FA3BDD801DC0B8C289D}

È possibile creare espressioni personalizzate che coprono la maggior parte degli intervalli di date collegando due termini con un operatore. Un termine è una combinazione di un moltiplicatore intero e un’abbreviazione di periodo. Un esempio di termine è 18d. Un esempio di operatore è +.

* Lo spazio vuoto non è consentito tra gli operatori e i termini.
* Usare solo queste abbreviazioni: cd cw cm cq cy d w m q y
* La best practice prevede l’utilizzo dello stesso riferimento data nella data di inizio e nella data di fine: cd, cd o cw, cw oppure cy, cy. La combinazione di riferimenti di date può portare a date non valide in determinati periodi dell’anno.
* I multipli validi delle abbreviazioni d w m q y sono costituiti da interi ( 1 2 3 ... ) preceduti dall&#39;abbreviazione, come 53d 3w 5q 9m 2y
* Non sono consentiti numeri non interi.
* Non anteporre all&#39;abbreviazione solo uno zero. Ad esempio, 0w non è consentito.
* Per concatenare le abbreviazioni vengono utilizzati i seguenti operatori: + -
* Poiché gli intervalli di date devono essere calcolati in relazione al periodo corrente, il primo termine in un’espressione inizia sempre con c.
