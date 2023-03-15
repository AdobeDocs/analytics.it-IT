---
title: Destinatario che inoltra
description: L’URL in cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Destinatario che inoltra

La dimensione &quot;Destinatario che inoltra&quot; segnala gli URL sui quali si trovavano i visitatori quando facevano clic per raggiungere il sito. Questa dimensione è utile per capire quali URL specifici generano più traffico verso il sito. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sull’URL esterno e un visitatore deve fare clic su di esso.

>[!IMPORTANT]
>
>Devi configurare i [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace segnala il referente per ogni singola pagina, escludendo i valori che corrispondono ai filtri URL interni. Data Warehouse segnala solo il primo referente della visita e ignora i filtri URL interni.

## Popola questa dimensione con i dati

Questa dimensione richiede la configurazione nell’interfaccia di Analytics e i dati nelle richieste di immagini.

* All&#39;interno dell&#39;implementazione, questa dimensione recupera i dati da [`r` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. È possibile utilizzare [`referrer`](/help/implement/vars/page-vars/referrer.md) override variabile per impostarlo manualmente. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), assicurati di includere i `r` parametro della stringa di query nelle richieste di immagini.
* Nell’interfaccia di Analytics, devi configurare i [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Elementi dimensionali

Gli elementi del Dimension includono URL accessibili dal visitatore al sito. Se un hit non ha dati di riferimento, viene raggruppato sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. Il `"Typed/Bookmarked"` viene visualizzato anche un elemento dimensione per i reindirizzamenti che non rientrano in Analytics. Consulta [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente delle note tecniche.

### elementi Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare gli elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine memorizzate in cache**: i ragni di Google esaminano costantemente il web e memorizzano copie delle pagine nel caso in cui vengano portate offline. Queste pagine memorizzate in cache sono disponibili accanto alla maggior parte dei risultati di ricerca facendo clic sul collegamento &quot;Memorizzate in cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato in cache da Google, `webcache.googleusercontent.com` è un elemento dimensionale tipico.
* **Pagine tradotte**: Google offre un servizio di traduzione solido e conveniente. Quando si visualizza un sito utilizzando questo servizio, il sito proviene da `translate.googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
