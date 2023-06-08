---
description: Condivisione e ruoli dei progetti in Workspace
keywords: Condivisione di Analysis Workspace
title: Condividere progetti
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 441484c0547439de2ab1cdc2596fb681592df012
workflow-type: tm+mt
source-wordcount: '1730'
ht-degree: 24%

---

# Condividere progetti

Puoi condividere un progetto Analysis Workspace con i seguenti tipi di persone:

* Utenti e gruppi della tua organizzazione che hanno accesso ad Adobe Analytics

  È possibile condividere l&#39;accesso Modifica, Duplica o Visualizza

* Utenti e gruppi della tua organizzazione che non hanno accesso ad Adobe Analytics

  I destinatari dispongono di accesso in sola lettura

* Persone esterne all’organizzazione

  I destinatari dispongono di accesso in sola lettura

Qualsiasi [cura](curate.md) L’applicazione prima della condivisione si riflette quando i destinatari aprono il progetto.

Ecco una panoramica video della condivisione dei progetti:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Condividi con utenti e gruppi di Analysis Workspace nella tua organizzazione {#Add}

Puoi condividere un progetto con utenti o gruppi Analysis Workspace esistenti nella tua organizzazione. Quando condividi un progetto come descritto in questa sezione, gli utenti con cui condividi devono già avere accesso ad Adobe Analytics.

Puoi condividere un ruolo specifico con utenti o gruppi, oppure un collegamento.

* [Condividere un ruolo di progetto specifico](#share-a-specific-project-role)

* [Condividere un collegamento a un progetto](#share-a-link-to-a-project)

## Condividere un ruolo di progetto specifico

Quando condividi un ruolo di progetto specifico con utenti e gruppi dell’organizzazione, considera quanto segue:

* Ruoli di progetto (**[!UICONTROL Can edit]**, **[!UICONTROL Can duplicate]**, e **[!UICONTROL Can view]**) sono legate all&#39;ID utente e al progetto specifico. I ruoli di progetto sono indipendenti dalle autorizzazioni utente gestite nella [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

* In Adobe Analytics, i gruppi sono definiti dai profili di prodotto nell’[Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it). Gli amministratori possono condividere con qualsiasi gruppo, incluso &quot;All&quot;. Gli utenti non amministratori possono condividere con qualsiasi gruppo di cui sono membri, ad eccezione di &quot;All&quot; (Tutti).

* Un utente che viene posizionato in più ruoli ottiene sempre l’esperienza di livello più alto. Ciò potrebbe verificarsi se un utente viene aggiunto sia come singolo utente che come parte di un gruppo. Ad esempio, se a un utente viene assegnato il **[!UICONTROL Can edit]** ruolo individuale e **[!UICONTROL Can view]** come membro di un gruppo, riceveranno un **[!UICONTROL Can edit]** esperienza di progetto.

* Amministratori inseriti in **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** ruolo ricevono tali esperienze limitate quando aprono un progetto. Un amministratore può modificare il proprio ruolo in **[!UICONTROL Can edit]** condividendo il progetto con se stessi e assegnando il ruolo Modifica, come descritto nella procedura seguente.

Per condividere un ruolo di progetto specifico con utenti o gruppi dell’organizzazione:

1. Vai al progetto che desideri condividere, quindi fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
Se sono presenti modifiche non salvate, viene richiesto di salvare prima il progetto.

   ![](assets/share-proj-modal.png)

   Per informazioni su come condividere più progetti contemporaneamente, consulta [Condivisione di progetti nel Project manager](#share-projects-in-the-project-manager).

1. Aggiungi destinatari o gruppi di destinatari in uno dei campi ruolo forniti:

   **Può modificare:** I destinatari possono **[!UICONTROL Save]** modifiche a un progetto e funzioni come co-proprietari. Questo ruolo è utile se desideri gestire un progetto con altri colleghi; ciò include la modifica e l’eliminazione degli elenchi dei destinatari per un progetto condiviso. <br>Nota: Analysis Workspace al momento non supporta la collaborazione in tempo reale, pertanto si consiglia di modificare un progetto solo un utente alla volta. Se i progetti vengono salvati contemporaneamente, viene mantenuta l’ultima versione.

   **Può duplicare:** I destinatari possono **[!UICONTROL Save as]** e accedere alla barra a sinistra. Le interazioni del progetto non sono limitate in questo ruolo. Questo ruolo è utile se desideri condividere un progetto con utenti che conoscono i dati della tua organizzazione e sanno come utilizzare Analysis Workspace, ma non desideri che il progetto venga modificato.

   **Può visualizzare:** I destinatari non possono **[!UICONTROL Save]** o **[!UICONTROL Save as]** e non hanno accesso alla barra a sinistra. Anche le interazioni del progetto sono limitate. Questo ruolo è utile se desideri condividere un progetto con utenti che hanno meno familiarità con la struttura dei dati della tua organizzazione e con Analysis Workspace o Adobe Analytics in genere. Tuttavia, desideri comunque che utilizzino dati e informazioni in un ambiente sicuro. Scopri di più sull’[esperienza di progetto Can view](/help/analyze/analysis-workspace/curate-share/view-only-projects.md).

1. Scegli se abilitare le seguenti opzioni durante la condivisione del progetto:

   * **Condividere componenti di progetto incorporati:** Condivide segmenti, metriche calcolate e intervalli di date con tutti i destinatari. Una volta condivisi, tali componenti sono disponibili nel menu a discesa Components nell’interfaccia Workspace del destinatario. Questa impostazione non è persistente; si tratta di un’azione una tantum al momento della condivisione.

   * **Imposta come pagina di destinazione per i destinatari:** Imposta questa pagina come pagina di destinazione per i destinatari. Questa impostazione non è persistente; si tratta di un’azione una tantum al momento della condivisione.

1. Fai clic su **[!UICONTROL Share]**. Se il progetto è già stato condiviso, fai clic su [!UICONTROL **Aggiorna**].)

   Oppure

   Clic **[!UICONTROL Curate and Share]** per applicare automaticamente la cura del progetto. Se il progetto è già stato condiviso, fai clic su **[!UICONTROL Curate & Update]**.) Ulteriori informazioni sulla [cura dei progetti](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it).

## Condividere un collegamento a un progetto

Quando condividi un collegamento come descritto in questa sezione, considera quanto segue:

* I destinatari che utilizzano il collegamento devono accedere ad Adobe Analytics prima di poter accedere al progetto.

* Se a un destinatario non viene assegnato un ruolo e riceve un [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=it) al progetto, per impostazione predefinita viene assegnato loro un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori ricevono **[!UICONTROL Can duplicate]**.

Per condividere il collegamento del progetto con gli utenti dell’organizzazione:

1. Salva il progetto. Se sono presenti modifiche non salvate, viene richiesto di salvare il progetto prima di condividere un collegamento.

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** accanto al **[!UICONTROL Share by link]** campo.

   ![](assets/share-proj-modal.png)

1. Condividi il collegamento con gli utenti della tua organizzazione. Ad esempio, puoi incollarlo in un’e-mail, in un sito web interno e così via.

## Condividere un progetto con altri utenti (accesso non richiesto) {#share-public-link}

Puoi concedere [accesso in sola lettura](/help/analyze/analysis-workspace/curate-share/view-only-projects.md) ai progetti Analysis Workspace per persone che non hanno accesso ad Adobe Analytics. Ciò può includere:

* Persone esterne all’organizzazione

* Persone dell’organizzazione che non hanno accesso ad Adobe Analytics

>[!NOTE]
>
>Quando condividi un progetto Analysis Workspace con persone che non hanno accesso ad Adobe Analytics, considera quanto segue:
>
>* La possibilità di condividere un progetto in questo modo può essere disabilitata dall’amministratore di Analytics, come descritto in [Preferenze](/help/analyze/analysis-workspace/user-preferences.md). Se non riesci a condividere un progetto come descritto in questa sezione, l’amministratore di Analytics ha disabilitato questa funzionalità.
>
>* I progetti con più di 50 visualizzazioni espanse non possono essere condivisi con persone che non hanno accesso ad Adobe Analytics.
>
>* Gli utenti con cui condividi il progetto possono visualizzare tutti i filtri applicati al progetto durante [cura](curate.md).
> 
>* Gli utenti con cui condividi possono modificare l’intervallo di date del progetto. L’intervallo di date impostato per il progetto viene visualizzato per impostazione predefinita.
>
>* Un progetto potrebbe diventare inaccessibile se molti utenti tentano di accedere contemporaneamente a un determinato collegamento. Per impostazione predefinita, più di 190 persone possono accedere a un singolo collegamento ogni 5 minuti. Se l’organizzazione raggiunge questo limite, attendi 5 minuti e prova di nuovo ad accedere al collegamento.

La seguente dimostrazione video e la relativa documentazione descrivono le opzioni associate alla condivisione di un collegamento con chiunque:

>[!VIDEO](https://video.tv.adobe.com/v/3420093/?learn=on)

Per condividere un progetto Analysis Workspace con persone che non hanno accesso ad Adobe Analytics:

1. Apri il progetto Analysis Workspace che desideri condividere.

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.

   In presenza di modifiche non salvate, viene richiesto di salvare il progetto.

   <!-- Add screen shot of new modal -->

1. Abilita **[!UICONTROL Link is active]** se non è già abilitata.

   Selezionando questa opzione viene creato un collegamento al progetto che può essere condiviso con chiunque. Disattivando questa opzione è possibile disattivare l’accesso al progetto in qualsiasi momento.

   Il proprietario del progetto è anche il proprietario di questo collegamento. La proprietà del collegamento può essere trasferita a un altro utente solo quando viene trasferita la proprietà del progetto, come descritto in [Trasferimento di risorse utente o impostazione delle scadenze dell&#39;account](/help/admin/admin/user-management2/users-assets.md) nella guida per l’amministratore di Analytics.

1. Scegli se abilitare la seguente opzione di sicurezza (questa opzione può essere controllata dall’amministratore Analytics):

   * **[!UICONTROL Require Experience Cloud authentication]:**

     Quando questa opzione è abilitata, gli unici utenti che possono accedere al progetto sono gli utenti che possono accedere all’organizzazione Adobe Experience Cloud in cui è stato creato il progetto condiviso. Tuttavia, gli utenti con cui condividi non devono avere accesso ad Adobe Analytics.

     Gli amministratori di Analytics possono configurare questa preferenza per l’azienda, come descritto in [Preferenze](/help/analyze/analysis-workspace/user-preferences.md). A seconda della configurazione di questa opzione da parte dell’amministratore, potrebbero verificarsi gli scenari seguenti:

      * Se questa opzione non è visibile, l’amministratore di Analytics non ha abilitato questa funzione.

      * Se questa opzione è abilitata e disabilitata, l’amministratore di Analytics richiede l’autenticazione Experience Cloud per tutti coloro che accedono ai progetti Analysis Workspace.

1. Accanto al **[!UICONTROL Share with anyone (no login required)]** , fare clic sul pulsante **Copia collegamento** icona ![Icona Copia collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg) per copiare il collegamento negli Appunti di sistema.

1. Condividi il collegamento con le persone che desideri possano accedere al progetto. Ad esempio, puoi incollare il collegamento in un messaggio e-mail.

   Qualsiasi persona con cui condividi il collegamento può visualizzare il progetto Analysis Workspace.

1. (Facoltativo) Puoi fare clic sul pulsante **Genera nuovo collegamento** icona ![Icona Genera collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) per rimuovere l’accesso da utenti che hanno precedentemente ricevuto un collegamento al progetto. Viene generato un nuovo collegamento che puoi condividere con gli utenti che desideri accedere al progetto.

1. Seleziona **[!UICONTROL Close]** per chiudere la finestra di dialogo condividi. Le modifiche vengono salvate automaticamente.

## Condivisione di progetti nel Project manager {#Manager}

I progetti possono essere condivisi anche da **[!UICONTROL Components]>[!UICONTROL Projects]**. Un singolo progetto può essere condiviso seguendo gli stessi passaggi indicati sopra.  Se sono stati selezionati più progetti da condividere, i destinatari verranno aggiunti all’elenco esistente di destinatari per ciascun progetto.

Ad esempio:

* Il progetto A è condiviso con i destinatari 1, 2, 3
* Il progetto B è condiviso con i destinatari 4, 5, 6

Con i progetti A e B selezionati, i destinatari 4 e 7 vengono aggiunti agli elenchi di condivisione. Il nuovo elenco di condivisione per ciascun progetto ora è:

* Progetto A: 1, 2, 3, 4, 7
* Progetto B: 4, 5, 6, 7

![](assets/mult-proj-sharing.png)

## Condividere componenti incorporati

Video sull’argomento:

>[!VIDEO](https://video.tv.adobe.com/v/24713/?quality=12)

## Domande frequenti {#FAQs}

| Domanda | Risposta |
| --- | --- |
| Cosa succede se due editor salvano un progetto contemporaneamente? | Le modifiche non vengono unite e viene mantenuta l’ultima versione del progetto salvata. Analysis Workspace non supporta attualmente la collaborazione in tempo reale. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo utente e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceverà sempre l’esperienza di livello più elevato. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Can edit]** come singolo utente e il ruolo **[!UICONTROL Can view]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Can edit]**. |
| Quale esperienza riceve un destinatario se apre un collegamento al progetto? | I destinatari ricevono il ruolo in cui li hai inseriti nella modalità di condivisione. Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** accanto al **[!UICONTROL Share by link]** ), per impostazione predefinita vengono inseriti in un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**. |
