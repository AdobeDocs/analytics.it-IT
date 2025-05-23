---
description: Le metriche calcolate e le metriche calcolate avanzate sono metriche personalizzate che puoi creare dalle metriche esistenti.
keywords: Metriche calcolate;Metriche calcolate avanzate
title: Metriche calcolate e metriche calcolate avanzate
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 31%

---

# Metriche calcolate e metriche calcolate avanzate

Le metriche calcolate e le metriche calcolate avanzate sono metriche personalizzate che puoi creare dalle metriche esistenti.

I nostri strumenti di metriche calcolate offrono un modo altamente flessibile di generare, gestire e curare le metriche. Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover modificare l&#39;implementazione di [!DNL Analytics]. Le metriche personalizzate disponibili in ciascun pacchetto [!DNL Analytics] sono:

* Adobe [!DNL Analytics] Foundation: calcolato
* [Selezione Adobe Analytics](https://www.adobe.com/it/data-analytics-cloud/analytics/select.html): Calcolato + Avanzato Calcolato
* [Adobe Analytics Prime](https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html): calcolato + Avanzato calcolato
* [Adobe Analytics Ultimate](https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html): calcolato + Avanzato calcolato

Ecco un confronto tra le metriche calcolate e le funzionalità avanzate delle metriche calcolate:

| Opzioni di generazione | Metriche calcolate | Metriche calcolate avanzate |
|---|---|---|
| [Tipi di formato (decimale, ora, percentuale, valuta)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sì | Sì |
| [Modifiche all&#39;attribuzione (predefinita, lineare, partecipazione, ecc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| [Tipi di metrica (standard, totale)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| Operatori di base (aggiungere, sottrarre, moltiplicare, dividere) | Sì | Sì |
| [Applica segmenti](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | No | Sì |
| [Funzioni di base (conteggio, valore assoluto, media, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | No | Sì |
| [Funzioni avanzate (regressione, if/then, t-score, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | No | Sì |

## Funzionalità {#section_A0A5C275B68A4D628950BBB0B1EE631F}

È possibile eseguire le seguenti azioni:

* Creare metriche in [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection] e [!UICONTROL Contribution Analysis].
* Creare metriche segmentate derivate in fase di esecuzione dei rapporti, senza dover modificare l’implementazione. Questi possono essere visualizzati storicamente perché sono basati su segmenti.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Metriche calcolate](https://video.tv.adobe.com/v/41662?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

* Condividere le metriche tra le suite di rapporti. Ciò significa che tutte le metriche create di recente si applicano a tutte le suite di rapporti nella stessa società di accesso.
* (Solo per metriche calcolate avanzate) Segmento sulle metriche. Ad esempio, puoi creare una metrica per “Nuovi visitatori”, conteggiando le persone per cui questa è la prima sessione.

* Incorpora funzioni statistiche per descrivere meglio i tuoi dati (solo per metriche calcolate avanzate). Ad esempio, puoi contare il numero di elementi in un rapporto o aggiungere il numero di deviazioni standard per ogni elemento.


>[!BEGINSHADEBOX]

Per un video dimostrativo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentazione delle metriche calcolate nei segmenti](https://video.tv.adobe.com/v/41661?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


## Limitazioni {#section_CB878B02451541D68A68B508D4DBD19A}

Alcune funzionalità di [!DNL Analytics] consentono di utilizzare eventi ma non metriche calcolate:

* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] in Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] per [!DNL Target]

## Strumenti {#section_D65E9C067E9C45E1A50DD30F50561BB2}

Ecco una breve panoramica degli strumenti [!UICONTROL Calculated metrics]:

| Strumento | Funzionalità |
|--- |--- |
| Generatore di metrica calcolata | <ul><li>Creare metriche calcolate e calcolate avanzate utilizzando modelli di allocazione avanzati.</li><li>Aggiungere segmenti inline alle formule delle metriche</li><li>Confrontare segmenti nello stesso rapporto. Ad esempio, confrontare i visitatori locali con quelli internazionali.</li><li>Utilizzare le funzioni statistiche</li><li>Fornisci descrizioni dettagliate delle metriche (mostra cosa fanno, dove usarle, dove NON usarle)</li><li>Copiare le definizioni in nuove metriche</li><li>Fornire un’anteprima delle metriche in linea</li><li>Imposta la polarità della metrica, che indica se è positivo o negativo se un dato evento personalizzato (metrica) aumenta</li><li>Assegnare tag alle metriche</li></ul> |
| Gestore metriche calcolate | <ul><li>Condividere le metriche con altri&lt;/li<li>Approvare e curare le metriche</li><li>Organizzare le metriche (assegnare tag) in modo che le persone possano trovarle</li><li>Eliminare le metriche</li><li>Rinominare le metriche</li></ul> |
| Barra del selettore delle metriche | Consente di cercare e aggiungere/applicare metriche al rapporto. Puoi anche modificare l’ordinamento (opzioni disponibili: alfabetico, consigliato, usato di frequente, usato di recente). Inoltre, puoi filtrare in base alle suite di rapporti in modo da visualizzare solo le metriche create in una specifica suite di rapporti.  Per accedere a questo selettore delle metriche, fai clic sull’icona Metriche a sinistra di un rapporto. |
| API per metriche calcolate | Parte del set di API di Adobe Analytics 2.0. |
