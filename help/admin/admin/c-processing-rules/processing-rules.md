---
description: Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto durante l'invio ai report.
subtopic: Processing rules
title: Panoramica sulle regole di elaborazione
topic: Strumenti di amministrazione
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: 7f34aa3b5056c56516daea6144723a1751ef9051
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 6%

---


# Panoramica sulle regole di elaborazione

Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto durante l&#39;invio ai report. Le regole di elaborazione semplificano l&#39;interazione con i gruppi IT e gli sviluppatori Web fornendo un&#39;interfaccia per:

* Impostare un evento nella pagina della panoramica del prodotto
* Compilare una campagna con un parametro stringa di query
* Concatenate la categoria e il nome della pagina in una prop per una generazione di rapporti più semplice
* Copiare un eVar  in una prop per vedere i percorsi
* Pulizia delle sezioni di sito errate
* Estrarre i termini di ricerca interni o un ID campagna dalla stringa di query in un eVar 

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## Autorizzazioni delle regole di elaborazione {#section_8A4846688050453784DAE4D89355169A}

Gli amministratori hanno i diritti per utilizzare le regole di elaborazione **per impostazione predefinita**. Gli amministratori possono concedere questo diritto anche ai non amministratori utilizzando l&#39;interfaccia Strumenti di amministrazione. Per le istruzioni del caso, consulta []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Poiché le regole di elaborazione influiscono in modo permanente sui dati di Analytics,  Adobe consiglia vivamente agli amministratori delle regole di elaborazione di ricevere formazione sulla certificazione in  Adobe Analytics e di avere familiarità con tutte le origini di dati per le suite di rapporti (siti Web standard, siti mobili, app mobili, API di inserimento dati e così via). La conoscenza delle variabili di dati contestuali e delle variabili standard popolate in varie piattaforme contribuirà a prevenire l’eliminazione o l’alterazione accidentale dei dati.

## Utilizza i dati contestuali per semplificare la raccolta di dati {#section_09EEA03612D24C15839631AA9E9668D8}

Le variabili di dati di contesto sono un tipo di variabile disponibile solo per le regole di elaborazione. Per utilizzare le variabili di dati di contesto, le coppie di dati chiave/valore vengono inviate dall&#39;implementazione e le regole di elaborazione vengono utilizzate per acquisire questi valori in variabili Analytics standard. Questo consente ai programmatori di capire esattamente quale prop e/o  eVar deve contenere tale valore.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Una volta impostato il codice, è possibile impostare le regole di elaborazione per assegnare valori alle variabili. Ad esempio:

1. Mappa `author` su `eVar2`
2. Mappa `section` su `prop1` e `eVar3`
3. Se esistono `author` e `section`, impostare `event5`

Per ulteriori informazioni, vedere [contextData](/help/implement/vars/page-vars/contextdata.md) nella guida Implementa utente.

## Utilizzare le regole di elaborazione per trasformare i dati di hit e gli eventi di attivazione {#section_8284E72E999244E091CD7FB1A22342B6}

Le regole di elaborazione possono monitorare i valori in arrivo per trasformare gli errori di battitura comuni e impostare gli eventi in base ai dati segnalati. Le proprietà possono essere copiate nelle eVar. I valori possono essere concatenati per i rapporti e gli eventi possono essere impostati.

## Utilizzo delle variabili di dati contestuali nel reporting {#section_BD098BC503024A0B8703596628071134}

Una volta definite le variabili di dati di contesto all&#39;interno dell&#39;implementazione, queste devono essere copiate in variabili quali eVar da utilizzare nei report.

Per ulteriori informazioni, vedere [Copiare una variabile di dati di contesto in un eVar ](processing-rules-examples/processing-rules-copy-context-data.md) e [Impostare un evento utilizzando una variabile di dati di contesto](processing-rules-examples/processing-rules-copy-context-data-event.md).
