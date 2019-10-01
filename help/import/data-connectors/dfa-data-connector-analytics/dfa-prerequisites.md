---
description: nulle
keywords: DFAE
seo-description: nulle
seo-title: Prerequisiti
solution: Analytics
title: Prerequisiti
topic: Connettori dati
uuid: b5f5e30c-e269-41a4-9236-5ddc404bfd94
translation-type: tm+mt
source-git-commit: a31f25e8a4681cf34525a7994b00580aa3aac15d

---


# Prerequisiti{#prerequisites}

Prima di avviare l’integrazione di Adobe Data Connectors per DFA, effettuate le seguenti operazioni:

* Decidete se eseguire l'integrazione con la versione 1.5 dell'integrazione o attendere la versione 2.0. Questa decisione dipende da quali funzioni vengono utilizzate nel vostro account DFAE e dal periodo di tempo in cui desiderate integrarsi.
* Decidete in che modo gli inserzionisti DFA verranno mappati sulle suite di rapporti di Adobe Analytics. Ad esempio, se hai più inserzionisti DFA e più suite di rapporti, dovrai decidere quali inserzionisti abbinano a quali suite di rapporti.
* Implementa il codice di raccolta dati Adobe su tutte le pagine da monitorare, utilizzando la versione H.22 o successiva del codice di raccolta dati.
* Conoscere l'ID inserzionista per un account DFA che fa parte della configurazione Floodlight da integrare. L'integrazione importa automaticamente tutti gli inserzionisti che si trovano all'interno della configurazione di Floodlight.
* Conoscere il nome utente e la password del tuo account DFA.
* Associate ciascun inserzionista DFA a una sola suite di rapporti Adobe Analytics. L’aggiunta di tag a più suite di rapporti non è supportata con l’integrazione Genesis predefinita per il DFA.
* Aggiungete un parametro di stringa query click-through alla pagina di destinazione per ogni posizionamento DFA che farà parte dell’integrazione. Questo parametro della stringa di query è necessario per contare correttamente i Click-through.
* Configura i posizionamenti DFA in modo che non reindirizzino i visitatori attraverso più domini. Ad esempio, un Posizionamento non dovrebbe indirizzare i rispondenti a un micro-sito ospitato in www.xyz.com se il micro-sito poi li reindirizzerà a un altro sito, www.fgh.com. Se la risposta della campagna si estende su più domini, i dati click-through e view-through possono essere ingranditi e fuorvianti.
* Identificate una variabile personalizzata in Reporting e analisi per contenere le informazioni sulla campagna.
* Identificare una eVar di Reporting e analisi per memorizzare le informazioni di visualizzazione del modulo DFA. Utilizzate questa eVar solo per questa integrazione DFA.
* Identificare gli eventi Reporting e analisi in cui memorizzare le impression e i dati Click. Potrebbe essere necessario rinominare correttamente questi eventi.
* (Facoltativo) Identificare gli eventi Reporting e analisi che archivieranno i dati dei costi DFA. Potrebbe essere necessario rinominare correttamente questi eventi.
* (Facoltativo) Identificare una variabile personalizzata Reporting e analisi ed un evento di successo che memorizzerà gli errori e i timeout DFA. Queste variabili aiutano a diagnosticare i problemi che potrebbero insorgere con l'integrazione.
* (Facoltativo) Crea un account e-mail speciale per ricevere informazioni e notifiche relative all’integrazione dei connettori dati per il DFA.

