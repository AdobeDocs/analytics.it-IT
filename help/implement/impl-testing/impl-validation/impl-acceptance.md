---
description: Procedura di implementazione
keywords: Implementazione di Analytics
seo-description: Procedura di implementazione
seo-title: Accettazione dell'implementazione
solution: Analytics
title: Accettazione dell'implementazione
topic: Sviluppatore e implementazione
uuid: 6f7ec56e-9e4f-4dc8-b534-92b1580b5b47
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Accettazione dell'implementazione

Procedura di implementazione

I passaggi seguenti delineano il processo di implementazione.

1. Il consulente Adobe raccoglie i requisiti dei rapporti e crea un piano di raccolta dati basato su tali requisiti.

   Il piano di raccolta dei dati include definizioni di variabili, regole VISTA obbligatorie e JavaScript personalizzato, correlazione dei dati e tutte le impostazioni per ciascuna suite di rapporti. Il cliente completa il Questionario di implementazione.
1. Le risorse tecniche sul lato client implementano il codice, JavaScript specifici per il sito e variabili lato server.
1. Il consulente Adobe affronta problemi tecnici durante l'implementazione e assiste nella definizione delle soluzioni come necessario.
1. Risorse tecniche sull'unità lato client per verificare l'implementazione.

   I tester accedono [!DNL Analytics] e verificano tutte le variabili ( *`page name`*, *`channel`*, *`server`*, *`events`*, *`campaign`*, variabili di conversione, variabili di traffico personalizzate *`products`* e tutte le altre variabili).
1. Il client notifica ad Adobe che l'implementazione è completa.

   Il client fornisce un esempio di convalida (esempio di dati) al consulente Adobe per convalidare l'accuratezza dei dati. (Le suite di rapporti generate da VISTA vengono convalidate confrontando le metriche appropriate. Un accordo client-Adobe sulle metriche da convalidare per tali suite di rapporti deve essere fatto in anticipo, al momento della creazione della regola VISTA.)
1. Il client invia via fax (o firma online) un'accettazione dell'implementazione e un accordo per il sito o i siti appropriati.
1. Dopo aver ricevuto l'accettazione, il consulente Adobe consente la certificazione Adobe Best Practices - Implementation Verification all'interno dell'interfaccia.
1. Facoltativamente, il client può contrarre con Adobe servizi di monitoraggio per le pagine chiave del sito implementato (in genere, si tratta dei modelli principali, della home page e delle pagine di immissione critiche).

   Questo software di monitoraggio è descritto in un documento separato, ma tiene traccia delle pagine caricando ed eseguendo la pagina, quindi confrontando la richiesta di immagine con una baseline memorizzata in un database. Se vengono rilevate delle differenze, il software invia una notifica via e-mail ad Adobe (AM/IE) e al personale cliente specificati.

Gli elementi seguenti contribuiscono a garantire il successo dell’implementazione:

* Un documento sulle procedure ottimali rivolto ai clienti che illustra i processi in modo dettagliato.
* Il documento di convalida utilizzato dal cliente per unit test dell'implementazione.
* Un modulo di accettazione dell'implementazione e di accordo per la firma da parte del client.
* Applicazione di monitoraggio che convalida continuamente i tag.
* Una relazione con Accenture per facilitare i test di implementazione.
* Utility e/o strumenti per il confronto tra visualizzazioni e/o ordini delle pagine. Quei confronti possono diventare abbastanza difficili.
* Metodo o processo per ottenere rapidamente il registro di debug per un dato giorno, per ID suite di rapporti.

