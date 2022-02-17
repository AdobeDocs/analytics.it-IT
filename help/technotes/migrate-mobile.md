---
description: Scopri come migrare le regole di elaborazione di Mobile Services in Adobe Analytics
title: Migrazione delle regole di elaborazione di Mobile Services ad Adobe Analytics
feature: Processing Rules
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
source-git-commit: c8faf29262b9b04fc426f4a26efaa8e51293f0ec
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 12%

---

# Migrazione delle regole di elaborazione di Mobile Services ad Adobe Analytics

Questo documento fornisce istruzioni su come migrare in Adobe Analytics eventuali regole di elaborazione aggiuntive, oltre alle metriche del ciclo di vita, create nell’interfaccia utente di Mobile Services.

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a proprietà ed eVar. Ad esempio, puoi inserire il valore di una variabile di dati di contesto &quot;a termine di ricerca&quot; nel valore di un eVar di variabile di commercio e sovrascrivere tale valore su ogni hit. Senza regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non compilano alcun rapporto in Analytics.

Questo documento mostra anche come eseguire rapporti sull’utilizzo di dispositivi mobili in Analysis Workspace.

## Regole di elaborazione migrazione

Se utilizzi Mobile Services per funzioni gratuite quali regole di elaborazione e funzioni di reporting sull’utilizzo, puoi passare direttamente all’interfaccia utente di Analytics (interfaccia utente delle regole di elaborazione o Analysis Workspace) per eseguire queste funzioni. Per le metriche del ciclo di vita o le regole impostate nell’interfaccia utente delle regole di elaborazione AA, non è necessario eseguire alcuna migrazione. Le metriche del ciclo di vita sono metriche &quot;pronte all’uso&quot; che vengono raccolte automaticamente al momento della prima implementazione dell’SDK mobile nell’app.

Tuttavia, se imposti eventuali regole di elaborazione aggiuntive nell’interfaccia utente di Mobile Services (oltre alle metriche del ciclo di vita), esegui la migrazione in modo da poterle modificare/eliminare in Analytics dopo aver perso l’accesso a Mobile Services.

1. Accedi a `experience.adobe.com` e vai a Mobile Services.
1. Fai clic sull’icona a forma di ruota dentata di un’app mobile di cui desideri eseguire la migrazione alle mappature delle variabili di contesto in Adobe Analytics .
1. Fai clic sul pulsante **[!UICONTROL Manage Variables and Metrics]** menu, quindi fai clic su **[!UICONTROL Custom Variables]** scheda . Qui puoi vedere quali mappature Variabile di contesto (dati contestuali) sono state aggiunte alla configurazione. Prendi nota di queste configurazioni (o scatta una schermata). Esempio:

   ![Variabile di contesto](assets/context-var.png)

1. Ad Experience Cloud, passa ad Adobe Analytics e assicurati di essere nella stessa suite di rapporti per dispositivi mobili che stavi guardando in Mobile Services.
1. Vai a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
1. Fai clic su **[!UICONTROL Add Rule]**.
1. Ignora le condizioni e continua ad aggiungere le stesse variabili di contesto esistenti in Mobile Services.

   ![Regola di elaborazione](assets/proc-rule.png)

1. Fai clic su **[!UICONTROL Save]**.

## Generazione di rapporti sull’utilizzo mobile in Analysis Workspace

Oltre alle metriche e alle dimensioni per dispositivi mobili (se la suite di rapporti è abilitata per Mobile Services), Analysis Workspace contiene diversi modelli di progetto Mobile che possono facilitare l’analisi:

* **[!UICONTROL Messaging]**: Si focalizza sulle prestazioni di messaggi in-app e push.
* **[!UICONTROL Location]**: Include una mappa che mostra i dati della posizione.
* **[!UICONTROL Key Metrics]**: Controlla le metriche chiave della tua app.
* **[!UICONTROL App Usage]**: Quanti utenti, avvii e primi avvii sono stati registrati per l’app, e quanto dura in media una sessione?
* **[!UICONTROL Acquisition]**: Come si comportano i collegamenti per acquisizione mobile?
* **[!UICONTROL Performance]**: Quali sono le prestazioni dell’app e dove vengono riscontrati problemi dagli utenti?
* **[!UICONTROL Retention]**: Chi sono i miei utenti più fedeli e cosa fanno?
* **[!UICONTROL Journeys]**: Quali sono i pattern di utilizzo principali per la l’app?

Ecco un estratto del modello di utilizzo dell’app mobile:

![Utilizzo app mobili](assets/mobile-app-usage.png)

Per accedere ai modelli:

1. Accedi a `experience.adobe.com` e seleziona Analytics.
1. Assicurati di essere in una suite di rapporti abilitata per Mobile Services.
1. Fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Fai clic su **[!UICONTROL Create New Project]**.
1. Seleziona uno dei modelli per dispositivi mobili e fai clic su **[!UICONTROL Create]**.

## Migrazione di altre funzionalità di Mobile Services

La seguente funzionalità di Mobile Services ha anche legami con Adobe Analytics, ma richiede un SKU Adobe Analytics acquistato:

* Collegamenti di acquisizione
* Messaggi push
* Messaggistica in-app
* Gestione dei punti di interesse della posizione

Se utilizzi Mobile Services per funzionalità a pagamento, non disponi di un percorso di migrazione valido ad altri strumenti interni/esterni:

* Per i collegamenti di acquisizione, puoi rivolgerti ai partner Adobe per soddisfare le tue esigenze.
* I messaggi push e i messaggi in-app sono disponibili in Adobe Campaign Standard e Adobe Campaign Classic (solo push). Tuttavia, il set di dati sottostante utilizzato per il targeting è diverso. È consigliabile collaborare con il team dell’account di Adobe per determinare le opzioni di migrazione per i dati di messaggistica.
* Per quanto riguarda la funzionalità Posizione, ti invitiamo ad adottare il nuovo [Servizio posizione Adobe Experience Platform](https://www.adobe.com/experience-platform/location-service.html), gratuita per tutti i clienti AEP.
