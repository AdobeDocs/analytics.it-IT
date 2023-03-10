---
description: Condivisione e ruoli dei progetti in Workspace
keywords: Condivisione di Analysis Workspace
title: Condividere progetti
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 66a02a6d0c6cc88752ea39172bd30b026908846b
workflow-type: tm+mt
source-wordcount: '1492'
ht-degree: 33%

---

# Condividere progetti

Puoi condividere un progetto Analysis Workspace con i seguenti tipi di persone:

* Utenti e gruppi della tua organizzazione che hanno accesso ad Adobe Analytics

   È possibile condividere l&#39;accesso Modifica, Duplica o Visualizza

* Utenti e gruppi della tua organizzazione che non hanno accesso ad Adobe Analytics

   I destinatari dispongono dell&#39;accesso in sola visualizzazione

* Persone esterne all’organizzazione

   I destinatari dispongono dell&#39;accesso in sola visualizzazione

Qualsiasi [cura](curate.md) L’applicazione prima della condivisione si riflette quando i destinatari aprono il progetto.

Ecco una panoramica video della condivisione dei progetti:

>[!VIDEO](https://video.tv.adobe.com/v/36207/?quality=12)


## Condividi con utenti e gruppi di Adobe Analytics nella tua organizzazione {#Add}

Puoi condividere un progetto con utenti o gruppi Adobe Analytics esistenti nella tua organizzazione. Quando condividi un progetto come descritto in questa sezione, gli utenti con cui condividi devono già avere un account Adobe Analytics.

Puoi condividere un ruolo specifico con utenti o gruppi, oppure un collegamento.

* [Condividere un ruolo di progetto specifico](#share-a-specific-project-role)

* [Condividere un collegamento a un progetto](#share-a-link-to-a-project)

## Condividere un ruolo di progetto specifico

Quando condividi un ruolo di progetto specifico con utenti e gruppi dell’organizzazione, considera quanto segue:

* Ruoli di progetto (**[!UICONTROL Can edit]**, **[!UICONTROL Can duplicate]**, e **[!UICONTROL Can view]**) sono legate all&#39;ID utente e al progetto specifico. I ruoli di progetto sono indipendenti dalle autorizzazioni utente gestite nella [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

* In Adobe Analytics, i gruppi sono definiti dai profili di prodotto nell’[Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it). Gli amministratori possono condividere con qualsiasi gruppo, incluso &quot;All&quot;. Gli utenti non amministratori possono condividere con qualsiasi gruppo di cui sono membri, ad eccezione di &quot;All&quot; (Tutti).

* Un utente che viene posizionato in più ruoli ottiene sempre l’esperienza di livello più alto. Ciò potrebbe verificarsi se un utente viene aggiunto sia come singolo utente che come parte di un gruppo. Ad esempio, se a un utente viene assegnato il **[!UICONTROL Can edit]** ruolo individuale e **[!UICONTROL Can view]** come membro di un gruppo, riceveranno un **[!UICONTROL Can edit]** esperienza di progetto.

* Amministratori inseriti in **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** ruolo ricevono tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Can edit]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**.

Per condividere un ruolo di progetto specifico con utenti o gruppi dell’organizzazione:

1. Vai al progetto che desideri condividere, quindi fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share project]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
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

* Se a un destinatario non viene assegnato un ruolo e riceve un [link](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=it) al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), per impostazione predefinita viene assegnato loro un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**.

Per condividere il collegamento del progetto con gli utenti dell’organizzazione:

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share project]**. <!-- recommned changing "Share project" to "Share project internally" or something like that -->
Se sono presenti modifiche non salvate, viene richiesto di salvare prima il progetto.

   ![](assets/share-proj-modal.png)

1. Clic **[!UICONTROL Copy link]** accanto al **[!UICONTROL Share URL field]**.

1. Condividi il collegamento con gli utenti della tua organizzazione. Ad esempio, puoi incollarlo in un’e-mail, in un sito web interno e così via.

## Condividere un collegamento pubblico con altri utenti (accesso non richiesto) {#share-public-link}

{{release-limited-testing-section}}

Puoi concedere [Accesso solo visualizzazione](/help/analyze/analysis-workspace/curate-share/view-only-projects.md) ai progetti Analysis Workspace per persone che non hanno accesso ad Adobe Analytics. Ciò può includere:

* Persone esterne all’organizzazione

* Persone dell’organizzazione che non dispongono del provisioning di Adobe Analytics

>[!NOTE]
>
>Quando condividi un collegamento pubblico tieni presente quanto segue:
>
>* L’amministratore di Analytics può disabilitare la condivisione di un collegamento di accesso pubblico, come descritto in [Preferenze](/help/analyze/analysis-workspace/user-preferences.md). Se non riesci a condividere un collegamento pubblico come descritto in questa sezione, l’amministratore di Analytics ha disabilitato questa funzionalità.
>
>* I progetti con più di 14 visualizzazioni espanse non possono essere condivisi utilizzando un collegamento di accesso pubblico.


Per condividere un collegamento pubblico a un progetto Analysis Workspace:

1. Apri il progetto Analysis Workspace che desideri condividere.

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share public link]**.

   In presenza di modifiche non salvate, viene richiesto di salvare il progetto.

   <!-- Add screen shot of new modal -->

1. Abilita **[!UICONTROL Link active]** se non è già abilitata.

1. Scegli se abilitare la seguente opzione di sicurezza (questa opzione può essere controllata dall’amministratore Analytics):

   * **[!UICONTROL Require Experience Cloud authentication]:**

      Quando questa opzione è abilitata, solo gli utenti che possono accedere all’organizzazione Adobe Experience Cloud in cui è stato creato il progetto che stai condividendo possono utilizzare questo collegamento.

      Gli amministratori di Analytics possono configurare questa preferenza per l’azienda, come descritto in [Preferenze](/help/analyze/analysis-workspace/user-preferences.md). A seconda della configurazione di questa opzione da parte dell’amministratore, potrebbero verificarsi gli scenari seguenti:

      * Se questa opzione non è visibile, l’amministratore di Analytics non ha abilitato questa funzione.

      * Se questa opzione è abilitata e disabilitata, l’amministratore di Analytics richiede l’autenticazione Experience Cloud per accedere a tutti i collegamenti pubblici.

1. Accanto al **[!UICONTROL Share with anyone (no login required)]** , fare clic sul pulsante **Copia collegamento** per copiare il collegamento negli Appunti di sistema.

1. Condividi il collegamento con le persone che desideri possano accedere al progetto. Ad esempio, puoi incollare il collegamento in un messaggio e-mail.

   Qualsiasi persona con cui condividi il collegamento può visualizzare il progetto Analysis Workspace. Se si sceglie di richiedere una password, è necessario condividerla con chiunque desideri accedere al collegamento.

1. Seleziona **[!UICONTROL Close]** per chiudere la finestra di dialogo condividi. Le modifiche vengono salvate automaticamente. <!-- True? -->

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
| In qualità di amministratore, quale esperienza di progetto visualizzerò? | Gli amministratori inseriti in un ruolo **[!UICONTROL Can duplicate]** o **[!UICONTROL Can view]** riceveranno tali esperienze limitate quando aprono un progetto. Se necessario, un amministratore può elevare il proprio ruolo a **[!UICONTROL Can edit]** in qualsiasi momento tramite **[!UICONTROL Components]>[!UICONTROL Projects]**. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo utente e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceverà sempre l’esperienza di livello più elevato. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Can edit]** come singolo utente e il ruolo **[!UICONTROL Can view]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Can edit]**. |
| Quale esperienza riceve un destinatario se apre un collegamento al progetto? | I destinatari ricevono il ruolo in cui li hai inseriti nella modalità di condivisione. Se a un destinatario non viene assegnato un ruolo e riceve un collegamento al progetto (**[!UICONTROL Share]>[!UICONTROL Get project link]**), per impostazione predefinita gli verrà assegnato un ruolo. Gli amministratori ricevono **[!UICONTROL Can edit]** e i non amministratori **[!UICONTROL Can duplicate]**. |
