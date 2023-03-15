---
description: Scopri come migrare le regole di elaborazione di Mobile Services in Adobe Analytics
title: Migrare le regole di elaborazione di Mobile Services ad Adobe Analytics
feature: Processing Rules
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 17%

---

# Migrare le regole di elaborazione di Mobile Services ad Adobe Analytics

Questo documento fornisce istruzioni su come migrare ad Adobe Analytics eventuali regole di elaborazione aggiuntive, oltre alle Metriche del ciclo di vita, create nell’interfaccia utente di Mobile Services.

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a prop e eVar. EVar Ad esempio, puoi inserire il valore di una variabile di dati contestuali &quot;search-term&quot; nel valore di una variabile Commerce e sovrascrivere tale valore su ogni hit. Ad esempio, puoi inserire il valore di una variabile di dati contestuali &quot;search-term&quot; nel valore di una variabile Commerce e sovrascrivere tale valore su ogni hit. Senza regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non compilano alcun rapporto in Analytics.

Questo documento illustra anche come creare rapporti sull’utilizzo dei dispositivi mobili in Analysis Workspace.

## Migra regole di elaborazione

Se utilizzi Mobile Services per funzionalità gratuite, come le regole di elaborazione e le funzioni di reporting sull’utilizzo, puoi passare facilmente all’interfaccia utente di Analytics (interfaccia utente delle regole di elaborazione o Analysis Workspace) per eseguire queste funzioni. Per le metriche del ciclo di vita, o per le regole impostate nell’interfaccia utente delle regole di elaborazione di AA, non è necessario eseguire alcuna migrazione. Le Metriche del ciclo di vita sono metriche &quot;pronte all’uso&quot; che vengono raccolte automaticamente quando l’SDK di Mobile viene implementato per la prima volta nell’app.

Tuttavia, se imposti ulteriori regole di elaborazione nell’interfaccia utente di Mobile Services (oltre alle Metriche del ciclo di vita), devi migrarle in modo da poterle modificare o eliminare in Analytics dopo aver perso l’accesso a Mobile Services.

1. Accedi a `experience.adobe.com` e vai a Mobile Services.
1. Fai clic sull’icona a forma di ingranaggio di un’app mobile di cui desideri eseguire la migrazione ad Adobe Analytics per le mappature delle variabili di contesto.
1. Fai clic su **[!UICONTROL Manage Variables and Metrics]** voce di menu, quindi fare clic su **[!UICONTROL Custom Variables]** scheda. Qui puoi vedere quali mappature di variabili di contesto (dati di contesto) sono state aggiunte alla configurazione. Prendi nota di queste configurazioni (o scatta una schermata). Esempio:

   ![Variabile di contesto](assets/context-var.png)

1. Ad Experience Cloud, passa ad Adobe Analytics e accertati di trovarti nella stessa suite di rapporti per dispositivi mobili che stavi esaminando in Mobile Services.
1. Vai a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
1. Fai clic su **[!UICONTROL Add Rule]** (Usa modello di attribuzione non predefinito).
1. Ignora le condizioni e procedi all’aggiunta delle stesse variabili di contesto esistenti in Mobile Services.

   ![Regola di elaborazione](assets/proc-rule.png)

1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

## Generazione di rapporti sull’utilizzo dei dispositivi mobili in Analysis Workspace

Oltre alle metriche e alle dimensioni per dispositivi mobili (se la suite di rapporti è abilitata per Mobile Services), Analysis Workspace contiene diversi modelli di progetto per dispositivi mobili che possono facilitare l’analisi:

* **[!UICONTROL Messaging]**: Si focalizza sulle prestazioni di messaggi in-app e push.
* **[!UICONTROL Location]**: include una mappa che mostra i dati della posizione.
* **[!UICONTROL Key Metrics]**: Controlla le metriche chiave della tua app.
* **[!UICONTROL App Usage]**: Quanti utenti, avvii e primi avvii sono stati registrati per l’app, e quanto dura in media una sessione?
* **[!UICONTROL Acquisition]**: come stanno andando i collegamenti per acquisizione mobile?
* **[!UICONTROL Performance]**: Quali sono le prestazioni dell’app e dove vengono riscontrati problemi dagli utenti?
* **[!UICONTROL Retention]**: Chi sono i miei utenti più fedeli e cosa fanno?
* **[!UICONTROL Journeys]**: Quali sono i pattern di utilizzo principali per la l’app?

Ecco un estratto del modello per l’utilizzo delle app mobili:

![Utilizzo app mobili](assets/mobile-app-usage.png)

Per accedere ai modelli:

1. Accedi a `experience.adobe.com` e seleziona Analytics.
1. Assicurati di trovarti in una suite di rapporti abilitata per Mobile Services.
1. Fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Fai clic su **[!UICONTROL Create New Project]** (Usa modello di attribuzione non predefinito).
1. Seleziona uno dei modelli Mobile e fai clic su **[!UICONTROL Create]**.

## Migrazione di altre funzionalità di Mobile Services

Anche la seguente funzionalità di Mobile Services è collegata ad Adobe Analytics, ma richiede uno SKU di Adobe Analytics acquistato:

* Collegamenti di acquisizione
* Messaggi push
* Messaggistica in-app
* Gestione dei punti di interesse della posizione

Se utilizzi Mobile Services per le funzionalità a pagamento, non disponi di un percorso di migrazione valido ad altri strumenti interni/esterni:

* Per i collegamenti di acquisizione, possiamo indirizzarti a partner Adobi per soddisfare le tue esigenze.
* I messaggi push e i messaggi in-app sono disponibili in Adobe Campaign Standard e Adobe Campaign Classic (solo push). Tuttavia, il set di dati sottostante utilizzato per il targeting è diverso. Consigliamo di collaborare con il team del tuo account Adobe per determinare le opzioni di migrazione per i dati di messaggistica.
* Per la funzionalità Posizione, ti invitiamo ad adottare il nuovo [Adobe Experience Platform Location Service](https://www.adobe.com/experience-platform/location-service.html), gratuito per tutti i clienti AEP.
