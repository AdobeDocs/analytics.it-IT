---
title: Riferimenti
description: Mostra l’URL dell’hit precedente, se l’hit si trovava all’esterno del sito.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# Riferimenti

La dimensione &#39;Referente&#39; mostra l&#39;URL dal quale i visitatori sono venuti prima che arrivassero sul sito. Ad esempio, se un visitatore fa clic su un collegamento da `example.com/example-page.html` e arriva sul sito, `example.com/example-page.html` è il referente se non è definito come parte del dominio.

Questa dimensione richiede la configurazione dei filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. Se non configurate filtri URL interni, Adobe Analytics considera tutti i domini come interni al sito.

## Proprietà dimensione

* Per impostazione predefinita, questa dimensione utilizza l&#39;allocazione più recente.
* Questa dimensione scade dopo la visita per impostazione predefinita.
* Questa dimensione è soggetta al limite univoco di 500 k prima di raggruppare i valori di dimensione in (traffico basso). Data Warehouse non ha un limite univoco.
* Se per una metrica non è presente alcun valore di riferimento, questo viene raggruppato in `Typed/Bookmarked`.
* Questa dimensione viene generalmente impostata sul primo hit della visita, ma può essere impostata a metà visita.

## Risoluzione dei problemi

**D: Perché viene visualizzato`googleusercontent.com`come valore di dimensione?**

A: [Google](https://about.google/) usa il dominio `googleusercontent.com` per il contenuto ospitato. Il contenuto ospitato include:

* **Pagine** memorizzate nella cache: I ragni di Google costantemente navigano sul web e salvano le pagine web nel caso in cui siano portate offline o altrimenti non disponibili. Queste pagine memorizzate nella cache sono disponibili accanto a tutti i risultati della ricerca facendo clic sul collegamento &quot;Cache&quot; da una delle pagine dei risultati della ricerca di Google. Quando un utente fa clic su questo collegamento, guarda il contenuto originale sul sito, `googleusercontent.com` viene elencato come dominio di riferimento. Queste pagine hanno il sottodominio `webcache.googleusercontent.com`.
* **Pagine** tradotte: Google offre un servizio di traduzione affidabile e conveniente. Quando si visualizza un sito utilizzando questo servizio, il servizio ha origine da `googleusercontent.com`. La dimensione del referente mostra gli URL di questo dominio se l&#39;utente fa clic su un collegamento per tornare al contenuto originale. Queste pagine hanno il sottodominio `translate.googleusercontent.com`.
