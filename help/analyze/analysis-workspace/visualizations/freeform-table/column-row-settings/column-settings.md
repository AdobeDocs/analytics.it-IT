---
description: Le impostazioni colonna consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.
title: Impostazioni colonna
uuid: 151d66da-04f7-4d0f-985c-4fdd92bc1308
feature: Freeform Tables
role: User, Admin
exl-id: 82034838-b015-4ca2-adb6-736f20a478d8
source-git-commit: 984406d00e5a5ae966fff60ec9fcfcb000958696
workflow-type: tm+mt
source-wordcount: '835'
ht-degree: 79%

---

# [!UICONTROL Column Settings]

Le [!UICONTROL Column Settings] consentono di configurare la formattazione delle colonne, che può essere parzialmente condizionale.

## Modificare [!UICONTROL Column Settings] {#edit-column-settings}

È possibile modificare le impostazioni delle colonne per una singola colonna o per più colonne contemporaneamente.

1. In Analysis Workspace, trascina una tabella a forma libera nel progetto.

1. (Condizionale) Per modificare più colonne contemporaneamente, seleziona ciascuna colonna da modificare tenendo premuto il tasto Maiusc.

1. Passa il puntatore del mouse sulla colonna da modificare, quindi seleziona l’icona a forma di ingranaggio.

   Se hai selezionato più colonne, fai clic sull’icona a forma di ingranaggio per una delle colonne selezionate. Tutte le modifiche apportate vengono applicate a tutte le colonne selezionate.

   ![](assets/column_settings.png)

1. Continua con [Impostazioni colonna](#column-settings).

## Impostazioni colonna

È possibile aggiornare le seguenti impostazioni di colonna per le singole tabelle in Analysis Workspace, come descritto in [Modifica impostazioni colonna](#edit-uicontrol-column-settings).

Alcune di queste impostazioni possono essere gestite anche per tutti i nuovi progetti creati in Analysis Workspace, come descritto in [Preferenze utente](/help/analyze/analysis-workspace/user-preferences.md)

| Elemento | Descrizione |
| --- | --- |
| **Celle totali** |  |
| Mostra totali | Questo totale è in genere uguale o un sottoinsieme del [!UICONTROL Grand Total] (Totale complessivo). Riflette eventuali filtri applicati alla tabella a forma libera, inclusa l’opzione [!UICONTROL Include None] (Includi nessuna). |
| Mostra totale complessivo | Questo totale rappresenta tutti gli hit che sono stati raccolti, talvolta denominati “totale suite di rapporti”. Quando un segmento viene applicato a livello di pannello o all’interno della tabella a forma libera, questo totale si regola per riflettere tutti gli hit che corrispondono ai criteri del segmento. Il totale complessivo non è supportato per tabelle o raggruppamenti con [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md). |
| **Celle della tabella** |   |
| Numero | Determina se mostrare/nascondere il valore numerico di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore numerico corrisponde al numero di visualizzazioni di pagina per l’elemento riga. |
| Percentuale | Determina se mostrare o nascondere il valore percentuale di una metrica nella cella. Ad esempio, se la metrica è Visualizzazioni di pagina, il valore percentuale corrisponde al numero di visualizzazioni di pagina per l’elemento riga, diviso per il totale di visualizzazioni di pagina per la colonna.  Nota: per garantire una maggiore precisione, è possibile visualizzare percentuali superiori al 100%. Inoltre, abbiamo spostato il limite superiore al 1000% per assicurare che le colonne possano crescere anche in larghezza. |
| Anomalie | Determina se eseguire il rilevamento delle anomalie sui valori di questa colonna. Per ulteriori informazioni, consulta la sezione [Visualizzare le anomalie in Analysis Workspace](/help/analyze/analysis-workspace/c-anomaly-detection/view-anomalies.md). |
| Testo a capo nelle intestazioni | Consente di mandare automaticamente a capo il testo delle intestazioni nelle tabelle a forma libera, per agevolare la lettura delle intestazioni e la condivisione delle tabelle. Questa opzione è utile per la creazione di file PDF e per le metriche con nomi lunghi. È attivata per impostazione predefinita. |
| Interpret zero as no value (Interpreta zero come nessun valore) | Per le celle con valore 0, determina se visualizzare 0 oppure la cella vuota. Questa funzione è particolarmente utile se si esaminano i dati quotidianamente e il mese in corso non è ancora terminato.  Invece di visualizzare valori 0 per le date future, è possibile sostituirli con delle celle vuote. Anche i grafici si adeguano a questa impostazione (ossia, se è stata selezionata, non visualizzano linee o barre con valori 0). |
| Informazioni di base | Determina se mostrare o nascondere tutta la formattazione della cella, inclusi il grafico a barre e la formattazione condizionale. |
| Grafico a barre | Visualizza un grafico a barre orizzontale che rappresenta il valore della cella rispetto al totale della colonna. |
| Formattazione condizionale | Consulta la sezione successiva. |
| Table Cell Preview (Anteprima celle tabella) | Mostra un’anteprima di ciascuna cella con le opzioni di formattazione attualmente selezionate attive. |

## Formattazione condizionale {#conditional-formatting}

La formattazione condizionale applica la formattazione ai limiti superiori e inferiori e ai punti intermedi definiti dall’utente. L’applicazione della formattazione condizionale (ad esempio, i colori) nelle tabelle a forma libera è abilitata automaticamente anche nelle suddivisioni, a meno che non venga selezionata l’opzione per limiti personalizzati.

![](assets/conditional-formatting.png)

| Elemento | Descrizione |
| --- | --- |
| Formattazione condizionale | Applica alle celle un set di colori preconfigurato scelto. A seconda delle 4 combinazioni di colori disponibili selezionate, i diversi colori vengono assegnati a valori alti, valori intermedi e valori bassi. <br> La sostituzione di una dimensione nella tabella ridefinisce i limiti della formattazione condizionale. La sostituzione di un dato ricalcola i limiti per la colonna (dove il dato si trova sull’asse X e la dimensione sull’asse Y). |
| Use Percent Limits (Usa limiti percentuali) | Modifica l’intervallo di limiti in modo che sia basato su percentuali anziché su valori assoluti. Funziona sia per metriche basate unicamente sulle percentuali (come Bounce Rate, o frequenza di rimbalzo), sia per quelle basate su conteggio e percentuale (come Visualizzazioni di pagina). |
| Generazione automatica | Calcola automaticamente i limiti superiori/medi/inferiori in base ai dati. Il limite superiore corrisponde al valore massimo nella colonna. Il limite inferiore corrisponde a quello minimo e il punto intermedio è la media fra il limite superiore e quello inferiore. |
| Personalizzato | Assegna manualmente i limiti superiori/medi/inferiori. Ciò offre la flessibilità di poter determinare quando il valore di una colonna diventa buono, medio o scarso. |
| Tavolozza con formattazione condizionale | Scegli quale delle 4 combinazioni di colori disponibili utilizzare per la formattazione condizionale. |

## Usa modello di attribuzione non predefinito {#attribution}

Analysis Workspace supporta l’[attribuzione](/help/analyze/analysis-workspace/attribution/overview.md) per quasi tutte le metriche.

1. Fai clic sull’icona delle impostazioni (a forma di ingranaggio) nella colonna di una tabella a forma libera.

   ![Casella di controllo di attribuzione](assets/attribution-checkbox.png)

1. In **[!UICONTROL Data Settings]**, spunta **[!UICONTROL Use non-default attribution model]**. Per ulteriori informazioni sui diversi modelli di attribuzione, consulta [Modelli di attribuzione](/help/analyze/analysis-workspace/attribution/models.md).

   ![Selezione del modello di attribuzione](assets/attribution-select.png)

>[!MORELIKETHIS]
>
>* [Gestione delle origini dati](/help/analyze/analysis-workspace/visualizations/t-sync-visualization.md)

## Colonne dinamiche

Ecco un video su come utilizzare le colonne dinamiche in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/23138/?quality=12)
