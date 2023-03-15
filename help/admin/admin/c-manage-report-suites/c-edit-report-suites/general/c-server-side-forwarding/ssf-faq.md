---
description: Domande frequenti sulle caratteristiche, sulle funzionalità e sui problemi correlati all’inoltro lato server.
title: Domande frequenti sull’inoltro lato server
feature: Server-Side Forwarding
exl-id: 63103d2b-e2e8-42da-bdbd-be90abe305f7
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 100%

---

# Domande frequenti sull’inoltro lato server

Domande frequenti sulle caratteristiche, sulle funzionalità e sui problemi correlati all’inoltro lato server.

## Server di tracciamento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Domanda | Risposta |
|--- |--- |
| D: cosa succede se utilizzo l’inoltro lato server basato sul server di tracciamento legacy? | Il metodo di inoltro lato server basato su server di tracciamento legacy continuerà a inoltrare i dati da Analytics ad Audience Manager. Tuttavia, se desideri inviare segmenti di Audience Manager in Analytics, è necessario il nuovo inoltro lato server basato su suite di rapporti. Inoltre, l’abilitazione di una suite di rapporti per l’inoltro lato server oltre alla configurazione del server di tracciamento non comporta alcun danno: la nuova impostazione di inoltro lato server della suite di rapporti verrà utilizzata ogni volta che si verifica un conflitto. |
| D: devo migrare l’inoltro lato server basato su server di tracciamento legacy alla nuova suite di rapporti basata sull’inoltro lato server? | Continueremo a supportare l’inoltro lato server basato sul server di tracciamento per il prossimo futuro. Tuttavia, se desideri sfruttare l’integrazione da Audience Manager ad Analytics (condivisione dei segmenti ad Analytics), dovrai abilitare l’inoltro lato server basato sulla nuova suite di rapporti per tutte le suite di rapporti applicabili. Tuttavia, non esiste un motivo urgente per disabilitare l&#39;inoltro lato server basato su server di tracciamento legacy. |

## Assegnazione di tag e reporting {#section_71391BA901AC47B9A2286281644FF281}

| Domanda | Risposta |
|--- |--- |
| D: cosa succede se dispongo di tag per più suite sul sito? L’inoltro lato server raddoppierà le chiamate server ad Audience Manager? | No, un hit inoltrato da Analytics all’Audience Manager verrà inoltrato una sola volta, indipendentemente dal numero di suite di rapporti nell’hit. Se disponi di origini di dati corrispondenti nell’Audience Manager per ciascuna suite di rapporti nell’hit, ciascuna di esse verrà compilata in modo appropriato dall’hit singolo.  Tieni presente tuttavia che se al momento utilizzi la raccolta dati lato client (DIL) e abiliti l’inoltro lato server senza installare il modulo Gestione dell’audience, le chiamate server all’Audience Manager verranno raddoppiate indipendentemente dal numero di suite di rapporti disponibili nell’hit di Analytics. |
| D: cosa succede se dispongo di suite di rapporti con tag con più suite mappate su organizzazioni di Experience Cloud separate? | Non devi mai inviare dati da un singolo hit di Analytics a due suite di rapporti che appartengono a organizzazioni di Experience Cloud separate, ma se ciò si verifica, l’hit verrà inoltrato solo all’organizzazione di Experience Cloud che corrisponde alla configurazione del servizio Identity nella pagina. |
| D: cosa succede se dispongo di tag con più suite e una sola suite di rapporti è mappata sulla mia organizzazione Experience Cloud e l’altra no? | Inoltreremo l’hit al server di raccolta dati corrispondente per l’organizzazione Experience Cloud nella tua suite di rapporti mappata. Tuttavia, poiché la suite di rapporti non mappata non avrà un’origine dati associata nell’Audience Manager, non verranno registrati dati per la suite di rapporti non mappata nell’Audience Manager. |
| D: cosa succede se dispongo di una suite di rapporti mappata su più organizzazioni di Experience Cloud? | Analytics considererà questa suite di rapporti come non mappata e non consentirà l’inoltro lato server di essere abilitato per questa suite di rapporti. Contattata il servizio clienti per risolvere il problema di mappatura. |
| D: il metodo di inoltro lato server basato su suite di rapporti sarà più lento rispetto all’inoltro lato server basato sul server di tracciamento? | No, il tempo di risposta sarà lo stesso. |
| D: cosa succede se disponiamo di due organizzazioni di Experience Cloud (o istanze AAM) e vogliamo condividere i dati tra entrambe le organizzazioni di Experience Cloud? Posso inoltrare un singolo hit di Analytics lato server a più organizzazioni di Experience Cloud? | No. Se devi condividere i dati raccolti in un’organizzazione di Experience Cloud con un’altra organizzazione di Experience Cloud, ti consigliamo di inviare un pubblico adeguato da un’istanza di Audience Manager a un’altra utilizzando audience marketplace. |
| D: l’inoltro lato server comporterà una fatturazione aggiuntiva in Audience Manager o Analytics? | In Analytics non si verificherà alcuna fatturazione aggiuntiva. In Audience Manager, gli hit inoltrati vengono trattati come qualsiasi altro hit e vengono fatturati.  Per questo motivo è importante non abilitare contemporaneamente l’inoltro lato server e DIL, il che potrebbe causare la doppia fatturazione e la duplicazione dei dati. |

>[!MORELIKETHIS]
>
>* [Inoltro lato server](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md)

