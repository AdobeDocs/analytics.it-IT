---
title: Referrer
description: L’URL a cui si trovava un visitatore prima di passare al sito.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%

---


# Referrer

La dimensione &quot;Referente&quot; indica gli URL che i visitatori accedevano quando facevano clic per raggiungere il sito. Questa dimensione è utile per comprendere quali URL specifici generano il maggior traffico verso il sito. Un collegamento deve esistere sull’URL esterno e un visitatore deve fare clic su di esso per visualizzare l’elemento dimensione.

>[!IMPORTANT]
>
>Devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md) interni della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

Lo stesso rapporto può mostrare risultati diversi tra  Analysis Workspace e Data Warehouse.  Analysis Workspace segnala il referente per ogni singola pagina, escludendo i valori che corrispondono ai filtri URL interni. L’Data Warehouse segnala solo il primo referente della visita e ignora i filtri URL interni.

## Compilare questa dimensione con i dati

Questa dimensione richiede la configurazione nell&#39;interfaccia di Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla stringa [`r` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. È possibile utilizzare l&#39;override della [`referrer`](/help/implement/vars/page-vars/referrer.md) variabile per impostarlo manualmente. Se utilizzi una libreria AppMeasurement (ad esempio tramite  Adobe Experience Platform Launch), questa dimensione non è inclusa nella casella. Se utilizzate un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), accertatevi di includere il parametro della stringa di `r` query nelle richieste di immagine.
* Nell&#39;interfaccia di Analytics devi configurare i filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni della suite di rapporti. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Elementi Dimension

Gli elementi di Dimension includono gli URL che i visitatori potranno scorrere sul sito. Se un hit non dispone di dati di riferimento, viene raggruppato sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione indica che non era presente alcun valore di referente, ad esempio se il visitatore digitava manualmente l&#39;indirizzo del browser nella barra degli indirizzi o faceva clic su un segnalibro. L&#39;elemento `"Typed/Bookmarked"` dimensione viene visualizzato anche per i reindirizzamenti non compatibili con Analytics. Consultate [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente di Technotes.

### Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare gli elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine** memorizzate nella cache: I ragni di Google continuamente strisciare il web e memorizzare copie delle pagine nel caso in cui vengono portate offline. Queste pagine memorizzate nella cache sono disponibili accanto alla maggior parte dei risultati della ricerca facendo clic sul collegamento &quot;In cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato nella cache di Google, `webcache.googleusercontent.com` è un elemento dimensione tipico.
* **Pagine** tradotte: Google offre un servizio di traduzione affidabile e conveniente. Quando si visualizza un sito utilizzando questo servizio, il servizio ha origine da `translate.googleusercontent.com`. Questo elemento dimensione viene visualizzato se l&#39;utente fa clic su un collegamento per tornare al contenuto originale.
