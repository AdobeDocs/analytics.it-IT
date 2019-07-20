---
description: Esempi, note e note sulla sintassi sull'uso degli intervalli di date nelle espressioni personalizzate.
seo-description: Esempi, note e note sulla sintassi sull'uso degli intervalli di date nelle espressioni personalizzate.
seo-title: Esempi di intervalli di date utilizzando espressioni personalizzate
solution: Analytics
title: Esempi di intervalli di date utilizzando espressioni personalizzate
topic: Generatore di report
uuid: 3 f 46816 d -9 eee -4 b 2 d -83 be-bf 1 c 9 fb 97 fcf
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Esempi di intervalli di date utilizzando espressioni personalizzate

Esempi, note e note sulla sintassi sull'uso degli intervalli di date nelle espressioni personalizzate.

La tabella presuppone che la data odierna sia lunedì, 10 novembre 2011, utilizzando il calendario gregoriano.

| Esempio  | Intervallo date | Personalizza espressione | Intervallo di date del rapporto |
|---|---|---|---|
|  |  | **Da** | **A** |  |
| 1 | Due settimane fa | cw -2 w | cw -1 w -1 d | Da 26 a 1 nov |
| 2 | Primi 3 giorni del quinto mese dello scorso anno | cy -1 y +4 m | cy -1 y +4 m +2 d | 1 maggio 2010 maggio 3 |
| 3 | Una settimana completa, a partire da 4 settimane | cw -4 w | cw -3 w -1 d | Da 12 a 18 ott. |
| 4 | Settimana scorsa nell'anno precedente | cw -53 w | cw -52 w -1 d | Nov al 9 novembre 2010 |
| 5 | Un mese a partire da 2 mesi fa | cm -2 m | cm -1 m -1 d | Da 1 a 30 settembre |
| 6 | 12 mesi fa nell'anno precedente | cm -12 m | cm -11 m -1 d | 1 nov al 30 novembre 2010 |

## Notes on examples {#section_37801B0D6D364ABAA8DCE3A4C0123B2C}

**Esempio 1**

Se oggi è lunedì 10 novembre 2011, passate alla data corrente e sottraete una settimana per ottenere l'ultima settimana di ottobre.

**Esempio 2**

Aggiungere quattro mesi all'inizio dell'anno (mese di gennaio) per ottenere il mese di maggio, aggiungere due giorni al primo giorno del mese per ottenere il terzo giorno del mese.

## Syntax notes {#section_555D6563B2D94FA3BDD801DC0B8C289D}

Le espressioni personalizzate che coprono la maggior parte degli intervalli di date possono essere create collegando due termini con un operatore. Un termine è una combinazione di un moltiplicatore intero e di un'abbreviazione del punto. Un esempio di termine è 18 d. Un esempio di operatore è +.

* Spazio vuoto non consentito tra operatori e termini.
* Utilizzare solo le abbreviazioni seguenti: cd cw cm cq cy d w m q y
* La procedura consigliata prevede di utilizzare lo stesso riferimento alla data nella data di inizio e nella data di fine: cd, cd o cw, cw o cy, cy. I riferimenti alla data di mixaggio possono portare a date non valide in determinati momenti dell'anno.
* Multipli validi delle abbreviazioni d w m q y sono formati da numeri interi (1 2 3…) preimpostati all'abbreviazione, ad esempio 53 d 3 w 5 q 9 m 2 y

   * I numeri non interi non sono consentiti.
   * Non anteporre l'abbreviazione solo a zero. Ad esempio, 0 w non è consentito.

* I seguenti operatori sono utilizzati per concatenare le abbreviazioni: + -
* Poiché gli intervalli di date devono essere riportati rispetto al periodo corrente, il primo termine di un'espressione inizia sempre con c.

