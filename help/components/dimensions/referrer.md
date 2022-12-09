---
title: Destinatario che inoltra
description: L'URL in cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Destinatario che inoltra

La dimensione &quot;Referente&quot; indica gli URL sui quali i visitatori si trovavano facendo clic per raggiungere il sito. Questa dimensione è utile per capire quali URL specifici generano il maggior traffico verso il sito. Un collegamento deve esistere sull’URL esterno e un visitatore deve fare clic su di esso per visualizzare l’elemento dimensione.

>[!IMPORTANT]
>
>Devi configurare i [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace segnala il referente per ogni singola pagina, escludendo i valori che corrispondono a filtri URL interni. Data Warehouse segnala solo il primo referente della visita e ignora i filtri URL interni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione nell’interfaccia di Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla [`r` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. È possibile utilizzare [`referrer`](/help/implement/vars/page-vars/referrer.md) override della variabile per impostarla manualmente. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il `r` parametro della stringa query nelle richieste di immagini.
* All’interno dell’interfaccia di Analytics, devi configurare i [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Elementi dimensionali

Gli elementi di Dimension includono gli URL che i visitatori fanno clic sul sito. Se un hit non ha dati di riferimento, si raggruppa sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non vi era alcun valore referente, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. La `"Typed/Bookmarked"` l’elemento dimensionale viene visualizzato anche per i reindirizzamenti non compatibili con Analytics. Vedi [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente delle note tecniche.

### Articoli di Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine memorizzate nella cache**: I ragni di Google cercano costantemente il web e memorizzano copie delle pagine nel caso in cui vengano portate offline. Le pagine memorizzate nella cache sono disponibili accanto alla maggior parte dei risultati della ricerca facendo clic sul collegamento &quot;Memorizzato nella cache&quot;. Quando un utente fa clic sul collegamento e visualizza il contenuto memorizzato nella cache in Google, `webcache.googleusercontent.com` è un elemento dimensionale tipico.
* **Pagine tradotte**: Google offre un servizio di traduzione robusto e comodo. Quando si visualizza un sito utilizzando questo servizio, viene da `translate.googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
