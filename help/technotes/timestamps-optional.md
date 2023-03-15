---
description: Scopri i vantaggi e i vincoli dell’impostazione opzionale Marca temporale.
keywords: Implementazione di Analytics
title: Utilizzo dei timestamp opzionali
topic-fix: Developer and implementation
feature: Implementation Basics
exl-id: c6a232d1-d7ce-4f21-9e8a-45703992bc6e
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 17%

---

# Utilizzo dei timestamp opzionali

Scopri i vantaggi e i vincoli dell’impostazione opzionale Marca temporale.

Video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/335740/?quality=12)

Marca temporale opzionale è l’impostazione predefinita per tutte le nuove suite di rapporti.

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiorna le app per utilizzare le marche temporali senza dover creare una nuova suite di rapporti.

>[!NOTE]
>
>Marca temporale opzionale è l&#39;impostazione predefinita per tutte le nuove suite per report generate da un modello Le nuove suite di rapporti copiate da una suite di rapporti esistente ereditano le impostazioni dall’originale.

Consulta [Marca temporale opzionale](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/timestamp-optional.html?lang=it) per ulteriori informazioni sulla configurazione.

## Marca temporale opzionale: integrazione di dati con marca temporale e senza marca temporale {#section_BF17CB593044462B993FD0D28EA56518}

Utilizzando la funzione facoltativa Marca temporale, puoi combinare dati senza marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e senza marca temporale da una pagina web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client.

* **Dati marca temporale**. I dati timestamp lato client vengono acquisiti e inviati direttamente con i dati del dispositivo utilizzando variabili timestamp lato client: JavaScript su una pagina web o utilizzando una chiamata SDK mobile ( [!DNL offlineEnabled=true]) in un&#39;app mobile.
* **Dati senza marca temporale**. Adobe imposta una marca temporale per i dati senza marca temporale in una suite di rapporti quando i dati raggiungono i server di raccolta.

Una suite di rapporti può avere una delle seguenti impostazioni di marca temporale:

* Marca temporale non consentita (impostazione che supporta visitorID)
* Marca temporale richiesta (impostazione visitorID non supportata)
* Marca temporale opzionale (impostazione che supporta visitorID tranne che per hit con marca temporale)

## Informazioni sulle funzioni opzionali con marca temporale {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Marca temporale opzionale consente di integrare e generare rapporti tra più suite di rapporti con o senza marche temporali lato client incluse. Con Marca temporale opzionale puoi aggiornare l’app per utilizzare le marche temporali mentre utilizzi ancora dati senza marca temporale dell’app precedente.

| Nelle versioni precedenti... | Inoltre... |
|--- |--- |
| Impossibile inviare dati con marca temporale a una suite di rapporti globale senza marca temporale. Di conseguenza, i dati hit inviati da dispositivi offline venivano eliminati quando si aggiungeva a una suite di rapporti senza marca temporale. <br/><br/>Di conseguenza, i dati hit inviati da dati offline venivano eliminati quando si aggiungeva a una suite di rapporti senza marca temporale. | L’aggiornamento di un’app per raccogliere e utilizzare le marche temporali richiedeva l’utilizzo di una nuova suite di rapporti. <br/>Non è possibile salvare nella suite di rapporti esistente o integrare i dati esistenti durante l’aggiornamento dell’app per l’utilizzo delle marche temporali. |

**Con Marca Temporale Opzionale**, puoi integrare dati senza marca temporale da un sito web live con dati offline da dispositivi mobili, oppure aggiornare l’app senza marca temporale a un’app con marca temporale.

## Combinazione di dati in una suite di rapporti globale {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

La combinazione di dati in una suite di rapporti globale può essere eseguita in diversi modi, tra cui l’assegnazione di tag a più suite, le regole di Vista e i file batch importati da origini offline.

>[!IMPORTANT]
>
>Pianifica attentamente la progettazione di ciascun set di dati dei componenti in modo che la combinazione abbia senso in una suite di rapporti globale.

## Best practice per l’utilizzo delle marche temporali {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

Di seguito sono riportate le best practice e alcuni requisiti e restrizioni di cui tenere conto durante l’integrazione di dati con marca temporale non registrata.

* In generale, le marche temporali per una determinata visita o visitatore devono arrivare all’Adobe nell’ordine cronologico corretto.

   I dati fuori servizio possono includere dati in arrivo tardivo dalla raccolta dati offline e hit in arrivo tardivo oppure orologi non sincronizzati su dispositivi mobili offline. I dati fuori servizio possono influire negativamente sui calcoli del tempo (come i valori del tempo trascorso), sull’attribuzione (persistenza eVar), sui conteggi di numero di visite/visite e sui rapporti sui percorsi.

* Utilizzo dei timestamp durante l’impostazione di un [s.visitorID](/help/implement/vars/config-vars/visitorid.md) non è consigliato. Può causare dati fuori servizio.

* Le app ibride composte da un’app (dati con marca temporale, dati offline) che apre un browser web (dati live, senza marca temporale) non devono utilizzare marche temporali. Questo comporta una segnalazione imprecisa della sessione.

   Inoltre, le app ibride non devono impostare un ID visitatore.
