---
description: Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto durante l'invio ai report.
seo-description: Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto durante l'invio ai report.
seo-title: Panoramica sulle regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Panoramica sulle regole di elaborazione
topic: Strumenti di amministrazione
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Panoramica sulle regole di elaborazione

Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto durante l'invio ai report. Le regole di elaborazione semplificano l'interazione con i gruppi IT e gli sviluppatori Web fornendo un'interfaccia per:

* Impostare un evento nella pagina della panoramica del prodotto
* Compilare una campagna con un parametro stringa di query
* Concatenate la categoria e il nome della pagina in una prop per una generazione di rapporti più semplice
* Copia di un'eVar in una prop per visualizzare i percorsi
* Pulizia delle sezioni di sito errate
* Estrarre i termini di ricerca interni o l'ID di una campagna dalla stringa di query in una eVar

>[!VIDEO](https://tv.adobe.com/embed/1181/16506/)

*Consulta la panoramica sulle regole di elaborazione e i corsi di formazione di Adobe Summit per scoprire perché devi usare le regole di elaborazione.*

## Get Authorized to Use Processing Rules {#section_8A4846688050453784DAE4D89355169A}

Prima del 20 aprile 2017, per usare le regole di elaborazione tutti gli utenti (anche gli amministratori) dovevano superare un esame e ottenere l'autorizzazione dell'assistenza clienti Adobe.

Ora gli amministratori dispongono delle autorizzazioni per utilizzare le regole di elaborazione **per impostazione predefinita**. L'esame non è più necessario. Gli amministratori possono concedere questo diritto anche ai non amministratori utilizzando l'interfaccia Strumenti di amministrazione. effettuando le seguenti operazioni:

1. Se non lo avete ancora fatto, [create un gruppo](../../../admin/user-management2/c-user-groups/groups.md) che includa solo i non amministratori che devono disporre dell'autorizzazione per utilizzare le regole di elaborazione.
1. [Aggiungete i non amministratori a tale gruppo](../../../admin/user-management2/c-user-management/t-add-user-to-group.md).
1. Quindi, andate a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL[nome]gruppo]** &gt; **[!UICONTROL Edit]** &gt; **[!UICONTROL Report Access]** **[!UICONTROL Report Suite Tools]** **[!UICONTROL Customize]** **[!UICONTROL Report Suite Management]**&gt; &gt; &gt; &gt; .
1. Selezionare la casella accanto a [!UICONTROL Processing Rules] e fare clic su **[!UICONTROL OK]**.

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Poiché le regole di elaborazione influiscono in modo permanente sui dati di Analytics, consigliamo vivamente agli amministratori delle regole di elaborazione di ricevere formazione sulla certificazione in Adobe Analytics, e di avere familiarità con tutte le origini di dati per le suite di rapporti (siti Web standard, siti mobili, app mobili, API di inserimento dati e così via). La conoscenza delle variabili di dati contestuali e delle variabili standard popolate in varie piattaforme contribuirà a prevenire l’eliminazione o l’alterazione accidentale dei dati.

## Utilizzare i dati contestuali per semplificare la raccolta dei dati {#section_09EEA03612D24C15839631AA9E9668D8}

Le variabili di dati di contesto sono un nuovo tipo di variabile disponibile solo per l'elaborazione delle regole. Per utilizzare le variabili di dati di contesto, le coppie di dati chiave/valore vengono inviate dall'implementazione e le regole di elaborazione vengono utilizzate per acquisire questi valori in variabili Analytics standard. Questo consente ai programmatori di capire esattamente quale prop e/o eVar deve contenere tale valore.

![](assets/evar-context-map.png)

Consulta Variabili [di dati di](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) contesto nella guida all'implementazione.

## Utilizzare le regole di elaborazione per trasformare gli eventi Hit e Triggers {#section_8284E72E999244E091CD7FB1A22342B6}

Le regole di elaborazione possono monitorare i valori in arrivo per trasformare gli errori di battitura comuni e impostare gli eventi in base ai dati segnalati. Le proprietà possono essere copiate nelle eVar. I valori possono essere concatenati per i rapporti e gli eventi possono essere impostati.

## Utilizzo delle variabili di dati contestuali nei rapporti {#section_BD098BC503024A0B8703596628071134}

Una volta definite le variabili di dati di contesto all'interno dell'implementazione, queste devono essere copiate in variabili quali eVar da utilizzare nei report.

Per maggiori informazioni, vai [qui](../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) e [qui](../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md#concept_359B4E165ED442938A8EB6A55A725682).
