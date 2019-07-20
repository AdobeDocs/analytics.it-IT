---
description: Passaggi di implementazione.
keywords: Implementazione di Analytics
seo-description: Passaggi di implementazione.
seo-title: Accettazione dell'implementazione
solution: Analytics
title: Accettazione dell'implementazione
topic: Sviluppatore e implementazione
uuid: 6 f 7 ec 56 e -9 e 4 f -4 dc 8-b 534-92 b 1580 b 5 b 47
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Accettazione dell'implementazione

Passaggi di implementazione.

I passaggi seguenti delineano il processo di implementazione.

1. Il consulente Adobe raccoglie i requisiti del rapporto e crea un piano di raccolta dati in base a tali requisiti.

   Il piano di raccolta dati include definizioni delle variabili, regole VISTA richieste e javascript personalizzati, correlazione dei dati e tutte le impostazioni per ogni suite di rapporti. Il client completa il questionario sull'implementazione.
1. Le risorse tecniche sul lato client implementano il codice, le variabili javascript specifiche per il sito e le variabili lato server.
1. Il consulente Adobe affronta problemi tecnici durante l'implementazione e contribuisce a progettare soluzioni in base alle esigenze.
1. Risorse tecniche sul test dell'unità lato client.

   Testers log in to [!DNL Analytics] and verifying all variables ( *`page name`*, *`channel`*, *`server`*, *`events`*, *`campaign`*, econversion variables, custom traffic variables, *`products`*, and all other variables).
1. Il client notifica ad Adobe che l'implementazione è completa.

   Il client fornisce un esempio di convalida (esempio di dati) al consulente Adobe per convalidare l'accuratezza dei dati. (Le suite di rapporti generate in VISTA vengono convalidate confrontando le metriche appropriate. Un contratto client-Adobe delle metriche da convalidare per tali suite di rapporti deve essere eseguito in anticipo, al momento della creazione della regola VISTA.)
1. Il client invia fax (o firma online) un'accettazione implementazione e un Contratto per i siti appropriati.
1. Una volta ricevuta l'accettazione, il consulente Adobe abilita le procedure consigliate Adobe - la certificazione di verifica dell'implementazione all'interno dell'interfaccia.
1. Facoltativamente, il client può negoziare con Adobe per i servizi per pagine chiave del sito implementato (in genere, questi sono i modelli principali, la home page e le pagine di immissione critica).

   Questo software di monitoraggio è descritto in un documento separato, ma tiene traccia delle pagine caricando e eseguendo la pagina, quindi confrontando la richiesta dell'immagine a una linea di base memorizzata in un database. Se vengono rilevate delle differenze, il software notifica ad Adobe (AM/IE) e al personale client via e-mail.

I seguenti elementi aiutano a garantire un'implementazione corretta:

* Un documento best practice, rivolto al client e illustra i processi in dettaglio.
* Documento di convalida utilizzato dal cliente per testare l'implementazione.
* Un modulo Accettazione e Contratto per consentire al client di firmare.
* Un'applicazione di monitoraggio che convalida continuamente i tag.
* Una relazione con Accenture per il testing di implementazione.
* Utility e/o strumenti per il confronto tra visualizzazioni di pagina e/o ordini. Questi confronti possono risultare difficili.
* Un metodo o un processo per ottenere rapidamente il registro di debug per un giorno specificato, tramite ID suite di rapporti.

