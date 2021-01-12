---
description: Questa integrazione combina le capacità di ricerca dei clienti della Qualtrics Research Suite con i dati avanzati raccolti in  Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la vostra organizzazione.
subtopic: Qualtrics
title: Connettore dati Qualtrics per Adobe Analytics
topic: Data connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 4%

---


# Connettore dati Qualtrics per Adobe Analytics{#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia del Connettore dati del Adobe  terminerà il 1 agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione combina le capacità di ricerca dei clienti della Qualtrics Research Suite con i dati avanzati raccolti in  Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la vostra organizzazione.

Questa integrazione bidirezionale collega innanzitutto i dati della risposta del sondaggio Qualtrics con i dati del clickstream dei visitatori. Successivamente, inserisce le azioni e gli attributi comportamentali rilevanti, da  Adobe Analytics, nel reporting del sondaggio Qualtrics.

## Vantaggi e funzionalità principali{#key-benefits-and-features}

* Crea segmenti di utenti in base alle risposte date dagli utenti a domande specifiche del sondaggio.
* Generazione di rapporti sul traffico e sulla conversione in base a sondaggi, domande e livelli di risposta.
* Utilizza solo 1 ListVar, 1  e 1 evento per integrare un numero illimitato di sondaggi Qualtrics.
* Migliorate la generazione di rapporti Qualtrics con fino a 5 dimensioni di conversione personalizzate, 5 dimensioni di traffico personalizzate, 5 eventi di successo personalizzati e più di 20 altre metriche e dimensioni standard tracciate con  Adobe Analytics.
* I dati di indagine integrata all&#39;interno  flussi Adobe Analytics in &quot;live&quot; durante la presentazione delle indagini. Le esportazioni verso i prodotti alternativi avvengono quotidianamente.

## Prima di attivare questo connettore{#before-you-activate-this-connector}

### Prerequisiti  Adobe {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* Deve essere un cliente corrente di  Adobe Analytics.
* Deve essere un utente amministratore.
* Nella suite di rapporti deve essere presente 1 variabile Elenco disponibile e abilitata.
* Nella suite di rapporti deve essere disponibile una variabile  eVar (o proprietà) abilitata e abilitata.
* Devono essere disponibili 1 evento personalizzato nella suite di rapporti.

### Prerequisiti per la query {#section-dbb780af47c145d7b6ae12acde3ca94c}

* Deve essere un cliente corrente della Qualtrics Research Suite.
* Deve essere un utente a cui sono state assegnate le autorizzazioni per abilitare  integrazione Adobe Analytics.
* Deve essere in grado di generare un token Adobe Analytics  all&#39;interno dell&#39;area **[!UICONTROL Qualtrics IDs]** di Research Suite.
