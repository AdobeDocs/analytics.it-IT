---
title: Dominio di riferimento
description: Il dominio generale su cui si trovava un visitatore prima di fare clic per accedere al sito.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 2%

---

# Dominio di riferimento

La [dimensione](overview.md) del &#39;dominio di riferimento&#39; segnala i domini su cui i visitatori fanno clic per raggiungere il sito. Questa dimensione è utile per capire quali siti di terze parti generano più traffico verso la tua. Affinché l’elemento dimensione venga visualizzato, deve esistere un collegamento sul sito esterno e un visitatore deve fare clic su di esso.

>[!IMPORTANT]
>
>Devi configurare i [filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) della suite di rapporti per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace segnala il dominio di riferimento per ogni singola pagina, esclusi i valori che corrispondono ai filtri URL interni. Data Warehouse segnala solo il primo dominio di riferimento della visita e ignora i filtri URL interni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione nell’interfaccia di Analytics e i dati nelle richieste di immagini.

* All&#39;interno dell&#39;implementazione, questa dimensione recupera i dati dalla stringa di query [`r`](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria di AppMeasurement (ad esempio tramite i tag in Adobe Experience Platform), questa dimensione funziona in modo predefinito. Se utilizzi un metodo di raccolta dati esterno a AppMeasurement (ad esempio tramite l&#39;API), accertati di includere il parametro della stringa di query `r` nelle richieste di immagini.
* Nell&#39;interfaccia di Analytics devi configurare i [filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) della suite di rapporti. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

L’Adobe persiste nel dominio di riferimento per una visita. Se un visitatore abbandona e fa clic su un collegamento su un dominio diverso all’interno di una singola visita, il nuovo valore viene aggiornato e persiste per il resto della visita. Se desideri visualizzare solo il valore originale, consulta [Dominio di riferimento originale](original-referring-domain.md).

## Elementi dimensionali

Gli elementi del Dimension includono i domini su cui i visitatori fanno clic per accedere al sito. Se un hit non dispone di dati di riferimento (impostati o persistenti), viene raggruppato sotto l&#39;elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non era presente alcun valore di riferimento, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. L&#39;elemento dimensione `"Typed/Bookmarked"` viene visualizzato anche per i reindirizzamenti che non supportano Analytics. Vedi [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente delle note tecniche.

### Elementi Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine memorizzate nella cache**: i ragni di Google eseguono costantemente la ricerca per indicizzazione del Web e memorizzano le copie delle pagine nel caso in cui vengano portate offline. Queste pagine memorizzate in cache sono disponibili accanto alla maggior parte dei risultati di ricerca facendo clic sul collegamento &quot;Memorizzate in cache&quot;. Quando un utente fa clic su questo collegamento e visualizza il contenuto memorizzato nella cache di Google, `googleusercontent.com` è l&#39;elemento dimensione.
* **Pagine tradotte**: Google offre un servizio di traduzione solido e comodo. Quando si visualizza un sito che utilizza questo servizio, il sito ha origine da `googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
