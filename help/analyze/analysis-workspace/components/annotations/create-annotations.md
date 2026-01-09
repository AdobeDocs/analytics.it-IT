---
title: Creare annotazioni
description: Scopri come creare annotazioni in Analysis Workspace.
role: Admin
feature: Annotations
exl-id: 3cf9a0fd-11c9-4375-8bbe-9551ba86f86d
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '783'
ht-degree: 94%

---

# Creare annotazioni

Per impostazione predefinita, solo gli amministratori possono creare annotazioni. Per visualizzare le annotazioni, gli utenti dispongono del diritto analogo a quello per visualizzare altri componenti (come segmenti, metriche calcolate ecc.).


Tuttavia, gli amministratori possono assegnare agli utenti l’autorizzazione [!UICONTROL Annotation Creation] (Analytics Tools) tramite [Adobe Admin Console](/help/admin/admin-console/permissions/analytics-tools.md).

Puoi creare un’annotazione nei modi seguenti:

![Creare un’annotazione](assets/create-annotation.png)

* **A**. Nell’interfaccia principale, seleziona **[!UICONTROL Components]** e quindi **[!UICONTROL Annotations]**. Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**] dal gestore [[!UICONTROL Annotations]](/help/analyze/analysis-workspace/components/annotations/manage-annotations.md).
* **B**. In un progetto Workspace, dal menu di scelta rapida in una visualizzazione, seleziona **[!UICONTROL Create annotation from selection]**.
* **C**. In un progetto Workspace, dal menu di scelta rapida in un grafico a linee, seleziona **[!UICONTROL Annotate Selection]**.
* **D**. In un progetto Workspace, seleziona **[!UICONTROL Components]** dal menu e quindi **[!UICONTROL Create annotation]**.
* **E**.  In un progetto Workspace, utilizza la scelta rapida da tastiera **[!UICONTROL ctrl+shift+o]** (Windows) o **[!UICONTROL shift+command+o]** (macOS)

Per definire l&#39;annotazione, utilizzare [[!UICONTROL Annotation builder]](#annotation-builder).



## Generatore di annotazioni {#annotation-builder}

>[!CONTEXTUALHELP]
>id="components_annotations_details"
>title="Dettagli annotazione"
>abstract="Le annotazioni consentono di comunicare in modo efficace dettagli sui dati contestuali a beneficio degli utenti in tutta l’organizzazione. Consentono di collegare eventi calendario a dimensioni o metriche specifiche."

>[!CONTEXTUALHELP]
>id="components_annotations_scope"
>title="Ambito"
>abstract="L’ambito consente di personalizzare i dati ai quali aggiungere annotazioni. Le metriche calcolate e i segmenti non ereditano automaticamente le annotazioni applicate ai componenti utilizzati nelle loro definizioni. Puoi aggiungere nuove metriche calcolate alla sezione dell’ambito di un’annotazione esistente. I segmenti nuovi richiedono un’annotazione nuova."



La finestra di dialogo **[!UICONTROL Annotations builder]** viene utilizzata per creare nuove annotazioni o modificare quelle esistenti. La finestra di dialogo si chiama **[!UICONTROL New annotation]** o **[!UICONTROL Edit annotation]** per le annotazioni create o gestite dal gestore [[!UICONTROL Annotations]](/help/analyze/analysis-workspace/components/annotations/manage-annotations.md).


>[!BEGINTABS]

>[!TAB Generatore di annotazioni]

![Finestra dei dettagli dell’annotazione con i campi e le opzioni descritti nella sezione successiva.](assets/annotation-builder.png)

>[!TAB Creare o modificare un’annotazione]

![Finestra dei dettagli dell’annotazione con i campi e le opzioni descritti nella sezione successiva.](assets/create-edit-annotation.png)

>[!ENDTABS]

1. Specifica i dettagli seguenti (![Obbligatorio](/help/assets/icons/Required.svg) indica i dati obbligatori):

   | Elemento | Descrizione |
   | --- | --- |
   | **[!UICONTROL Report suite]** | Puoi selezionare la suite di rapporti per l’annotazione. L’annotazione definita è disponibile come annotazione nei progetti Workspace in base alla suite di rapporti selezionata. Questa selezione viene annullata se hai abilitato [!UICONTROL Apply to all report suites]. |
   | **[!UICONTROL Project-only Annotation]** | Una casella di informazioni per spiegare che l’annotazione creata è visibile solo nel progetto Workspace su cui stai lavorando. Abilita **[!UICONTROL Make this Annotation available to all your projects]** per rendere l’annotazione visibile a tutti i tuoi progetti. Questa casella di informazioni è visibile solo quando crei un’annotazione dall’interno di un progetto Workspace. |
   | **[!UICONTROL Title]** ![Obbligatorio](/help/assets/icons/Required.svg) | Assegna un nome all’annotazione, ad esempio `Needs further investigation`. |
   | **[!UICONTROL Description]** | Fornisci una descrizione per l’annotazione, ad esempio `We never expected such a fluctuation in numbers.`. |
   | **[!UICONTROL Tags]** | Organizza l’annotazione creando o applicando uno o più tag. Inizia a digitare per trovare i tag esistenti che puoi selezionare. Oppure premi **[!UICONTROL Enter]** per aggiungere un nuovo tag. Seleziona ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un tag. |
   | **[!UICONTROL Applied date]** ![Obbligatorio](/help/assets/icons/Required.svg) | Seleziona la data o l’intervallo di date che è necessario riportare per rendere visibile l’annotazione. Quando crei un’annotazione utilizzando la scelta rapida da tastiera, per impostazione predefinita l’annotazione viene impostata su un intervallo di date limitato al solo giorno. Quando crei un’annotazione utilizzando una selezione in una visualizzazione, per impostazione predefinita l’annotazione si basa sull’intervallo di date del pannello a cui appartiene la visualizzazione. |
   | **[!UICONTROL Color]** | Applica un colore all’annotazione. L’annotazione viene visualizzata nel progetto con il colore selezionato. Puoi scegliere colori diversi per diverse categorie di annotazioni, ad esempio festività, eventi esterni, problemi di tracciamento, ecc. |
   | **[!UICONTROL Scope]** | Trascina e rilascia le metriche dal pannello dei componenti che attivano l’annotazione. Ad esempio persone, sessioni ed eventi. Quindi, trascina dal pannello dei componenti, i segmenti o le dimensioni che fungono da segmenti per determinare se visualizzare o meno l’annotazione. Se non specifichi un ambito, l’annotazione verrà applicata a tutti i dati. <br/>Puoi scegliere tra due opzioni:<ul><li>**[!UICONTROL Any of these metrics are present]**: trascina fino a 10 metriche per attivare la visualizzazione dell’annotazione.<br/>Ad esempio, se la metrica Entrate non ha raccolto dati per un intervallo di date specifico, trascina la metrica Entrate in questa casella.</li><li>**[!UICONTROL With all of these segments]**: trascina fino a 10 dimensioni o segmenti che determinano se l’annotazione viene visualizzata.</li></ul><p><p>**Nota:** un’annotazione applicata a un componente e quindi utilizzata come parte di una metrica calcolata o di una definizione di segmento NON eredita automaticamente l’annotazione. Per visualizzare l’annotazione, è necessario aggiungere alla sezione dell’ambito anche la metrica calcolata desiderata. Tuttavia, è necessario creare una nuova annotazione per ogni segmento che si desidera annotare con le stesse informazioni. Ad esempio: hai applicato un’annotazione a [!UICONTROL Orders] in un giorno specifico. Quindi utilizzi [!UICONTROL Orders] in una metrica calcolata per lo stesso intervallo di date. La nuova metrica calcolata non visualizza automaticamente l’annotazione per gli ordini. Aggiungi anche la metrica calcolata alla sezione dell’ambito per l’annotazione da visualizzare. |
   | **[!UICONTROL Apply to all report suites]** | Per impostazione predefinita, l’annotazione è applicabile alla suite di rapporti di origine. Selezionando questa casella, l’annotazione viene applicata a tutte le suite di rapporti dell’azienda. |

   {style="table-layout:auto"}

1. Seleziona
   * **[!UICONTROL Save]** per salvare l’annotazione;
   * **[!UICONTROL Save As]** per salvare una copia dell’annotazione;
   * **[!UICONTROL Delete]** per eliminare un’annotazione;
   * **[!UICONTROL Cancel]** per annullare le modifiche apportate a un’annotazione o per annullare la creazione di una nuova annotazione.
