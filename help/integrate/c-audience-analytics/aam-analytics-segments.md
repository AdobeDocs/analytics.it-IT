---
description: Analytics e Audience Manager usano entrambi i segmenti. Tuttavia, un segmento di Analytics non è esattamente lo stesso di un segmento di Audience Manager. Queste differenze contribuiscono, in parte, alle discrepanze visualizzate nei report di Analytics e Audience Manager. Di conseguenza, è importante e utile cercare di comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe le soluzioni.
title: Comprendere i segmenti in Analytics e Audience Manager
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Comprendere i segmenti in Analytics e Audience Manager

Analytics e Audience Manager usano entrambi i segmenti. Tuttavia, un segmento di Analytics non è esattamente lo stesso di un segmento di Audience Manager. Queste differenze contribuiscono, in parte, alle discrepanze visualizzate nei report di Analytics e Audience Manager. Di conseguenza, è importante e utile cercare di comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe le soluzioni.

## Segmenti di Audience Manager {#section_417DC4B5648547778A27E42CE1D09900}

Un segmento di Audience Manager è un gruppo di visitatori (ID utente) idonei per un set di caratteristiche definite, uniti da regole logiche. Esistono quattro criteri che determinano se un visitatore (ID utente) fa parte di un segmento in Audience Manager:

* Regole impostate sui segmenti stessi e sulle caratteristiche che compongono ciascun segmento. Queste regole definiscono le condizioni che un ID utente deve soddisfare o mostrare per essere qualificato per un segmento.
* Modellazione algoritmica. Gli utenti idonei per un particolare segmento possono qualificarsi per altri segmenti basati sulla modellazione e analisi algoritmica.
* Intervalli time-to-live (TTL). L’appartenenza al segmento può scadere dopo un determinato intervallo o continuare indefinitamente.
* Recency e frequenza. Definire quando e con quale frequenza gli utenti dispongono di un’interazione (realizzazione delle caratteristiche) può aiutare a creare segmenti basati sul livello di interesse reale (o percepito) in un sito, una sezione o un particolare livello creativo.

L'appartenenza al segmento di Audience Manager è fluida. Gli utenti possono immettere o uscire da un segmento a seconda che siano idonei per i criteri del segmento nel momento corrente. Ciò significa che la popolazione di un segmento di Audience Manager può aumentare o diminuire nel tempo.

Un segmento di Audience Manager è indicato come audience in Analytics.

Per ulteriori informazioni, consulta [Caratteristiche e dati sulla popolazione dei segmenti in Generatore](https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html) di segmenti e [segnali, caratteristiche e segmenti](https://marketing.adobe.com/resources/help/en_US/aam/c_signal_trait_segment.html).

## Segmenti di Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Un segmento di Analytics è un meccanismo di filtraggio per i dati nei report. Il filtraggio può avvenire a livello di visitatore, visita o hit, anziché a livello di visitatore come in Audience Manager. Quando si confronta un segmento di Analytics con un segmento di Audience Manager, è necessario considerare diversi fattori importanti:

* I segmenti di Analytics operano su un set di dati diverso rispetto ai segmenti di Audience Manager. Durante la raccolta dei dati, Analytics applica molti diversi passaggi di post-elaborazione ai dati che non sono disponibili per Audience Manager. La post-elaborazione può includere persistenza eVar, regole di elaborazione, ricerche (geolocalità, dispositivo mobile), VISTA e molti altri. Audience Manager riceve i dati preelaborati tramite l’inoltro lato server (o DIL).

   Si verificano comuni discrepanze di dati quando si confrontano segmenti basati su dimensioni che non scadono mai in Analytics con la stessa dimensione in Audience Manager. Ad esempio, listVar o eVar di merchandising che non scadono mai.

   Ad esempio, se eVar = blue e viene impostato per non scadere mai in Analytics, qualsiasi segmento in Analytics con criteri "eVar = blue" includerà sempre questo visitatore. In Audience Manager, invece, il visitatore potrebbe non avere più un segmento definito in modo simile dopo un determinato periodo di tempo.

* I segmenti di Analytics hanno più funzionalità dei segmenti AAM. I segmenti di Audience Manager vengono sempre valutati a livello di visitatore. I segmenti di Analytics possono essere definiti a livello di visitatore, visita o hit (o a una combinazione di questi livelli). Analytics supporta inoltre funzionalità di segmentazione avanzate che Audience Manager non supporta, ad esempio la segmentazione sequenziale.
* Come già detto, i visitatori di Audience Manager possono entrare o uscire da un segmento a seconda che siano idonei per i criteri del segmento nel momento corrente.

   Al contrario, in Analytics, i visitatori saranno inclusi o esclusi da un segmento in base all'intervallo di date del rapporto. Ad esempio, un singolo visitatore ha effettuato un acquisto il mese scorso. In AAM, tale visitatore sarebbe incluso in un segmento "acquirente", indipendentemente dall'intervallo di date. In Analytics, un report basato su questo mese non includerebbe il visitatore nel segmento. Tuttavia, un rapporto basato su questo mese e sullo scorso mese includerebbe il visitatore nel segmento.

Per ulteriori informazioni, consulta la Guida [alla segmentazione di](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) Analytics.
