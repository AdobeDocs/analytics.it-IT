---
source-git-commit: 33ac467cd73e3099ce0ca03aa41cbd4192eb2384
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 96%

---
# Snippet

## Annuncio sulla fine del ciclo di vita di Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>A decorrere dal **17 gennaio 2024**, Adobe ha interrotto Reports &amp; Analytics e i relativi rapporti e funzioni. In quel momento Reports &amp; Analytics e tutti i suoi rapporti e pianificazioni cessarono di funzionare. I rapporti, le visualizzazioni e la tecnologia alla base di Reports &amp; Analytics non soddisfano più gli standard tecnologici di Adobe. La maggior parte delle funzioni di Reports &amp; Analytics sono disponibili in Analysis Workspace. Per informazioni sull&#39;utilizzo dei report in Analysis Workspace, vedere [Utilizzare report predefiniti](/help/analyze/analysis-workspace/reports/use-reports.md).
> 
>Dal rilascio di Analysis Workspace nel 2015, le funzionalità e le caratteristiche di Reports &amp; Analytics sono state spostate in Analysis Workspace ed è stata raggiunta una soglia di parità dei flussi di lavoro. Questo avviso spiega il processo di fine del ciclo di vita.
>
>Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://www.adobe.com/go/analytics_rnaeol_it) di Reports &amp; Analytics.

## Criteri del filtro del dizionario dati {#dd-filter-criteria}

1. (Facoltativo) Seleziona l’icona **Filtro** ![icona Filtro dizionario dati](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e quindi una delle seguenti opzioni per filtrare l’elenco dei componenti:

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
| [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell’elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
| [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimensioni. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
| [!UICONTROL **Metriche**] | Mostra solo i componenti che sono Metriche. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
| [!UICONTROL **Segmenti**] | Mostra solo i componenti che sono Segmenti. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) <!--this is Filters in Customer Journey Analytics--> |
| [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono Intervalli di date. (Questa opzione è disponibile anche nella scheda [!UICONTROL **Filtri rapidi**] durante il primo accesso al dizionario dati.) |
| [!UICONTROL **Mostra tutti**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
| [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, questo è utile per identificare i componenti che richiedono la revisione e l’approvazione. Questa opzione è disponibile solo per gli amministratori. |
| [!UICONTROL **Descrizione mancante**] | Mostra solo i componenti che non dispongono ancora di una descrizione nel campo apposito. Questa opzione è disponibile solo per gli amministratori. |
| [!UICONTROL **Mostra duplicati**] | <p>Mostra solo i componenti che hanno lo stesso nome o la stessa definizione di un altro componente della suite di rapporti selezionata. Per poter essere visualizzati come duplicati, i nomi o le definizioni devono corrispondere esattamente.</p><p>Questa opzione è disponibile solo per gli amministratori.</p><p>**NOTA:** per le definizioni, sono inclusi i componenti creati dall’utente e quelli forniti da Adobe. Per i nomi, al momento sono inclusi solo i componenti creati dall’utente e non quelli forniti da Adobe. La visualizzazione di nomi duplicati per i componenti forniti da Adobe verrà aggiunta in una versione futura.</p> |
| [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
| [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

{style="table-layout:auto"}

## Informazioni sui componenti del dizionario dati {#dd-component-information}

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

## Opzioni di ordinamento dei componenti {#components-sort-options}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Consigliato**] | Ordina i componenti a partire da quelli consigliati. I componenti utilizzati più di frequente e più di recente da te o da altri nella tua organizzazione vengono visualizzati più in alto nell’elenco. |
| [!UICONTROL **Alfabetico**] | Ordina alfabeticamente i componenti. |
| [!UICONTROL **Per categorie**] | Ordina i componenti in base al tipo (dimensione, metrica, segmento, intervallo di date). |

{style="table-layout:auto"}

## Fase di test del rilascio {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

## Sezione della fase di test del rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, consulta [Rilascio delle funzioni di Adobe Analytics](/help/release-notes/releases.md).


## Esclusione di responsabilità del plug-in {#plug-in}

>[!IMPORTANT]
>
>Questo plug-in è fornito a titolo di cortesia da Adobe Consulting per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, per la sua installazione né per la risoluzione di problemi. Se hai bisogno di aiuto con questo plug-in, contatta il team dell’account Adobe della tua organizzazione. Il team può organizzare una riunione con un consulente per l’assistenza.

