---
title: Dominio di riferimento
description: Il dominio di primo piano su cui si trovava un visitatore prima di fare clic sul sito.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 0%

---

# Dominio di riferimento

La dimensione &quot;Dominio di riferimento&quot; indica quali domini i visitatori fanno clic attraverso per raggiungere il tuo sito. Questa dimensione è utile per comprendere quali siti di terze parti generano il maggior traffico verso i tuoi. Un collegamento deve esistere sul sito esterno e un visitatore deve fare clic su di esso per visualizzare l’elemento dimensione.

>[!IMPORTANT]
>
>Devi configurare i [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md) per utilizzare questa dimensione. La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

Lo stesso rapporto può mostrare risultati diversi tra Analysis Workspace e Data Warehouse. Analysis Workspace riporta il dominio di riferimento per ogni singola pagina, esclusi i valori che corrispondono a filtri URL interni. Data Warehouse riporta solo il primo dominio di riferimento della visita e ignora i filtri URL interni.

## Popolare questa dimensione con i dati

Questa dimensione richiede la configurazione nell’interfaccia di Analytics e i dati nelle richieste di immagini.

* All’interno dell’implementazione, questa dimensione recupera i dati dalla [`r` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile JavaScript `document.referrer` nel browser. Se utilizzi una libreria AppMeasurement (ad esempio tramite tag in Adobe Experience Platform), questa dimensione funziona automaticamente. Se utilizzi un metodo di raccolta dati al di fuori di AppMeasurement (ad esempio tramite l’API), assicurati di includere il `r` parametro della stringa query nelle richieste di immagini.
* All’interno dell’interfaccia di Analytics, devi configurare i [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md). La mancata configurazione dei filtri URL interni può includere domini interni o impedire la visualizzazione di domini esterni.

L&#39;Adobe persiste nel dominio di riferimento per una visita. Se un visitatore parte e fa clic su un collegamento su un dominio diverso all’interno di una singola visita, il nuovo valore viene aggiornato e persiste per il resto della visita. Se desideri visualizzare solo il valore originale, consulta [Dominio di riferimento originale](original-referring-domain.md).

## Elementi Dimension

Gli elementi di Dimension includono domini che i visitatori cliccano sul tuo sito. Se un hit non ha dati di riferimento (impostati o persistenti), si raggruppa sotto l’elemento dimensione `"Typed/Bookmarked"`. Questo elemento dimensione significa che non vi era alcun valore referente, ad esempio se il visitatore ha digitato manualmente l’indirizzo del browser nella barra degli indirizzi o ha fatto clic su un segnalibro. La `"Typed/Bookmarked"` l’elemento dimensionale viene visualizzato anche per i reindirizzamenti non compatibili con Analytics. Vedi [Reindirizzamenti e alias](/help/technotes/redirects.md) nella guida utente delle note tecniche.

### Articoli di Dimension contenenti `googleusercontent.com`

Gli utenti possono visualizzare elementi dimensionali con il dominio `googleusercontent.com`.

* **Pagine memorizzate nella cache**: I ragni di Google cercano costantemente il web e memorizzano copie delle pagine nel caso in cui vengano portate offline. Le pagine memorizzate nella cache sono disponibili accanto alla maggior parte dei risultati della ricerca facendo clic sul collegamento &quot;Memorizzato nella cache&quot;. Quando un utente fa clic sul collegamento e visualizza il contenuto memorizzato nella cache in Google, `googleusercontent.com` è l’elemento della dimensione.
* **Pagine tradotte**: Google offre un servizio di traduzione robusto e comodo. Quando si visualizza un sito utilizzando questo servizio, viene da `googleusercontent.com`. Questo elemento dimensione viene visualizzato se l’utente fa clic su un collegamento per tornare al contenuto originale.
