---
description: Visualizza le medie per le metriche nel gruppo di reporting Campagne. Le metriche predefinite sono Click-through, Vendite totali, Ordini e Entrate.
seo-description: Visualizza le medie per le metriche nel gruppo di reporting Campagne. Le metriche predefinite sono Click-through, Vendite totali, Ordini e Entrate.
seo-title: Funnel di conversione campagna
solution: Analytics
title: Funnel di conversione campagna
topic: Rapporti
uuid: b0a90917-e4c7-40da-854e-58649de09742
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Funnel di conversione campagna

Visualizza le medie per le metriche nel gruppo di reporting Campagne. Le metriche predefinite sono Click-through, Vendite totali, Ordini e Entrate.

**[!UICONTROL Campaigns]** &gt; **[!UICONTROL Campaign Conversion Funnel]**

Nella parte superiore di un elemento grafico funnel sono visualizzati i dati di conversione. Il basso visualizza le statistiche per tutti gli eventi nell'area superiore, in base agli Ordini e fino a due altre metriche, Entrate e Unità.

Quando interpreti i dati funnel di conversione, tieni presente le informazioni seguenti:

* Le statistiche per i periodi di tempo correnti potrebbero non essere completate quando si visualizzano i dati, il che può influenzare le tendenze da un giorno precedente a quello corrente.
* Quando non viene applicato alcun filtro al funnel, la metrica Visite rappresenta le visite di conversione o le visite durante le quali è stata attivata la variabile della campagna, qualsiasi variabile eVar o un evento di successo. Le visite durante le quali nessuna di queste proprietà è stata passata in rapporti non sono incluse in questo totale.
* Quando un filtro viene applicato al funnel, la metrica Visite rappresenta le istanze (o click-through). Questo valore è il numero totale di volte in cui la variabile specificata è stata compilata dagli utenti del sito, escludendo quelle istanze che non soddisfano i requisiti del filtro. Una singola visita può includere più istanze.
* È possibile che i livelli più profondi nell'imbuto riportino numeri più alti di quelli più bassi. Ad esempio, potreste visualizzare più ordini che clic, o più pagamenti rispetto alle viste prodotto. La situazione è dovuta a diversi motivi:

   * Se la variabile Codice di tracciamento è impostata su una scadenza di cookie lunga (ad esempio, un mese) e gli utenti eseguono un solo click-through ma restituiscono più volte e inseriscono gli ordini durante il periodo, prima della scadenza del valore Codice di tracciamento.
   * Se l'utente è in grado di saltare la pagina di visualizzazione del prodotto (come nel caso di una pagina di upselling) o se è in grado di salvare il carrello e di tornare in un secondo momento per completare l'ordine, si dispone di più checkout rispetto alle viste del prodotto. Se la visualizzazione del prodotto si verifica prima dell'intervallo di date selezionato e il checkout si verifica successivamente, vengono visualizzate una visualizzazione di prodotto checkout e zero. Se noti tale discrepanza, non indica alcun problema di segnalazione o nemmeno un errore di implementazione. Puoi piuttosto utilizzare questi dati per comprendere in che modo gli utenti interagiscono con il tuo sito, anche se non rientrano nel funnel come ti aspetti.

