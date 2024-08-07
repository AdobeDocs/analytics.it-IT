---
title: Cos’è l’analisi per coorte e come funziona?
description: Approfondisci i dati relativi al pubblico e suddividili in gruppi correlati con la funzione di analisi per coorte. Scopri l’analisi per coorte in Analysis Workspace.
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: fbb9c742ca169e727cffa9b8e5e93ba23ced0ebf
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 86%

---

# Informazioni sulla funzione [!UICONTROL Cohort Analysis] in Adobe Analytics

Una *`cohort`* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. L’[!UICONTROL Cohort Analysis] è utile, ad esempio, quando vuoi comprendere in che modo una coorte si relaziona con un marchio. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. Puoi trovare informazioni sull’[!UICONTROL Cohort Analysis] su Internet, ad esempio [Cohort Analysis 101](https://it.wikipedia.org/wiki/Analisi_di_coorte).

Dopo aver generato un rapporto sulla coorte, puoi curarne i componenti (dimensioni, metriche e segmenti specifici) e condividerlo con chiunque. Consulta [Cura e condivisione](/help/analyze/analysis-workspace/curate-share/curate.md).

Esempi di cosa è possibile fare con l’[!UICONTROL Cohort Analysis]:

* Lanciare campagne sviluppate per promuovere un’azione desiderata.
* Spostare il budget marketing nel momento giusto del ciclo di vita di un cliente.
* Riconoscere quando interrompere una versione di prova o un’offerta in modo da massimizzare il valore.
* Sviluppare idee per il test A/B in aree come prezzo, percorso di upgrade ecc.

L’[!UICONTROL Cohort Analysis] è disponibile per tutti i clienti Adobe Analytics con diritti di accesso ad [!UICONTROL Analysis Workspace].

Video sulle tabelle coorte in Analysis Workspace:

>[!VIDEO](https://video.tv.adobe.com/v/25965/?quality=12)

>[!IMPORTANT]
>
>[!UICONTROL Cohort Analysis] non supporta metriche non segmentabili (incluse le metriche calcolate), metriche non intere (come Revenue) o Occurrences.
>
>Solo le metriche utilizzabili nei segmenti possono essere utilizzate in [!UICONTROL Cohort Analysis] e possono essere incrementate solo di >1 alla volta.

## Capacità dell’analisi per coorte

Le seguenti funzionalità consentono un controllo accurato delle coorti che crei:

### [!UICONTROL Retention] Tabella

Un report della coorte [!UICONTROL Retention] restituisce i visitatori: ogni cella di dati mostra il numero e la percentuale di visitatori nella coorte che hanno eseguito un’azione in quel determinato periodo di tempo. Puoi includere fino a 3 metriche e 10 segmenti.

![](assets/retention-report.png)

Video sul calcolo della conservazione continua:

>[!VIDEO](https://video.tv.adobe.com/v/25962/?quality=12)

### [!UICONTROL Churn] Tabella

Una coorte [!UICONTROL Churn] è l’inverso di una tabella Retention e mostra i visitatori che non rientrano più o non sono mai rientrati nei criteri della coorte nel tempo. Puoi includere fino a 3 metriche e 10 segmenti.

![](assets/churn-report.png)

Video sull’analisi dell’abbandono:

>[!VIDEO](https://video.tv.adobe.com/v/25966/?quality=12)

### [!UICONTROL Rolling Calculation]

Consente di calcolare il livello di fidelizzazione o abbandono dei visitatori in base alla colonna precedente, non alla colonna Included.

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL Latency] Tabella

Misura il tempo trascorso prima e dopo il verificarsi dell’evento di inclusione. È un ottimo strumento di analisi pre/post. La colonna **[!UICONTROL Included]** è al centro della tabella ed è preceduta e seguita dai periodi di tempo precedenti e successivi all’evento di inclusione.

![](assets/cohort-latency.png)

### Coorte [!UICONTROL Custom Dimension]

Puoi creare le coorti in base a una dimensione selezionata anziché in base al tempo, che è l’impostazione predefinita. Puoi usare dimensioni quali [!UICONTROL marketing channel], [!UICONTROL campaign], [!UICONTROL product], [!UICONTROL page], [!UICONTROL region] o qualsiasi altra dimensione in Adobe Analytics per mostrare in che modo la fidelizzazione cambia in base a valori diversi di tali dimensioni.

![](assets/cohort-customizable-cohort-row.png)

Per istruzioni su come impostare ed eseguire un rapporto sulla coorte, vai a [Configurare un rapporto di analisi per coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md).
