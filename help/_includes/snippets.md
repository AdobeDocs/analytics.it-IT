---
source-git-commit: 57772f5a2e74ec20fd7c234b996678f7e75607ea
workflow-type: tm+mt
source-wordcount: '974'
ht-degree: 11%

---
# Snippet

## Annuncio sulla fine del ciclo di vita di Reports &amp; Analytics {#ra-eol}

>[!IMPORTANT]
>
>Ulteriori informazioni sull’[Annuncio sulla fine del ciclo di vita](https://express.adobe.com/page/6WnF8JK6IRDhf/) di Reports &amp; Analytics.

## Criteri di filtro del dizionario dati {#dd-filter-criteria}

1. (Facoltativo) Seleziona la **Filtro** icona ![Icona Filtro dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/assets/data-dictionary-filter-icon.png), quindi seleziona una delle seguenti opzioni di filtro per filtrare l’elenco dei componenti:

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Approvato**] | Mostra solo i componenti contrassegnati come approvati da un amministratore. |
   | [!UICONTROL **Preferiti**] | Mostra solo i componenti inclusi nell&#39;elenco dei Preferiti. Per informazioni sull’aggiunta di componenti all’elenco dei preferiti, consulta [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensioni**] | Mostra solo i componenti che sono Dimension. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). |
   | [!UICONTROL **Metriche**] | Mostra solo i componenti che sono metriche. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). |
   | [!UICONTROL **Segmenti**] | Mostra solo i componenti che sono Segmenti. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). <!--this is Filters in CJA--> |
   | [!UICONTROL **Intervalli di date**] | Mostra solo i componenti che sono intervalli di date. (Questa opzione è disponibile anche nel [!UICONTROL **Filtri rapidi**] al primo accesso al dizionario dati). |
   | [!UICONTROL **Mostra tutto**] | Mostra tutti i componenti. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Non approvato**] | Mostra solo i componenti non ancora contrassegnati come approvati da un amministratore. In qualità di amministratore, è utile per identificare i componenti che richiedono la revisione e l’approvazione dell’utente. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Descrizione mancante**] | Nel campo Descrizione è possibile visualizzare solo i componenti che non dispongono ancora di una descrizione. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Mostra duplicati**] | <p>Mostra solo i componenti che hanno lo stesso nome o la stessa definizione di un altro componente della suite di rapporti selezionata. Per poter essere visualizzati come duplicati, i nomi o le definizioni devono corrispondere esattamente.</p><p>Questa opzione è disponibile solo per gli amministratori.</p><p>**NOTA:** Per le definizioni, sono inclusi i componenti creati dall’utente e quelli forniti dall’Adobe. Per i nomi, al momento sono inclusi solo i componenti creati e non quelli forniti dall’Adobe. La visualizzazione di nomi duplicati per i componenti forniti da Adobe verrà aggiunta in una versione futura.</p> |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style="table-layout:auto"}

## Informazioni sui componenti del dizionario dati {#dd-component-information}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | <p>Indica che il componente è stato rivisto e approvato dall’amministratore.</p><p>Dopo l’approvazione di un componente, gli amministratori possono rimuovere l’approvazione selezionando la **Approvato** pulsante .</p> |
| [!UICONTROL **Approvazione necessaria**] | <p>Indica che il componente non è ancora stato rivisto e approvato dall’amministratore.</p><p>Gli amministratori visualizzano un’opzione per [!UICONTROL **Approva**]. Selezionando questa opzione, il componente viene contrassegnato come &quot;Approvato&quot; dagli utenti.</p> |
| [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente utilizzato con**] | <p>Mostra i componenti più comunemente utilizzati con il componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Segmento e Intervallo date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono visualizzati solo i componenti a cui hai accesso.</p><p>Gli amministratori possono curare i componenti visualizzati dagli utenti in questa sezione selezionando i componenti desiderati nel [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**] campi a discesa. Prima di curare i componenti visualizzati dagli utenti, applica le **Mostra tutto** filtro per assicurarti di visualizzare tutti i componenti che non sono condivisi con te.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
| [!UICONTROL **Simile a**] | <p>Mostra i componenti con nomi simili al componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Segmento e Intervallo date.</p><p>Vengono visualizzati solo i componenti a cui hai accesso.</p><p>Anche eventuali componenti duplicati nella suite di rapporti vengono visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare lo stato del dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Gli amministratori possono curare i componenti visualizzati dagli utenti in questa sezione selezionando i componenti desiderati nel [!UICONTROL **Includi sempre**] e [!UICONTROL **Escludi sempre**] campi a discesa. Prima di curare i componenti visualizzati dagli utenti, applica le **Mostra tutto** filtro per assicurarti di visualizzare tutti i componenti che non sono condivisi con te.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**NOTA:** Attualmente, il **Simile a** include solo i componenti creati e non quelli forniti da Adobe. I componenti forniti da Adobe verranno aggiunti in una versione futura.</p> |
| [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
| [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, che si tratti di un Dimension, una metrica, un segmento o un intervallo di date. |
| [!UICONTROL **Creato da**] | Visualizza il nome dell’utente che ha creato il componente. |
| [!UICONTROL **Anteprima**] | Mostra un’anteprima del componente in Analysis Workspace. |
| [!UICONTROL **Data ultima modifica**] | Visualizza il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando si visualizzano Segmenti, metriche calcolate e intervalli di date. |

{style="table-layout:auto"}

## Fase di test del rilascio {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, vedi [Versioni delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

## Sezione della fase di test del rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di test del rilascio e potrebbe non essere ancora disponibile nell‘ambiente. Questa nota verrà rimossa non appena la funzionalità sarà disponibile a livello generale. Per informazioni sul processo di rilascio di Analytics, vedi [Versioni delle funzioni di Adobe Analytics](/help/release-notes/releases.md).


## Esclusione di responsabilità del plug-in {#plug-in}

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta il team dell&#39;account Adobe della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

