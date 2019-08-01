---
description: nulle
keywords: DFA
seo-description: nulle
seo-title: Prerequisiti
solution: Analytics
title: Prerequisiti
topic: Connettori dati
uuid: b 5 f 5 e 30 c-e 269-41 a 4-9236-5 ddc 404 bfd 94
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Prerequisiti{#prerequisites}

Prima di avviare l'integrazione di Adobe Data Connettori per DFA, effettua le operazioni seguenti:

* Decidete se integrare con la versione 1.5 dell'integrazione o per attendere la versione 2.0. Questa decisione dipende dalle funzioni utilizzate nell'account DFA e dal periodo di tempo in cui si desidera integrare. See [About Version 2.0](../dfa-data-connector-analytics/dfa-version-differences.md#concept-2c7d6a6ab8524dccad96ea0c17228664) for more information.
* Decidi in che modo i inserzionisti DFA verranno mappati sulle suite di rapporti di Adobe Analytics. Ad esempio, se hai più crezionisti DFA e più suite di rapporti, dovrai decidere quale coppia pubblicitaria con quali suite di rapporti.
* Implementa il codice di raccolta dati Adobe su tutte le pagine da monitorare, utilizzando la versione H .22 o successiva del codice di raccolta dati.
* Conoscere l'ID inserzionista per un account DFA che fa parte della configurazione fiordlight che desideri integrare. L'integrazione importa automaticamente tutti gli Advertiser che si trovano nella configurazione Floodlight.
* Conoscere il nome utente e la password dell'account DFA.
* Associate ogni inserzionista DFA a una sola suite di rapporti di Adobe Analytics. L'assegnazione di tag a più suite di rapporti non è supportata con l'integrazione Genesis predefinita per DFA.
* Aggiungete un parametro di stringa di query click-through alla pagina di destinazione per ogni posizione DFA che sarà parte dell'integrazione. Questo parametro di stringa query è necessario per conteggiare correttamente i click-through.
* Configura le posizioni DFA in modo che non eseguano nuovamente il reindirizzamento dei visitatori attraverso più domini. Ad esempio, un posizionamento non deve rispondere direttamente a un micro-sito ospitato in www.xyz.com se il micro-site quindi li reindirizza a un altro sito, www.fgh.com. Se la risposta della campagna si estende su più domini, i dati click-through e view-through possono essere ingranditi e fuorvianti.
* Identifica una variabile personalizzata in Reporting e analisi per contenere le informazioni sulla campagna.
* Identifica un evar Reporting e analisi per memorizzare le informazioni di visualizzazione DFA. Utilizzate questa evar solo per l'integrazione DFA.
* Identificare gli eventi Reporting e analisi in cui desideri memorizzare i dati Impression e Clic. Potrebbe essere utile rinominare questi eventi in modo appropriato.
* (Facoltativo) Identificate gli eventi Reporting e analisi che archivieranno i dati costi DFA. Potrebbe essere utile rinominare questi eventi in modo appropriato.
* (Facoltativo) Identifica una variabile personalizzata di reporting e analisi e un evento di successo che archiviano gli errori e i timeout DFA. Queste variabili contribuiscono a diagnosticare i problemi che potrebbero sorgere nell'integrazione.
* (Facoltativo) Crea un account e-mail speciale per ricevere informazioni e notifiche correlate all'integrazione dei Connettori dati per DFA.

