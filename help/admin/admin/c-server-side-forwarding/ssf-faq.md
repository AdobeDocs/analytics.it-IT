---
description: Domande frequenti sulle caratteristiche, sulle funzionalità e sui problemi correlati all'inoltro lato server.
seo-description: Domande frequenti sulle caratteristiche, sulle funzionalità e sui problemi correlati all'inoltro lato server.
seo-title: Domande frequenti sull'inoltro lato server
title: Domande frequenti sull'inoltro lato server
uuid: ecd 0 bc 9 b-ebf 7-414 e -88 a 2-ebba 3 fd 75 c 92
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Domande frequenti sull'inoltro lato server

Domande frequenti sulle caratteristiche, sulle funzionalità e sui problemi correlati all'inoltro lato server.

## Server di tracciamento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Domanda | Risposta |
|--- |--- |
| Q: Cosa succede se attualmente sto utilizzando l'inoltro lato server basato su server di tracciamento? | Il metodo di inoltro lato server basato su server di tracciamento legacy continuerà a inoltrare i dati da Analytics ad Audience Manager, tuttavia se desideri inviare segmenti Audience Manager in Analytics, è necessario il nuovo inoltro lato server basato su suite di rapporti. Inoltre, non si verificano danni quando si abilita una suite di rapporti per l'inoltro lato server nella configurazione del server di tracciamento. La nuova impostazione di inoltro lato server sarà utilizzata in ogni caso in cui si verifica un conflitto. |
| Q: Devo migrare il mio lato server basato su server di tracciamento legacy, inoltrato al nuovo inoltro lato server basato su suite di rapporti? | Continueremo a supportare l'inoltro lato server basato su server in futuro, tuttavia se desideri sfruttare l'integrazione da Audience Manager ad Analytics (condivisione segmenti in Analytics), dovrai abilitare la nuova funzione lato server basata su suite di rapporti per tutte le suite di rapporti applicabili. Non c'è alcun motivo urgente per disattivare l'inoltro lato server basato su server di tracciamento legacy. |

## Tagging and Reporting {#section_71391BA901AC47B9A2286281644FF281}

| Domanda | Risposta |
|--- |--- |
| Q: Cosa succede se sul sito sono presenti tag per più suite? Will server-side inoltrdue my server calls to Audience Manager? | No, un hit inoltrato da Analytics ad Audience Manager verrà inoltrato una volta ad Audience Manager, indipendentemente dal numero di suite di rapporti nell'hit. Se hai delle sorgenti dati corrispondenti in Audience Manager per ciascuna suite di rapporti nell'hit, ogni elemento verrà popolato appropriatamente da quel singolo hit. Ricorda però che se usi al momento la raccolta dati lato client (DIL) e attivi l'inoltro lato server senza installare il modulo Gestione dell'audience, potrai raddoppiare le chiamate del server ad Audience Manager, indipendentemente dal numero di suite di rapporti che hai nell'hit Analytics. |
| Q: Cosa succede se sono presenti suite di rapporti con tag con più suite mappate a diverse organizzazioni Experience Cloud? | Non devi mai inviare dati da un singolo hit Analytics a due suite di rapporti che appartengono a Experience Cloud Orgs separate, ma se ciò accade, inoltreremo l'hit solo all'organizzazione Experience Cloud corrispondente alla configurazione del servizio identità sulla pagina. |
| Q: Cosa succede se dispongo di tag per più suite e solo una delle mie suite di rapporti viene mappata sulla mia organizzazione Experience Cloud e l'altra su No? | L'hit verrà inoltrato al server di raccolta dati corrispondente per l'organizzazione Experience Cloud nella suite di rapporti mappata. Tuttavia, dato che la suite di rapporti non mappata non avrà un'origine dati associata in Audience Manager, nessun dato verrà registrato per la suite di rapporti senza mappatura in Audience Manager. |
| Q: Cosa succede se ho una suite di rapporti mappata su più organizzazioni Experience Cloud? | Analytics considererà questa suite di rapporti come non mappata e non consentirà l'inoltro lato server per questa suite di rapporti. Contatta l'assistenza clienti per risolvere il problema di mappatura. |
| Q: Il metodo di inoltro lato server basato su suite di rapporti sarà più lento rispetto all'inoltro lato server basato sul server di tracciamento? | No, il tempo di risposta sarà uguale. |
| Q: Cosa succede se sono presenti due istanze Experience Cloud (o AAM) e vuoi condividere i dati tra entrambe le soluzioni Experience Cloud? Posso eseguire il lato server in avanti di un singolo hit Analytics per più organizzazioni Experience Cloud? | No. Se devi condividere i dati raccolti in un'organizzazione Experience Cloud in un'altra organizzazione Experience Cloud, consigliamo di inviare qualsiasi audience applicabile da un'istanza Audience Manager a un'altra mediante l'audience marketplace. |
| Q: L'inoltro lato server darà luogo a qualsiasi ulteriore fatturazione in Audience Manager o Analytics? | In Analytics, non si verifica alcuna fatturazione aggiuntiva. In Audience Manager, gli hit inoltrati sono gestiti come qualsiasi altro hit e sono fatturati. Per questo motivo è importante non abilitare l'inoltro lato server e l'inoltro lato server allo stesso tempo, causando così la doppia fatturazione e la duplicazione dei dati. |

>[!MORE_ LIKE_ THIS]
>
>* [Inoltro lato server](ssf.md#concept_9563FCADF29748928E770EC5221B2685)

