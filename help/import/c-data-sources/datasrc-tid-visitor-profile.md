---
description: Utilizza l’ID transazione nelle origini dati per collegare insieme dati online e offline.
title: ID transazione e profili visitatore
topic: Sviluppatore e implementazione
uuid: 7a72779c-7f67-4872-ad5e-edf298d53cac
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 98%

---


# ID transazione e profili visitatore

La presente sezione contiene informazioni importanti relative ai dati dal profilo visitatore utilizzato durante il caricamento dei dati con un ID transazione.

## ID transazione {#section_B248FA93ECC84F6290D237EB83618070}

Quando un ID transazione è registrato, uno &quot;snapshot&quot; del profilo visitatore corrente viene salvato e associato all&#39;ID transazione. Questo &quot;snapshot&quot; contiene tutti i valori di variabili attualmente impostati per il visitatore, incluse le variabili persistenti (ad esempio eVar e campagne). I valori nello snapshot ricevono l&#39;attribuzione per eventi di successo, eventi di acquisto e ricavi caricati successivamente utilizzando lo stesso ID transazione.

Dopo la creazione dello &quot;snapshot&quot; del profilo visitatore, esso non viene aggiornato con le modifiche del profilo visitatore correnti (a causa del comportamento online), viene aggiornato solo con i dati caricati utilizzando le origini dati ID transazione. Se imposti lo stesso valore ID transazione su più pagine durante la stessa visita, il caricamento dell&#39;origine dati che avviene successivamente sarà collegato allo &quot;snapshot&quot; creato la prima volta che è stato impostato l&#39;ID.

**Caricamenti multipli**

È possibile caricare più righe di dati nello stesso ID transazione in tutta la finestra di scadenza ID transazione (vedi sotto).

**Scadenza variabile**

La scadenza della variabile non viene considerata ai fini di ID transazione, perché i dati del profilo visitatore associati devono riflettere lo stato del visitatore al momento della transazione. Ad esempio, se la scadenza di eVar1 è configurata dopo la visita, il valore nello &quot;snapshot&quot; del profilo visitatore riceve credito anche se è scaduto o se è stato sostituito nel profilo visitatore corrente al momento del caricamento dei dati ID transazione.

**Prodotti**

Le informazioni sui prodotti (da `s.products`) non sono contenute nello &quot;snapshot&quot; del profilo visitatore, pertanto devi caricare eventuali dati di prodotti associati nel file origine dati insieme all&#39;ID transazione. Puoi specificare solo un prodotto per riga, pertanto potresti dover caricare più righe con lo stesso ID transazione per includere tutti i prodotti.

**Persistenza eVar caricate**

Le eVar caricate utilizzando le origini dati ID transazione vengono aggiunte allo &quot;snapshot&quot; del profilo visitatore, non vengono aggiunte al profilo visitatore corrente o al cookie virtuale. Ciò significa che il comportamento online che avviene dopo il caricamento non viene accreditato sulle eVar caricate, perché questi valori non fanno parte del profilo visitatore corrente.

**Finestra di scadenza ID transazione**

Lo &quot;snapshot&quot; del profilo visitatore associato a un ID transazione è idoneo all&#39;eliminazione dopo 90 giorni, anche se la pianificazione effettiva dell&#39;eliminazione può variare. Se necessario, puoi contattare l&#39;Assistenza clienti Adobe per prolungare la finestra di scadenza. Se una riga viene caricata dopo la finestra di scadenza ID transazione, i dati nella riga vengono registrati, ma nessun dato nello &quot;snapshot&quot; del profilo visitatore sarà accreditato se il profilo è stato eliminato.

## Suddivisioni e segmentazione utilizzando gli ID transazione {#section_A4D39291200A42C496122FDB9EF6EF68}

Le eVar caricate utilizzando le origini dati possono essere utilizzate per suddividere le eVar contenute nello &quot;snapshot&quot; del profilo visitatore. Poiché questi dati sono separati dal profilo del visitatore corrente, non puoi suddividere per altre eVar che potrebbero essere state impostate prima o dopo l&#39;impostazione dell&#39;ID transazione ma che non fanno parte dello &quot;snapshot&quot;.

Esistono alcuni modi per visualizzare i dati visitatore associati che potrebbero non essere disponibili in una suddivisione. Nei rapporti Data Warehouse, puoi visualizzare i dati di ID transazione con un ID visitatore corrispondente agli altri hit del visitatore. Anche se queste righe ID transazione sono escluse durante il conteggio di visite/visitatori al giorno, vengono utilizzate nel calcolo della maggior parte delle metriche e nei segmenti.

Come risultato, puoi creare un segmento di visitatori che esegue alcuni eventi online caricati con origini dati ID transazione. Sarà restituito tutto ciò che il visitatore ha fatto prima e dopo l&#39;evento ID transazione.

In modo simile, la partecipazione del visitatore ti consente di visualizzare come proprietà ID transazione e eVar hanno preceduto un evento online o come proprietà online e eVar hanno preceduto un evento ID transazione.
