---
description: Prima di attivare questa integrazione, controlla i seguenti elementi rispetto alle distribuzioni di Adobe Analytics® e del software e-mail.
seo-description: Prima di attivare questa integrazione, controlla i seguenti elementi rispetto alle distribuzioni di Adobe Analytics® e del software e-mail.
seo-title: Prima Di Attivare Questa Integrazione
title: Prima Di Attivare Questa Integrazione
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Prima Di Attivare Questa Integrazione {#before-you-activate-this-integration}

Prima di attivare questa integrazione, controlla i seguenti elementi rispetto alle distribuzioni di Adobe Analytics® e del software e-mail.

In questo modo, prima dell'attivazione verranno messe in atto le procedure ottimali appropriate o i prerequisiti necessari, il che porterà a un'integrazione ottimale e di successo.

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Leggi le informazioni seguenti sull’integrazione di questo connettore dati per quanto riguarda Adobe Analytics:

* **** Suite di rapporti specifica: Questa integrazione è specifica per la suite di rapporti. Accertati di aver selezionato la suite di rapporti desiderata prima di attivare l'integrazione e che la suite di rapporti contenga dei dati.
* **** Variabili Analytics disponibili e configurate: Questa integrazione richiede 10 eventi personalizzati e 1 eVar personalizzata. Consulta Variabili [di integrazione di](appfigures-before-activation.md#analytics-integration-variables)Analytics.

* **** Suite di rapporti inizializzata con dati dal vivo: Se stai creando una nuova suite di rapporti per questa integrazione, devi aver ricevuto alcuni (almeno un hit) dati tramite i requisiti appFigures per tracciamento live. Se i dati live non sono stati registrati, la suite di rapporti non sarà pronta a ricevere i dati dell'App Store integrati.

* **** Integrazione esistente con App Store: Questo back di integrazione riempie i dati per 13 mesi. Per evitare sovrapposizioni con eventuali provider di dati dell'App Store precedente, contattate il rappresentante appFigures. Informateli dell'ultima data in cui avete ricevuto i dati. appFigures regolerà di conseguenza il periodo di riempimento del retro.

## appFigures Requirements{#appfigures-requirements}

Leggi le informazioni seguenti sull’integrazione di questo connettore dati per quanto riguarda appFigures:

* **** Cliente corrente di appFigures: Questa integrazione richiede che tu sia un utente di Adobe e appFigures. Se al momento non sei un utente del piano enterprise appFigures, non avrai le informazioni necessarie per completare la procedura guidata di integrazione. Per maggiori informazioni, visita appFigures sul web.
* **** Chiave account appFigures: Per attivare il Connettore dati appFigures è necessaria una chiave di account appFigures. Questa chiave account può essere generata nella sezione "Componenti aggiuntivi". Per ulteriori informazioni, consulta [Configurare l’integrazione](../appfigures-overview/t-appfigures-integration.md) .

* **Finalizzazione** dati: Le informazioni su download, vendite e classifica vengono sincronizzate ogni giorno per i precedenti 7 giorni. Dopo 7 giorni i dati vengono considerati definitivi e non vengono più aggiornati.

## Prezzi{#pricing}

L'integrazione di questi connettori dati include considerazioni di prezzo che è necessario tenere presenti.

Le sezioni che seguono contengono le informazioni seguenti:

### Considerazioni sui prezzi di Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Al momento non sono presenti costi per l'attivazione di questa integrazione. Tuttavia, potrebbe verificarsi un leggero aumento delle chiamate al server a causa dell'importazione delle origini dati.

### considerazioni sui prezzi di appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Al momento non sono presenti tariffe associate a questa integrazione. Questa integrazione è attualmente disponibile solo per i clienti Enterprise. Per ulteriori informazioni, [contatta appFigures](https://appfigures.com/support/contact) .

## Analytics Integration Variables{#analytics-integration-variables}

L'integrazione dei connettori dati per appFigures utilizza le variabili di Analytics per tenere traccia delle varie metriche appFigures.

La tabella seguente descrive le variabili Analytics attivate automaticamente per l'integrazione appFigures.

### Variabili richieste {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] Questa integrazione utilizza variabili dedicate per i dati dell'app store, pertanto non è necessario assegnare variabili ed eventi di commercio personalizzati.

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| eVar | ID oggetto App Store | Importato da appFigures. | Configura questa eVar con scadenza visita, allocazione più recente e sottorelazioni di base. |
| event (numerico) | Download dall'app store | Importato da appFigures. | Numero di download di applicazioni mobili. |
| event (numerico) | Acquisti app store (nell'app) | Importato da appFigures. | Numero di acquisti in-app e iscrizioni. |
| event (numerico) | Valutazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata della metrica appFigures media. Non utilizzato direttamente. |
| event (numerico) | Divisore classificazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata della metrica appFigures media. Non utilizzato direttamente. |
| event (numerico) | Valutazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata della metrica appFigures media. Non utilizzato direttamente. |
| event (numerico) | Divisore valutazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata della metrica appFigures media. Non utilizzato direttamente. |
| event (currency) | Ricavi da app store (in-app) | Importato da appFigures. | L'importo delle entrate in-app meno la tariffa dello store. |
| event (currency) | Ricavi da app store (una tantum) | Importato da appFigures. | Entrate totali dagli acquisti dell'app meno la tariffa dello store. |
| event (currency) | Royalty dell'app store (nell'app) | Importato da appFigures. | Non utilizzato |
| event (currency) | Royalty dell'app store (una tantum) | Importato da appFigures. | Non utilizzato |
