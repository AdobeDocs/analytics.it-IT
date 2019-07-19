---
description: nulle
seo-description: nulle
seo-title: ID transazione e profili visitatore
solution: Analytics
title: ID transazione e profili visitatore
topic: Sviluppatore e implementazione
uuid: 7 a 72779 c -7 f 67-4872-ad 5 e-edf 298 d 53 cac
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID transazione e profili visitatore

La presente sezione contiene informazioni importanti relative ai dati dal profilo visitatore utilizzato durante il caricamento dei dati con un ID transazione.

## ID transazione {#section_B248FA93ECC84F6290D237EB83618070}

Quando un ID transazione è registrato, uno "snapshot" del profilo visitatore corrente viene salvato e associato all'ID transazione. Questo "snapshot" contiene tutti i valori di variabili attualmente impostati per il visitatore, incluse le variabili persistenti (ad esempio eVar e campagne). I valori nello snapshot ricevono l'attribuzione per eventi di successo, eventi di acquisto e ricavi caricati successivamente utilizzando lo stesso ID transazione.

Dopo la creazione dello "snapshot" del profilo visitatore, esso non viene aggiornato con le modifiche del profilo visitatore correnti (a causa del comportamento online), viene aggiornato solo con i dati caricati utilizzando le origini dati ID transazione. Se imposti lo stesso valore ID transazione su più pagine durante la stessa visita, il caricamento dell'origine dati che avviene successivamente sarà collegato allo "snapshot" creato la prima volta che è stato impostato l'ID.

**Caricamenti multipli**

È possibile caricare più righe di dati nello stesso ID transazione in tutta la finestra di scadenza ID transazione (vedi sotto).

**Scadenza variabile**

La scadenza della variabile non viene considerata ai fini di ID transazione, perché i dati del profilo visitatore associati devono riflettere lo stato del visitatore al momento della transazione. Ad esempio, se la scadenza di eVar1 è configurata dopo la visita, il valore nello "snapshot" del profilo visitatore riceve credito anche se è scaduto o se è stato sostituito nel profilo visitatore corrente al momento del caricamento dei dati ID transazione.

**Prodotti**

Le informazioni sui prodotti (da `s.products`) non sono contenute nello "snapshot" del profilo visitatore, pertanto devi caricare eventuali dati di prodotti associati nel file origine dati insieme all'ID transazione. Puoi specificare solo un prodotto per riga, pertanto potresti dover caricare più righe con lo stesso ID transazione per includere tutti i prodotti.

**Persistenza eVar caricate**

Le eVar caricate utilizzando le origini dati ID transazione vengono aggiunte allo "snapshot" del profilo visitatore, non vengono aggiunte al profilo visitatore corrente o al cookie virtuale. Ciò significa che il comportamento online che avviene dopo il caricamento non viene accreditato sulle eVar caricate, perché questi valori non fanno parte del profilo visitatore corrente.

**Finestra di scadenza ID transazione**

Lo "snapshot" del profilo visitatore associato a un ID transazione è idoneo all'eliminazione dopo 90 giorni, anche se la pianificazione effettiva dell'eliminazione può variare. Se necessario, puoi contattare l'Assistenza clienti Adobe per prolungare la finestra di scadenza. Se una riga viene caricata dopo la finestra di scadenza ID transazione, i dati nella riga vengono registrati, ma nessun dato nello "snapshot" del profilo visitatore sarà accreditato se il profilo è stato eliminato.

## Suddivisioni e segmentazione utilizzando gli ID transazione {#section_A4D39291200A42C496122FDB9EF6EF68}

Le eVar caricate utilizzando le origini dati possono essere utilizzate per suddividere le eVar contenute nello "snapshot" del profilo visitatore. Poiché questi dati sono separati dal profilo del visitatore corrente, non puoi suddividere per altre eVar che potrebbero essere state impostate prima o dopo l'impostazione dell'ID transazione ma che non fanno parte dello "snapshot".

Esistono alcuni modi per visualizzare i dati visitatore associati che potrebbero non essere disponibili in una suddivisione. Nei rapporti Data Warehouse, puoi visualizzare i dati di ID transazione con un ID visitatore corrispondente agli altri hit del visitatore. Anche se queste righe ID transazione sono escluse durante il conteggio di visite/visitatori al giorno, vengono utilizzate nel calcolo della maggior parte delle metriche e nei segmenti.

Come risultato, puoi creare un segmento di visitatori che esegue alcuni eventi online caricati con origini dati ID transazione. Sarà restituito tutto ciò che il visitatore ha fatto prima e dopo l'evento ID transazione.

In modo simile, la partecipazione del visitatore ti consente di visualizzare come proprietà ID transazione e eVar hanno preceduto un evento online o come proprietà online e eVar hanno preceduto un evento ID transazione.
