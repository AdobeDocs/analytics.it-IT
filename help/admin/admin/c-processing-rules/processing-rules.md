---
description: Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto mentre viene inviato al reporting.
subtopic: Processing rules
title: Panoramica sulle regole di elaborazione
feature: Strumenti di amministrazione
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 6%

---

# Panoramica sulle regole di elaborazione

Le regole di elaborazione semplificano la raccolta dei dati e gestiscono il contenuto mentre viene inviato al reporting. Le regole di elaborazione consentono di semplificare l’interazione con i gruppi IT e gli sviluppatori Web fornendo un’interfaccia per:

* Impostare un evento nella pagina di panoramica del prodotto
* Popolare la campagna con un parametro di stringa query
* Concatenare il nome di una categoria e di una pagina in un prop per una generazione di rapporti più semplice
* Copia un eVar in un prop per visualizzare i percorsi
* Pulizia delle sezioni del sito errate
* Estrarre i termini di ricerca interni o un ID campagna dalla stringa di query in un eVar

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## Autorizzazioni delle regole di elaborazione {#section_8A4846688050453784DAE4D89355169A}

Per impostazione predefinita, gli amministratori dispongono dei diritti per utilizzare le regole di elaborazione **a1/>.** Gli amministratori possono concedere questo diritto anche ai non amministratori utilizzando l&#39;interfaccia Strumenti di amministrazione. Per le istruzioni del caso, consulta []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>Poiché le regole di elaborazione influiscono in modo permanente sui dati di Analytics, Adobe consiglia vivamente agli amministratori delle regole di elaborazione di ricevere un corso di formazione sulla certificazione in Adobe Analytics e di avere familiarità con tutte le fonti di dati per le suite di rapporti (siti web standard, siti mobili, app mobili, API di inserimento dati e così via). La conoscenza delle variabili di dati di contesto e delle variabili standard popolate in varie piattaforme aiuterà a prevenire l’eliminazione o l’alterazione accidentale dei dati.

## Utilizza i dati contestuali per semplificare la raccolta dei dati {#section_09EEA03612D24C15839631AA9E9668D8}

Le variabili di dati di contesto sono un tipo di variabile disponibile solo per le regole di elaborazione. Per utilizzare le variabili di dati di contesto, le coppie chiave/valore vengono inviate dall’implementazione e le regole di elaborazione vengono utilizzate per acquisire questi valori nelle variabili di Analytics standard. Questo consente ai programmatori di capire esattamente quale prop e/o eVar deve contenere quale valore.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Una volta impostato il codice, puoi impostare le regole di elaborazione per assegnare valori alle variabili. Ad esempio:

1. Mappa `author` su `eVar2`
2. Mappa `section` su `prop1` e `eVar3`
3. Se esistono `author` e `section`, impostare `event5`

Per ulteriori informazioni, consulta [contextData](/help/implement/vars/page-vars/contextdata.md) nella guida utente Implementa .

## Utilizzare le regole di elaborazione per trasformare i dati di hit e gli eventi di attivazione {#section_8284E72E999244E091CD7FB1A22342B6}

Le regole di elaborazione possono monitorare i valori in arrivo per trasformare gli errori di battitura comuni e impostare gli eventi in base ai dati segnalati. Le proprietà possono essere copiate in eVar. I valori possono essere concatenati per i rapporti e possono essere impostati eventi.

## Utilizzo delle variabili di dati di contesto nel reporting {#section_BD098BC503024A0B8703596628071134}

Una volta definite le variabili di dati di contesto nell’implementazione, queste devono essere copiate in variabili quali eVar da utilizzare nei rapporti.

Per ulteriori informazioni, consulta [Copiare una variabile di dati di contesto in un eVar](processing-rules-examples/processing-rules-copy-context-data.md) e [Impostare un evento utilizzando una variabile di dati di contesto](processing-rules-examples/processing-rules-copy-context-data-event.md) .
