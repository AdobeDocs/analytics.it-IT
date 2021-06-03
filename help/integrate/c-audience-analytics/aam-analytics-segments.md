---
description: Analytics e Audience Manager utilizzano entrambi i segmenti. Tuttavia, un segmento di Analytics non corrisponde esattamente a un segmento di Audience Manager. Queste differenze contribuiscono, in parte, alle discrepanze che vedrai nei rapporti di Analytics e di Audience Manager. Di conseguenza, è importante e utile cercare di comprendere queste differenze quando inizi a lavorare con i segmenti in entrambe queste soluzioni.
title: Comprendere i segmenti in Analytics e Audience Manager
uuid: 13f7d1d7-6a3f-42f1-822e-8d3523999efa
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 2%

---

# Comprendere i segmenti in Analytics e Audience Manager

Analytics e Audience Manager utilizzano entrambi i segmenti. Tuttavia, un segmento di Analytics non corrisponde esattamente a un segmento di Audience Manager. Queste differenze contribuiscono, in parte, alle discrepanze che vedrai nei rapporti di Analytics e di Audience Manager. Di conseguenza, è importante e utile cercare di comprendere queste differenze quando inizi a lavorare con i segmenti in entrambe queste soluzioni.

## Segmenti di Audience Manager {#section_417DC4B5648547778A27E42CE1D09900}

Un segmento di Audience Manager è un gruppo di visitatori (ID utente) qualificati per un set di caratteristiche definite unite da regole logiche. Esistono quattro criteri che determinano se un visitatore (ID utente) fa parte di un segmento, ad Audience Manager:

* Regole impostate sui segmenti stessi e sulle caratteristiche che compongono ciascun segmento. Queste regole definiscono le condizioni che un ID utente deve soddisfare o presentare per essere qualificato per un segmento.
* Modellazione algoritmica. Gli utenti qualificati per un particolare segmento possono qualificarsi per altri segmenti sulla base di modelli e analisi algoritmici.
* Intervalli time-to-live (TTL). L’appartenenza al segmento può scadere dopo un intervallo impostato o continuare indefinitamente.
* Recency e frequenza. Definire quando e con quale frequenza gli utenti hanno un’interazione (realizzazione delle caratteristiche) può aiutare a creare segmenti in base al livello di interesse reale (o percepito) in un sito, una sezione o un particolare livello creativo.

L’appartenenza al segmento di Audience Manager è fluida. Gli utenti possono inserire o eliminare un segmento a seconda che si qualifichino o meno per i criteri del segmento nel momento attuale. Ciò significa che la popolazione di un segmento di Audience Manager può aumentare o diminuire nel tempo.

Un segmento di Audience Manager è identificato come pubblico in Analytics.

Per ulteriori informazioni, consulta [Dati sulle caratteristiche e sulla popolazione dei segmenti in Generatore di segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html) e [Segnali, caratteristiche e segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html).

## Segmenti di Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Un segmento di Analytics è un meccanismo di filtro per i dati nei rapporti. Il filtraggio può avvenire a livello di visitatore, visita o hit, anziché rigorosamente a livello di visitatore come nell’Audience Manager. Ci sono diversi fattori importanti da considerare quando si confronta un segmento di Analytics con un segmento di Audience Manager:

* I segmenti di Analytics operano su un set di dati diverso rispetto ai segmenti di Audience Manager. Durante la raccolta dei dati, Analytics applica molti passaggi di post-elaborazione diversi ai dati che non sono disponibili per l’Audience Manager. La post-elaborazione può includere la persistenza eVar, le regole di elaborazione, le ricerche (geolocalizzazione, dispositivo mobile), VISTA e molti altri. Audience Manager riceve i dati preelaborati tramite l’inoltro lato server (o DIL).

   Si verificano comuni discrepanze di dati quando si confrontano segmenti basati su dimensioni che non scadono mai in Analytics, con la stessa dimensione nell’Audience Manager. Ad esempio, listVar o eVar per merchandising che non scadono mai.

   Ad esempio, se eVar = blu e è impostato per non scadere mai in Analytics, qualsiasi segmento in Analytics con criteri &quot;eVar = blu&quot; includerà sempre questo visitatore. In alternativa, nell’Audience Manager, il visitatore potrebbe uscire da un segmento definito in modo simile dopo un determinato periodo di tempo.

* I segmenti di Analytics hanno più funzionalità dei segmenti AAM. I segmenti di Audience Manager vengono sempre valutati a livello di visitatore. I segmenti di Analytics possono essere definiti a livello di visitatore, visita o hit (o a una combinazione di questi livelli). Inoltre, Analytics supporta funzionalità di segmentazione avanzate che Audience Manager non supporta, ad esempio la segmentazione sequenziale.
* Come accennato in precedenza, i visitatori di Audience Manager possono entrare o uscire da un segmento a seconda che si qualifichino o meno per i criteri del segmento nel momento attuale.

   Al contrario, in Analytics, i visitatori verranno inclusi o esclusi da un segmento in base all’intervallo di date del rapporto. Ad esempio, un singolo visitatore ha effettuato un acquisto il mese scorso. In AAM, quel visitatore sarebbe incluso in un segmento &quot;acquirente&quot;, indipendentemente dall&#39;intervallo di date. In Analytics, un report basato su questo mese non includerebbe il visitatore nel segmento. Tuttavia, un rapporto basato su questo mese e lo scorso mese includerebbe il visitatore nel segmento.

Per ulteriori informazioni, consulta la [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html) .
