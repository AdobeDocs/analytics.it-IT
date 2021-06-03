---
description: Elenco delle limitazioni note in Adobe Analysis Workspace e dei relativi componenti
title: Limitazioni note in Analysis Workspace
feature: Concetti di base di Workspace
role: Business Practitioner, Administrator
exl-id: 520e970b-1387-4f70-985b-bfe397f4a21b
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 98%

---

# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Create metric from selection (Crea metrica da selezione) è disabilitata quando i segmenti sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).
* [!UICONTROL Contribution Analysis] può essere eseguita con granularità [!UICONTROL daily] _esclusivamente_. Non può essere eseguita con dati [!UICONTROL hourly], [!UICONTROL weekly], ecc.

## Visualizzazioni

* Le visualizzazioni che sfruttano la segmentazione, come [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort] e [!UICONTROL Histogram], non possono accettare metriche calcolate come input.
* [!UICONTROL Flow]: dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page], non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort]: i valori non interi non possono essere utilizzati come criteri di coorte.

## Pannelli

* Confronto segmenti: il segmento [!UICONTROL Everyone Else] non viene creato se viene utilizzato un modello di segmento nella zona di rilascio iniziale.

## Componenti > Segmenti

* Alcune metriche e dimensioni non sono segmentabili, come [!UICONTROL Occurrences], [!UICONTROL Unique Visitors], ecc.
* I segmenti ad hoc creati nell’[area di rilascio del pannello](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/panels.html?lang=it) non vengono visualizzati nella barra a sinistra di Workspace o nel Gestore dei componenti del segmento, a meno che non vengano resi pubblici. Per rendere pubblico un segmento occorre modificarlo e selezionare **[!UICONTROL Make this segment public]**.

## Componenti > Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi “Visualizzazioni” sopra.
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution], poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > Segments], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address].

## Componenti > Intervallo date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month], ecc.

## Componenti > Suite di rapporti virtuali

* Quando l’elaborazione dei tempi di report è abilitata, alcuni componenti non sono supportati. Per un elenco completo, vedi [Elaborazione dei tempi di report](/help/components/vrs/vrs-report-time-processing.md).

## Componenti > Tutti i componenti > Impostazioni dei rapporti

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding] e [!UICONTROL CSV Separator Character].

## Attribution IQ

* Un sottoinsieme di metriche non è supportato in [!UICONTROL Attribution IQ]. Per un elenco completo, vedi le [domande frequenti relative ad Attribution IQ](../attribution/faq.md).
