---
title: Referrer
description: L'URL in cui si trovava un visitatore prima di fare clic sul sito.
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Referrer

La dimensione &quot;Referente&quot; indica gli URL sui quali i visitatori si trovavano facendo clic per raggiungere il sito. Questa dimensione è utile per capire quali URL specifici generano il maggior traffico verso il sito. Un collegamento deve esistere sull’URL esterno e un visitatore deve fare clic su di esso per visualizzare l’elemento dimensione.

>[!IMPORTANT]
>
>Per utilizzare questa dimensione, devi configurare i [filtri URL interni](/help/admin/admin/internal-url-filter-admin.md) della suite di rapporti. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace segnala il referente per ogni singola pagina, escludendo i valori che corrispondono a filtri URL interni. Data Warehouse segnala solo il primo referente della visita e ignora i filtri URL interni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione nell’interfaccia di Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla [`r` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. È possibile utilizzare la sostituzione della variabile [`referrer`](/help/implement/vars/page-vars/referrer.md) per impostarla manualmente. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati all’esterno di AppMeasurement (ad esempio tramite l’API), assicurati di includere il parametro della stringa di query `r` nelle richieste di immagini.
* Nell&#39;interfaccia di Analytics devi configurare i [filtri URL interni della suite di rapporti](/help/admin/admin/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Elementi Dimension

Gli elementi di Dimension includono gli URL che i visitatori fanno clic sul sito. Se un hit non dispone di dati di riferimento, viene raggruppato sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non vi era alcun valore referente, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. L’elemento della dimensione `"Typed/Bookmarked"` viene visualizzato anche per i reindirizzamenti non adatti ad Analytics. Consulta [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente relativa alle note tecniche.

### Elementi di Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine** memorizzate nella cache: I ragni di Google cercano costantemente il web e immagazzinano copie delle pagine nel caso in cui vengano portate offline. Le pagine memorizzate nella cache sono disponibili accanto alla maggior parte dei risultati della ricerca facendo clic sul collegamento &quot;Memorizzato nella cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato in cache da Google, `webcache.googleusercontent.com` è un elemento dimensionale tipico.
* **Pagine** tradotte: Google offre un servizio di traduzione robusto e conveniente. Quando si visualizza un sito utilizzando questo servizio, il sito proviene da `translate.googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
