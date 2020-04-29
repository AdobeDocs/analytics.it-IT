---
description: Le metriche di partecipazione assegnano l'intero credito dagli eventi di successo a tutti i valori di una eVar che sono stati passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzate contribuiscono maggiormente al successo del sito. La partecipazione si basa sulla visita. Tutti i valori eVar di una visita prima e incluso l'hit quando si verifica un evento ricevono il credito di partecipazione, indipendentemente dall'impostazione della scadenza.
title: Partecipazione
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Partecipazione

Le metriche di partecipazione assegnano l&#39;intero credito dagli eventi di successo a tutti i valori di una eVar che sono stati passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzate contribuiscono maggiormente al successo del sito. La partecipazione si basa sulla visita. Tutti i valori eVar di una visita prima e incluso l&#39;hit quando si verifica un evento ricevono il credito di partecipazione, indipendentemente dall&#39;impostazione della scadenza.

Consulta Partecipazione [del visitatore - Analisi](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) ad hoc per ulteriori informazioni su come Analisi ad hoc utilizza la partecipazione.

Le metriche di partecipazione hanno due impostazioni per l&#39;evento di conversione:

* **Disattivato**: Lo stato predefinito di ciascun evento di conversione. I dati di partecipazione non verranno raccolti per questo evento.
* **Abilitato**: I dati di partecipazione vengono raccolti per questo evento.

>[!NOTE] Potete abilitare la partecipazione per un massimo di 100 eventi personalizzati. Oltre a ciò, potete creare metriche di partecipazione nel generatore Metriche [](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/participation-metric.html) calcolate.

Una volta attivato, le metriche di partecipazione sono automaticamente disponibili in tutti i report di conversione. Tuttavia, le metriche di partecipazione possono essere visualizzate anche in specifici rapporti sul traffico su richiesta. Facoltativamente, potete richiedere che le metriche di partecipazione siano disponibili in alcuni rapporti sul traffico personalizzati.

## Esempio di partecipazione ai ricavi {#section_DAB6C348201B454BB4ED01313AA777AF}

Si supponga che la sequenza seguente:

1. Un utente accede al sito e cerca &quot;shoes&quot;.
1. L&#39;utente poi cerca &quot;scarpe da tennis&quot;.
1. L&#39;utente fa clic su un collegamento alla pagina del prodotto, aggiunge l&#39;elemento al carrello ed effettua un acquisto da $ 120.

Quando si visualizzano i ricavi nel rapporto Termini di ricerca interna, viene visualizzato quanto segue in base all&#39;allocazione selezionata:

* **Primo**: &quot;shoes&quot; otterrebbe il credito per i $120. &quot;scarpe da tennis&quot; avrebbe preso 0$.
* **Ultimo**: &quot;scarpe da tennis&quot; avrebbe il merito di 120$. &quot;scarpe&quot; avrebbe preso 0$.
* **Lineare**: Ogni campagna riceverebbe 60 dollari di credito.

   La partecipazione è simile all&#39;allocazione lineare, tranne che il credito totale è dato a tutti i valori. Se utilizzate Revenue (Partecipazione) come metrica, l&#39;allocazione viene ignorata. Revenue (Partecipazione) in questo esempio riporta $120 per entrambi i termini di ricerca.

>[!MORELIKETHIS]
>
>* [Calcoli metrica](/help/components/c-variables/c-metrics/metrics-calculations.md)

