---
title: Implementazione modale
description: Scopri la prima esperienza cliente per implementare l’implementazione di Adobe Analytics.
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# Implementazione modale

<!-- https://activation.adobedtm.com/index.php?redirected=1 -->

La finestra modale &quot;Benvenuti in Adobe Analytics&quot; fornisce un flusso di lavoro semplificato per creare una suite di rapporti. Adobe consiglia di utilizzare questo flusso di lavoro ogni volta che nell&#39;organizzazione sono necessarie più suite di rapporti.

![Schermata modale](assets/implementation-modal.png)

## Prerequisiti

Il tuo Adobe ID deve avere accesso sia ad Adobe Analytics che ad Adobe Experience Platform Launch. Se non disponete dell&#39;accesso a Launch, potete essere inseriti in un loop di autenticazione in cui viene richiesto di verificare le credenziali a tempo indeterminato. Per accedere a Launch, rivolgiti a un amministratore di sistema della tua organizzazione.

## Accesso al modale

Accedi alla modalità per creare una suite di rapporti utilizzando i passaggi seguenti.

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
2. Fate clic sull&#39;icona a 9 griglie nella parte superiore, quindi fate clic [!UICONTROL Adobe Analytics].
3. Se non hai ancora creato una suite di rapporti, la modale viene visualizzata automaticamente. Se esiste una suite di rapporti per questa società di accesso, fai clic sull’icona Aiuto in alto a destra, quindi fai clic su [!UICONTROL Welcome to Adobe Analytics].

> [!NOTE] L&#39; [!UICONTROL Welcome to Adobe Analytics] opzione viene visualizzata solo se accedete tramite Adobe Experience Cloud. Se accedete tramite domini legacy, la modalità non è disponibile.

## Creare una suite di rapporti

Fate clic sul [!UICONTROL Start Setup] pulsante per avviare il flusso di lavoro per la creazione della suite di rapporti.

![Procedura guidata RS](assets/analytics-implementation-rs-wizard.png)

### Tipo proprietà

Il tipo di proprietà aiuta Adobe a determinare alcune impostazioni di back-end in base a dove si intende implementare Analytics.

* **Sito Web**: Se intendete implementare Adobe Analytics solo per un sito Web.
* **App** mobile nativa: Se intendete implementare Adobe Analytics solo per un&#39;app mobile.
* **Entrambi**: Se questa suite di rapporti contiene dati sia per un sito Web che per un&#39;app mobile.

### Industrie

Specifica il tuo modello di business principale. Questa impostazione consente ad Adobe di preconfigurare alcuni nomi e impostazioni di variabili in base al modello aziendale principale.

### Livello dati

Un livello [](data-layer.md) dati è un oggetto JavaScript che organizza tutte le variabili utilizzate nell&#39;implementazione in un&#39;unica posizione utile. Per ulteriori informazioni, consulta Livelli [di](data-layer.md) dati.

### Repository dei dati

Assegna alla suite di rapporti un nome descrittivo. Il tuo ID suite di rapporti (RSID) viene generato automaticamente in base al nome descrittivo e alla società di accesso.

### Fuso orario

Verifica che Adobe abbia rilevato il fuso orario corretto per la suite di rapporti.

### Viste di pagina stimate al giorno

Stimare il traffico giornaliero generato dal sito Web o dall’app. Queste informazioni consentono ad Adobe di allocare la quantità corretta di risorse di elaborazione alla suite di rapporti.

### Valuta di base

Determinare la valuta in cui la suite di rapporti memorizza i valori monetari.

> [!IMPORTANT] Assicurarsi di specificare la valuta corretta, soprattutto se si dispone di requisiti di reporting relativi alle entrate. È difficile modificare la valuta di base dopo l&#39;inizio della raccolta dei dati.

## Risorse di implementazione

Dopo la creazione della suite di rapporti, hai una delle due opzioni per procedere con la tua implementazione:

* **Vai al lancio** di Adobe Experience Platform: Collegamenti a [launch.adobe.com](https://launch.adobe.com) per configurare l’implementazione e scaricare il codice di distribuzione. Vedi [Implementare con Launch](../launch/overview.md). Nella maggior parte dei casi, Adobe consiglia di utilizzare Launch.
* **Download del codice** di implementazione: Fornisce un collegamento diretto per scaricare i file JavaScript per un&#39;implementazione JavaScript manuale. Vedi [AppMeasurement per JavaScript](../js/overview.md).
