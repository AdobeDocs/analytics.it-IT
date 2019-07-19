---
description: Le metriche di partecipazione assegnano il credito completo agli eventi di successo a tutti i valori di un evar passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzati contribuiscono maggiormente al successo del sito. La partecipazione è basata su visite. Tutti i valori evar in una visita prima e incluso l'hit quando si verifica un evento ricevono credito di partecipazione a prescindere dall'impostazione di scadenza.
seo-description: Le metriche di partecipazione assegnano il credito completo agli eventi di successo a tutti i valori di un evar passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzati contribuiscono maggiormente al successo del sito. La partecipazione è basata su visite. Tutti i valori evar in una visita prima e incluso l'hit quando si verifica un evento ricevono credito di partecipazione a prescindere dall'impostazione di scadenza.
seo-title: Partecipazione
solution: Analytics
title: Partecipazione
topic: Metrics (Metriche)
uuid: a 7 fa 791 d -0 a 77-429 e -808 e -4 f 97 bb 9 ae 5 fc
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Partecipazione

Le metriche di partecipazione assegnano il credito completo agli eventi di successo a tutti i valori di un evar passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzati contribuiscono maggiormente al successo del sito. La partecipazione è basata su visite. Tutti i valori evar in una visita prima e incluso l'hit quando si verifica un evento ricevono credito di partecipazione a prescindere dall'impostazione di scadenza.

See [Visitor Participation - Ad Hoc Analysis](../../../components/c-variables/c-metrics/metrics-visitor-participation.md#concept_ACBAE3626B224D9683257B5F73E0FB4A) for more information about how Ad Hoc Analysis uses participation.

Le metriche di partecipazione hanno due impostazioni per evento di conversione:

* **Disattivato**: Lo stato predefinito di ogni evento di conversione. I dati di partecipazione non verranno raccolti per questo evento.
* **Attivato**: I dati di partecipazione vengono raccolti per l'evento.

>[!NOTE]
>
>Potete abilitare la partecipazione fino a 100 eventi personalizzati. Beyond that, you can create participation metrics in the [Calculated Metrics](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html) builder.

Una volta abilitata, le metriche di partecipazione sono automaticamente disponibili in tutti i rapporti sulla conversione. Tuttavia, anche le metriche di partecipazione possono essere visualizzate in report traffico specifici su richiesta. Facoltativamente, puoi richiedere metriche di partecipazione in determinati rapporti sul traffico personalizzato.

## Revenue Participation Example {#section_DAB6C348201B454BB4ED01313AA777AF}

Immagina la sequenza seguente:

1. Un utente passa al sito e cerca "scarpe".
1. L'utente quindi cerca «scarpe da tennis».
1. L'utente fa clic su un collegamento alla pagina del prodotto, aggiunge l'elemento al carrello ed effettua un acquisto da $ 120.

Quando visualizzi Revenue (Entrate) nel report Internal Search Terms (Termini di ricerca interni), visualizzerai quanto segue in base all'allocazione selezionata:

* **Prima**: «scarpe» ottieni credito per $ 120. «scarpe da tennis» otterrebbe $ 0.
* **Ultimo**: «scarpe da tennis» ottenere credito per $ 120. «scarpe» otterrebbe $ 0.
* **Lineare**: Ogni campagna ha un credito di $ 60.

   La partecipazione è simile all'allocazione lineare, ad eccezione del credito completo a tutti i valori. Se utilizzate Revenue (Entrate) (Partecipazione) come metrica, l'allocazione viene ignorata. Revenue (Partecipazione) in questo esempio restituirebbero $ 120 per entrambi i termini di ricerca.

>[!MORE_ LIKE_ THIS]
>
>* [Calcoli metriche](/help/components/c-variables/c-metrics/metrics-calculations.md)

