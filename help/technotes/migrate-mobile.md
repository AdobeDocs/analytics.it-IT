---
description: Scopri come migrare le regole di elaborazione di Mobile Services in  Adobe Analytics
title: Migrazione delle regole di elaborazione di Mobile Services a  Adobe Analytics
translation-type: tm+mt
source-git-commit: bdb6f9ba435513cd1dc3febf35eae0e821c756ca
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 14%

---


# Migrazione delle regole di elaborazione di Mobile Services a  Adobe Analytics

Con il prossimo (non ancora annunciato) tramonto della funzionalità di Mobile Services di  Adobe, questo documento fornisce istruzioni su come migrare eventuali regole di elaborazione aggiuntive, oltre a Metriche del ciclo di vita, create nell&#39;interfaccia di Mobile Services per  Adobe Analytics.

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili dei dati di contesto a prop ed eVar. Ad esempio, puoi inserire il valore di una variabile di dati di contesto &quot;a termine di ricerca&quot; nel valore di una variabile di commercio  eVar e sovrascrivere tale valore su ogni hit. Senza le regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non popolano alcun report in Analytics.

## Migra regole di elaborazione

Se utilizzi Mobile Services per funzionalità gratuite quali regole di elaborazione e funzioni di reporting dell&#39;utilizzo, puoi passare direttamente all&#39;interfaccia utente di Analytics (interfaccia utente delle regole di elaborazione o  Analysis Workspace) per eseguire queste funzioni. Per le Metriche del ciclo di vita o le regole configurate nell’interfaccia utente delle regole di elaborazione AA, non è necessario effettuare alcuna migrazione. Metriche del ciclo di vita sono metriche &quot;pronte all’uso&quot; che vengono raccolte automaticamente quando l’SDK di Mobile viene implementato per la prima volta nell’app.

Tuttavia, se imposti eventuali regole di elaborazione aggiuntive nell&#39;interfaccia utente di Mobile Services (oltre a Metriche del ciclo di vita), devi migrarle in modo da poterle modificare o eliminare in Analytics dopo aver perso l&#39;accesso a Mobile Services.

1. Accedi a experience.adobe.com e passa a Mobile Services.
1. Fate clic sull&#39;icona a forma di ingranaggio di un&#39;app mobile di cui desiderate migrare le mappature delle variabili di contesto  Adobe Analytics .
1. Fare clic sulla voce di **[!UICONTROL Manage Variables and Metrics]** menu, quindi fare clic sulla **[!UICONTROL Custom Variables]** scheda. Qui puoi vedere quali mappature variabili di contesto (dati contestuali) sono state aggiunte alla configurazione. Prendete nota di queste configurazioni (o scattate una schermata). Esempio:

   ![Variabile di contesto](assets/context-var.png)

1.  Experience Cloud, passa a  Adobe Analytics e assicurati di essere nella stessa suite di rapporti per dispositivi mobili che stavi guardando in Mobile Services.
1. Vai a Admin (Amministratore) > Report Suites (Suite di rapporti) > Edit Settings (Modifica impostazioni) > General (Generale) > Processing Rules (Regole di elaborazione).
1. Fai clic su Aggiungi regola.
1. Ignora le condizioni e continua ad aggiungere le stesse variabili di contesto esistenti in Mobile Services.

   ![Regola di elaborazione](assets/proc-rule.png)

## Generazione di rapporti sull&#39;uso mobile in  Analysis Workspace

Oltre alle metriche e alle dimensioni per dispositivi mobili (se la suite di rapporti è abilitata per Mobile Services),  Analysis Workspace contiene diversi modelli di progetto Mobile che possono facilitare l&#39;analisi:

* Messaggistica: si focalizza sulle prestazioni di messaggi in-app e push.
* Posizione: include una mappa che mostra i dati della posizione.
* Metriche chiave: controlla le metriche chiave della tua app.
* Utilizzo app: quanti utenti, avvii e primi avvii sono stati registrati per l’app, e quanto dura in media una sessione?
* Acquisizione: Come si comportano i collegamenti di acquisizione per dispositivi mobili?
* Prestazioni: quali sono le prestazioni dell’app e dove vengono riscontrati problemi dagli utenti?
* Fidelizzazione: chi sono i miei utenti più fedeli e cosa fanno?
* Percorsi: Quali sono i pattern di utilizzo principali per la l’app?

Ecco un estratto del modello Uso app mobile:

![Utilizzo app mobile](assets/mobile-app-usage.png)

Per accedere ai modelli:

1. Accedete a experience.adobe.com e selezionate Analytics.
1. Accertati di essere in una suite di rapporti abilitata per Mobile Services.
1. Fare clic sulla scheda Area di lavoro.
1. Fai clic su Crea nuovo progetto.
1. Selezionate uno dei modelli per dispositivi mobili e fate clic su Crea.

## Migrazione di altre funzionalità di Mobile Services

Anche la seguente funzionalità di Mobile Services ha collegamenti  Adobe Analytics, ma richiede uno SKU Adobe Analytics  acquistato:

* Collegamenti di acquisizione
* Messaggi push
* Messaggistica in-app
* Gestione dei punti di interesse

Se utilizzi Mobile Services per le funzionalità a pagamento, non hai un percorso di migrazione valido verso altri strumenti interni/esterni:

* Per i collegamenti di acquisizione, possiamo indirizzarti  partner di Adobe per soddisfare le tue esigenze.
* Anche se i messaggi push e i messaggi in-app si trovano in  Adobe Campaign Standard e Adobe Campaign Classic (solo push), il set di dati sottostante utilizzato per il targeting è diverso e non è possibile effettuare la migrazione di dati o attività di messaggistica.
* Per la funzionalità Posizione, si consiglia di adottare il nuovo servizio [di localizzazione](https://www.adobe.com/experience-platform/location-service.html)Adobe Experience Platform, gratuito per tutti i clienti AEP.
