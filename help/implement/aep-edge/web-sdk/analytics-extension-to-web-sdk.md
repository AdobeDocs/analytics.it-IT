---
title: Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK
description: Aggiorna l’implementazione di Analytics sui tag di raccolta dati di Adobe Experience Platform per utilizzare l’estensione Web SDK.
exl-id: 691c29ca-d169-4ef8-9f91-d0375166796d
source-git-commit: 7bd4a188e5a2171260f1f0696d8bebad854dba4a
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 5%

---

# Migrare dall’estensione tag Adobe Analytics all’estensione tag Web SDK

Questo percorso di implementazione prevede un approccio metodologico di migrazione per passare dall’estensione tag Adobe Analytics all’estensione tag Web SDK. Altri percorsi di implementazione sono trattati in pagine separate:

* [Libreria JavaScript da AppMeasurement a Web SDK](appmeasurement-to-web-sdk.md): approccio semplice e sistematico per la migrazione al Web SDK, ma senza l&#39;utilizzo di tag. È invece possibile rimuovere manualmente la raccolta dati di Adobe Analytics (`AppMeasurement.js`) e sostituirla con la raccolta JavaScript di Web SDK (`alloy.js`).
* [Estensione tag Web SDK](web-sdk-tag-extension.md): una nuova installazione di Web SDK in cui è possibile gestire l&#39;implementazione utilizzando i tag in Raccolta dati Adobe Experience Platform. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.
* [Libreria Web SDK JavaScript](web-sdk-javascript-library.md): una nuova installazione di Web SDK utilizzando la libreria Web SDK JavaScript (`alloy.js`). Gestisci autonomamente l’implementazione anziché utilizzare l’interfaccia utente dei tag. Richiede il gruppo di campi ExperienceEvent di Adobe Analytics, che include le variabili Analytics tipiche da includere nello schema XDM.

## Vantaggi e svantaggi di questo percorso di implementazione

L’utilizzo di questo approccio alla migrazione presenta sia vantaggi che svantaggi. Valuta attentamente ogni opzione per decidere quale approccio è meglio per la tua organizzazione.

| Vantaggi | Svantaggi |
| --- | --- |
| <ul><li>**Nessuna modifica al codice nel sito**: poiché l&#39;implementazione dispone già di tag installati, è possibile eseguire tutti gli aggiornamenti della migrazione nell&#39;interfaccia dei tag.</li><li>**Utilizza l&#39;implementazione esistente**: questo approccio non richiede una nuova implementazione. Anche se richiede nuove azioni della regola, puoi riutilizzare gli elementi dati e le condizioni della regola esistenti con modifiche minime.</li><li>**Non richiede uno schema**: per questa fase della migrazione al Web SDK non è necessario uno schema XDM. È invece possibile popolare l&#39;oggetto `data`, che invia i dati direttamente ad Adobe Analytics. Una volta completata la migrazione al Web SDK, puoi creare uno schema per la tua organizzazione e utilizzare la mappatura dello stream di dati per popolare i campi XDM applicabili. Se in questa fase del processo di migrazione fosse necessario uno schema, l’organizzazione sarebbe costretta a utilizzare uno schema XDM di Adobe Analytics. L’utilizzo di questo schema rende più difficile per l’organizzazione utilizzare il proprio schema in futuro.</li></ul> | <ul><li>**Debito tecnico per l&#39;implementazione**: poiché questo approccio utilizza una forma modificata dell&#39;implementazione esistente, può essere più difficile tenere traccia della logica di implementazione ed eseguire modifiche quando necessario. Il debug del codice personalizzato può essere particolarmente difficile.</li><li>**Richiede la mappatura per inviare i dati a Platform**: quando l’organizzazione è pronta per utilizzare Customer Journey Analytics, devi inviare i dati a un set di dati in Adobe Experience Platform. Questa azione richiede che ogni campo nell&#39;oggetto `data` sia una voce nello strumento di mappatura dello stream di dati che lo assegna a un campo dello schema XDM. La mappatura deve essere eseguita solo una volta per questo flusso di lavoro e non implica l’apportazione di modifiche all’implementazione. Tuttavia, si tratta di un passaggio aggiuntivo non richiesto quando si inviano dati in un oggetto XDM.</li></ul> |

Adobe consiglia di seguire questo percorso di implementazione nei seguenti scenari:

* È presente un’implementazione tramite l’estensione tag Adobe Analytics. Se hai un&#39;implementazione che utilizza AppMeasurement, segui [Esegui migrazione da AppMeasurement al Web SDK](appmeasurement-to-web-sdk.md).
* Intendi utilizzare Customer Journey Analytics in futuro, ma non desideri sostituire l’implementazione di Analytics con un’implementazione di Web SDK da zero. La sostituzione dell’implementazione da zero sul Web SDK richiede il massimo impegno, ma offre anche l’architettura di implementazione a lungo termine più efficiente. Se la tua organizzazione è disposta a passare attraverso l&#39;implementazione di un SDK Web pulito, consulta [Inserire dati tramite Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/it/docs/analytics-platform/using/cja-data-ingestion/ingest-use-guides/edge-network/aepwebsdk) nella guida utente di Customer Journey Analytics.

## Passaggi necessari per la migrazione al Web SDK

Le seguenti fasi contengono obiettivi concreti da perseguire. Fai clic su ogni passaggio per istruzioni dettagliate su come eseguirlo.

+++**1. Crea e configura un flusso di dati**

Creare uno stream di dati in Raccolta dati di Adobe Experience Platform. Quando invii dati a questo stream di dati, questi vengono inoltrati ad Adobe Analytics. In futuro, lo stesso flusso di dati inoltra i dati a Customer Journey Analytics.

1. Passa a [experience.adobe.com](https://experience.adobe.com) e accedi con le tue credenziali.
1. Utilizzare la home page o il selettore di prodotti in alto a destra per passare a **[!UICONTROL Data Collection]**.
1. Nel menu di navigazione a sinistra, selezionare **[!UICONTROL Datastreams]**.
1. Seleziona **[!UICONTROL New Datastream]**.
1. Immettere il nome desiderato, quindi selezionare **[!UICONTROL Save]**.
1. Una volta creato lo stream di dati, selezionare **[!UICONTROL Add Service]**.
1. Nel menu a discesa del servizio, selezionare **[!UICONTROL Adobe Analytics]**.
1. Immetti lo stesso ID suite di rapporti del sito a cui invii attualmente i dati di analisi. Fai clic su **[!UICONTROL Save]**.

![Aggiungi servizio Adobe Analytics](assets/datastream-rsid.png) {style="border:1px solid lightslategray"}

Il flusso di dati è ora pronto per ricevere e trasmettere dati ad Adobe Analytics.

+++

+++**2. Aggiungi l&#39;estensione Web SDK alla proprietà tag**

Questa sezione prepara il tag per la maggior parte dell’impegno di migrazione che verrà eseguito nel passaggio successivo.

1. Fai clic sull&#39;icona dell&#39;hamburger in alto a sinistra nell&#39;interfaccia di Adobe Experience Platform, quindi seleziona **[!UICONTROL Tags]**.
1. Seleziona la proprietà tag desiderata.
1. Nel menu di navigazione a sinistra della proprietà tag, seleziona **[!UICONTROL Extensions]**.
1. Seleziona **[!UICONTROL Catalog]** nella parte superiore per visualizzare un elenco di tutte le estensioni disponibili.
1. Cerca e seleziona l&#39;estensione **[!UICONTROL Adobe Experience Platform Web SDK]**, quindi fai clic su **[!UICONTROL Install]** a destra.

   ![Catalogo](assets/catalog.png) {style="border:1px solid lightslategray"}

1. Vengono visualizzate le impostazioni di configurazione dell’estensione. Individuate la sezione Flussi di dati e selezionate lo stream di dati creato nel passaggio precedente.

   ![Selezione dello stream di dati](assets/datastream-select.png) {style="border:1px solid lightslategray"}

1. Seleziona **[!UICONTROL Save]**.

Il Web SDK è installato nella proprietà del tag.

+++

+++**3. Crea un elemento dati dell&#39;oggetto dati**

L’elemento dati dell’oggetto dati fornisce un framework intuitivo per configurare un payload che il Web SDK utilizza per inviare a un flusso di dati. La maggior parte delle regole che aggiorni nel passaggio seguente interagisce con questo elemento dati.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Data Elements]**.
1. Seleziona **[!UICONTROL Add Data Element]**
1. Attribuisci all’elemento dati le seguenti impostazioni:
   * [!UICONTROL Name]: qualsiasi cosa desideri, ad esempio &quot;Livello dati&quot; o &quot;Oggetto dati&quot;
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Data Element Type]: [!UICONTROL Variable]
   * Le caselle di controllo possono rimanere invariate
1. A destra, seleziona le impostazioni seguenti:
   * Pulsante di scelta Proprietà: [!UICONTROL Data]
   * Soluzione: [!UICONTROL Adobe Analytics]
1. Seleziona **[!UICONTROL Save]**.

![Crea elemento dati](assets/create-data-element.png) {style="border:1px solid lightslategray"}

La proprietà tag ora dispone di tutto il necessario per aggiornare ogni regola.

+++

+++**4. Aggiorna le regole per utilizzare l&#39;estensione Web SDK anziché l&#39;estensione Analytics**

Questo passaggio contiene la maggior parte dello sforzo necessario per migrare al Web SDK e richiede la conoscenza di come funziona la tua implementazione. Di seguito è riportato un esempio di come modificare una tipica regola di tag. Aggiorna tutte le regole di tag nell’implementazione per sostituire tutti i riferimenti all’estensione Adobe Analytics con l’estensione Web SDK.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Rules]**.
1. Seleziona una regola da modificare.
1. Selezionare l&#39;azione **[!UICONTROL Adobe Analytics - Set Variables]**
1. Nota tutte le variabili di Analytics impostate all’interno di questa regola. Includi sia le variabili impostate nei menu a discesa che le variabili impostate nel codice personalizzato.
1. Cambia [!UICONTROL Action Configuration] con le impostazioni seguenti:
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Action type]: Aggiorna variabile
1. Assicurati che l’oggetto dati sia selezionato nel menu a discesa a destra.
1. Imposta le variabili Analytics sugli stessi valori configurati nell’estensione Analytics.
   * Le variabili impostate nell’interfaccia dei tag possono tradursi direttamente negli stessi valori.
   * Le variabili stringa impostate nel codice personalizzato richiedono regolazioni minime. Anziché utilizzare l&#39;oggetto `s`, utilizzare `data.__adobe.analytics`. `s.eVar1`, ad esempio, tradurrebbe in `data.__adobe.analytics.eVar1`.
   * Le variabili di configurazione e le chiamate ai metodi di Analytics nel codice personalizzato possono richiedere una logica di implementazione modificata. Consulta ogni rispettiva [variabile](/help/implement/vars/overview.md) per determinare come ottenere il suo equivalente utilizzando Web SDK.
1. Una volta replicata la logica di tutte le regole tramite l&#39;estensione Web SDK, selezionare **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza l&#39;estensione Adobe Analytics per impostare i valori. Questo passaggio include sia le variabili impostate tramite l’interfaccia tag che quelle impostate tramite il codice personalizzato. I blocchi di codice personalizzato non possono fare riferimento all&#39;oggetto `s` in alcun punto.

I passaggi precedenti si applicano solo alle regole che impostano valori. I passaggi seguenti sostituiscono tutte le azioni che utilizzano [!UICONTROL Action Configuration] [!UICONTROL Send Beacon].

1. Seleziona una regola che invia un beacon.
1. Selezionare l&#39;azione **[!UICONTROL Adobe Analytics - Send Beacon]**.
1. Si noti il valore corrente del pulsante di scelta [!UICONTROL Tracking] a destra ([`s.t()`](../../vars/functions/t-method.md) o [`s.tl()`](../../vars/functions/tl-method.md)).
1. Cambia [!UICONTROL Action Configuration] con le impostazioni seguenti:
   * [!UICONTROL Extension]: [!UICONTROL Adobe Experience Platform Web SDK]
   * [!UICONTROL Action type]: [!UICONTROL Send event]
1. A destra, modifica le impostazioni delle azioni come segue:
   * [!UICONTROL Type]: Per `s.t()`, utilizzare **[!UICONTROL Web Webpagedetails Page Views]**. Per `s.tl()`, utilizzare **[!UICONTROL Web Webinteraction Link Clicks]**. Se utilizzi [`s.tl()`](../../vars/functions/tl-method.md), devi includere anche i seguenti campi nell&#39;oggetto dati. Questi campi sono elencati in [!UICONTROL Additional properties] durante l&#39;esecuzione della configurazione dell&#39;azione [!UICONTROL Update variable]:
      * [Nome collegamento](../../vars/functions/tl-method.md)
      * [Tipo di collegamento](../../vars/functions/tl-method.md)
      * [URL collegamento](../../vars/config-vars/linkurl.md)
1. Seleziona **[!UICONTROL Keep Changes]**.
1. Ripeti questi passaggi per ogni configurazione di azione che utilizza Adobe Analytics per inviare un beacon.

+++

+++**5. Pubblica regole aggiornate**

La pubblicazione delle regole aggiornate segue lo stesso flusso di lavoro di qualsiasi altra modifica alla configurazione dei tag.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Publishing Flow]**.
1. Seleziona **[!UICONTROL Add Library]**.
1. Assegna un nome al commit del tag, ad esempio &quot;Esegui aggiornamento a Web SDK&quot;.
1. Seleziona **[!UICONTROL Add All Changed Resources]** (Aggiungi set di dati).
1. Seleziona **[!UICONTROL Save]** (Salva).
1. Il flusso di lavoro di pubblicazione visualizza un punto arancione, che indica che è in corso la creazione. Quando il punto diventa verde, le modifiche sono disponibili nell’ambiente di sviluppo.
1. Verifica le modifiche nell’ambiente di sviluppo per assicurarti che tutte le regole vengano attivate correttamente e che l’oggetto dati venga popolato con i valori previsti.
1. Quando è pronta, invia la libreria per l’approvazione, la build alla staging, quindi alla fine approva e pubblica in produzione.

![Flusso di pubblicazione](assets/publishing-flow.png) {style="border:1px solid lightslategray"}

+++

+++**6. Disabilita estensione Analytics**

Una volta che l’implementazione dei tag è completamente sul Web SDK, puoi disabilitare l’estensione Adobe Analytics.

1. Nel menu di navigazione a sinistra dell&#39;interfaccia dei tag, selezionare **[!UICONTROL Extensions]**.
1. Individuare e selezionare l&#39;estensione [!UICONTROL Adobe Analytics]. A destra, selezionare **[!UICONTROL Disable]**.
1. Seguire lo stesso flusso di lavoro di pubblicazione riportato sopra per pubblicare la rimozione dell&#39;estensione [!UICONTROL Adobe Analytics].
1. Una volta che l’estensione è disabilitata in produzione, puoi disinstallarla completamente. Seleziona l&#39;estensione, fai clic sul menu a tre punti a destra, quindi seleziona **[!UICONTROL Uninstall]**.
1. Segui lo stesso flusso di lavoro di pubblicazione indicato sopra per pubblicare tali modifiche in produzione.

+++

A questo punto, l’implementazione di Analytics è completamente sul Web SDK ed è adeguatamente preparata per il passaggio a Customer Journey Analytics in futuro.
