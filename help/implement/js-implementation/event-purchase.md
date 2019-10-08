---
description: Per l'evento di acquisto, le variabili di Analytics sono utilizzate per acquisire informazioni di acquisto specifiche. La variabile s.purchaseID viene utilizzata per serializzare (deduplicare) l’evento.
keywords: Implementazione di Analytics
seo-description: Per l'evento di acquisto, le variabili di Analytics sono utilizzate per acquisire informazioni di acquisto specifiche. La variabile s.purchaseID viene utilizzata per serializzare (deduplicare) l’evento.
seo-title: Eventi di acquisto
solution: Analytics
title: Eventi di acquisto
topic: Sviluppatore e implementazione
uuid: d90cdec7-7397-445a-84e5-31014f7ff875
translation-type: tm+mt
source-git-commit: e21bb18dd0d0eb13222c655091c3a87939a0351d

---


# Eventi di acquisto

Per l'evento di acquisto, le variabili di Analytics sono utilizzate per acquisire informazioni di acquisto specifiche. La `s.purchaseID` variabile viene utilizzata per serializzare (deduplicare) l’evento.

Se un evento di acquisto viene chiamato senza un `purchaseID`, ne viene generato automaticamente uno univoco in base alle `s.products` variabili e `s.events` . Questo ID acquisto generato automaticamente viene memorizzato localmente come cookie nel browser del visitatore e non viene inviato ad Adobe. Gli ID acquisto definiti manualmente vengono invece inviati ad Adobe. Gli ultimi cinque acquisti effettuati da un visitatore (con o senza ID acquisto) vengono memorizzati nel cookie locale.

Quando un visitatore effettua un acquisto, vengono effettuati i seguenti controlli:

* L'ID acquisto corrisponde a uno dei cinque valori dei cookie? In tal caso, la richiesta di immagine viene considerata un acquisto duplicato. Tutte le variabili di conversione, incluso l'evento di acquisto, non vengono visualizzate nel reporting.
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
