---
title: Dominio di riferimento
description: Il dominio di primo livello su cui era collocato un visitatore prima di passare al sito.
translation-type: tm+mt
source-git-commit: 0870ace3fea8e3ef650d2de2960006a0d655cf9f
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 0%

---


# Dominio di riferimento

La dimensione &#39;Dominio di riferimento&#39; indica quali domini i visitatori selezionano per raggiungere il tuo sito. Questa dimensione è utile per capire quali siti di terze parti generano il maggior traffico verso i vostri. Un collegamento deve esistere sul sito esterno e un visitatore deve fare clic su di esso per visualizzare l’elemento dimensione.

>[!IMPORTANT]
>
>Devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Lo stesso rapporto può mostrare risultati diversi tra  Analysis Workspace e Data Warehouse.  Analysis Workspace segnala il dominio di riferimento per ogni singola pagina, escludendo i valori che corrispondono ai filtri URL interni. Data Warehouse segnala solo il primo dominio di riferimento della visita e ignora i filtri URL interni.

## Compilare questa dimensione con i dati

Questa dimensione richiede la configurazione nell&#39;interfaccia di Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla stringa [`r` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite  Adobe Experience Platform Launch), questa dimensione non è inclusa nella casella. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `r` query nelle richieste di immagine.
* Nell&#39;interfaccia di Analytics devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

 Adobe persiste il dominio di riferimento per una visita. Se un visitatore lascia e fa clic su un collegamento su un dominio diverso all’interno di una singola visita, il nuovo valore si aggiorna e persiste per il resto della visita. Se si desidera visualizzare solo il valore originale, vedere Dominio [di riferimento](original-referring-domain.md)originale.

## Elementi Dimension

Gli elementi di Dimension includono domini che i visitatori fanno clic sul sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione indica che non era presente alcun valore di referente, ad esempio se il visitatore digitava manualmente l&#39;indirizzo del browser nella barra degli indirizzi o faceva clic su un segnalibro. L&#39;elemento `"Typed/Bookmarked"` dimensione viene visualizzato anche per i reindirizzamenti non compatibili con Analytics. Consultate [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente di Technotes.

### Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare gli elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine** memorizzate nella cache: I ragni di Google continuamente strisciare il web e memorizzare copie delle pagine nel caso in cui vengono portate offline. Queste pagine memorizzate nella cache sono disponibili accanto alla maggior parte dei risultati della ricerca facendo clic sul collegamento &quot;In cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato nella cache di Google, `googleusercontent.com` è l&#39;elemento dimensione.
* **Pagine** tradotte: Google offre un servizio di traduzione affidabile e conveniente. Quando si visualizza un sito utilizzando questo servizio, il servizio ha origine da `googleusercontent.com`. Questo elemento dimensione viene visualizzato se l&#39;utente fa clic su un collegamento per tornare al contenuto originale.
