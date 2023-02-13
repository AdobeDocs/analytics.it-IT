---
source-git-commit: d8442f1ec8f35fbcda98b35070936677813ce330
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 5%

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
   | [!UICONTROL **Mostra duplicati**] | Mostra solo i componenti che hanno la stessa etichetta o la stessa descrizione di un altro componente della suite di rapporti selezionata. Le etichette o le descrizioni devono corrispondere esattamente per poter essere visualizzate come duplicati. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Nessun dato recente**] | Mostra solo i componenti che non hanno raccolto dati negli ultimi 90 giorni. Questa opzione è disponibile solo per gli amministratori. |
   | [!UICONTROL **Creato da Adobe**] <!-- I don't see this option--> | Mostra solo i componenti creati da Adobe. I componenti creati da un amministratore o da un altro utente dell’organizzazione non vengono visualizzati. |

   {style=&quot;table-layout:auto&quot;}

## Informazioni sui componenti del dizionario dati {#dd-component-information}

| Opzione | Funzione |
|---------|----------|
| [!UICONTROL **Approvato**] | Indica che il componente è stato rivisto e approvato dall’amministratore. Gli amministratori visualizzano un [!UICONTROL **Approvazione richiesta**] per i componenti non approvati. Selezionando questa opzione, l&#39;opzione viene contrassegnata come Approvata. |
| [!UICONTROL **Descrizione**] | Descrive la funzione prevista del componente. (Queste informazioni vengono aggiunte dall’amministratore di Analytics, come descritto in [Aggiungi descrizioni dei componenti](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
| [!UICONTROL **Frequentemente utilizzato con**] | <p>Mostra i componenti più comunemente utilizzati con il componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Segmento e Intervallo date.</p><p>Questo elenco è basato sui dati degli ultimi 90 giorni. Vengono visualizzati solo i componenti a cui hai accesso. <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Simile a**] | <p>Mostra i componenti con etichette simili al componente che stai visualizzando.</p><p>Sono visualizzati fino a 5 componenti tra i 5 tipi di componenti principali: Metrica, Metrica calcolata, Dimension, Segmento e Intervallo date.</p><p>Vengono visualizzati solo i componenti a cui hai accesso.</p><p>Eventuali componenti duplicati nella suite di rapporti verranno visualizzati qui. Gli amministratori di Analytics devono identificare e rimuovere tutti i componenti duplicati, come descritto in [Monitorare lo stato del dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md). <!--Add info about how users with administrator access can control these after the feature is available. How?--></p> |
| [!UICONTROL **Tag**] | Mostra tutti i tag applicati al componente. Gli utenti con accesso amministratore possono aggiungere tag durante la modifica del componente. |
| [!UICONTROL **Tipo di componente**] | Elenca il tipo di componente, che si tratti di un Dimension, una metrica, un segmento o un intervallo di date. |
| [!UICONTROL **Creato da**] | Visualizza il nome dell’utente che ha creato il componente. |
| [!UICONTROL **Anteprima**] | Mostra un’anteprima del componente in Analysis Workspace. |
| [!UICONTROL **Data ultima modifica**] | Visualizza il giorno dell’ultima modifica apportata al componente. Questa sezione viene visualizzata quando si visualizzano Segmenti, metriche calcolate e intervalli di date. <!--for CJA, it is displayed for all components--> |

{style=&quot;table-layout:auto&quot;}

## Fase di rilascio Test limitati {#release-limited-testing}

>[!AVAILABILITY]
>
>La funzionalità descritta in questo articolo si trova nella fase di testing limitato della versione e potrebbe non essere ancora disponibile nel tuo ambiente. Questa nota verrà rimossa quando la funzionalità è generalmente disponibile. Per informazioni sul processo di rilascio di Analytics, vedi [Versioni delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

## Sezione Test limitati della fase di rilascio {#release-limited-testing-section}

>[!AVAILABILITY]
>
>La funzionalità descritta in questa sezione si trova nella fase di testing limitata della versione e potrebbe non essere ancora disponibile nel tuo ambiente. Questa nota verrà rimossa quando la funzionalità è generalmente disponibile. Per informazioni sul processo di rilascio di Analytics, vedi [Versioni delle funzioni di Adobe Analytics](/help/release-notes/releases.md).

