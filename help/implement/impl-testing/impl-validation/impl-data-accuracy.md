---
description: La convalida dell'accuratezza dei dati è un processo di confronto dei dati del rapporto con punti dati noti e verificabili.
keywords: Implementazione di Analytics
seo-description: La convalida dell'accuratezza dei dati è un processo di confronto dei dati del rapporto con punti dati noti e verificabili.
seo-title: Convalida accurata dei dati
solution: Analytics
title: Convalida accurata dei dati
topic: Sviluppatore e implementazione
uuid: 267f6c61-705a-41cf-9e09-4e2ce2331f32
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Convalida accurata dei dati

La convalida dell'accuratezza dei dati è un processo di confronto dei dati del rapporto con punti dati noti e verificabili.

Il processo di convalida deve essere completato dal personale Adobe, preferibilmente dal consulente Adobe (la persona che più conosce i dettagli di implementazione tecnica).

I punti dati preferiti per questa convalida, in ordine di preferenza, sono elencati di seguito:

* (Siti di conversione) Confronto tra ordini di conversione per un singolo giorno.
* Confronto di eventi di successo noti, in particolare i dati registrati in cui l'indirizzo IP e altre informazioni del browser generalmente memorizzati nei registri del server Web possono essere confrontati con i dati raccolti.
* Confronto delle visualizzazioni di pagina.

> [!NOTE] Le pagine predefinite, come [!DNL index.html], spesso ricevono traffico automatizzato o di monitoraggio. Queste pagine rappresentano una differenza maggiore per la raccolta dati basata su browser rispetto alle altre pagine visitate.

Tutti e tre i tipi di convalida richiedono un registro di debug o un feed di dati per il periodo di tempo in questione. Generalmente questo è un giorno o meno.

È previsto che gli ordini o gli eventi di successo possano essere misurati entro il 2-3% dei valori effettivi (raggiungendo talvolta livelli di precisione più elevati) utilizzando implementazioni standard basate su JavaScript. Ciò presuppone una pagina SSL, poiché le pagine SSL sono memorizzate nella cache con minore frequenza e per definizione non devono essere memorizzate nella cache. Un’implementazione con richieste di immagini completamente lato server su una pagina SSL dovrebbe corrispondere a circa lo 0-1% dei valori effettivi. Le pagine non sicure possono presentare differenze maggiori, ma comunque entro il 5% dei valori effettivi.

Quando si confrontano le visualizzazioni di pagina per un singolo periodo di tempo, è previsto che le visualizzazioni di pagina possano essere prese in considerazione entro il 5% dei valori effettivi, senza includere il monitoraggio (come Keynote o WhatsUpGold) o il traffico automatizzato (spider, bot e script).

I confronti dell'accuratezza dei dati devono tenere conto dei seguenti elementi:

* QA o altri tipi di test interni che possono essere filtrati dagli indirizzi IP o dalle regole VISTA.
* Tag avanzati che generano solo tag per determinati tipi di ordini o traffico.
* Le query per il confronto devono tenere conto di quanto viene misurato dal sito Web (esclusi i resi, gli ordini effettuati dal personale del servizio clienti o altre condizioni speciali).
* Verificate che le differenze di fuso orario tra la query e la suite di rapporti corrispondano.
* Nota chiave personalizzata o traffico simile (transazione nota chiave, ecc.) che misurano il processo di ordinazione e possono riflettersi nei tag, ma rimosse dai sistemi di ordinazione.
* Account per i processi di deduplicazione del cliente.
* Ricarica della pagina dell'ordine (gli ordini vengono deduplicati in base a *`purchaseID`*).

