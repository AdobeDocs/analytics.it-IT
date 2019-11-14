---
description: Domande frequenti su funzionalità, funzionalità e problemi relativi all'inoltro lato server.
title: Domande frequenti sull'inoltro lato server
uuid: ecd0bc9b-ebf7-414e-88a2-ebba3fd75c92
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Domande frequenti sull'inoltro lato server

Domande frequenti su funzionalità, funzionalità e problemi relativi all'inoltro lato server.

## Server di tracciamento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Domanda | Risposta |
|--- |--- |
| D: Cosa succede se uso l'inoltro lato server legacy basato sul server di tracciamento? | Il metodo di inoltro lato server legacy basato sul server di tracciamento continuerà a inoltrare i dati da Analytics ad Audience Manager. Tuttavia, se desideri inviare segmenti Audience Manager in Analytics, è necessario inoltrare il nuovo server lato suite di rapporti. Inoltre, non vi è alcun problema nell'abilitare una suite di rapporti per l'inoltro lato server sulla configurazione del server di tracciamento: la nuova impostazione di inoltro lato server della suite di rapporti verrà utilizzata ogni volta che si verifica un conflitto. |
| D: Devo migrare l’inoltro lato server legacy basato sul server di tracciamento all’inoltro lato server basato sulla nuova suite di rapporti? | Continueremo a supportare l’inoltro lato server basato sul server di tracciamento per il prossimo futuro. Tuttavia, se desiderate sfruttare l’integrazione da Audience Manager ad Analytics (condivisione segmenti ad Analytics), dovrete abilitare l’inoltro lato server basato sulla suite di rapporti per tutte le suite di rapporti applicabili. Non esiste un motivo urgente per disabilitare l’inoltro lato server legacy basato sul server di tracciamento. |

## Assegnazione di tag e reporting {#section_71391BA901AC47B9A2286281644FF281}

| Domanda | Risposta |
|--- |--- |
| D: Cosa succede se sul sito sono presenti tag per più suite? L'inoltro lato server raddoppierà le chiamate server ad Audience Manager? | No, un hit inoltrato da Analytics ad Audience Manager verrà inoltrato solo una volta ad Audience Manager, indipendentemente dal numero di suite di rapporti nell’hit. Se hai delle origini dati corrispondenti in Audience Manager per ciascuna delle suite di rapporti nell’hit, ciascuna di esse verrà compilata in modo appropriato a partire da tale hit.  Tenete presente, tuttavia, che se utilizzate attualmente la raccolta dati lato client (DIL) e abilitate l'inoltro lato server senza installare il modulo Gestione dell'audience, raddoppierete le chiamate server ad Audience Manager indipendentemente dal numero di suite di rapporti che avete nell'hit Analytics. |
| D: Cosa succede se dispongo di suite di rapporti con tag con più suite mappate su organizzazioni Experience Cloud separate? | Non devi mai inviare dati da un singolo hit di Analytics a due suite di rapporti che appartengono a organizzazioni Experience Cloud separate. In questo caso, l’hit verrà inoltrato solo all’organizzazione Experience Cloud che corrisponde alla configurazione del servizio identità sulla pagina. |
| D: Cosa succede se dispongo di tag con più suite e solo una delle mie suite di rapporti viene mappata sull’organizzazione Experience Cloud e l’altra no? | Inoltreremo l’hit al server di raccolta dati corrispondente per l’organizzazione Experience Cloud nella suite di rapporti mappata. Tuttavia, poiché la suite di rapporti non mappata non avrà un’origine dati associata in Audience Manager, non verranno registrati dati per la suite di rapporti non mappata in Audience Manager. |
| D: Cosa succede se dispongo di una suite di rapporti mappata su più organizzazioni Experience Cloud? | Analytics considererà questa suite di rapporti non mappata e non consentirà l'inoltro lato server per questa suite di rapporti. Contatta l’assistenza clienti per risolvere questo problema di mappatura. |
| D: Il metodo di inoltro lato server basato su suite di rapporti sarà più lento rispetto all’inoltro lato server basato sul server di tracciamento? | No, il tempo di risposta sarà lo stesso. |
| D: Cosa succede se disponiamo di due organizzazioni Experience Cloud (o AAM) e vogliamo condividere i dati tra entrambe le organizzazioni Experience Cloud? Posso inoltrare sul lato server un singolo hit di Analytics a più organizzazioni Experience Cloud? | No. Se devi condividere i dati raccolti in un'organizzazione Experience Cloud con un'altra organizzazione Experience Cloud, ti consigliamo di inviare qualsiasi pubblico applicabile da un'istanza di Audience Manager a un'altra tramite il mercato del pubblico. |
| D: L'inoltro lato server comporterà una fatturazione aggiuntiva in Audience Manager o Analytics? | In Analytics non si verificherà alcuna fatturazione aggiuntiva. In Audience Manager, gli hit inoltrati vengono trattati come qualsiasi altro hit e vengono fatturati.  Per questo motivo è importante non abilitare allo stesso tempo DIL e l'inoltro lato server, che potrebbe causare sia la doppia fatturazione che la duplicazione dei dati. |

>[!MORELIKETHIS]
>
>* [Inoltro lato server](/help/admin/admin/c-server-side-forwarding/ssf.md)

