---
description: I pannelli sono raccolte di tabelle e visualizzazioni.
title: Panoramica dei pannelli
feature: Pannelli
role: Business Practitioner, Administrator
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '981'
ht-degree: 100%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da un [pannello vuoto](blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi. In Analysis Workspace sono disponibili i seguenti tipi di pannello:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](blank-panel.md) | Per iniziare a eseguire analisi, scegli tra i pannelli e le visualizzazioni disponibili. |
| [Pannello Quick Insights](quickinsight.md) | Crea una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |
| [Pannello Analytics for Target](a4t-panel.md) | Analizza le attività ed esperienze Target in Analysis Workspace. |
| [Pannello Attribution](attribution.md) | Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Pannello Freeform](freeform-panel.md) | Esegui confronti illimitati e suddivisioni, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |
| [Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Pannello Segment Comparison](c-segment-comparison/segment-comparison.md) | Confronta rapidamente due segmenti su tutti i punti dati per trovare automaticamente differenze rilevanti. |

![](assets/panel-overview.png)

I pannelli [!UICONTROL Quick Insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Analytics for Target], [!UICONTROL Attribution IQ], [!UICONTROL Media Concurrent Viewers] e [!UICONTROL Segment Comparison] si prestano ad analisi più avanzate. Nei progetti è disponibile un pulsante `"+"` che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare come predefinito il [pannello vuoto](/help/analyze/analysis-workspace/c-panels/blank-panel.md).

## Suite di rapporti {#report-suite}

Le tabelle e le visualizzazioni all’interno di un pannello derivano i dati dalla [!UICONTROL report suite] selezionata in alto a destra nel pannello. La suite di rapporti determina anche i componenti disponibili nella barra a sinistra. All’interno di un progetto, puoi utilizzare una o [più suite di rapporti](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) a seconda dei casi di utilizzo dell’analisi. Per applicare una singola suite di rapporti a tutti i pannelli di un progetto, **fai clic con il pulsante destro del mouse sull’intestazione del pannello e scegli Applica suite di rapporti a tutti i pannelli**.

L’elenco delle suite di rapporti è ordinato in base alla rilevanza, che Adobe definisce in base a quanto recentemente e con quale frequenza l’utente corrente ha utilizzato la suite, e alla frequenza con cui questa viene utilizzata all’interno dell’organizzazione.

![](assets/panel-report-suite.png)

## Calendario {#calendar}

Il calendario del pannello controlla l’intervallo di reporting per tabelle e visualizzazioni all’interno di un pannello.

Nota: se un componente di intervallo date (viola) viene utilizzato all’interno di una tabella, di una visualizzazione o di una zona di rilascio di un pannello, questo sovrascriverà il calendario del pannello.

![](assets/panel-calendar.png)

## Zona di rilascio {#dropzone}

La zona di rilascio del pannello consente di applicare segmenti e filtri a discesa a tutte le tabelle e visualizzazioni di un pannello. Puoi applicare uno o più filtri a un pannello. Per modificare il titolo sopra ogni filtro, fai clic sull’icona della matita (Modifica); per rimuoverlo, fai clic con il pulsante destro del mouse.

### Filtri dei segmenti

Per iniziare a filtrare il pannello., trascina un segmento dalla barra a sinistra fino alla zona di rilascio del pannello.

![](assets/segment-filter.png)

### Filtri di segmenti ad hoc

Puoi anche trascinare componenti diversi da segmenti direttamente nella zona di rilascio, per creare segmenti ad hoc in modo più rapido e senza dover passare al Generatore di segmenti. I segmenti creati in questo modo vengono automaticamente definiti come segmenti a livello di hit. Puoi modificarli come di consueto facendo clic sull’icona delle informazioni (i) accanto al segmento, quindi sull’icona Modifica a forma di matita per accedere al Generatore di segmenti.

I segmenti ad hoc sono locali per il progetto e non verranno visualizzati nella barra a sinistra, a meno che non li rendi pubblici.

![](assets/adhoc-segment-filter.png)

### Filtri a discesa {#dropdown-filter}

Oltre ai filtri dei segmenti, i filtri a discesa consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un filtro a discesa per i tipi di dispositivi mobili, in modo da segmentare il pannello per Tablet, Telefono o Desktop.

I filtri a discesa possono essere utilizzati per consolidare più progetti in un progetto unico. Ad esempio, se hai creato più versioni dello stesso progetto, assegnando a ciascuna un segmento Paese diverso, puoi consolidarle tutte in un unico progetto e aggiungere un filtro a discesa Paese.

![](assets/dropdown-filter-intro.png)

Per creare un filtro a discesa:

1. Per creare un filtro a discesa utilizzando [!UICONTROL Dimension items], ad esempio valori della dimensione [!UICONTROL Marketing Channel], fai clic sull’icona a forma di freccia verso destra accanto alla dimensione nella barra a sinistra. Verranno esposti tutti gli elementi disponibili. Seleziona uno o più elementi componenti nella barra a sinistra, **tieni premuto il tasto Maiusc** e trascinali nella zona di rilascio del pannello. I componenti diventano un elenco a discesa, anziché un segmento.
1. Per creare un filtro a discesa utilizzando un altro componente, ad esempio metriche, segmenti o intervalli di date, selezionalo da un tipo di componente nella barra a sinistra, **tieni premuto il tasto Maiusc** e rilascialo nella zona di rilascio del pannello.
1. Per cambiare i dati visualizzati nel pannello, seleziona una delle opzioni dal menu a discesa. Puoi anche scegliere di non filtrare nessuno dei dati del pannello, selezionando **[!UICONTROL No filter]**.

![](assets/create-dropdown.png)

Per ulteriori informazioni su come aggiungere filtri a discesa a un progetto, [guarda questo video](https://docs.adobe.com/content/help/it/analytics-learn/tutorials/analysis-workspace/using-panels/using-panels-to-organize-your-analysis-workspace-projects.html).

## Menu di scelta rapida {#right-click}

Ulteriori funzionalità per un pannello sono disponibili nel menu di scelta rapida che compare quandi fai clic con il pulsante destro del mouse sull’intestazione del pannello.

![](assets/right-click-menu.png)

Sono disponibili le seguenti impostazioni:

| Impostazione | Descrizione |
| --- | --- |
| Inserisci visualizzazione/pannello copiato | Consente di incollare (inserire) l’elemento copiato altrove nello stesso progetto o in un altro progetto. |
| Copia pannello | Consente di fare clic con il pulsante destro del mouse e copiare un pannello, in modo da poterlo inserire altrove nello stesso progetto o in un altro progetto. |
| Applica suite di rapporti a tutti i pannelli | Consente di applicare la suite di rapporti del pannello attivo a tutti i pannelli del progetto. |
| Duplica pannello | Crea una copia del pannello corrente, che potrai quindi modificare. |
| Comprimi/Espandi tutti i pannelli | Comprime ed espande tutti i pannelli del progetto. |
| Comprimi/Espandi tutte le visualizzazioni nel pannello | Comprime ed espande tutte le visualizzazioni nel pannello corrente. |
| Modifica descrizione | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| Ottieni collegamento pannello | Consente di indirizzare un utente a uno specifico pannello in un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello a cui è collegato. |
