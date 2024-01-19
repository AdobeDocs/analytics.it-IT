---
description: Le metriche calcolate e avanzate calcolate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.
keywords: Metriche calcolate;Metriche derivate;Metriche calcolate avanzate
title: Metriche calcolate e metriche calcolate avanzate (derivate)
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 33%

---

# Metriche calcolate e metriche calcolate avanzate (derivate)

Le metriche calcolate e le metriche calcolate avanzate (o derivate) sono metriche personalizzate che puoi creare dalle metriche esistenti.

I nostri strumenti di metriche calcolate offrono un modo altamente flessibile di generare, gestire e curare le metriche. Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover cambiare il [!DNL Analytics] implementazione. Le metriche personalizzate disponibili in ogni [!DNL Analytics] pacchetto:

* Adobe [!DNL Analytics] Foundation: calcolato
* [Selezione Adobe Analytics](https://www.adobe.com/it/data-analytics-cloud/analytics/select.html): calcolato + Avanzato calcolato
* [Adobe Analytics Prime](https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html): calcolato + Avanzato calcolato
* [Adobe Analytics Ultimate](https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html): calcolato + Avanzato calcolato

Ecco un confronto tra le metriche calcolate e le funzionalità avanzate delle metriche calcolate:

| Opzioni di generazione | Metriche calcolate | Metriche calcolate avanzate (derivate) |
|---|---|---|
| [Tipi di formato (decimale, ora, percentuale, valuta)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sì | Sì |
| [Modifiche all’attribuzione (predefinita, lineare, di partecipazione, ecc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| [Tipi di metriche (standard, totale)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| Operatori di base (aggiungere, sottrarre, moltiplicare, dividere) | Sì | Sì |
| [Applicare segmenti](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | No | Sì |
| [Funzioni di base (conteggio, valore assoluto, media, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | No | Sì |
| [Funzioni avanzate (regressione, if/then, t-score, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | No | Sì |

## Funzionalità {#section_A0A5C275B68A4D628950BBB0B1EE631F}

È possibile eseguire le seguenti azioni:

* Creare metriche in [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection], e [!UICONTROL Contribution Analysis].
* Creare metriche segmentate derivate in fase di esecuzione dei rapporti, senza dover modificare l’implementazione. Questi possono essere visualizzati storicamente perché sono basati su segmenti.

  >[!VIDEO](https://video.tv.adobe.com/v/25407/?quality=12&learn=on)

* Condividere le metriche tra le suite di rapporti. Ciò significa che tutte le metriche create di recente si applicano a tutte le suite di rapporti nella stessa società di accesso.
* (Solo per metriche calcolate avanzate) Segmento sulle metriche. Ad esempio, puoi creare una metrica per “Nuovi visitatori”, conteggiando le persone per cui questa è la prima sessione.

* Incorpora funzioni statistiche per descrivere meglio i tuoi dati (solo per metriche calcolate avanzate). Ad esempio, puoi contare il numero di elementi in un rapporto o aggiungere il numero di deviazioni standard per ogni elemento.

  >[!VIDEO](https://video.tv.adobe.com/v/25409/?quality=12&learn=on)

## Limitazioni {#section_CB878B02451541D68A68B508D4DBD19A}

Alcuni [!DNL Analytics] Le funzioni di consentono di utilizzare eventi ma non metriche calcolate:

* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] in Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] per [!DNL Target]

## Strumenti {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Ecco una breve panoramica della [!UICONTROL Calculated metrics] strumenti:

| Strumento | Funzionalità |
|--- |--- |
| Generatore di metrica calcolata | <ul><li>Creare metriche calcolate e calcolate avanzate utilizzando modelli di allocazione avanzati.</li><li>Aggiungere segmenti inline alle formule delle metriche</li><li>Confrontare segmenti nello stesso rapporto. Ad esempio, confrontare i visitatori locali con quelli internazionali.</li><li>Utilizzare le funzioni statistiche</li><li>Fornisci descrizioni dettagliate delle metriche (mostra cosa fanno, dove usarle, dove NON usarle)</li><li>Copiare le definizioni in nuove metriche</li><li>Fornire un’anteprima delle metriche in linea</li><li>Imposta la polarità della metrica, che indica se è positivo o negativo se un dato evento personalizzato (metrica) aumenta</li><li>Assegnare tag alle metriche</li></ul> |
| Gestore metriche calcolate | <ul><li>Condividere le metriche con altri&lt;/li><li>Approvare e curare le metriche</li><li>Organizzare le metriche (assegnare tag) in modo che le persone possano trovarle</li><li>Eliminare le metriche</li><li>Rinominare le metriche</li></ul> |
| Barra del selettore delle metriche | Consente di cercare e aggiungere/applicare metriche al rapporto. Puoi anche modificare l’ordinamento (opzioni disponibili: alfabetico, consigliato, usato di frequente, usato di recente). Inoltre, puoi filtrare in base alle suite di rapporti in modo da visualizzare solo le metriche create in una specifica suite di rapporti.  Per accedere a questo selettore delle metriche, fai clic sull’icona Metriche a sinistra di un rapporto. |
| API per metriche calcolate | Parte del set di API di Adobe Analytics 2.0. |