---
description: Questa integrazione combina le funzionalità di ricerca dei clienti della Qualtrics Research Suite con i dati avanzati raccolti in Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la tua organizzazione.
subtopic: Qualtrics
title: Connettore dati Qualtrics per Adobe Analytics
feature: Data Connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
exl-id: 5c1234b1-bca8-4e7a-981e-1379e88821b8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 5%

---

# Connettore dati Qualtrics per Adobe Analytics{#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnologia Adobe Data Connector terminerà il 1° agosto 2021. [Ulteriori informazioni...](/help/import/data-connectors/data-connectors-eol.md)

Questa integrazione combina le funzionalità di ricerca dei clienti della Qualtrics Research Suite con i dati avanzati raccolti in Adobe Analytics per creare potenti opportunità di analisi e ottimizzazione per la tua organizzazione.

Questa integrazione bidirezionale collega prima i dati di risposta del sondaggio Qualtrics con i dati clickstream dei visitatori. Vengono quindi inserite le azioni e gli attributi comportamentali rilevanti, da Adobe Analytics, nel reporting del sondaggio Qualtrics.

## Vantaggi e caratteristiche principali{#key-benefits-and-features}

* Crea segmenti di utenti in base alle risposte fornite dagli utenti a domande specifiche del sondaggio.
* Generazione di rapporti sul traffico e sulla conversione basati sui dettagli del sondaggio, della domanda e del livello di risposta.
* Utilizza solo 1 ListVar, 1 eVar e 1 evento per integrare sondaggi Qualtrics illimitati.
* Generazione di rapporti Qualtrics ottimizzata con fino a 5 dimensioni di conversione personalizzate, 5 dimensioni di traffico personalizzate, 5 eventi di successo personalizzati e più di 20 altre metriche e dimensioni standard tracciate con Adobe Analytics.
* Dati di sondaggio integrati all’interno dei flussi Adobe Analytics in &quot;live&quot; durante la presentazione delle indagini. Le esportazioni verso Qualtrics avvengono quotidianamente.

## Prima di attivare questo connettore{#before-you-activate-this-connector}

### Prerequisiti di Adobe {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* Deve essere un cliente corrente di Adobe Analytics.
* Deve essere un utente amministratore.
* Nella suite di rapporti deve essere presente una variabile di elenco disponibile e abilitata.
* Nella suite di rapporti deve essere presente una variabile eVar (o prop) disponibile e abilitata.
* Deve essere disponibile un evento personalizzato nella suite di rapporti.

### Prerequisiti per le soluzioni Qualtrics {#section-dbb780af47c145d7b6ae12acde3ca94c}

* Deve essere un cliente attuale della Qualtrics Research Suite.
* Deve essere un utente a cui sono state assegnate le autorizzazioni per abilitare l&#39;integrazione di Adobe Analytics.
* Deve essere in grado di generare un token Adobe Analytics all’interno dell’ area **[!UICONTROL Qualtrics IDs]** della Suite di ricerca.
