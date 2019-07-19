---
description: Di seguito sono riportati alcuni insidie comuni quando si utilizza Generatore di report con Power BI.
seo-description: Di seguito sono riportati alcuni insidie comuni quando si utilizza Generatore di report con Power BI.
seo-title: Risoluzione dei problemi dell'integrazione Power BI
title: Risoluzione dei problemi dell'integrazione Power BI
uuid: c 1 e 7 e 164-4 bc 6-4513-9332-92 c 53 be 021 cc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Risoluzione dei problemi dell'integrazione Power BI

Di seguito sono riportati alcuni insidie comuni quando si utilizza Generatore di report con Power BI.

## Passaggio 1: Failure to publish to Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

I documenti di lavoro pianificati che richiedono la pubblicazione Power BI dipendono dai servizi Power BI per essere operativi. Due motivi principali per un errore di pubblicazione sono:

* Power BI services may be down.
* L'utente che ha pianificato la cartella di lavoro non dispone più di credenziali account Microsoft valide.

Ogni attività pianificata per Generatore di report ha tre tentativi per esecuzione pianificata:

* Dopo il primo tentativo non riuscito, riceverete questo messaggio: " Impossibile pubblicare questa cartella di lavoro pianificata su Microsoft Power BI. Riproveremo più tardi.»
* Dopo il secondo tentativo non riuscito, non viene visualizzato alcun messaggio.
* Dopo il terzo tentativo non riuscito, riceverete questo messaggio: " Impossibile pubblicare questa cartella di lavoro su Power BI. "

## Passaggio 2: Broken visualizations in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Di seguito sono illustrati i motivi principali per visualizzare visualizzazioni interrotte dopo la pubblicazione delle richieste di Generatore di report a Power BI:

* Hai modificato una richiesta in Generatore di report, ad esempio la modifica delle metriche o delle dimensioni e la successiva pubblicazione su Power BI. Le richieste di modifica possono interrompere le visualizzazioni.
* Hai eliminato una richiesta utilizzata in una visualizzazione.

