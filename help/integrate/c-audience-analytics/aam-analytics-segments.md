---
description: Analytics e Audience Manager utilizzano entrambi i segmenti. Tuttavia, un segmento di Analytics non è esattamente la stessa cosa di un segmento di Audience Manager. Queste differenze contribuiscono in parte alle discrepanze che vedrai nei tuoi report di Analytics e di Audience Manager. Di conseguenza, è importante e utile provare a comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe queste soluzioni.
title: Comprendere i segmenti in Analytics e Audience Manager
feature: Audience Analytics
exl-id: 2bc662e7-7552-41e1-9d4a-bc7aa81b8c1d
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '739'
ht-degree: 2%

---

# Comprendere i segmenti in Analytics e Audience Manager

Analytics e Audience Manager utilizzano entrambi i segmenti. Tuttavia, un segmento di Analytics non è esattamente la stessa cosa di un segmento di Audience Manager. Queste differenze contribuiscono in parte alle discrepanze che vedrai nei tuoi report di Analytics e di Audience Manager. Di conseguenza, è importante e utile provare a comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe queste soluzioni.

## Segmenti Audience Manager {#section_417DC4B5648547778A27E42CE1D09900}

Un segmento di Audience Manager è un gruppo di visitatori (ID utente) idonei per un set di caratteristiche definite unite da regole logiche. Ci sono quattro criteri che determinano se un visitatore (ID utente) fa parte di un segmento in Audience Manager:

* Regole impostate sui segmenti stessi e sulle caratteristiche che compongono ciascun segmento. Queste regole definiscono le condizioni che un ID utente deve soddisfare o mostrare per essere qualificato per un segmento.
* Modellazione algoritmica. Gli utenti idonei per un particolare segmento possono qualificarsi per altri segmenti in base a modellazione e analisi algoritmiche.
* Intervalli time-to-live (TTL). L’iscrizione al segmento può scadere dopo un intervallo impostato o continuare a tempo indefinito.
* Recency e frequenza. Definire quando e con quale frequenza gli utenti hanno un’interazione (realizzazione delle caratteristiche) può aiutare a creare segmenti in base al livello reale (o percepito) di interesse in un sito, una sezione o una particolare creatività.

L’iscrizione al segmento di Audience Manager è fluida. Gli utenti possono inserire o eliminare un segmento a seconda che siano idonei per i criteri del segmento nel momento corrente. Ciò significa che la popolazione di un segmento Audience Manager può aumentare o diminuire nel tempo.

Un segmento di Audience Manager è identificato come un pubblico in Analytics.

Per ulteriori informazioni, consulta [Dati sulle caratteristiche e sulle popolazioni dei segmenti nel Generatore di segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/segments/segment-builder-data.html) e [Segnali, caratteristiche e segmenti](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/signal-trait-segment.html).

## Segmenti di Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Un segmento di Analytics è un meccanismo di filtro per i dati presenti nei rapporti. Il filtro può essere applicato a livello di visitatore, visita o hit, anziché esclusivamente a livello di visitatore come nell’Audience Manager. Esistono diversi fattori importanti da considerare quando si confronta un segmento di Analytics con un segmento di Audience Manager:

* I segmenti di Analytics funzionano su un set di dati diverso dai segmenti Audience Manager. Durante la raccolta dei dati, Analytics applica molti passaggi di post-elaborazione diversi ai dati che non sono disponibili per Audience Manager. La post-elaborazione può includere persistenza eVar, regole di elaborazione, ricerche (geolocalizzazione, dispositivo mobile), VISTA e molte altre. Audience Manager riceve dati pre-elaborati tramite inoltro lato server (o DIL).

  Si verificano discrepanze di dati comuni quando si confrontano segmenti basati su dimensioni che non scadono mai in Analytics con la stessa dimensione in Audience Manager. Ad esempio, listVar o eVar di merchandising che non scadono mai.

  Ad esempio, se eVar = blu e è impostato per non scadere mai in Analytics, qualsiasi segmento in Analytics con il criterio &quot;eVar = blu&quot; includerà sempre questo visitatore. Mentre, ad Audience Manager, quel visitatore potrebbe non rientrare in un segmento definito in modo simile dopo un determinato periodo di tempo.

* I segmenti di Analytics hanno più funzionalità dei segmenti di Adobe Audience Manager. I segmenti di Audience Manager vengono sempre valutati a livello di visitatore. I segmenti di Analytics possono essere definiti a livello di visitatore, visita o hit (o una combinazione di questi livelli). Inoltre, Analytics supporta funzionalità di segmentazione avanzate non supportate da Audience Manager, ad esempio la segmentazione sequenziale.
* Come accennato in precedenza, i visitatori Audienci Manager possono entrare o uscire da un segmento a seconda che siano idonei per i criteri del segmento nel momento corrente.

  Al contrario, in Analytics i visitatori verranno inclusi o esclusi da un segmento in base all’intervallo di date del rapporto. Ad esempio, un singolo visitatore ha effettuato un acquisto il mese scorso. In Adobe Audience Manager, quel visitatore veniva incluso in un segmento &quot;acquirente&quot;, indipendentemente dall’intervallo di date. In Analytics, un rapporto basato su questo mese non includerebbe il visitatore nel segmento. Tuttavia, un rapporto basato su questo e sull’ultimo mese includerebbe il visitatore nel segmento.

Consulta la [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html) per ulteriori informazioni.
