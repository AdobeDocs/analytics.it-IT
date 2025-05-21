---
description: Condivisione e ruoli dei progetti in Workspace
keywords: Condivisione di Analysis Workspace
title: Condividere progetti
feature: Curate and Share
role: User, Admin
exl-id: da106eb1-7f5c-469a-a8aa-8497fc3706dc
source-git-commit: 440cc4c977aae97e3fc3c97f3998c5d542cd88c3
workflow-type: tm+mt
source-wordcount: '1889'
ht-degree: 98%

---

# Condividere progetti {#share-projects}

>[!CONTEXTUALHELP]
>id="workspace_shareprojects"
>title="Condividere progetti"
>abstract="Puoi condividere uno di questi ruoli di progetto con altri utenti dell’organizzazione."



Puoi condividere un progetto di Analysis Workspace con i seguenti tipi di persone:

* Utenti e gruppi della tua organizzazione che hanno accesso ad Adobe Analytics

  È possibile condividere l’accesso a Modifica, Duplica o Visualizza

* Utenti e gruppi della tua organizzazione che non hanno accesso ad Adobe Analytics

  I destinatari dispongono di accesso di sola lettura

* Persone esterne all’organizzazione

  I destinatari dispongono di accesso di sola lettura

Qualsiasi [cura](curate.md) applichi prima della condivisione, viene visualizzata all’apertura del progetto da parte dei destinatari.



>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Condividi progetti](https://video.tv.adobe.com/v/40037?quality=12&learn=on&captions=ita){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


## Condividere con utenti e gruppi di Analysis Workspace nella tua organizzazione {#Add}

Puoi condividere un progetto con utenti o gruppi di Analysis Workspace esistenti nella tua organizzazione. Quando condividi un progetto come descritto in questa sezione, gli utenti con effettui la condivisione devono già avere accesso ad Adobe Analytics.

Puoi condividere un ruolo specifico con utenti o gruppi, oppure un collegamento.

* [Condividere un ruolo di progetto specifico](#share-a-specific-project-role)

* [Condividere un collegamento a un progetto](#share-a-link-to-a-project)

## Condividere un ruolo di progetto specifico

Quando condividi un ruolo di progetto specifico con utenti e gruppi dell’organizzazione, considera quanto segue:

* I ruoli di progetto  (**[!UICONTROL Edit original]**, **[!UICONTROL Edit copy]**, e **[!UICONTROL Read only]**) sono legati all’ID dell’utente e del progetto specifico. I ruoli di progetto sono indipendenti dalle autorizzazioni utente gestite nella [Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it).

* In Adobe Analytics, i gruppi sono definiti dai profili di prodotto nell’[Admin Console di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it). Gli amministratori possono condividere con qualsiasi gruppo, incluso “Tutti”. I non amministratori possono condividere con i gruppi di cui sono membri, ad eccezione di “Tutti”.

* Un destinatario posizionato in più ruoli, avrà sempre l’esperienza di livello più elevato. Ciò potrebbe verificarsi se un utente viene aggiunto sia come singolo utente che come parte di un gruppo. Ad esempio, se a un utente viene assegnato il ruolo **[!UICONTROL Edit original]** come singolo utente e il ruolo **[!UICONTROL Read only]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Edit original]**.

* Gli amministratori inseriti in un ruolo **[!UICONTROL Edit copy]** o **[!UICONTROL Read only]** riceveranno tali esperienze limitate quando aprono un progetto. Un amministratore può modificare il proprio ruolo in **[!UICONTROL Edit original]** condividendo il progetto con se stesso e assegnandosi il ruolo **Modifica**, come descritto nella procedura seguente.

* Se sono stati selezionati più progetti da condividere, i destinatari verranno aggiunti all’elenco esistente di destinatari per ciascun progetto.

  Ad esempio, il progetto A è già condiviso con i destinatari 1, 2 e 3, mentre il progetto B è già condiviso con i destinatari 4, 5 e 6.

  I progetti A e B sono quindi condivisi con i destinatari 4 e 7. Il nuovo elenco di condivisione per il progetto A è ora 1, 2, 3, 4 e 7, mentre il nuovo elenco di condivisione per il progetto B è 4, 5, 6 e 7.

Per condividere un ruolo di progetto specifico con utenti o gruppi dell’organizzazione:

1. In Adobe Analytics, seleziona la scheda [!UICONTROL **Workspace**], quindi scegli [!UICONTROL **Progetti**] nella barra a sinistra.

1. Seleziona la casella di controllo accanto a uno o più progetti da condividere, quindi seleziona [!UICONTROL **Condividi**].

   Oppure

   Per condividere solo un singolo progetto, puoi aprire il progetto da condividere e poi selezionare **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**.
In presenza di modifiche non salvate, ti verrà richiesto di salvare prima il progetto.

   Viene visualizzata la finestra di dialogo Condividi progetto. Le sezioni [!UICONTROL **Condividi tramite collegamento**] e [!UICONTROL **Impostazioni**] della finestra di dialogo sono visibili solo quando si condivide un singolo progetto.

   ![](assets/share-proj-modal.png)

1. Aggiungi destinatari o gruppi di destinatari in uno dei campi ruolo forniti:

   **Modifica originale:** i destinatari possono **[!UICONTROL Save]** le modifiche a un progetto e fungere da co-proprietari. Questo ruolo è utile se desideri gestire un progetto con altri colleghi; ciò include la modifica e l’eliminazione degli elenchi dei destinatari per un progetto condiviso. <br>Nota: Analysis Workspace al momento non supporta la collaborazione in tempo reale, pertanto si consiglia di modificare un progetto solo un utente alla volta. Se i progetti vengono salvati contemporaneamente, viene mantenuta l’ultima versione.

   **Modifica copia:** i destinatari possono **[!UICONTROL Save as]** e accedere alla barra a sinistra. Le interazioni del progetto non sono limitate in questo ruolo. Questo ruolo è utile se desideri condividere un progetto con utenti che conoscono i dati dell’organizzazione e sanno come utilizzare Analysis Workspace, ma non desideri che il progetto venga modificato.

   **Sola lettura:** i destinatari non possono **[!UICONTROL Save]** o **[!UICONTROL Save as]** e non hanno accesso alla barra a sinistra. Anche le interazioni del progetto sono limitate. Questo ruolo è utile se desideri condividere un progetto con utenti che hanno meno familiarità con la struttura dei dati della tua organizzazione e con Analysis Workspace o Adobe Analytics in genere. Tuttavia, desideri comunque che utilizzino dati e informazioni in un ambiente sicuro. Scopri di più sull’[esperienza di progetto di Sola lettura](/help/analyze/analysis-workspace/curate-share/view-only-projects.md).

1. (Condizionale) Se condividi un singolo progetto, scegli se abilitare le seguenti opzioni durante la condivisione:

   * **Condividi componenti di progetto incorporati:** condividi segmenti, metriche calcolate e intervalli di date con tutti i destinatari. Una volta condivisi, tali componenti sono disponibili nel menu a discesa Componenti nell’interfaccia Workspace del destinatario. Questa impostazione non è persistente: è una singola azione da eseguire al momento della condivisione.

   * **Imposta come pagina di destinazione per i destinatari:** imposta questa pagina come pagina di destinazione per i destinatari. Questa impostazione non è persistente: è una singola azione da eseguire al momento della condivisione.

1. Seleziona **[!UICONTROL Share]**. Se il progetto è già stato condiviso, seleziona [!UICONTROL **Aggiorna**].

   Oppure

   Fai clic su **[!UICONTROL Curate and Share]** per applicare automaticamente la cura del progetto. (Se il progetto è già stato condiviso, seleziona **[!UICONTROL Curate & Update]**). Ulteriori informazioni su [cura del progetto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/curate.html?lang=it).

## Condividere un collegamento a un progetto

Quando condividi un collegamento come descritto in questa sezione, prendi in considerazione quanto segue:

* Gli utenti che ricevono un collegamento devono accedere ad Adobe Analytics prima di poter accedere al progetto.

* Se a un destinatario non viene assegnato un ruolo e riceve un [collegamento](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/shareable-links.html?lang=it) al progetto, per impostazione predefinita gli verrà assegnato un ruolo. Gli amministratori ricevono **[!UICONTROL Edit original]** e i non amministratori **[!UICONTROL Edit copy]**.

Per condividere il collegamento del progetto con gli utenti dell’organizzazione:

1. Salva il progetto. In presenza di modifiche non salvate, ti verrà richiesto di salvare prima il progetto prima di condividere un collegamento.

1. Seleziona **[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** accanto al campo **[!UICONTROL Share by link]**.

   ![](assets/share-proj-modal.png)

1. Condividi il collegamento con gli utenti della tua organizzazione. Ad esempio, puoi incollarlo in un’e-mail, in un sito web interno e così via.

## Condividere un progetto con chiunque (accesso non richiesto) {#share-public-link}

>[!CONTEXTUALHELP]
>id="workspace_share_with_anyone_require_aec_authentication"
>title="Richiedere l’autenticazione Experience Cloud"
>abstract="La tua organizzazione richiede che gli utenti abbiano effettuato l’accesso ad Experience Cloud per utilizzare questo collegamento."

Puoi consentire l’[accesso di sola lettura](/help/analyze/analysis-workspace/curate-share/view-only-projects.md) ai progetti di Analysis Workspace a coloro che non hanno accesso ad Adobe Analytics. Questo può includere:

* Persone esterne all’organizzazione

* Persone dell’organizzazione che non hanno accesso ad Adobe Analytics

>[!NOTE]
>
>Quando condividi un progetto di Analysis Workspace con persone che non hanno accesso ad Adobe Analytics, considera quanto segue:
>
>* La possibilità di condividere un progetto in questo modo può essere disabilitata dall’amministratore di Analytics, come descritto in [Preferenze](/help/analyze/analysis-workspace/user-preferences.md). Se non riesci a condividere un progetto come descritto in questa sezione, l’amministratore di Analytics ha disabilitato questa funzionalità.
>
>* I progetti con più di 50 visualizzazioni espanse non possono essere condivisi con persone che non hanno accesso ad Adobe Analytics.
>
>* Gli utenti con cui condividi il progetto possono visualizzare tutti i filtri applicati al progetto durante la [cura](curate.md).
> 
>* Gli utenti con cui condividi possono modificare l’intervallo di date del progetto. L’intervallo di date impostato per il progetto viene visualizzato per impostazione predefinita.
>
>* Un progetto potrebbe diventare inaccessibile se molti utenti tentano di accedere contemporaneamente a un determinato collegamento. Per impostazione predefinita, più di 190 persone possono accedere a un singolo collegamento ogni 5 minuti. Se l’organizzazione raggiunge questo limite, attendi 5 minuti e prova di nuovo ad accedere al collegamento.


>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Condividi un collegamento con qualcuno](https://video.tv.adobe.com/v/3452466?quality=12&learn=on&captions=ita){target="_blank"} per vedere un video demo.

>[!ENDSHADEBOX]


Per condividere un progetto Analysis Workspace con persone che non hanno accesso ad Adobe Analytics:

1. Apri il progetto Analysis Workspace che desideri condividere.

1. Fai clic su **[!UICONTROL Share]** > **[!UICONTROL Share with anyone]**.

   In presenza di modifiche non salvate, ti verrà richiesto di salvare il progetto.

   <!-- Add screen shot of new modal -->

1. Abilita l’opzione **[!UICONTROL Link is active]** se non è già abilitata.

   Selezionando questa opzione viene creato un collegamento al progetto che può essere condiviso con chiunque. Disattivando questa opzione è possibile disattivare l’accesso al progetto in qualsiasi momento.

   Il proprietario del progetto è anche il proprietario di questo collegamento. La proprietà del collegamento può essere trasferita a un altro utente solo quando viene trasferita la proprietà del progetto, come descritto in [Trasferimento delle risorse utente o impostazione delle scadenze dell’account](/help/admin/admin/user-management2/users-assets.md) nella guida dell’amministratore di Analytics.

1. Scegli se abilitare la seguente opzione di sicurezza (questa opzione può essere controllata dall’amministratore di Analytics):

   * **[!UICONTROL Require Experience Cloud authentication]:**

     Quando questa opzione è abilitata, gli unici utenti che possono accedere al progetto sono quelli che possono accedere all’organizzazione Adobe Experience Cloud in cui è stato creato il progetto condiviso. Tuttavia, gli utenti con cui condividi non devono avere accesso ad Adobe Analytics.

     Gli amministratori di Analytics possono configurare questa preferenza per l’azienda, come descritto in [Preferenze](/help/analyze/analysis-workspace/user-preferences.md). A seconda della configurazione di questa opzione da parte dell’amministratore, potrebbero verificarsi gli scenari seguenti:

      * Se questa opzione non è visibile, l’amministratore di Analytics non ha abilitato questa funzione.

      * Se questa opzione è abilitata e disabilitata, l’amministratore di Analytics richiede l’autenticazione Experience Cloud per tutti coloro che accedono ai progetti Analysis Workspace.

1. Accanto al campo **[!UICONTROL Share with anyone (no login required)]**, fai clic sull’icona **Copia collegamento** ![Icona Copia collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Link_18_N.svg) per copiare il collegamento negli Appunti di sistema.

1. Condividi il collegamento con le persone che desideri possano accedere al progetto. Ad esempio, puoi incollare il collegamento in un messaggio e-mail.

   Qualsiasi persona con cui condividi il collegamento può visualizzare il progetto Analysis Workspace.

1. (Facoltativo) Puoi fare clic sull’icona **Genera nuovo collegamento** ![Icona Genera collegamento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Refresh_18_N.svg) per rimuovere l’accesso da utenti che hanno precedentemente ricevuto un collegamento al progetto. Viene generato un nuovo collegamento che puoi condividere con gli utenti che desideri accedano al progetto.

1. Seleziona **[!UICONTROL Close]** per chiudere la finestra di dialogo condividi. Le modifiche vengono salvate automaticamente.

## Visualizza progetti condivisi con te

Quando qualcuno condivide un progetto con te tramite la [condivisione di un ruolo di progetto specifico](#share-a-specific-project-role), puoi accedere ai progetti condivisi dalla [scheda Progetti della pagina di destinazione di Analytics](/help/analyze/landing.md#navigate-the-projects-tab).

Quando qualcuno condivide un progetto con te tramite un collegamento (dalla [scheda Condividi progetto](#share-a-link-to-a-project) o utilizzando un collegamento di tipo [condividi con chiunque](#share-a-project-with-anyone-no-login-required)), per accedere al progetto devi utilizzare il collegamento condiviso con te. Ad esempio, il collegamento potrebbe essere stato condiviso in un’e-mail, in un sito web interno e così via.

## Condividere componenti incorporati

Puoi condividere i componenti incorporati che fanno parte del progetto.

>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Condividi componenti incorporati](https://video.tv.adobe.com/v/329425?quality=12&learn=on&captions=ita){target="_blank"} per un video dimostrativo.

>[!ENDSHADEBOX]


## Domande frequenti {#FAQs}

| Domanda | Risposta |
| --- | --- |
| Cosa succede se due editor salvano un progetto contemporaneamente? | Le modifiche non vengono unite e viene mantenuta l’ultima versione del progetto salvata. Analysis Workspace non supporta attualmente la collaborazione in tempo reale. |
| Cosa succede se un destinatario viene collocato in un ruolo come singolo utente e in un altro ruolo come membro di un gruppo? | Se un destinatario viene posizionato in più ruoli, riceverà sempre l’esperienza di livello più elevato. Ad esempio, se a un destinatario viene assegnato il ruolo **[!UICONTROL Edit original]** come singolo utente e il ruolo **[!UICONTROL Read only]** come membro di un gruppo, riceverà un’esperienza di progetto **[!UICONTROL Edit original]**. |
| Quale esperienza riceve un destinatario se apre un collegamento al progetto? | I destinatari ricevono il ruolo in cui li hai inseriti nella modalità di condivisione. Se non viene assegnato un ruolo al destinatario e questo riceve un collegamento al progetto (**[!UICONTROL Share]** > **[!UICONTROL Share with Workspace users]**, quindi seleziona **[!UICONTROL Copy]** vicino al campo **[!UICONTROL Share by link]**), gli verrà assegnato un ruolo per impostazione predefinita. Gli amministratori ricevono **[!UICONTROL Edit original]** e i non amministratori **[!UICONTROL Edit copy]**. |
