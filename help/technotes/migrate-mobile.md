---
description: Scopri come migrare le regole di elaborazione di Mobile Services in  Adobe Analytics
title: Migrazione delle regole di elaborazione di Mobile Services a  Adobe Analytics
translation-type: tm+mt
source-git-commit: d6601640d06f65dd1ddd09cb9bde0267df20eec3
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 12%

---


# Migrazione delle regole di elaborazione di Mobile Services a  Adobe Analytics

Questo documento fornisce istruzioni su come migrare ad Adobe Analytics eventuali regole di elaborazione aggiuntive, oltre a Metriche del ciclo di vita, create nell&#39;interfaccia di Mobile Services.

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili dei dati di contesto a prop ed eVar. Ad esempio, puoi inserire il valore di una variabile di dati di contesto &quot;a termine di ricerca&quot; nel valore di una variabile di commercio  eVar e sovrascrivere tale valore su ogni hit. Senza le regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non popolano alcun report in Analytics.

Questo documento mostra anche come eseguire rapporti sull’utilizzo di dispositivi mobili in  Analysis Workspace.

## Migra regole di elaborazione

Se utilizzi Mobile Services per funzionalità gratuite quali regole di elaborazione e funzioni di reporting dell&#39;utilizzo, puoi passare direttamente all&#39;interfaccia utente di Analytics (interfaccia utente delle regole di elaborazione o  Analysis Workspace) per eseguire queste funzioni. Per le Metriche del ciclo di vita o le regole configurate nell’interfaccia utente delle regole di elaborazione AA, non è necessario effettuare alcuna migrazione. Metriche del ciclo di vita sono metriche &quot;pronte all’uso&quot; che vengono raccolte automaticamente quando l’SDK di Mobile viene implementato per la prima volta nell’app.

Tuttavia, se imposti eventuali regole di elaborazione aggiuntive nell&#39;interfaccia utente di Mobile Services (oltre a Metriche del ciclo di vita), devi migrarle in modo da poterle modificare o eliminare in Analytics dopo aver perso l&#39;accesso a Mobile Services.

1. Accedi a Mobile Services `experience.adobe.com` e accedi a tale applicazione.
1. Fate clic sull&#39;icona a forma di ingranaggio di un&#39;app mobile di cui desiderate migrare le mappature delle variabili di contesto  Adobe Analytics .
1. Fare clic sulla voce di **[!UICONTROL Manage Variables and Metrics]** menu, quindi fare clic sulla **[!UICONTROL Custom Variables]** scheda. Qui puoi vedere quali mappature variabili di contesto (dati contestuali) sono state aggiunte alla configurazione. Prendete nota di queste configurazioni (o scattate una schermata). Esempio:

   ![Variabile di contesto](assets/context-var.png)

1.  Experience Cloud, passa a  Adobe Analytics e assicurati di essere nella stessa suite di rapporti per dispositivi mobili che stavi guardando in Mobile Services.
1. Vai a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Processing Rules]**.
1. Fai clic su **[!UICONTROL Add Rule]**.
1. Ignora le condizioni e continua ad aggiungere le stesse variabili di contesto esistenti in Mobile Services.

   ![Regola di elaborazione](assets/proc-rule.png)

1. Fai clic su **[!UICONTROL Save]**.

## Generazione di rapporti sull&#39;uso mobile in  Analysis Workspace

Oltre alle metriche e alle dimensioni per dispositivi mobili (se la suite di rapporti è abilitata per Mobile Services),  Analysis Workspace contiene diversi modelli di progetto Mobile che possono facilitare l&#39;analisi:

* **[!UICONTROL Messaging]**: Si focalizza sulle prestazioni di messaggi in-app e push.
* **[!UICONTROL Location]**: Include una mappa che mostra i dati sulla posizione.
* **[!UICONTROL Key Metrics]**: Controlla le metriche chiave della tua app.
* **[!UICONTROL App Usage]**: Quanti utenti, avvii e primi avvii sono stati registrati per l’app, e quanto dura in media una sessione?
* **[!UICONTROL Acquisition]**: Come si comportano i collegamenti di acquisizione per dispositivi mobili?
* **[!UICONTROL Performance]**: Quali sono le prestazioni dell’app e dove vengono riscontrati problemi dagli utenti?
* **[!UICONTROL Retention]**: Chi sono i miei utenti più fedeli e cosa fanno?
* **[!UICONTROL Journeys]**: Quali sono i pattern di utilizzo principali per la l’app?

Ecco un estratto del modello Uso app mobile:

![Utilizzo app mobile](assets/mobile-app-usage.png)

Per accedere ai modelli:

1. Accedi a `experience.adobe.com` e seleziona Analytics.
1. Accertati di essere in una suite di rapporti abilitata per Mobile Services.
1. Fai clic sulla scheda **[!UICONTROL Workspace]**.
1. Fai clic su **[!UICONTROL Create New Project]**.
1. Selezionate uno dei modelli per dispositivi mobili e fate clic su **[!UICONTROL Create]**.

## Migrazione di altre funzionalità di Mobile Services

Anche la seguente funzionalità di Mobile Services ha collegamenti  Adobe Analytics, ma richiede uno SKU Adobe Analytics  acquistato:

* Collegamenti di acquisizione
* Messaggi push
* Messaggistica in-app
* Gestione dei punti di interesse

Se utilizzi Mobile Services per le funzionalità a pagamento, non hai un percorso di migrazione valido verso altri strumenti interni/esterni:

* Per i collegamenti di acquisizione, possiamo indirizzarti  partner di Adobe per soddisfare le tue esigenze.
* Messaggi push e messaggi in-app sono disponibili in  Adobe Campaign Standard e Adobe Campaign Classic (solo push). Tuttavia, il set di dati sottostante utilizzato per il targeting è diverso. Consigliamo di collaborare con il team  account di Adobe per determinare le opzioni di migrazione per i dati di messaggistica.
* Per la funzionalità Posizione, si consiglia di adottare il nuovo servizio [di localizzazione](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, gratuito per tutti i clienti AEP.
