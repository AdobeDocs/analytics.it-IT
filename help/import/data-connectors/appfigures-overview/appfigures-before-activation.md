---
description: Prima di attivare questa integrazione, controllate i seguenti elementi rispetto alle distribuzioni di Adobe  Analytics® e del software e-mail.
title: Prima di attivare questa integrazione
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 4%

---


# Prima di attivare questa integrazione {#before-you-activate-this-integration}

Prima di attivare questa integrazione, controllate i seguenti elementi rispetto alle distribuzioni di Adobe  Analytics® e del software e-mail.

In questo modo, prima dell&#39;attivazione verranno messe in atto le procedure ottimali appropriate o i prerequisiti necessari, il che porterà a un&#39;integrazione ottimale e di successo.

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Per informazioni sull&#39;integrazione di questo connettore dati, consultate Adobe  Analytics:

* **Suite di rapporti specifica:** Questa integrazione è specifica per la suite di rapporti. Accertati di aver selezionato la suite di rapporti desiderata prima di attivare l&#39;integrazione e che la suite di rapporti contenga dei dati.
* **Disponibili e configurate  variabili Analytics:** Questa integrazione richiede 10 eventi personalizzati e 1 eVar personalizzata. See [Analytics Integration Variables](appfigures-before-activation.md#analytics-integration-variables).

* **Suite di rapporti inizializzata con dati dal vivo:** Se stai creando una nuova suite di rapporti per questa integrazione, devi aver ricevuto alcuni (almeno un hit) dati tramite i requisiti appFigures per tracciamento live. Se i dati live non sono stati registrati, la suite di rapporti non sarà pronta a ricevere i dati dell&#39;App Store integrati.

* **Integrazione esistente con App Store:** Il back di questa integrazione riempie i dati per 13 mesi. Per evitare sovrapposizioni con eventuali provider di dati dell&#39;App Store precedente, contattate il rappresentante appFigures. Informateli dell&#39;ultima data in cui avete ricevuto i dati. appFigures regolerà di conseguenza il periodo di riempimento del retro.

## appFigures Requirements{#appfigures-requirements}

Leggi le informazioni seguenti sull’integrazione di questo connettore dati per quanto riguarda appFigures:

* **Cliente corrente di appFigures:** Questa integrazione richiede che tu sia un utente di Adobe e appFigures. Se al momento non sei un utente del piano enterprise appFigures, non avrai le informazioni necessarie per completare la procedura guidata di integrazione. Per maggiori informazioni, visita appFigures sul web.
* **Chiave account appFigures:** Per attivare il Connettore dati appFigures è necessaria una chiave di account appFigures. Questa chiave account può essere generata nella sezione &quot;Componenti aggiuntivi&quot;. Per ulteriori informazioni, consulta [Configurare l’integrazione](../appfigures-overview/t-appfigures-integration.md) .

* **Finalizzazione** dati: Le informazioni su download, vendite e classifica vengono sincronizzate ogni giorno per i precedenti 7 giorni. Dopo 7 giorni i dati vengono considerati definitivi e non vengono più aggiornati.

## Prezzi{#pricing}

L&#39;integrazione di questi connettori dati include considerazioni di prezzo che è necessario tenere presenti.

Le sezioni che seguono contengono le informazioni seguenti:

### Considerazioni sui prezzi di Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Al momento non sono presenti costi per l&#39;attivazione di questa integrazione. Tuttavia, potrebbe verificarsi un leggero aumento delle chiamate al server a causa dell&#39;importazione delle origini dati.

### considerazioni sui prezzi di appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Al momento non sono presenti tariffe associate a questa integrazione. Questa integrazione è attualmente disponibile solo per i clienti Enterprise. Per ulteriori informazioni, [contatta appFigures](https://appfigures.com/support/contact) .

## Variabili dell&#39;integrazione di Analytics{#analytics-integration-variables}

L&#39;integrazione dei connettori dati per appFigures utilizza  variabili Analytics per tenere traccia delle varie metriche appFigures.

Nella tabella seguente sono descritte le  variabili Analytics attivate automaticamente per l&#39;integrazione appFigures.

### Variabili richieste {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE]
>
>Questa integrazione utilizza variabili dedicate per i dati dell&#39;app store, pertanto non è necessario assegnare variabili ed eventi di commercio personalizzati.

| Tipo di variabile | Nome | Metodo di compilazione | Descrizione |
|---|---|---|---|
| eVar | ID oggetto App Store | Importato da appFigures. | Configura questa eVar con scadenza visita, allocazione più recente e sottorelazioni di base. |
| event (numerico) | Download dall’app store | Importato da appFigures. | Numero di download di applicazioni mobili. |
| event (numerico) | Acquisti nell&#39;app store (nell&#39;app) | Importato da appFigures. | Numero di acquisti in-app e iscrizioni. |
| event (numerico) | Valutazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata della metrica appFigures media. Non utilizzato direttamente. |
| event (numerico) | Divisore classificazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata dell&#39;appFigures media. Non utilizzato direttamente. |
| event (numerico) | Valutazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata dell&#39;appFigures media. Non utilizzato direttamente. |
| event (numerico) | Divisore valutazione app store | Importato da appFigures. | Utilizzato per definire la metrica calcolata della metrica appFigures media. Non utilizzato direttamente. |
| event (currency) | Ricavi da app store (in-app) | Importato da appFigures. | L&#39;importo delle entrate in-app meno la tariffa dello store. |
| event (currency) | Ricavi da app store (una tantum) | Importato da appFigures. | Entrate totali dagli acquisti dell&#39;app meno la tariffa dello store. |
| event (currency) | Royalty dell&#39;app store (nell&#39;app) | Importato da appFigures. | Non utilizzato |
| event (currency) | Royalty dell&#39;app store (una tantum) | Importato da appFigures. | Non utilizzato |
