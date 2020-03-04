---
description: Elenco delle limitazioni note in Adobe Analysis Workspace e dei relativi componenti
title: Limitazioni note in Analysis Workspace
translation-type: tm+mt
source-git-commit: 06d2e64fc72c911828f089de5c487117251e060e

---


# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando si utilizzano intervalli di date o metriche di date nelle righe di una tabella.
* La funzione Create metric from selection (Crea metrica da selezione) è disabilitata quando i segmenti sono utilizzati come righe di una tabella. Inoltre, la funzione Create metric from selection (Crea metrica da selezione) non deve essere applicata a colonne allineate su data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe dei totali della tabella non possono includere tendenze quando si applica l’impostazione di calcolo dei totali sommando i valori delle righe (generalmente utilizzato per righe con elementi statici).
* [!UICONTROL Contribution Analysis] (Analisi dei contributi) può essere eseguita con granularità [!UICONTROL daily] _esclusivamente_. Non può essere eseguita con dati [!UICONTROL hourly] (orari), [!UICONTROL weekly] (settimanali), ecc.

## Visualizzazioni

* Le visualizzazioni che sfruttano la segmentazione, come [!UICONTROL Fallout] (Abbandono), [!UICONTROL Flow] (Flusso), [!UICONTROL Cohort] (Coorte) e [!UICONTROL Histogram] (Istogramma), non possono accettare metriche calcolate come input.
* [!UICONTROL Flow] (Flusso): dimensioni di entrata/uscita, ad esempio [!UICONTROL Entry page] (pagina di entrata), non possono essere utilizzate in Flusso.
* [!UICONTROL Cohort] (Coorte): i valori non interi non possono essere utilizzati come criteri di coorte.

## Pannelli

* Confronto segmenti: il segmento [!UICONTROL Everyone Else] (Tutti) non viene creato se viene utilizzato un modello di segmento nella zona di rilascio iniziale.

## Componenti > Segmenti

* Alcune metriche e dimensioni non sono segmentabili, come [!UICONTROL Occurrences] (Occorrenze), [!UICONTROL Unique Visitors] (Visitatori unici), ecc.
* Alcuni componenti e operatori non sono disponibili se un segmento viene creato da Workspace (anziché da [!UICONTROL Components > Segments], ovvero Componenti > Segmenti). Ad esempio, Indirizzo IP.

## Componenti > Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi “Visualizzazioni” sopra.
* Le metriche calcolate non possono essere utilizzate nel pannello [!UICONTROL Attribution] (Attribuzione), poiché possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se una metrica calcolata viene creata da Workspace (anziché da [!UICONTROL Components > Segments], ovvero Componenti > Segmenti). Ad esempio, [!UICONTROL IP Address] (Indirizzo IP).

## Componenti > Intervallo date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year] (Questo giorno l’anno scorso), [!UICONTROL This day last month] (Questo giorno il mese scorso), ecc.

## Componenti > Suite di rapporti virtuali

* Quando l’elaborazione dei tempi di report è abilitata, alcuni componenti non sono supportati. Per un elenco completo, vedi [Elaborazione dei tempi di report](/help/components/vrs/vrs-report-time-processing.md).

## Componenti > Impostazioni report

* Alcune delle impostazioni sulla pagina [!UICONTROL Report Settings] (Impostazioni report) non sono applicabili. Analysis Workspace utilizza solo le impostazioni [!UICONTROL Language/Currency/Encoding] (Lingua/Valuta/Codifica) in basso:[!UICONTROL Thousands separator] (Separatore delle migliaia), [!UICONTROL Scheduled Report Encoding] (Codifica rapporti pianificati) e [!UICONTROL CSV Separator Character] (Separatore CSV).

## Attribution IQ

* Un sottoinsieme di metriche non è supportato in [!UICONTROL Attribution IQ]. Per un elenco completo, vedi le [domande frequenti relative ad Attribution IQ](c-panels/attribution/attribution-faq.md).
