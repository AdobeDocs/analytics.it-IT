---
title: Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK
description: Aggiorna l’implementazione di Analytics sui tag di raccolta dati di Adobe Experience Platform per utilizzare l’estensione Web SDK.
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 1%

---

# Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK

Questo percorso di implementazione prevede un approccio metodologico di migrazione per passare dall’estensione tag Adobe Analytics all’estensione tag Web SDK. Altri percorsi di implementazione sono trattati in pagine separate:

* [AppMeasurement della libreria JavaScript di Web SDK](appmeasurement-to-web-sdk.md): approccio fluido e metodico per la migrazione all’SDK web, con la differenza che non utilizza i tag. Al contrario, rimuovi manualmente la libreria di raccolta dati di Adobe Analytics (`AppMeasurement.js`) e sostituirla con la libreria JavaScript di Web SDK (`alloy.js`).
* [Estensione tag Web SDK](web-sdk-tag-extension.md): nuova installazione di Web SDK in cui puoi gestire l’implementazione utilizzando i tag in Raccolta dati di Adobe Experience Platform. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Libreria JavaScript dell’SDK per web](web-sdk-javascript-library.md): nuova installazione di Web SDK tramite la libreria JavaScript di Web SDK (`alloy.js`). Gestisci autonomamente l’implementazione anziché utilizzare l’interfaccia utente dei tag. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Nessuna modifica al codice sul sito**: poiché nell’implementazione sono già installati i tag, è possibile eseguire tutti gli aggiornamenti della migrazione nell’interfaccia dei tag.</li><li>**Utilizza l’implementazione esistente**: questo approccio non richiede una nuova implementazione netta. Anche se richiede nuove azioni della regola, puoi riutilizzare gli elementi dati e le condizioni della regola esistenti con modifiche minime.</li><li>**Non richiede uno schema**: in questa fase della migrazione all’SDK per web non è necessario uno schema XDM. È invece possibile compilare il `data` , che invia i dati direttamente ad Adobe Analytics. Una volta completata la migrazione all’SDK per web, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Adobe Analytics. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Obbligo tecnico di attuazione**: poiché questo approccio utilizza una forma modificata dell’implementazione esistente, può essere più difficile tracciare la logica di implementazione ed eseguire modifiche quando necessario. Il debug del codice personalizzato può essere particolarmente difficile.</li><li>**Richiede la mappatura per inviare dati a Platform**: quando l’organizzazione è pronta per utilizzare il Customer Journey Analytics, è necessario inviare dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nel `data` object può essere una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita una sola volta per questo flusso di lavoro e non richiede l’apporto di modifiche all’implementazione. Si tratta tuttavia di un passaggio aggiuntivo non richiesto per l’invio di dati in un oggetto XDM.</li></ul> |

L’Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È presente un’implementazione tramite l’estensione tag Adobe Analytics. Se hai un’implementazione tramite AppMeasurement, segui [Migrare da AppMeasurement a Web SDK](appmeasurement-to-web-sdk.md) invece.
* Intendi utilizzare il Customer Journey Analytics in futuro, ma non desideri sostituire l’implementazione di Analytics con un’implementazione Web SDK da zero. La sostituzione dell’implementazione da zero su Web SDK richiede il massimo impegno, ma offre anche l’architettura di implementazione a lungo termine più efficiente. Se la tua organizzazione è disposta a passare attraverso l’implementazione di un SDK web pulito, consulta [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) nella guida utente del Customer Journey Analytics.

## Passaggi necessari per migrare a Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Fai clic su ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Creare e configurare uno stream di dati**

Creare uno stream di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Adobe Analytics. In futuro, lo stesso flusso di dati inoltra i dati al Customer Journey Analytics.

1. Accedi a [experience.adobe.com](https://experience.adobe.com) e accedere utilizzando le credenziali.
1. Utilizza la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, seleziona **[!UICONTROL Datastreams]**.
1. Seleziona **[!UICONTROL New Datastream]**.
1. Immetti il nome desiderato, quindi seleziona **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, seleziona **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, seleziona **[!UICONTROL Adobe Analytics]**.
1. Immetti lo stesso ID suite di rapporti del sito a cui invii attualmente i dati di analisi. Fai clic su **[!UICONTROL Save]**.

![Aggiungi servizio Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid gray"}

Il flusso di dati è ora pronto per ricevere e trasmettere dati ad Adobe Analytics.

+++

+++**2. Aggiungere l’estensione Web SDK alla proprietà tag**

Questa sezione prepara il tag per la maggior parte dell’impegno di migrazione che verrà eseguito nel passaggio successivo.

1. Fai clic sull’icona dell’hamburger in alto a sinistra nell’interfaccia di Adobe Experience Platform, quindi seleziona **[!UICONTROL Tags]**.
1. Seleziona la proprietà tag desiderata.
1. Nel menu di navigazione a sinistra della proprietà tag, seleziona **[!UICONTROL Extensions]**.
1. Seleziona **[!UICONTROL Catalog]** nella parte superiore per visualizzare un elenco di tutte le estensioni disponibili.
1. Cerca e seleziona la **[!UICONTROL Adobe Experience Platform Web SDK]** , quindi fai clic su **[!UICONTROL Install]** a destra.

   ![Catalogo](assets/catalog.png) {style="border:1px solid gray"}

1. Vengono visualizzate le impostazioni di configurazione dell’estensione. Individuate la sezione Flussi di dati e selezionate lo stream di dati creato nel passaggio precedente.

   ![Selezione dello stream di dati](assets/datastream-select.png) {style="border:1px solid gray"}

1. Seleziona **[!UICONTROL Save]**.

L’SDK web è ora installato nella proprietà del tag.

+++

+++**3. Creare un elemento dati dell’oggetto dati**

L’elemento dati dell’oggetto dati fornisce un framework intuitivo per configurare un payload che l’SDK web utilizza per inviare a un flusso di dati. La maggior parte delle regole che aggiorni nel passaggio seguente interagisce con questo elemento dati.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Data Elements]**.
1. Seleziona **[!UICONTROL Add Data Element]**
1. Attribuisci all’elemento dati le seguenti impostazioni:
   * [!UICONTROL Name]: qualsiasi cosa desideri, ad esempio &quot;Livello dati&quot; o &quot;Oggetto dati&quot;
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Variable]: [!UICONTROL Variable]
   * Le caselle di controllo possono rimanere invariate
1. A destra, seleziona le impostazioni seguenti:
   * Pulsante di scelta Proprietà: [!UICONTROL Data]
   * Soluzione: [!UICONTROL Adobe Analytics]
1. Seleziona **[!UICONTROL Save]**.

![Creare un elemento dati](assets/create-data-element.png) {style="border:1px solid gray"}

La proprietà tag ora dispone di tutto il necessario per aggiornare ogni regola.

+++

+++**4. Aggiornare le regole per utilizzare l’estensione Web SDK invece dell’estensione Analytics**

Questo passaggio contiene la maggior parte dello sforzo necessario per migrare all’SDK per web e richiede la conoscenza di come funziona l’implementazione. Di seguito è riportato un esempio di come modificare una tipica regola di tag. Aggiorna tutte le regole di tag nell’implementazione per sostituire tutti i riferimenti all’estensione Adobe Analytics con l’estensione Web SDK.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Rules]**.
1. Seleziona una regola da modificare.
1. Seleziona l’azione **[!UICONTROL Adobe Analytics - Set Variables]**
1. Nota tutte le variabili di Analytics impostate all’interno di questa regola. Nota sia le variabili impostate nei menu a discesa che quelle impostate nel codice personalizzato.
1. Modificare il [!UICONTROL Action Configuration] alle seguenti impostazioni:
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Action type]: Aggiorna variabile
1. Assicurati che l’oggetto dati sia selezionato nel menu a discesa a destra.
1. Imposta le variabili Analytics sugli stessi valori configurati nell’estensione Analytics.
   * Le variabili impostate nell’interfaccia dei tag possono tradursi direttamente negli stessi valori.
   * Le variabili stringa impostate nel codice personalizzato richiedono regolazioni minime. Invece di utilizzare `s` oggetto, utilizzare `data.__adobe.analytics` invece. Ad esempio: `s.eVar1` tradurrebbe in `data.__adobe.analytics.eVar1`.
   * Le variabili di configurazione e le chiamate ai metodi di Analytics nel codice personalizzato possono richiedere una logica di implementazione modificata. Vedi ogni [variabile](/help/implement/vars/overview.md) per determinare come raggiungere il suo equivalente utilizzando Web SDK.
1. Una volta replicata tutta la logica della regola utilizzando l’estensione Web SDK, seleziona **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza l&#39;estensione Adobe Analytics per impostare i valori. Questo passaggio include sia le variabili impostate tramite l’interfaccia tag che quelle impostate tramite il codice personalizzato. I blocchi di codice personalizzato non possono fare riferimento a `s` oggetto ovunque.

I passaggi precedenti si applicano solo alle regole che impostano valori. I passaggi seguenti sostituiscono tutte le azioni che utilizzano [!UICONTROL Action Configuration] [!UICONTROL Send Beacon].

1. Seleziona una regola che invia un beacon.
1. Seleziona l’azione **[!UICONTROL Adobe Analytics - Send Beacon]**.
1. Osserva il valore corrente del [!UICONTROL Tracking] pulsante di scelta a destra ([`s.t()`](../../vars/functions/t-method.md) o [`s.tl()`](../../vars/functions/tl-method.md)).
1. Modificare il [!UICONTROL Action Configuration] alle seguenti impostazioni:
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Action type]: [!UICONTROL Send event]
1. A destra, modifica le impostazioni delle azioni come segue:
   * [!UICONTROL Type]: per `s.t()`, utilizza **[!UICONTROL Web Webpagedetails Page Views]**. Per `s.tl()`, utilizza **[!UICONTROL Web Webinteraction Link Clicks]**. Se usa [`s.tl()`](../../vars/functions/tl-method.md), è inoltre necessario includere i campi seguenti nell’oggetto dati. Questi campi sono elencati in [!UICONTROL Additional properties] quando si esegue [!UICONTROL Update variable] configurazione azione:
      * [Nome collegamento](../../vars/functions/tl-method.md)
      * [Tipo di collegamento](../../vars/functions/tl-method.md)
      * [URL collegamento](../../vars/config-vars/linkurl.md)
1. Seleziona **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza Adobe Analytics per inviare un beacon.

+++

+++**5. Pubblicare regole aggiornate**

La pubblicazione delle regole aggiornate segue lo stesso flusso di lavoro di qualsiasi altra modifica alla configurazione dei tag.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Publishing Flow]**.
1. Seleziona **[!UICONTROL Add Library]**.
1. Assegna un nome al commit del tag, ad esempio &quot;Aggiorna a Web SDK&quot;.
1. Seleziona **[!UICONTROL Add All Changed Resources]** (Aggiungi set di dati).
1. Seleziona **[!UICONTROL Save]** (Salva).
1. Il flusso di lavoro di pubblicazione visualizza un punto arancione, che indica che è in corso la creazione. Quando il punto diventa verde, le modifiche sono disponibili nell’ambiente di sviluppo.
1. Verifica le modifiche nell’ambiente di sviluppo per assicurarti che tutte le regole vengano attivate correttamente e che l’oggetto dati venga popolato con i valori previsti.
1. Quando è pronta, invia la libreria per l’approvazione, la build alla staging, quindi alla fine approva e pubblica in produzione.

![Flusso di pubblicazione](assets/publishing-flow.png) {style="border:1px solid gray"}

+++

+++**6. Disabilita estensione Analytics**

Una volta che l’implementazione dei tag è completamente sul Web SDK, puoi disabilitare l’estensione Adobe Analytics.

1. Nel menu di navigazione a sinistra dell’interfaccia dei tag, seleziona **[!UICONTROL Extensions]**.
1. Individua e seleziona la [!UICONTROL Adobe Analytics] estensione. A destra, seleziona **[!UICONTROL Disable]**.
1. Segui lo stesso flusso di lavoro di pubblicazione indicato sopra per pubblicare la rimozione del [!UICONTROL Adobe Analytics] estensione.
1. Una volta che l’estensione è disabilitata in produzione, puoi disinstallarla completamente. Seleziona l’estensione, fai clic sul menu a tre punti a destra, quindi seleziona **[!UICONTROL Uninstall]**.
1. Segui lo stesso flusso di lavoro di pubblicazione indicato sopra per pubblicare tali modifiche in produzione.

+++

A questo punto, l’implementazione di Analytics si basa interamente sull’SDK per web ed è adeguatamente preparata per passare al Customer Journey Analytics in futuro.
