---
description: Le regole di elaborazione semplificano la raccolta dati e gestiscono il contenuto quando viene inviato al reporting.
seo-description: Le regole di elaborazione semplificano la raccolta dati e gestiscono il contenuto quando viene inviato al reporting.
seo-title: Panoramica sulle regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Panoramica sulle regole di elaborazione
topic: Strumenti di amministrazione
uuid: 6 b 4 ee 7 c 9-2 b 86-47 a 6-b 64 c-c 8 d 644 fff 67 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica sulle regole di elaborazione

Le regole di elaborazione semplificano la raccolta dati e gestiscono il contenuto quando viene inviato al reporting. Le regole di elaborazione semplificano l'interazione con i gruppi IT e gli sviluppatori Web fornendo un'interfaccia:

* Impostare un evento nella pagina Panoramica del prodotto
* Compilare una campagna con un parametro di stringa query
* Concatenazione di categoria e nome pagina in un prop per un rapporto più semplice
* Copiare una evar in un prop per visualizzare i percorsi
* Pulizia delle sezioni con errore ortografico
* Estrarre termini di ricerca interni o un ID campagna dalla stringa query in una evar

>[!VIDEO](https://tv.adobe.com/embed/1181/16506/)

*Guarda la panoramica e la formazione sulle regole di elaborazione dal Summit Adobe per scoprire perché utilizzare le regole di elaborazione.*

## Get Authorized to Use Processing Rules {#section_8A4846688050453784DAE4D89355169A}

Prima del 20 aprile 2017, per usare le regole di elaborazione tutti gli utenti (anche gli amministratori) dovevano superare un esame e ottenere l'autorizzazione dell'assistenza clienti Adobe.

Now, administrators have rights to use processing rules **by default**. L'esame non è più necessario. Gli amministratori possono concedere questo diritto anche ai non amministratori utilizzando l'interfaccia Strumenti di amministrazione. effettuando le seguenti operazioni:

1. If you have not already done so, [create a group](../../../admin/user-management2/c-user-groups/groups.md) that includes only those non-admins that should have authorization to use processing rules.
1. [Aggiungete i non amministratori a tale gruppo](../../../admin/user-management2/c-user-management/t-add-user-to-group.md).
1. Then go to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL[group name]]** &gt; **[!UICONTROL Edit]** &gt; **[!UICONTROL Report Access]** &gt; **[!UICONTROL Report Suite Tools]** &gt; **[!UICONTROL Customize]** &gt; **[!UICONTROL Report Suite Management]**.
1. Check the box next to [!UICONTROL Processing Rules] and click **[!UICONTROL OK]**.

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Poiché le regole di elaborazione influenzano in modo permanente i dati di Analytics, consigliamo fortemente agli amministratori delle regole di elaborazione di ricevere la formazione di certificazione in Adobe Analytics e acquisire familiarità con tutte le fonti di dati per le suite di rapporti (siti Web standard, siti mobili, app mobili, API di inserimento dati e così via). La conoscenza delle variabili di dati di contesto e delle variabili standard popolate in diverse piattaforme contribuirà a impedire l'eliminazione accidentale o l'alterazione dei dati.

## Use Context Data to Simplify Data Collection {#section_09EEA03612D24C15839631AA9E9668D8}

Le variabili di dati di contesto sono un nuovo tipo di variabile disponibile solo per le regole di elaborazione. Per utilizzare variabili di dati di contesto, le coppie di dati chiave/valore vengono inviate dall'implementazione e le regole di elaborazione vengono utilizzate per acquisire tali valori nelle variabili di Analytics standard. In questo modo i programmatori possono capire esattamente quale prop e/o evar devono contenere il valore.

![](assets/evar-context-map.png)

See [Context Data Variables](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) in Implementation Help.

## Use Processing Rules to Transform Hit Data and Trigger Events {#section_8284E72E999244E091CD7FB1A22342B6}

Le regole di elaborazione possono monitorare i valori in arrivo per trasformare gli eventi più comuni e impostare gli eventi in base ai dati segnalati. I prop possono essere copiati in evar. I valori possono essere concatenati per i rapporti ed è possibile impostare eventi.

## Using Context Data Variables in Reporting {#section_BD098BC503024A0B8703596628071134}

Una volta definiti le variabili di dati di contesto nella tua implementazione, devono essere copiate in variabili quali evar da utilizzare nei rapporti.

For more information, go [here](../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) and [here](../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md#concept_359B4E165ED442938A8EB6A55A725682).
