---
description: Prerequisiti per l’utilizzo del connettore dati DFA con Adobe Analytics.
keywords: DFA
title: Prerequisiti
topic: Connettori dati
uuid: b5f5e30c-e269-41a4-9236-5ddc404bfd94
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 1%

---


# Prerequisiti{#prerequisites}

Prima di avviare l’integrazione di Adobe Data Connectors per DFA, procedi come segue:

* Decidi se eseguire l’integrazione con la versione 1.5 dell’integrazione o attendere la versione 2.0. Questa decisione dipende dalle funzionalità utilizzate nel tuo account DFA e dall’intervallo di tempo in cui desideri eseguire l’integrazione.
* Decidi in che modo gli inserzionisti DFA verranno mappati sulle suite di rapporti di Adobe Analytics. Ad esempio, se disponi di più inserzionisti DFA e più suite di rapporti, dovrai decidere quali inserzionisti associano a quali suite di rapporti.
* Implementa il codice di raccolta dati di Adobe su tutte le pagine che desideri monitorare, utilizzando la versione H.22 o successiva del codice di raccolta dati.
* Conoscere l’ID inserzionista per un account DFA che fa parte della configurazione di Floodlight che si desidera integrare. L’integrazione importa automaticamente tutti gli inserzionisti che si trovano all’interno della configurazione di Floodlight.
* Conoscere il nome utente e la password del tuo account DFA.
* Associa ogni inserzionista DFA a una sola suite di rapporti di Adobe Analytics. L’assegnazione tag a più suite di rapporti non è supportata con l’integrazione di Genesis predefinita per DFA.
* Aggiungi un parametro della stringa di query click-through alla pagina di destinazione per ogni posizionamento DFA che farà parte dell’integrazione. Questo parametro della stringa di query è necessario per contare correttamente i click-through.
* Configura i posizionamenti DFA in modo che non reindirizzino i visitatori attraverso più domini. Ad esempio, un posizionamento non dovrebbe indirizzare i rispondenti a un micro sito ospitato in www.xyz.com se il micro sito poi li reindirizzerà a un altro sito, www.fgh.com. Se la risposta della campagna si estende su più domini, i dati click-through e view-through possono essere gonfiati e fuorvianti.
* Identifica una variabile personalizzata in Reporting e analisi per contenere le informazioni sulla campagna.
* Identifica un eVar di Reports &amp; Analytics per memorizzare le informazioni di visualizzazione through DFA. Utilizza questo eVar solo per questa integrazione DFA.
* Identifica gli eventi di Reports &amp; Analytics in cui memorizzare le impressioni e i dati di clic. È possibile rinominare questi eventi in modo appropriato.
* (Facoltativo) Identifica gli eventi Reports &amp; Analytics che memorizzeranno i dati DFA Cost. È possibile rinominare questi eventi in modo appropriato.
* (Facoltativo) Identifica una variabile personalizzata e un evento di successo di Reports &amp; Analytics che memorizzerà gli errori e i timeout DFA. Queste variabili aiutano a diagnosticare i problemi che potrebbero insorgere con l’integrazione.
* (Facoltativo) Crea un account e-mail speciale per ricevere informazioni e notifiche relative all’integrazione dei Data Connectors per DFA.

