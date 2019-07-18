---
description: Crea una coorte ed esegui un rapporto di analisi per coorte in Analysis Workspace.
keywords: Analysis Workspace
seo-description: Crea una coorte ed esegui un rapporto di analisi per coorte in Analysis Workspace.
seo-title: Esecuzione di un rapporto di analisi per coorte
solution: Analytics
title: Esecuzione di un rapporto di analisi per coorte
topic: Reports & Analytics
uuid: 5574230 f -8 f 35-43 ea -88 d 6-cb 4960 ff 0 bf 4
translation-type: tm+mt
source-git-commit: be8d889e03479cfb1926e7a82112964635cd2545

---


# Configurare un rapporto di analisi per coorte

Crea una coorte ed esegui un rapporto di analisi per coorte in Analysis Workspace.

1. In Analysis Workspace, click the **[!UICONTROL Visualizations]** icon in the left rail and drag a **[!UICONTROL Cohort Table]** to the canvas.

   ![](assets/cohort-table.png)

1. Define the **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]**, and **[!UICONTROL Settings]** as defined in the table below.

| Elemento | Descrizione |
|--- |--- |
| **[!UICONTROL Inclusion Criteria]** | Puoi applicare fino a 10 segmenti di inclusione e fino a 3 metriche di inclusione. La metrica specifica cosa colloca un utente in una coorte. Ad esempio, se il dato di inclusione è Orders (Ordini), solo gli utenti che hanno effettuato un acquisto durante l’intervallo di tempo dell’analisi della coorte saranno inclusi nella coorte iniziale.<br>L’operatore predefinito tra più metriche è AND, ma è possibile cambiarlo in OR. Inoltre, è possibile aggiungere alle metriche un filtro numerico. Ad esempio: “Visite &gt;= 1”.</br> |
| **[!UICONTROL Return Criteria]** | Puoi applicare fino a 10 segmenti di ritorno e fino a 3 metriche di ritorno. Questa metrica indica se l’utente è stato mantenuto (Retention, fidelizzazione) o meno (Churn, abbandono). Ad esempio, se la metrica di ritorno è Visualizzazioni video, saranno considerati fidelizzati solo gli utenti che hanno visualizzato un video durante i periodi successivi (dopo il periodo in cui sono stati aggiunti a una coorte). Un altro dato che quantifica la fidelizzazione è Visits (Visite). |
| **[!UICONTROL Granularity]** | Granularità temporale per Day, Week, Month, Quarter, o Year (Giorno, Settimana, Mese, Trimestre, Anno). |
| **[!UICONTROL Type]** | **[!UICONTROL Retention]**(Fidelizzazione),impostazione predefinita: una coorte di fidelizzazione misura se le coorti dei visitatori ritornano a visitare la proprietà digitale nel tempo. Si tratta della coorte standard che abbiamo sempre usato e indica il comportamento degli utenti in merito a ritorno e visite ripetute. Nella tabella, le coorti Retention (Fidelizzazione) sono indicate in verde.<br>**[!UICONTROL Churn]**: Una coorte churn (detta anche "attrito" o "abbandono") misura in che modo le coorti dei visitatori abbandonano la tua proprietà nel tempo. Abbandono = 1 - Fidelizzazione. La coorte di abbandono è utile per misurare il successo e le opportunità, in quanto mostra con quale frequenza i clienti non ritornano. Potete usare churn per analizzare e identificare le aree di interesse: quali segmenti di coorte potrebbero usare. A Churn Cohort is indicated by the color red in the table (similar to fallout in our **[!UICONTROL Flow]** visualization).</br> |
| **[!UICONTROL Settings]** | **[!UICONTROL Rolling Calculation]** (Calcolo continuo): consente di calcolare il livello di fidelizzazione o abbandono in base alla colonna precedente, non alla colonna Included (Inclusione) che è l’impostazione predefinita. Rolling Calculation (Calcolo continuo) cambia il metodo di calcolo per i periodi di “ritorno”. Con il calcolo normale vengono trovati in modo indipendente gli utenti che rispondono ai criteri di “ritorno” e che rientrano nel periodo di inclusione, a prescindere dalla loro inclusione nella coorte per il periodo precedente. Il calcolo continuo, invece, individua gli utenti che rispondono ai criteri di “ritorno” e che rientravano nel periodo precedente. Il calcolo continuo, quindi, filtra e incanala gli utenti che continuano a rispondere ai requisiti di “ritorno” per più periodi di tempo. I criteri di ritorno vengono applicati a ogni periodo precedente al periodo selezionato. </br><br>**[!UICONTROL Latency Table]** (Tabella di latenza): misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. La latenza è utile per l’analisi pre/post. Ad esempio, se in previsione del lancio di un prodotto o di una campagna si desidera tenere traccia del comportamento prima del lancio e ottenere le prestazioni successive al lancio, la tabella di latenza visualizza a confronto il comportamento prima e dopo il lancio, per vederne l’impatto diretto. Le celle di pre-inclusione nella tabella di latenza sono calcolate in base agli utenti che rispondono ai criteri di “inclusione” nel periodo di inclusione e quindi rispondono ai criteri di “ritorno” nei periodi precedenti al periodo di inclusione. Tieni presente che non è possibile usare insieme le tabelle di latenza e le coorti con dimensione personalizzata.</br><br>**[!UICONTROL Custom Dimension Cohort]**: Crea coorti in base alla dimensione selezionata, anziché alle coorti basate sul tempo (impostazione predefinita). Molti clienti vogliono poter analizzare le coorti in base a fattori diversi dal tempo. Con la nuova funzione per coorti con dimensione personalizzata hai la flessibilità di creare le coorti in base alle dimensioni che rispondono alle tue esigenze. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia, in base a valori diversi di tali dimensioni. La definizione del segmento Custom Cohort Dimension (Coorte con dimensione personalizzata) applica l’elemento dimensionale solo come parte del periodo di inclusione e non come parte della definizione di ritorno.</br><br>Dopo aver scelto l’opzione Custom Dimension Cohort (Coorte con dimensione personalizzata), puoi trascinare nella zona di rilascio la dimensione che ti interessa. Puoi quindi confrontare elementi con dimensione simile in uno stesso periodo di tempo. Ad esempio, puoi confrontare le prestazioni per diverse città, diversi prodotti, diverse campagne ecc. Vengono restituiti i primi 14 elementi per la dimensione in questione. Per visualizzare solo specifici elementi per la dimensione scelta, puoi anche usare un filtro, passando il cursore a destra della dimensione che hai trascinato. Una coorte con dimensione personalizzata non può essere usata con la funzione Tabella di latenza.</br> |

1. Adjust the **[!UICONTROL Cohort Table Settings]** by clicking the gear icon.

| Impostazione | Descrizione |
| Mostra solo percentuale | Rimuove il valore numerico e mostra solo la percentuale. |
| Percentuale arrotondata al valore intero più vicino | Arrotonda il valore percentuale al tutto più vicino, anziché mostrare il valore decimale. |
| Mostra riga media percentuale | Inserisce una nuova riga nella parte superiore della tabella, quindi aggiunge la media per i valori all'interno di ciascuna colonna. |

## Creare il rapporto Analisi per coorte

1. Fai clic su **[!UICONTROL Build]**.

   ![Risultato passaggio](assets/cohort-report.png)

   The report shows visitors who placed an order ( *`Included`* column), and who returned to your site in subsequent visits. La riduzione nelle visite nel tempo consente di individuare i problemi e di prendere delle contro misure.
1. (Facoltativo) Crea un segmento da una selezione.

   Select cells (contiguous or noncontiguous), then right-click &gt; **[!UICONTROL Create Segment From Selection]**.

1. In the [Segment Builder](https://marketing.adobe.com/resources/help/en_US/analytics/segment/?f=seg_build), further edit the segment, then click **[!UICONTROL Save]**.

   The saved segment is available for use in the [!UICONTROL Segment] panel in Analysis Workspace.
1. Rinomina e salva il progetto della coorte.
1. (Optional) [Curate and share](../../../../analyze/analysis-workspace/curate-share/curate.md#concept_4A9726927E7C44AFA260E2BB2721AFC6) the project components.

   >[!NOTE]
   >
   >Prima di curare è necessario salvare il progetto.

