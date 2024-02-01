---
description: Il sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.
title: Avvisi intelligenti
feature: Alerts
exl-id: 1b23211e-7632-4b33-a27d-c58b3bbbbab1
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '512'
ht-degree: 41%

---

# Avvisi intelligenti

Il sistema intelligente di avvisi offre un controllo più granulare sugli avvisi e integra il rilevamento delle anomalie con il sistema di avvisi.

Panoramica video:

>[!VIDEO](https://video.tv.adobe.com/v/25446/?quality=12)

## Panoramica {#section_6AC8CA81DEA94E99B0F192B60D0FDF03}

>[!IMPORTANT]
>
>Adobe di avvisi intelligenti [!DNL Analytics] Prime e Adobe [!DNL Analytics] Solo per i clienti più esperti.

La funzione Avvisi intelligenti permette di

* Creare avvisi basati su anomalie (soglie del 90%, 95%, 99%, 99,75% e 99,9%; modifica della percentuale; superiore/inferiore).
* Visualizzare in anteprima la frequenza di attivazione degli avvisi.
* Inviare avvisi tramite e-mail o SMS con collegamenti ai progetti di Analysis Workspace generati automaticamente.
* Creare avvisi “impilati” in grado di acquisire più metriche in un singolo avviso.

I componenti del sistema di avvisi includono: Generatore di avvisi, Gestione avvisi, Anteprima avvisi e un migliore accesso contestuale alla creazione di avvisi. L’interfaccia del precedente sistema di avvisi non sarà più disponibile, mentre gli avvisi veri e propri vengono trasferiti al nuovo sistema. Alcune funzioni di avviso legacy [non sono più disponibili](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/alerts.html).

Esistono tre modi per accedere al generatore di avvisi:

* Utilizzando la seguente scelta rapida in Analysis Workspace:

  `ctrl (or cmd) + shift + a`
* Andando direttamente al Generatore di avvisi:  **[!UICONTROL Workspace]** > **[!UICONTROL Components]** > **[!UICONTROL New Alert]** .
* Selezionando una o più voci di tabella a forma libera, facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Create Alert from Selection]**. Viene aperto il Generatore di avvisi, precompilato con le metriche appropriate e i filtri applicati dalla tabella. Se necessario, puoi quindi modificare l’avviso.

  ![](assets/create-alert-from-selection.png)


## Domande frequenti: come vengono calcolati e attivati gli avvisi {#trigger}

Le soglie espresse in % rappresentano le deviazioni standard. Ad esempio, 95% = 2 deviazioni standard e 99% = 3 deviazioni standard. A seconda della granularità temporale scelta, [diversi modelli](/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md) vengono utilizzati per calcolare lo scarto (ossia il numero di deviazioni standard) tra ciascun punto dati e il valore di norma. Impostando un valore di soglia basso (ad esempio 90%), si ottengono più anomalie rispetto a quando si imposta un valore superiore (99%). Sono state introdotte soglie del 99,75% e del 99,99% specificamente per la granularità oraria in modo da non attivare tutte le anomalie.

+++ Quanto indietro nel tempo va il rilevamento delle anomalie dell&#39;avviso per determinare le anomalie nei dati?

Il periodo di rilevamento varia in base al tipo di granularità selezionato. Consulta Tecniche di statistica utilizzate in <a href="/help/analyze/analysis-workspace/c-anomaly-detection/statistics-anomaly-detection.md">Rilevamento delle anomalie</a> per maggiori dettagli. Segue un breve riepilogo:

* Mensile = 15 mesi + lo stesso intervallo relativo allo scorso anno
* Settimanale = 15 settimane + lo stesso intervallo relativo allo scorso anno
* Giornaliero = 35 giorni + lo stesso intervallo relativo allo scorso anno
* Orario = 336 ore

+++

+++ Per essere avvisato solo di un calo del comportamento o solo di un picco nel comportamento, posso utilizzare la funzione di anomalia o devo utilizzare un valore assoluto?

L’utilizzo del valore assoluto attiverebbe comunque gli avvisi sui ribassi e sui picchi. Non è possibile limitare gli avvisi ai soli cali o soli picchi.

+++

+++ È possibile configurare gli avvisi in modo che vengano attivati solo durante determinate ore della giornata (ad esempio l’orario di lavoro rispetto a quello non di ufficio)?

Al momento non è possibile.

+++

+++ Posso ottenere una tabella dei &quot;valori previsti&quot; che compongono la linea punteggiata, o una sorta di output dei valori?

Non in Workspace, ma in Report Builder. Consulta [questo video](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/exporting/report-builder/anomaly-detection-in-report-builder.html) sul rilevamento delle anomalie nel Report Builder.

Tieni presente che il Report Builder si avvale di metodi di rilevamento delle anomalie meno sofisticati. Utilizza un periodo di formazione fisso di 30 giorni, con un intervallo fisso del 95%.

+++
