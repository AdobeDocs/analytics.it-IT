---
description: Scopri come creare e configurare una tabella coorte ed eseguire un rapporto di analisi per coorte in Analysis Workspace.
keywords: Analysis Workspace
title: Configurare Una Tabella Coorte
feature: Visualizations
role: User, Admin
exl-id: 523e6f62-b428-454b-9460-6b06e96742c3
source-git-commit: bf8bc40e3ec325e8e70081955fb533eee66a1734
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 39%

---

# Configurare una tabella coorte

Per creare e configurare una [!UICONTROL Cohort table]:

1. Aggiungi una visualizzazione ![TextNumbered](/help/assets/icons/TextNumbered.svg) **[!UICONTROL Cohort table]**. Consulta [Aggiungere una visualizzazione a un pannello](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

1. Definisci **[!UICONTROL Inclusion Criteria]**, **[!UICONTROL Return Criteria]**, **[!UICONTROL Cohort Type]** e **[!UICONTROL Settings]** come definito nella tabella seguente.

   ![Configurare una tabella coorte](assets/cohort-configure.png)

   | Elemento | Descrizione |
   |--- |--- |
   | **[!UICONTROL Inclusion criteria]** | Puoi applicare fino a 10 filtri di inclusione e fino a 3 metriche di inclusione. La metrica specifica a quale coorte appartiene un utente. Ad esempio, se la metrica di inclusione è Ordini, nella coorte iniziale vengono inclusi solo gli utenti che hanno effettuato un ordine durante l’intervallo di tempo dell’analisi della coorte.<br>L’operatore predefinito tra più metriche è AND, ma è possibile cambiarlo in OR. Inoltre, è possibile aggiungere alle metriche un filtro numerico. Esempio: `Sessions >= 1`.</br> |
   | **[!UICONTROL Return criteria]** | Puoi applicare fino a 10 filtri di ritorno e fino a 3 metriche di ritorno. Questa metrica indica se l’utente è stato mantenuto (Retention, fidelizzazione) o meno (Churn, abbandono). Ad esempio, se la metrica di ritorno è Visualizzazioni video, vengono considerati fidelizzati solo gli utenti che hanno visualizzato un video durante i periodi successivi (dopo il periodo in cui sono stati aggiunti a una coorte). Un’altra metrica che quantifica la conservazione è Sessioni. |
   | **[!UICONTROL Granularity]** | Granularità temporale per Day, Week, Month, Quarter, o Year (Giorno, Settimana, Mese, Trimestre, Anno). |
   | **[!UICONTROL Type]** | **[!UICONTROL Retention]** (impostazione predefinita): una coorte di **[!UICONTROL Retention]** misura se le coorti delle persone ritornano a visitare la proprietà digitale nel tempo. Una coorte di fidelizzazione è la coorte standard e indica il comportamento degli utenti in merito a ritorno e ripetizione. Un colore verde indica una coorte [!UICONTROL Retention] nella tabella.<br>**[!UICONTROL Churn]**: una coorte **[!UICONTROL Churn]**(nota anche come perdita o attrito) misura il modo in cui le coorti di persone abbandonano la proprietà digitale nel tempo. Churn è l&#39;opposto di Retention: `Churn = 1 - Retention`. [!UICONTROL Churn] è utile per misurare la fedeltà e le opportunità, in quanto mostra con quale frequenza i clienti non ritornano. Utilizzando la coorte di abbandono puoi analizzare e individuare specifiche aree su cui concentrarti, ovvero i filtri di coorte che richiedono maggiore attenzione. Un colore rosso indica una coorte [!UICONTROL Churn] nella tabella (simile all&#39;abbandono nella visualizzazione **[!UICONTROL Flow]**).</br> |
   | **[!UICONTROL Settings]** | **[!UICONTROL Rolling calculation]**: consente di calcolare il livello di fidelizzazione o abbandono in base alla colonna precedente, non alla colonna Included (che è l’impostazione predefinita). [!UICONTROL Rolling Calculation] cambia il metodo di calcolo per i periodi di “ritorno”. Con il calcolo normale vengono trovati gli utenti che rispondono ai criteri di ritorno e che rientravano nel periodo di inclusione. Indipendentemente dal fatto che rientrassero o meno nella coorte del periodo precedente. Il [!UICONTROL Rolling Calculation], invece, individua gli utenti che rispondono ai criteri di “ritorno” e che rientravano nel periodo precedente. Il [!UICONTROL Rolling Calculation], quindi, filtra e incanala gli utenti che continuano a rispondere ai requisiti di “ritorno” per più periodi di tempo. I criteri [!UICONTROL Return] vengono applicati a ogni periodo precedente al periodo selezionato. </br><br>**[!UICONTROL Latency Table]**: [!UICONTROL Latency table] misura il tempo trascorso prima e dopo il verificarsi dell&#39;evento di inclusione. La [!UICONTROL Latency table] è utile per l’analisi pre/post. Ad esempio, in previsione del lancio di un prodotto o di una campagna, desideri tenere traccia del comportamento prima e dopo il lancio. [!UICONTROL Latency table] visualizza a confronto il comportamento prima e dopo il test per vedere l&#39;impatto diretto. Le celle di pre-inclusione in [!UICONTROL Latency table] calcolano gli utenti che soddisfano i criteri [!UICONTROL Inclusion] nel periodo di inclusione e quindi i criteri [!UICONTROL Return] nei periodi precedenti al periodo di inclusione. [!UICONTROL Latency table] e [!UICONTROL Custom dimension cohort] non possono essere utilizzati insieme.</br><br>**[!UICONTROL Custom dimension cohort]**: consente di creare coorti in base alla dimensione selezionata, anziché in base al tempo (impostazione predefinita). Molti clienti vogliono poter analizzare le coorti in base a fattori diversi dal tempo. Con la nuova funzione per coorti con dimensione personalizzata hai la flessibilità di creare le coorti in base alle dimensioni che rispondono alle tue esigenze. Puoi usare dimensioni quali canale di marketing, campagna, prodotto, pagina, regione, o qualsiasi altra dimensione per mostrare in che modo la fidelizzazione cambia in base a valori diversi di tali dimensioni. La definizione del filtro di coorte [!UICONTROL Custom Dimension] applica l’elemento dimensionale solo come parte del periodo di inclusione e non come parte della definizione di ritorno.</br><br>Dopo aver scelto l&#39;opzione [!UICONTROL Custom dimension cohort], puoi trascinare nella zona di rilascio la dimensione che ti interessa. L’aggiunta di dimensioni consente di confrontare elementi dimensionali simili nello stesso periodo di tempo. Ad esempio, puoi confrontare le prestazioni di città una accanto all’altra, prodotti, campagne, ecc. La tabella coorte restituisce i primi 14 elementi dimensionali. È tuttavia possibile utilizzare un filtro ![Filter](/help/assets/icons/Filter.svg) per visualizzare solo gli elementi dimensionali desiderati. Impossibile utilizzare [!UICONTROL Custom dimension cohort] con la funzionalità [!UICONTROL Latency table].</br> |

1. Fai clic su **[!UICONTROL Build]**.
1. Per riconfigurare [!UICONTROL Cohort table], selezionare ![Modifica](/help/assets/icons/Edit.svg).

1. (Facoltativo) Crea un segmento da una selezione.

   Selezionare una o più celle (contigue o non contigue), quindi fare clic con il pulsante destro del mouse > **[!UICONTROL Create Segment From Selection]**.


1. Nel [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md), modifica ulteriormente il segmento, quindi fai clic su **[!UICONTROL Save]**.

   Il segmento salvato è disponibile per l’utilizzo nel pannello [!UICONTROL Segment] di [!UICONTROL Analysis Workspace].

## Impostazioni

È possibile definire impostazioni specifiche per [!UICONTROL Cohort table].

1. Selezionare ![Impostazioni](/help/assets/icons/Setting.svg) per regolare le impostazioni di [!UICONTROL Cohort table].

   | Impostazione | Descrizione |
   |---|---|
   | **Mostra solo percentuale** | Rimuove il valore numerico e visualizza solo la percentuale. |
   | **Arrotondare la percentuale al numero intero più vicino** | Arrotonda il valore percentuale al numero intero più vicino invece di mostrare il valore decimale. |
   | **Mostra riga percentuale media** | Inserisce una nuova riga nella parte superiore della tabella, quindi aggiunge la media dei valori all’interno di ogni colonna. |


>[!MORELIKETHIS]
>
>[Aggiungere una visualizzazione a un pannello](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>>[Impostazioni di visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>>[Menu di scelta rapida della visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>

