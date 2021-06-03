---
description: Scopri i vantaggi e i vincoli dell’utilizzo dell’impostazione Marca temporale opzionale.
keywords: Implementazione di Analytics
title: Utilizzo dei timestamp opzionali
topic-fix: Developer and implementation
uuid: 956aaa16-6ffa-4b63-b022-a659f5143e00
exl-id: c6a232d1-d7ce-4f21-9e8a-45703992bc6e
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 15%

---

# Utilizzo dei timestamp opzionali

Scopri i vantaggi e i vincoli dell’utilizzo dell’impostazione Marca temporale opzionale.

Marca temporale opzionale è l’impostazione predefinita per tutte le nuove suite di rapporti.

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiorna le app per utilizzare le marche temporali senza dover creare una nuova suite di rapporti.

>[!NOTE]
>
>Marca temporale opzionale è l&#39;impostazione predefinita per tutte le nuove suite per report generate da un modello Le nuove suite di rapporti copiate da una suite di rapporti esistente erediteranno le impostazioni dall’originale.

Per ulteriori informazioni sulla configurazione, consulta [Marca temporale opzionale](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/timestamp-optional.html) .

## Marca temporale opzionale: Integrazione dei dati con marca temporale e dei dati con marca non temporale {#section_BF17CB593044462B993FD0D28EA56518}

Utilizzando la funzione facoltativa Marca temporale, puoi combinare dati senza marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e senza marca temporale da una pagina web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client.

* **Dati di marca temporale**. I dati di marca temporale lato client vengono acquisiti e inviati direttamente con i dati del dispositivo utilizzando le variabili di marca temporale lato client: Javascript su una pagina web o utilizzando una chiamata SDK Mobile ( [!DNL offlineEnabled=true]) in un’app mobile.
* **Dati** non di marca temporale. Adobe imposta una marca temporale sui dati privi di marca temporale in una suite di rapporti quando i dati arrivano sui server di raccolta.


Una suite di rapporti può avere una delle seguenti impostazioni di marca temporale:

* Marca temporale non consentita (impostazione di visitorID supportata)
* Marca temporale necessaria (impostazione visitorID non supportata)
* Marca temporale opzionale (impostazione di visitorID supportato ma non sugli hit con marca temporale)

## Informazioni sulle funzioni opzionali delle marche temporali {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Marca temporale opzionale consente di integrare e creare rapporti tra più suite di rapporti con o senza marche temporali lato client incluse. Con Marca temporale opzionale è possibile aggiornare l’app in modo da utilizzare marche temporali mentre si utilizzano comunque dati privi di marca temporale dell’app precedente.

| Nelle versioni precedenti... | Inoltre... |
|--- |--- |
| Impossibile inviare i dati con marca temporale a una suite di rapporti globale senza marca temporale. Di conseguenza, i dati hit inviati da dispositivi offline sono stati eliminati quando si aggiungevano a una suite di rapporti senza marca temporale. <br/><br/>Di conseguenza, i dati hit inviati da dati offline sono stati eliminati quando si aggiungevano a una suite di rapporti senza marca temporale. | L’aggiornamento di un’app per raccogliere e utilizzare le marche temporali richiedeva l’utilizzo di una nuova suite di rapporti. <br/>Non è stato possibile salvare nella suite di rapporti esistente o integrare dati esistenti quando si aggiorna l’app per l’utilizzo di marche temporali. |

**Con Marca temporale opzionale**, puoi integrare dati non con marca temporale da un sito web live con dati offline da dispositivi mobili oppure aggiornare l’app senza marca temporale a un’app con marca temporale.

## Combinazione di dati in una suite di rapporti globale {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

La combinazione di dati in una suite di rapporti globale può essere eseguita in diversi modi, tra cui l’assegnazione di tag a più suite, le regole Vista e i file batch importati da origini offline.

>[!IMPORTANT]
>
>Pianifica attentamente la progettazione di ciascun set di dati dei componenti in modo che la combinazione abbia senso in una suite di rapporti globale.

## Procedure consigliate per l’utilizzo delle marche temporali {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

Di seguito sono riportate le best practice e alcuni requisiti e limitazioni da tenere presenti durante l’integrazione di marche temporali con dati privi di marca temporale.

* In generale, i timestamp di un visitatore o di una visita devono arrivare all&#39;Adobe nell&#39;ordine cronologico corretto.

   I dati fuori ordine possono includere i dati in arrivo ritardati dalla raccolta dati offline e gli hit in arrivo ritardati o gli orologi non sincronizzati su dispositivi mobili offline. I dati fuori ordine possono avere un impatto negativo sui calcoli del tempo (come i valori del tempo trascorso), sull’attribuzione (persistenza eVar), sul numero di visite/sui conteggi delle visite e sui rapporti sui percorsi.

* L&#39;utilizzo di marche temporali quando si imposta un [s.visitorID](https://experienceleague.adobe.com/docs/analytics/technotes/visitor-identification.html) non è consigliato. Può portare a dati fuori servizio.

* Le app ibride composte da un’app (con marca temporale e dati offline) che apre un browser web (dati live e senza marca temporale) non devono utilizzare marche temporali. Ne consegue una segnalazione inesatta della sessione.

   Inoltre, le app ibride non devono impostare un ID visitatore.
