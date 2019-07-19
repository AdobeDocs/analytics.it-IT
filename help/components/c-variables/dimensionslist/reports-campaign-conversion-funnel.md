---
description: Visualizza medie per le metriche nel gruppo di rapporti Campagne. Le metriche predefinite sono Click-through, Total Sales, Orders e Revenue.
seo-description: Visualizza medie per le metriche nel gruppo di rapporti Campagne. Le metriche predefinite sono Click-through, Total Sales, Orders e Revenue.
seo-title: Funnel di conversione campagna
solution: Analytics
title: Funnel di conversione campagna
topic: Rapporti
uuid: b 0 a 90917-e 4 c 7-40 da -854 e -58649 de 09742
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Funnel di conversione campagna

Visualizza medie per le metriche nel gruppo di rapporti Campagne. Le metriche predefinite sono Click-through, Total Sales, Orders e Revenue.

**[!UICONTROL Campaigns]** &gt; **[!UICONTROL Campaign Conversion Funnel]**

La parte superiore di un grafico funnel visualizza i dati di conversione. In basso vengono visualizzate le statistiche per tutti gli eventi nella parte superiore, basati su Ordini e fino a due altre metriche, Entrate e Unità.

Quando interpretate i dati funnel di conversione, tenete presenti le seguenti informazioni:

* Le statistiche relative ai periodi di tempo correnti potrebbero non essere completate quando visualizzate i dati, il che può influire sulle tendenze da un giorno precedente a quello corrente.
* Quando al funnel non viene applicato alcun filtro, la metrica Visite rappresenta visite di conversione, o visite in cui la variabile della campagna, qualsiasi variabile evar o un evento riuscito è stato avviato. Le visite durante le quali nessuna di queste proprietà sono state trasmesse nei report non sono incluse in questo totale.
* Quando un filtro viene applicato al funnel, la metrica Visite rappresenta le istanze (o i clic). Questo valore è il numero totale di volte in cui la variabile è stata compilata dagli utenti sul sito, escludendo quelle che non soddisfano i requisiti del filtro. Una singola visita può includere istanze multiple.
* È possibile utilizzare livelli più dettagliati sul funnel per riportare numeri più alti rispetto ai livelli omonimi. Ad esempio, puoi vedere più ordini rispetto a click-through, o più pagamenti rispetto alle visualizzazioni del prodotto. Ci sono molti motivi per cui si verifica questa situazione:

   * Se la variabile Codice di tracciamento è impostata su una scadenza lunga del cookie (ad esempio, un mese) e gli utenti eseguono un solo clic e inserisci degli ordini durante il periodo, prima della scadenza del valore del codice di tracciamento, hai più ordini rispetto ai click-through.
   * Se l'utente è in grado di saltare la pagina di visualizzazione del prodotto (come nel caso di una pagina di upselling) o se l'utente è in grado di salvare il carrello e tornare successivamente per completare l'ordine, avete più pagamenti rispetto alle visualizzazioni del prodotto. Se la visualizzazione prodotto viene effettuata prima dell'intervallo di date selezionato e il checkout si verifica in seguito, visualizzerai un checkout e visualizzerai le visualizzazioni di prodotto zero. Se notate tale discrepanza, non viene segnalato un problema di reporting o addirittura di errore di implementazione. Puoi utilizzare questi dati per comprendere in che modo gli utenti interagiscono con il tuo sito, anche se non adatta il funnel come previsto.

