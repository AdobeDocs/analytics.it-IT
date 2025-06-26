---
description: Il dizionario dei dati in Analysis Workspace consente agli utenti di catalogare e tenere traccia dei vari componenti in Analysis Workspace, incluso l’uso previsto, quali sono approvati, quali sono duplicati e così via.
title: Visualizzare il dizionario dei dati
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: 74ef4e73b6ed1e2a4ad498e2314af704acb6d8cb
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 98%

---

# Visualizzare le informazioni sui componenti nel dizionario dati

Il dizionario dei dati consente di visualizzare informazioni su un componente, tra cui la sua descrizione, componenti simili, altri componenti con cui viene utilizzato di frequente e altro ancora.

Per visualizzare informazioni su un componente nel dizionario dei dati:

1. Vai al progetto Analysis Workspace che contiene il componente che desideri visualizzare.

1. Seleziona l’icona [!UICONTROL **Dizionario dei dati**] nella barra a sinistra di Analysis Workspace. In [Accedere al dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary) sono descritti metodi alternativi per accedere al dizionario dati.

   Viene visualizzata la finestra Dizionario dei dati.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Assicurati che la suite di rapporti contenente il componente che desideri visualizzare sia selezionata nel menu a discesa. Per impostazione predefinita, viene visualizzata la suite di rapporti in cui ti trovi già.

1. (Facoltativo) Nel campo di ricerca, inizia a digitare il nome del componente che desideri visualizzare.

   Il tipo di componente può essere identificato sia dal colore che dall’icona. **Dimensioni** ![icona Dimensione](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) sono arancioni, **Segmenti** ![icona Segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) sono blu, **Intervalli di date** ![icona Intervallo di date](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) sono viola, e **Metriche** ![icona Metrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) sono verdi. L’icona Adobe indica un modello di metrica calcolata o un modello di segmento, e l’icona della calcolatrice ![icona Calcolatrice](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg) indica una metrica calcolata creata da un amministratore Analytics della tua organizzazione.

1. (Facoltativo) Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimensioni. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono Metriche. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Segmenti**] | Mostra solo i componenti che sono Segmenti. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono Intervalli di date. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
   | [!UICONTROL **Mostra tutti**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Mostra solo i componenti che non dispongono ancora di una descrizione nel campo apposito. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | <p>Mostra solo i componenti che hanno lo stesso nome o la stessa definizione di un altro componente della suite di rapporti selezionata. Per poter essere visualizzati come duplicati, i nomi o le definizioni devono corrispondere esattamente.</p><p>Questa opzione è disponibile solo per gli amministratori.</p><p>**NOTA:** per le definizioni, sono inclusi i componenti creati dall’utente e quelli forniti da Adobe. Per i nomi, al momento sono inclusi solo i componenti creati dall’utente e non quelli forniti da Adobe. La visualizzazione di nomi duplicati per i componenti forniti da Adobe verrà aggiunta in una versione futura.</p> |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

1. (Facoltativo) Seleziona l’icona **Ordina** ![icona Ordina componenti](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

   {{components-sort-options}}

1. Dall’elenco dei componenti, seleziona il componente che desideri visualizzare.

   Vengono visualizzate le seguenti informazioni sul componente:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Dopo che un componente è stato approvato, gli amministratori possono rimuovere l’approvazione selezionando il pulsante **Approvato**.</p> |
   | [!UICONTROL **Approvazione necessaria**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano l’opzione [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene visualizzato dagli utenti come “Approvato”.</p> |
   | [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
   | [!UICONTROL **Utilizzato di frequente con**] | <p>Mostra i componenti più comunemente utilizzati insieme a quello che stai visualizzando.</p><p>Tra i 5 tipi di componenti principali, ne sono mostrati fino a 5: Metrica, Metrica calcolata, Dimensione, Segmento e Intervallo di date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**]. Prima di curare i componenti che gli utenti possono visualizzare, applica il filtro **Mostra tutti** per assicurarti di esaminare anche i componenti che non sono condivisi con te.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | [!UICONTROL **Simile a**] | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Tra i 5 tipi di componenti principali, ne sono mostrati fino a 5: Metrica, Metrica calcolata, Dimensione, Segmento e Intervallo di date.</p><p>Vengono mostrati solo i componenti a cui hai accesso alla visualizzazione.</p><p>Qui vengono visualizzati anche eventuali componenti duplicati nella suite di rapporti. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare l’integrità del dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti che gli utenti possono visualizzare in questa sezione, selezionandoli nei campi a discesa [!UICONTROL **Includi sempre**] ed [!UICONTROL **Escludi sempre**]. Prima di curare i componenti che gli utenti possono visualizzare, applica il filtro **Mostra tutti** per assicurarti di esaminare anche i componenti che non sono condivisi con te.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** attualmente, la sezione **Simile a** include solo i componenti che hai creato e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
   | [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
   | [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, che si tratti di Dimensione, Metrica, Segmento o Intervallo di date. |
   | [!UICONTROL **Creato da**] | Mostra il nome dell’utente che ha creato il componente. |
   | [!UICONTROL **Anteprima**] | Mostra un’anteprima dell’aspetto del componente in Analysis Workspace. |
   | [!UICONTROL **Data ultima modifica**] | Mostra il giorno dell’ultima modifica apportata al componente. Questa sezione compare quando si visualizzano Segmenti, Metriche calcolate e Intervalli di date. |

   {style="table-layout:auto"}

1. (Facoltativo) Trascina un componente dal dizionario dei dati ad Analysis Workspace.
