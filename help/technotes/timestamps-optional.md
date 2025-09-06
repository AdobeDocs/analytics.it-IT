---
description: Scopri i vantaggi e i vincoli dell’impostazione opzionale Marca temporale.
keywords: Implementazione di Analytics
title: Marche temporali opzionali
topic-fix: Developer and implementation
feature: Implementation Basics
exl-id: c6a232d1-d7ce-4f21-9e8a-45703992bc6e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 9%

---

# Marche temporali opzionali

Scopri i vantaggi e i vincoli dell’impostazione opzionale Marca temporale.

<!-- Hide video as it is not adding a lot according to feedback from customer in feedback report January 2025.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Timestamps Optional](https://video.tv.adobe.com/v/3418614?quality=12&learn=on&captions=ita){target="_blank"} for a demo video.

>[!ENDSHADEBOX]
-->


Marca temporale opzionale è l’impostazione predefinita per tutte le nuove suite di rapporti.

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiorna le app per utilizzare le marche temporali senza dover creare una nuova suite di rapporti.

>[!NOTE]
>
>Marca temporale opzionale è l&#39;impostazione predefinita per tutte le nuove suite per report generate da un modello Le nuove suite di rapporti copiate da una suite di rapporti esistente ereditano le impostazioni dall’originale.

Per ulteriori informazioni sull&#39;installazione, vedere [Marca temporale opzionale](/help/technotes/timestamps-optional.md).

## Marca temporale opzionale: integrazione di dati con marca temporale e senza marca temporale {#integrate}

Utilizzando la funzione facoltativa Marca temporale, puoi combinare dati senza marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e senza marca temporale da una pagina web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client.

* **Dati timestamp**. I dati timestamp lato client vengono acquisiti e inviati direttamente con i dati del dispositivo utilizzando variabili timestamp lato client: JavaScript in una pagina Web o utilizzando una chiamata SDK mobile ( [!DNL offlineEnabled=true]) in un&#39;app mobile.
* **Dati senza marca temporale**. Adobe imposta una marca temporale per i dati senza marca temporale in una suite di rapporti quando i dati raggiungono i server di raccolta.

Una suite di rapporti può avere una delle seguenti impostazioni di marca temporale:

* Marca temporale non consentita (impostazione che supporta visitorID)
* Marca temporale richiesta (impostazione visitorID non supportata)
* Marca temporale opzionale (impostazione che supporta visitorID tranne che per hit con marca temporale)

## Informazioni sulle funzioni facoltative Marca temporale {#features}

Marca temporale opzionale consente di integrare e generare rapporti tra più suite di rapporti con o senza marche temporali lato client incluse. Con Marca temporale opzionale puoi aggiornare l’app per utilizzare le marche temporali mentre utilizzi ancora dati senza marca temporale dell’app precedente.

| Nelle versioni precedenti... | Inoltre... |
|--- |--- |
| Impossibile inviare dati con marca temporale a una suite di rapporti globale senza marca temporale. Di conseguenza, i dati hit inviati da dispositivi offline venivano eliminati quando si aggiungeva a una suite di rapporti senza marca temporale. <br/><br/>Di conseguenza, i dati hit inviati da dati offline sono stati eliminati durante l&#39;aggiunta a una suite di rapporti senza marca temporale. | L’aggiornamento di un’app per raccogliere e utilizzare le marche temporali richiedeva l’utilizzo di una nuova suite di rapporti. <br/>Impossibile salvare nella suite di rapporti esistente o integrare dati esistenti durante l&#39;aggiornamento dell&#39;app per l&#39;utilizzo di marche temporali. |

**Con Marca temporale opzionale**, puoi integrare dati senza marca temporale da un sito Web attivo con dati offline da dispositivi mobili oppure aggiornare l&#39;app senza marca temporale a un&#39;app con marca temporale.

## Combinazione di dati in una suite di rapporti globale {#combine}

La combinazione di dati in una suite di rapporti globale può essere eseguita in diversi modi, tra cui l’assegnazione di tag a più suite, le regole di Vista e i file batch importati da origini offline.

>[!IMPORTANT]
>
>Pianifica attentamente la progettazione di ciascun set di dati dei componenti in modo che la combinazione abbia senso in una suite di rapporti globale.

## Best practice per l’utilizzo delle marche temporali {#best-pratices}

Di seguito sono riportate le best practice e alcuni requisiti e restrizioni di cui tenere conto durante l’integrazione di dati con marca temporale non registrata.

* In generale, i timestamp per una determinata visita o visitatore devono pervenire ad Adobe nell’ordine cronologico corretto.

  I dati fuori servizio possono includere dati in arrivo tardivo dalla raccolta dati offline e hit in arrivo tardivo oppure orologi non sincronizzati su dispositivi mobili offline. I dati fuori servizio possono influire negativamente sui calcoli del tempo (come i valori del tempo trascorso), sull’attribuzione (persistenza di eVar), sui conteggi di numero di visite/visite e sui rapporti sui percorsi.

* L&#39;utilizzo di marche temporali durante l&#39;impostazione di un [s.visitorID](/help/implement/vars/config-vars/visitorid.md) non è consigliato. Può causare dati fuori servizio.

* Le app ibride composte da un’app (dati con marca temporale, dati offline) che apre un browser web (dati live, senza marca temporale) non devono utilizzare marche temporali. Questo comporta una segnalazione imprecisa della sessione.

  Inoltre, le app ibride non devono impostare un ID visitatore.
