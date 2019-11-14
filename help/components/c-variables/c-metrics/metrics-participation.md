---
description: Le metriche di partecipazione assegnano l'intero credito dagli eventi di successo a tutti i valori di una eVar che sono stati passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzate contribuiscono maggiormente al successo del sito. La partecipazione si basa sulla visita. Tutti i valori eVar di una visita prima e incluso l'hit quando si verifica un evento ricevono il credito di partecipazione, indipendentemente dall'impostazione della scadenza.
solution: Analytics
title: Partecipazione
topic: Metrics
uuid: a7fa791d-0a77-429e-808e-4f97bb9ae5fc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Partecipazione

Le metriche di partecipazione assegnano l'intero credito dagli eventi di successo a tutti i valori di una eVar che sono stati passati durante una visita. Le metriche di partecipazione sono utili per determinare quali pagine, campagne o altri valori di variabili personalizzate contribuiscono maggiormente al successo del sito. La partecipazione si basa sulla visita. Tutti i valori eVar di una visita prima e incluso l'hit quando si verifica un evento ricevono il credito di partecipazione, indipendentemente dall'impostazione della scadenza.

Consulta Partecipazione [del visitatore - Analisi](/help/components/c-variables/c-metrics/metrics-visitor-participation.md) ad hoc per ulteriori informazioni su come Analisi ad hoc utilizza la partecipazione.

Le metriche di partecipazione hanno due impostazioni per l'evento di conversione:

* **Disattivato**: Lo stato predefinito di ciascun evento di conversione. I dati di partecipazione non verranno raccolti per questo evento.
* **Abilitato**: I dati di partecipazione vengono raccolti per questo evento.

> [!NOTE] Potete abilitare la partecipazione per un massimo di 100 eventi personalizzati. Oltre a ciò, potete creare metriche di partecipazione nel generatore Metriche [](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/participation_metric.html) calcolate.

Una volta attivato, le metriche di partecipazione sono automaticamente disponibili in tutti i report di conversione. Tuttavia, le metriche di partecipazione possono essere visualizzate anche in specifici rapporti sul traffico su richiesta. Facoltativamente, potete richiedere che le metriche di partecipazione siano disponibili in alcuni rapporti sul traffico personalizzati.

## Esempio di partecipazione ai ricavi {#section_DAB6C348201B454BB4ED01313AA777AF}

Si supponga che la sequenza seguente:

1. Un utente accede al sito e cerca "shoes".
1. L'utente poi cerca "scarpe da tennis".
1. L'utente fa clic su un collegamento alla pagina del prodotto, aggiunge l'elemento al carrello ed effettua un acquisto da $ 120.

Quando si visualizzano i ricavi nel rapporto Termini di ricerca interna, viene visualizzato quanto segue in base all'allocazione selezionata:

* **Primo**: "shoes" otterrebbe il credito per i $120. "scarpe da tennis" avrebbe preso 0$.
* **Ultimo**: "scarpe da tennis" avrebbe il merito di 120$. "scarpe" avrebbe preso 0$.
* **Lineare**: Ogni campagna riceverebbe 60 dollari di credito.

   La partecipazione è simile all'allocazione lineare, tranne che il credito totale è dato a tutti i valori. Se utilizzate Revenue (Partecipazione) come metrica, l'allocazione viene ignorata. Revenue (Partecipazione) in questo esempio riporta $120 per entrambi i termini di ricerca.

>[!MORELIKETHIS]
>
>* [Calcoli metrica](/help/components/c-variables/c-metrics/metrics-calculations.md)

