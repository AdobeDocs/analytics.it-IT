---
description: nulle
seo-description: nulle
seo-title: Limitazioni dell’area di lavoro, limitazioni note in Analysis Workspace
title: Limitazioni note in Analysis Workspace
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Limitazioni note in Analysis Workspace

Elenco delle limitazioni note in Analysis Workspace e dei relativi componenti:

## Tabelle

* Non è possibile aggiungere colonne di confronto delle date quando intervalli di date o metriche sono utilizzate come righe di una tabella.
* La funzione Crea metrica dalla selezione è disabilitata quando i segmenti sono utilizzati come righe di una tabella. Inoltre, la funzione Crea metrica dalla selezione non deve essere applicata alle colonne allineate alla data.
* La formattazione condizionale per le righe di suddivisione non può utilizzare intervalli personalizzati.
* Le righe totali della tabella non possono essere con tendenze quando si applica il calcolo dei totali sommando l'impostazione dei valori delle righe (generalmente utilizzato con gli elementi delle righe statiche).
* [!UICONTROL Contribution Analysis] può essere eseguito [!UICONTROL daily] solo _alla_ granularità. Non può essere eseguito con dati [!UICONTROL hourly], [!UICONTROL weekly]ecc.

## Visualizzazioni

* Le visualizzazioni che sfruttano la segmentazione, come [!UICONTROL Fallout], [!UICONTROL Flow], [!UICONTROL Cohort]e [!UICONTROL Histogram], non possono accettare metriche calcolate come input.
* [!UICONTROL Flow]: Dimensioni di entrata/uscita, ad esempio Non [!UICONTROL Entry page]può essere utilizzato in Flusso.
* [!UICONTROL Cohort]: I non interi non possono essere utilizzati come criteri di coorte.

## Pannelli

* Confronto segmenti: Il [!UICONTROL Everyone Else] segmento non viene creato se viene utilizzato un modello di segmento nella zona di rilascio iniziale.

## Componenti &gt; Segmenti

* Alcune metriche e dimensioni non sono segmentabili, come [!UICONTROL Occurrences], [!UICONTROL Unique Visitors]ecc.
* Alcuni componenti e operatori non sono disponibili se un segmento viene creato da Workspace (anziché da [!UICONTROL Components > Segments]). Ad esempio, Indirizzo IP.

## Componenti &gt; Metriche calcolate

* Le metriche calcolate non possono essere utilizzate in alcune visualizzazioni. Vedi 'Visualizations' sopra.
* Le metriche calcolate non possono essere utilizzate nel [!UICONTROL Attribution] pannello, poiché le metriche calcolate possono includere modelli di attribuzione separati.
* Alcuni componenti e operatori non sono disponibili se viene creata una metrica calcolata da Workspace (anziché da [!UICONTROL Components > Segments]). Ad esempio, [!UICONTROL IP Address].

## Componenti &gt; Intervalli di date

* Gli intervalli di date personalizzati non supportano [!UICONTROL This day last year], [!UICONTROL This day last month]ecc.

## Componenti &gt; Suite di rapporti virtuali

* Quando l'elaborazione del tempo del rapporto è abilitata, alcuni componenti non sono supportati. Per un elenco completo, consultate [Elaborazione](/help/components/vrs/vrs-report-time-processing.md)dei tempi di rapporto.

## Componenti &gt; Impostazioni rapporto

* Alcune delle impostazioni sulla [!UICONTROL Report Settings] pagina non sono applicabili. Analysis Workspace utilizza solo le [!UICONTROL Language/Currency/Encoding] impostazioni in basso: [!UICONTROL Thousands separator], [!UICONTROL Scheduled Report Encoding], e [!UICONTROL CSV Separator Character].

## Attribution IQ

* Un sottoinsieme di metriche non è supportato in [!UICONTROL Attribution IQ]. Per un elenco completo, consultate le domande frequenti relative all’ [attribuzione](/help/analyze/analysis-workspace/attribution-iq/attribution-faq.md).