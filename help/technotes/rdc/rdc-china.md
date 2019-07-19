---
title: Raccolta dati regionali per Cina
seo-title: Adobe Analytics Cina RDC
description: null
seo-description: null
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Raccolta dati regionali per Cina

La raccolta dati regionali di Adobe (RDC) nella Cina continentale consente ai clienti cinesi di inviare dati direttamente a un Data Collection Center (DCC) in Cina, anziché in altre posizioni globali. Questo migliora i tempi di caricamento delle pagine e la precisione dei dati durante l'invio dei dati ai DCCS fuori dalla Cina.

> [!IMPORTANT] Esiste un costo aggiuntivo associato all'utilizzo del nodo RDC Cina. Prima di implementare la raccolta dati in Cina utilizzando il nodo RDC descritto in questo documento, contattate l'account manager della vostra organizzazione per assicurarvi di avere diritto a questa funzionalità.

## Impostazione del server di tracciamento per Cina

Il tracciamento può essere eseguito in Cina RDC in qualsiasi momento, utile per il servizio. Per qualsiasi proprietà digitale (ad esempio un'app mobile o una pagina Web) che desideri indirizzare alla Cina RDC, modifica il server di tracciamento in:

`<namespace>.sc.adobedc.cn`

Accertarsi di inserire lo spazio nomi corretto. In genere si trova all'inizio del server di tracciamento esistente. For example: `<namespace>.sc.adobedc.cn` - although any namespace value will work. You can also point a non-SSL first-party [CNAME](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/fpcookies_cname.html) record to this new location.

Non impostare il valore trackingserver globalmente, per tutte le proprietà e le aree geografiche, sulla Cina RDC se una parte sostanziale della base cliente è all'esterno della Cina. Trackingserver deve essere impostato sul valore RDC Cina solo per i clienti che si trovano in Cina. In caso contrario, influenzerà in modo negativo la velocità degli utenti esterni alla Cina perché forza la raccolta dei dati a andare in Cina e a tornare indietro per una risposta.

## Identificazione degli utenti in Cina

A prescindere dalla posizione in cui è ospitato la tua proprietà digitale, o dalla lingua utilizzata, i tuoi utenti in Cina riscontreranno miglioramenti se usi il nodo RDC in Cina. Pertanto, è consigliabile determinare quali utenti si trovano in Cina, quindi utilizzare la Cina RDC per tali utenti. Metodi che possono facilitare l'identificazione di questi utenti:

* Utilizzo di una soluzione geoip affidabile. Potresti decidere di utilizzare una soluzione lato server per facilmente integrarti con Adobe Experience Platform Launch (o Gestione tag dati). In questo caso, la posizione può essere determinata includendo un elemento di dati standard nell'oggetto Experience Platform Launch o DTM. Oppure, puoi usare una soluzione geoip lato client. In questo caso, Experience Platform Launch può essere agganciato al codice lato client. Queste soluzioni potrebbero richiedere all'utente di passare al sito localizzato. Questo presenta il rischio che la prima pagina venga conteggiata dal server di tracciamento globale e dalla seconda pagina in Cina, che può dare luogo a una visita doppia. Segui le best practice per le soluzioni geoip. Adobe non è responsabile della precisione della soluzione geoip utilizzata.

* Using site structure or the browser language (the `navigator.language / accept-language` header). Il vantaggio di questo metodo è costi inferiore ed eventualmente prestazioni migliori. Lo svantaggio di questo metodo è rappresentato dal fatto che i visitatori che parlano cinesi all'esterno della Cina sono soggetti a velocità negative.
* Utilizzo di una soluzione di hosting basata in Cina e impostazione di trackingserver in Cina RDC basato sull'host. In questo modo, aumenterà notevolmente anche la velocità.

## Limitazioni correnti

Limiti correnti della Cina RDC:

1. China RDC does not support first party SSL ([s.trackingServerSecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) in your JavaScript), or [Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/reference/ssf.html) to Adobe Audience Manager.
2. Although [A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/a4t.html) and [ECID](https://marketing.adobe.com/resources/help/en_US/mcvid/) are supported, the Target and Demdex domains are not currently in mainland China and will not have the same speed or reliability benefits as those within the China RDC.

## Impegno di Adobe in Cina

Adobe pianifica di continuare costantemente il progresso della Cina RDC e aggiunge in futuro il supporto per funzioni quali SSL di prime parti e inoltri lato server. Adobe prevede inoltre di fornire un dominio demdex (equivalente) in Cina per supportare completamente la raccolta ECID e Audience Manager da Cina. I clienti che iniziano a utilizzare la Cina RDC della Cina sono lieti di continuare a utilizzare questo endpoint di raccolta dati indefinito.
