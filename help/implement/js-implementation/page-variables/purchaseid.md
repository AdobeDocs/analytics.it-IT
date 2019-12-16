---
description: Scopri la variabile purchaseID, che impedisce la visualizzazione di acquisti duplicati in Adobe Analytics.
keywords: duplicate,purchase,purchaseid,s.purchaseid
subtopic: Variables
title: purchaseID
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# purchaseID

La `purchaseID` variabile viene utilizzata per impedire che un ordine venga conteggiato più volte nel reporting. Ogni volta che l'evento di acquisto viene utilizzato sul sito, Adobe consiglia di utilizzare la `purchaseID` variabile.

Quando un visitatore acquista un elemento dal sito, `purchaseID` viene in genere popolato nella pagina "Conferma" o "Conferma ordine". Impostare la `purchaseID` variabile contemporaneamente all'attivazione di un evento di acquisto. Quando `purchaseID` è definito su un valore univoco, i valori delle variabili di conversione contano solo per hit con tale ID acquisto univoco. La definizione `purchaseID` è utile perché i visitatori segnalano comunemente una pagina di conferma dell'acquisto per i propri scopi. Se l’implementazione non viene utilizzata `purchaseID`, i dati di conversione (come le entrate) possono facilmente aumentare a causa dell’aggiornamento delle pagine da parte dei visitatori.

Oltre ai dati di acquisto, tutte le variabili e gli eventi di conversione non vengono conteggiati più volte per gli hit con lo stesso ID acquisto.

## Sintassi

La `purchaseID` variabile può contenere qualsiasi valore alfanumerico, fino a un massimo di 20 byte. Se imposti un ID di acquisto maggiore di 20 byte, il valore viene troncato.

```js
s.purchaseID = "uniqueid";
```
