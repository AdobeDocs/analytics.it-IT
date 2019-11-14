---
description: Per l'evento di acquisto, le variabili di Analytics sono utilizzate per acquisire informazioni di acquisto specifiche. La variabile s.purchaseID viene utilizzata per serializzare (deduplicare) l’evento.
keywords: Analytics Implementation
solution: Analytics
title: Eventi di acquisto
topic: Developer and implementation
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Eventi di acquisto

Per l'evento di acquisto, le variabili di Analytics sono utilizzate per acquisire informazioni di acquisto specifiche. La `s.purchaseID` variabile viene utilizzata per serializzare (deduplicare) l’evento.

Se un hit con un evento di acquisto viene passato senza un ID acquisto, Adobe Analytics utilizza le informazioni dall’hit (s.purchase e s.events) per creare un "ID acquisto temporaneo". Questo ID acquisto temporaneo si applica solo al visitatore dell’hit. I 5 ID acquisto temporaneo precedenti sono memorizzati per ciascun ID visitatore (per suite di rapporti).

Quando un visitatore effettua un acquisto, vengono effettuati i seguenti controlli:

* L'ID acquisto temporaneo corrisponde a uno degli ultimi cinque ID acquisto temporaneo memorizzati? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l'evento di acquisto, non vengono visualizzate nel reporting.
* Se `s.purchaseID` è definito, corrisponde ad alcun valore già raccolto nella suite di rapporti? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l'evento di acquisto, non vengono visualizzate nel reporting.

È possibile utilizzare un codice lato server specifico per generare il numero univoco (valore alfanumerico) incorporato nell'origine HTML. Solitamente, a questo scopo viene utilizzato l'ID ordine o un valore alfanumerico simile. Questo valore non deve essere modificato se l'utente aggiorna la pagina.

## Sintassi

```js
s.purchaseID="12345678";
```

## Esempi

```js
s.products="Footwear;Hiking Boots;1;170.00";
s.purchaseID="12345678";
s.events="purchase";
```

## Note aggiuntive

* Non utilizzate una funzione di randomizzazione JavaScript per generare un numero, che genera numeri univoci ogni volta che la pagina viene caricata. Adobe consiglia di utilizzare un livello dati per memorizzare un dato ID acquisto.
* Gli identificatori univoci sono applicabili a tutti gli utenti in tutte le sessioni. Assicurati che tutti gli ID acquisto siano davvero univoci.
* I valori validi sono valori alfanumerici di lunghezza massima di 20 caratteri.
* La `s.purchaseID` variabile serializza tutti gli eventi passati nella `s.events` variabile e sostituisce qualsiasi valore di serializzazione per gli eventi. Non utilizzate [!UICONTROL Event serialization] per gli eventi se la `s.purchaseID` variabile viene utilizzata nella pagina corrente.
* Se la `s.purchaseID` variabile viene lasciata vuota, viene conteggiata ogni istanza dell'evento acquisto, anche i ricarichi di pagina.
