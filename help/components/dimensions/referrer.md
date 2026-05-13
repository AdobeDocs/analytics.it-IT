---
title: Pagina di provenienza
description: L’URL in cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 146f0327-c73c-40f5-8cc1-584e31d163a2
TQID: https://experienceleague.adobe.com/VE1bJD2ah1N9t-fHKc5GC0-pC4YmXEDkCwhVmI5rHZQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 2%

---

# Pagina di provenienza

La [dimensione](overview.md) del &#39;Destinatario che inoltra&#39; segnala gli URL sui quali si trovavano i visitatori quando facevano clic per raggiungere il sito. Questa dimensione è utile per capire quali URL specifici generano più traffico verso il sito. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sull’URL esterno e un visitatore deve fare clic su di esso.

>[!IMPORTANT]
>
>Devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace segnala il referente per ogni singola pagina, escludendo i valori che corrispondono ai filtri URL interni. Data Warehouse segnala solo il primo referente della visita e ignora i filtri URL interni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione nell’interfaccia di Analytics e i dati nelle richieste di immagini.

* All&#39;interno dell&#39;implementazione, questa dimensione recupera i dati dalla stringa di query [`r`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. È possibile utilizzare la sostituzione della variabile [`referrer`](/help/implement/vars/page-vars/referrer.md) per impostarla manualmente. Se utilizzi una libreria AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno ad AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `r` nelle richieste di immagini.
* Nell&#39;interfaccia di Analytics devi configurare i [filtri URL interni](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) della suite di rapporti. La mancata configurazione dei filtri URL interni può includere URL interni o impedire la visualizzazione di URL esterni.

## Elementi dimensionali

Gli elementi di Dimension includono URL accessibili dal visitatore al sito. Se un hit non dispone di dati di riferimento, viene raggruppato sotto l&#39;elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. L&#39;elemento dimensione `"Typed/Bookmarked"` viene visualizzato anche per i reindirizzamenti che non supportano Analytics. Vedi [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente delle note tecniche.

### Elementi Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine memorizzate nella cache**: i ragni di Google scansionano costantemente il Web e memorizzano le copie delle pagine nel caso in cui vengano portate offline. Queste pagine memorizzate in cache sono disponibili accanto alla maggior parte dei risultati di ricerca facendo clic sul collegamento &quot;Memorizzate in cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato nella cache di Google, `webcache.googleusercontent.com` è un tipico elemento dimensione.
* **Pagine tradotte**: Google offre un servizio di traduzione solido e comodo. Quando si visualizza un sito che utilizza questo servizio, il sito ha origine da `translate.googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
