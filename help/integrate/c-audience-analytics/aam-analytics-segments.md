---
description: Analytics e Audience Manager usano entrambi i segmenti. Tuttavia, un segmento Analytics non è esattamente lo stesso di un segmento Audience Manager. Queste differenze contribuiscono in parte a discrepanze nei rapporti di Analytics e Audience Manager. Di conseguenza, è importante provare a comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe queste soluzioni.
seo-description: Analytics e Audience Manager usano entrambi i segmenti. Tuttavia, un segmento Analytics non è esattamente lo stesso di un segmento Audience Manager. Queste differenze contribuiscono in parte a discrepanze nei rapporti di Analytics e Audience Manager. Di conseguenza, è importante provare a comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe queste soluzioni.
seo-title: Comprendere i segmenti in Analytics e Audience Manager
title: Comprendere i segmenti in Analytics e Audience Manager
uuid: 13 f 7 d 1 d 7-6 a 3 f -42 f 1-822 e -8 d 3523999 efa
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Comprendere i segmenti in Analytics e Audience Manager

Analytics e Audience Manager usano entrambi i segmenti. Tuttavia, un segmento Analytics non è esattamente lo stesso di un segmento Audience Manager. Queste differenze contribuiscono in parte a discrepanze nei rapporti di Analytics e Audience Manager. Di conseguenza, è importante provare a comprendere queste differenze quando si inizia a lavorare con i segmenti in entrambe queste soluzioni.

## Audience Manager Segments {#section_417DC4B5648547778A27E42CE1D09900}

Un segmento Audience Manager è un gruppo di visitatori (ID utente) idonei per un set di caratteristiche definite uniti da regole logiche. Esistono quattro criteri che determinano se un visitatore (ID utente) fa parte di un segmento in Audience Manager:

* Regole impostate sui segmenti stessi e sulle caratteristiche che costituiscono ogni segmento. Queste regole definiscono le condizioni che un ID utente deve soddisfare o mostrare per essere qualificato per un segmento.
* Modellazione algoritmica. Gli utenti idonei per un particolare segmento possono qualificarsi per altri segmenti in base alla modellazione algoritmica e all'analisi.
* Intervalli time-to-live (TTL). L'iscrizione al segmento può scadere dopo un intervallo impostato o continuare a tempo indefinito.
* Recency e frequenza. Definire quando e quanto spesso gli utenti hanno un'interazione (realizzazione caratteristica) possono contribuire a creare segmenti basati sul livello reale (o percepito) di interesse in un sito, sezione o particolare creatività.

L'iscrizione al segmento Audience Manager è fluida. Gli utenti possono inserire o rilasciare un segmento a seconda che siano idonei per i criteri di segmento nel momento corrente. Ciò significa che la popolazione di un segmento Audience Manager può aumentare o diminuire nel tempo.

Un segmento Audience Manager è denotato come audience in Analytics.

For more information, refer to [Trait and Segment Population Data in Segment Builder](https://marketing.adobe.com/resources/help/en_US/aam/segment-builder-data.html) and [Signals, Traits, and Segments](https://marketing.adobe.com/resources/help/en_US/aam/c_signal_trait_segment.html).

## Segmenti di Analytics {#section_62EC584BB7134E10923BCBA7F9BD89A8}

Un segmento Analytics è un meccanismo di filtro per i dati nei rapporti. Il filtro può avvenire al visitatore, alla visita o al livello hit, anziché rigorosamente a livello di visitatore come in Audience Manager. Esistono diversi fattori importanti da tenere in considerazione quando si confronta un segmento Analytics con un segmento Audience Manager:

* I segmenti di Analytics operano su un insieme diverso di dati rispetto ai segmenti Audience Manager. Durante la raccolta di dati, Analytics applica molti passaggi di post-elaborazione diversi ai dati non disponibili per Audience Manager. La post-elaborazione può includere persistence evar, regole di elaborazione, ricerca (geolocalità, dispositivo mobile), VISTA e molti altri. Audience Manager riceve i dati pre-elaborati tramite l'inoltro lato server (DIL).

   Si verificano discrepanze di dati comuni quando si confrontano segmenti basati su dimensioni che non scadono in Analytics, alla stessa dimensione in Audience Manager. Ad esempio, listvar o evar di merchandising che non scadono.

   Ad esempio, se evar = blue e impostato per non scade in Analytics, qualsiasi segmento in Analytics con i criteri «evar = blu» includerà sempre questo visitatore. Tuttavia, in Audience Manager, tale visitatore potrebbe uscire da un segmento definito in modo simile dopo un determinato periodo di tempo.

* I segmenti di Analytics hanno più funzionalità rispetto ai segmenti AAM. I segmenti Audience Manager vengono sempre valutati a livello di visitatore. I segmenti di Analytics possono essere definiti a un visitatore, a una visita o a un livello hit (o a una combinazione di questi livelli). Inoltre, Analytics supporta funzionalità avanzate di segmentazione non supportate da Audience Manager, come la segmentazione sequenziale.
* Come indicato in precedenza, i visitatori Audience Manager possono entrare o rilasciare un segmento a seconda che siano idonei per i criteri di segmento nel momento corrente.

   In modo analogo, in Analytics i visitatori saranno inclusi o esclusi da un segmento in base all'intervallo di date del rapporto. Ad esempio, un singolo visitatore ha effettuato un acquisto scorso. In AAM, tale visitatore viene incluso in un segmento «acquirente», a prescindere dall'intervallo di date. In Analytics, un report basato su questo mese non includerà il visitatore nel segmento. Tuttavia, un report basato su questo mese e ultimo mese includerà il visitatore nel segmento.

See the [Analytics Segmentation Guide](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) for more information.
