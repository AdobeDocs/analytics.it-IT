---
description: Il dizionario dei dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, quali sono approvati, quali sono duplicati e così via.
title: Modificare le voci nel dizionario dei dati
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1102'
ht-degree: 78%

---

# Modificare le voci dei componenti nel dizionario dei dati

Gli amministratori di Analytics possono modificare le voci dei componenti nel dizionario dei dati per una determinata suite di rapporti. Tutte le modifiche apportate sono visibili a tutti gli utenti della suite di rapporti.

Per modificare un componente nel dizionario dei dati:

1. Vai al progetto Analysis Workspace che contiene il componente da modificare.

1. Seleziona l’icona **Dizionario dei dati** nella barra a sinistra di Analysis Workspace. In [Accedere al dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary) sono descritti metodi alternativi per accedere al dizionario dati.

   Viene visualizzata la finestra Dizionario dei dati.

   ![Vista amministratore del dizionario dei dati](assets/data-dictionary-admin.png)

1. Assicurati che nel menu a discesa sia selezionata la suite di rapporti corretta. Per impostazione predefinita, viene visualizzata la suite di rapporti in cui ti trovi già.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri modificare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimensioni** ![icona Dimensione](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Segmenti** ![icona Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![icona Intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![icona Metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L’icona Adobe indica un modello di metrica calcolata o un modello di segmento, e l’icona della calcolatrice ![icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

1. (Facoltativo) Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | **[!UICONTROL Approved]** | Solo i componenti contrassegnati come Approvati da un amministratore. |
   | **[!UICONTROL Favorites]** | Solo i componenti inclusi nell&#39;elenco Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | **[!UICONTROL Dimensions]** | Solo i componenti che sono quote. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick filters]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Metrics]** | Solo i componenti che sono metriche. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick filters]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Segments]** | Solo i componenti che sono segmenti. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick filters]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Date ranges]** | Solo i componenti che sono intervalli di date. Questa opzione è disponibile anche nella scheda **[!UICONTROL Quick filters]** quando si accede per la prima volta al dizionario dati. |
   | **[!UICONTROL Show all]** | Tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Unapproved]** | Solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Missing Description]** | Solo i componenti che non hanno ancora una descrizione nel campo Descrizione. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Show duplicates]** | <p>Solo i componenti con lo stesso nome o la stessa definizione di quello di un altro componente nella suite di rapporti selezionata. Per poter essere visualizzati come duplicati, i nomi o le definizioni devono corrispondere esattamente.</p><p>Questa opzione è disponibile solo per gli amministratori.</p><p>**NOTA:** per le definizioni, sono inclusi i componenti creati dall’utente e quelli forniti da Adobe. Per i nomi, al momento sono inclusi solo i componenti creati dall’utente e non quelli forniti da Adobe. La visualizzazione di nomi duplicati per i componenti forniti da Adobe verrà aggiunta in una versione futura.</p> |
   | **[!UICONTROL No recent data]** | Solo componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | **[!UICONTROL Created by Adobe]** <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe.  Ad esempio Adobe Target. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

1. (Facoltativo) Seleziona l’icona **Ordina** ![icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Consigliato**] | Ordina i componenti a partire da quelli consigliati. I componenti utilizzati più di frequente e più di recente da te o da altri nella tua organizzazione vengono visualizzati più in alto nell’elenco. |
   | [!UICONTROL **Alfabetico**] | Ordina alfabeticamente i componenti. |
   | [!UICONTROL **Per categorie**] | Ordina i componenti in base al tipo (dimensione, metrica, segmento, intervallo di date). |

   {style="table-layout:auto"}

1. Dall’elenco dei componenti, seleziona il componente da modificare.

1. Seleziona l’icona **Modifica** ![icona Modifica dizionario dei dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) accanto al nome del componente.

1. Modifica una delle seguenti informazioni sul componente:

   | Opzione | Funzione |
   |---------|----------|
   | **[!UICONTROL Approved]** | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Dopo che un componente è stato approvato, gli amministratori possono rimuovere l’approvazione selezionando il pulsante **Approvato**.</p> |
   | **[!UICONTROL Approval needed]** | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un&#39;opzione per **[!UICONTROL Approve]**. Selezionando questa opzione, il componente viene visualizzato dagli utenti come “Approvato”.</p> |
   | **[!UICONTROL Description]** | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
   | **[!UICONTROL Frequently used with]** | <p>Mostra i componenti più comunemente utilizzati insieme a quello che stai visualizzando.</p><p>Tra i 5 tipi di componenti principali, ne sono mostrati fino a 5: Metrica, Metrica calcolata, Dimensione, Segmento e Intervallo di date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Gli amministratori possono curare i componenti visualizzati in questa sezione selezionando i componenti desiderati nei campi a discesa **[!UICONTROL Always Include]** e **[!UICONTROL Always Exclude]**. Prima di curare i componenti che gli utenti possono visualizzare, applica il filtro **Mostra tutti** per assicurarti di esaminare anche i componenti che non sono condivisi con te.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | **[!UICONTROL Similar to]** | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Tra i 5 tipi di componenti principali, ne sono mostrati fino a 5: Metrica, Metrica calcolata, Dimensione, Segmento e Intervallo di date.</p><p>Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Qui vengono visualizzati anche eventuali componenti duplicati nella suite di rapporti. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti visualizzati in questa sezione selezionando i componenti desiderati nei campi a discesa **[!UICONTROL Always Include]** e **[!UICONTROL Always Exclude]**. Prima di curare i componenti che gli utenti possono visualizzare, applica il filtro **Mostra tutti** per assicurarti di esaminare anche i componenti che non sono condivisi con te.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** attualmente, la sezione **Simile a** include solo i componenti che hai creato e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
   | **[!UICONTROL Tags]** | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
   | **[!UICONTROL Component type]** | Elenca il tipo di componente, che si tratti di Dimensione, Metrica, Segmento o Intervallo di date. |
   | **[!UICONTROL Created by]** | Mostra il nome dell’utente che ha creato il componente. |
   | **[!UICONTROL Preview]** | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
   | **[!UICONTROL Date last modified]** | Mostra il giorno dell’ultima modifica apportata al componente. Questa sezione compare quando si visualizzano Segmenti, Metriche calcolate e Intervalli di date. |

   {style="table-layout:auto"}

1. Fai clic sull’icona **Salva** ![icona Salva del dizionario dei dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) per salvare le modifiche.
