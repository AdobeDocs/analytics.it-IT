---
description: Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting.
subtopic: Processing rules
title: Panoramica sulle regole di elaborazione
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 85%

---

# Panoramica sulle regole di elaborazione

Utilizza le regole di elaborazione per semplificare la raccolta dati e gestire i contenuti quando viene inviato al reporting. Le regole di elaborazione aiutano a semplificare l’interazione con i gruppi IT e gli sviluppatori Web fornendo un’interfaccia per:

* Impostare un evento nella pagina di panoramica del prodotto
* Popolare la campagna con un parametro di stringa query
* Concatenare il nome di una categoria e di una pagina in un prop per una generazione di rapporti più semplice
* Copiare un eVar in un prop per visualizzare i percorsi
* Pulire delle sezioni del sito errate
* Estrarre i termini di ricerca interni o un ID campagna dalla stringa di query in un eVar



>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Panoramica sulle regole di elaborazione](https://video.tv.adobe.com/v/26124/?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]


## Autorizzazioni delle regole di elaborazione {#section_8A4846688050453784DAE4D89355169A}

Ora gli amministratori dispongono delle autorizzazioni per utilizzare le regole di elaborazione **per impostazione predefinita**. Gli amministratori possono concedere questo diritto anche ai non amministratori utilizzando l’interfaccia Strumenti di amministrazione. Per le istruzioni del caso, consulta []

![Regole di elaborazione](assets/processing-rules.png)

## Utilizzare i dati contestuali per semplificare la raccolta dei dati {#section_09EEA03612D24C15839631AA9E9668D8}

Le variabili di dati di contesto sono un tipo di variabile disponibile solo per le regole di elaborazione. Per utilizzare le variabili di dati di contesto, le coppie chiave/valore vengono inviate dall’implementazione e le regole di elaborazione vengono utilizzate per acquisire questi valori nelle variabili di Analytics standard. Questo consente ai programmatori di capire esattamente quale prop e/o eVar deve contenere quale valore.

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

Una volta impostato il codice, puoi impostare le regole di elaborazione per assegnare valori alle variabili. Esempio:

1. Mappa `author` a `eVar2`
2. Mappa `section` a `prop1` e `eVar3`
3. Se `author` e `section` esiste, imposta `event5`

Consulta [contextData](/help/implement/vars/page-vars/contextdata.md) nella guida utente Implementa per ulteriori informazioni.

## Utilizzare le regole di elaborazione per trasformare i dati di hit e gli eventi di attivazione {#section_8284E72E999244E091CD7FB1A22342B6}

Le regole di elaborazione possono monitorare i valori in arrivo per trasformare gli errori di battitura comuni e impostare gli eventi in base ai dati segnalati. Le proprietà possono essere copiate in eVar. I valori possono essere concatenati per i rapporti e possono essere impostati eventi.

## Utilizzo delle variabili di dati di contesto nel reporting {#section_BD098BC503024A0B8703596628071134}

Una volta definite le variabili di dati di contesto nell’implementazione, queste devono essere copiate in variabili quali eVar da utilizzare nei rapporti.

Consulta [Copiare una variabile di dati di contesto in un eVar](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) e [Impostare un evento utilizzando una variabile di dati di contesto](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md) per ulteriori informazioni.

## Limitazioni note

**Utilizzo di carati (^) nelle regole di elaborazione.** Se si desidera utilizzare i carati nelle regole di elaborazione come delimitatori o per altri scopi, ogni singolo carato deve essere rappresentato da due carati. Ad esempio, rappresenta un singolo carato come ^^, un doppio carato come ^^^^, ecc.