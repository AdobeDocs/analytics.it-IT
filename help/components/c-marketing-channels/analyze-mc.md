---
title: Analisi dei canali di marketing
description: Scopri come utilizzare le dimensioni Marketing Channels (Canali di marketing) in Workspace.
translation-type: tm+mt
source-git-commit: 586dabe8454bb2e6fbd4f3fbdb18d13a18b0417d
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Analisi dei canali di marketing

Probabilmente vuoi sapere quale dei tuoi canali di marketing è il più efficace, e con chi, in modo da poter indirizzare meglio i tuoi sforzi e ricevere un ritorno migliore sui tuoi dollari di marketing. In Adobe Analytics, le dimensioni e le metriche di Marketing Channels in Workspace sono uno degli strumenti che possono aiutarti a monitorare l&#39;influenza di diversi canali sugli ordini, sulle entrate e così via. e offre informazioni utili sui canali. Ecco le dimensioni e le metriche che puoi usare in relazione ai canali di marketing:

![](assets/mc-dims.png)

| Dimensioni/metrica | Definizione |
|---|---|
| Canale di marketing | Questa è la dimensione di Marketing Channels (Canali di marketing) consigliata da utilizzare. I modelli di Attribution IQ possono essere applicati a esso in fase di esecuzione. Questa dimensione si comporta in modo identico alla dimensione Ultimo canale di contatto, ma viene etichettata in modo diverso per evitare confusione quando viene utilizzata con un modello di attribuzione diverso. |
| Ultimo canale touch | Dimensione legacy, con l’ultimo modello di attribuzione tocco preapplicato e immutabile. |
| Primo canale touch | Dimensione legacy, con il primo modello di attribuzione touch preapplicato e non modificabile. |
| Istanze canale di marketing | Questa metrica misura il numero di volte in cui un canale di marketing è stato definito in una richiesta di immagine, comprese le visualizzazioni di pagina standard e le chiamate di collegamento personalizzate. Non include valori persistenti. |
| Nuovi impegni | Questa metrica è simile a Istanze, ma viene incrementata solo quando il primo canale di marketing touch è definito in una richiesta di immagine. |

## Analisi di base

Questa tabella a forma libera mostra le metriche Ordini online, Ricavi online e Tasso di conversione per ciascuno dei canali di marketing:

![](assets/mc-viz1.png)

Qui puoi vedere gli ordini online e i ricavi online di ciascun canale di marketing in un grafico ad anello:

![](assets/mc-viz2.png)

Questo grafico a linee mostra le tendenze negli ordini online per diversi canali nel tempo:

![](assets/mc-viz3.png)

## Analisi avanzata

Marketing Channels Details (Dettagli canali di marketing): i dettagli si approfondiscono in ogni canale per mostrarvi campagne, posizionamenti, ecc. specifici. Potete suddividere ciascun canale di marketing in dettagli:

![](assets/mc-viz4.png)

## Applicazione di modelli di attribuzione

Potete usare [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/use-attribution.html) per applicare istantaneamente diversi modelli di attribuzione:

![](assets/mc-viz5.png)

La stessa metrica (Ordini online) genera risultati diversi quando si applicano modelli di attribuzione diversi.

Di seguito sono riportati alcuni video che spiegano l&#39;attributo IQ in modo più dettagliato: [playlist](https://www.youtube.com/playlist?list=PL2tCx83mn7GuDzYEZ8jQlaScruZr3tBTR)di Attribution IQ.

## Analisi marketing multi-scheda

Utilizzando il canale First Touch precedente e l’ultimo canale di contatto, puoi ottenere una vista utile sulle interazioni dei canali:

![](assets/mc-viz6.png)

Ulteriori informazioni sull&#39;analisi di marketing a schede in [questo video](https://www.youtube.com/watch?v=M3EOdONa-3E).
