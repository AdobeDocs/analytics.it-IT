---
title: Identificazione dei visitatori tramite l’API di inserimento dati
description: Identifica i visitatori per la raccolta dati lato server e diretta Adobe Analytics con l’API di inserimento dati.
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 7fcd738b7eb13c13d5f9f23d625287988c803220
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%
---
# Identificazione dei visitatori tramite l’API di inserimento dati

L&#39;[API di inserimento dati](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) invia hit ai server di raccolta Adobe Analytics senza una libreria lato client come AppMeasurement o Web SDK. Poiché non è presente alcuna libreria per gestire l&#39;identità, è possibile impostare l&#39;identificatore del visitatore nel browser per le richieste dirette di immagini o sul server per la raccolta lato server.

>[!NOTE]
>
>Questa pagina descrive l’identità del visitatore. Per la creazione e l&#39;invio delle richieste stesse, consulta la [documentazione API di inserimento dati](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) su Adobe Developer.

Adobe identifica un visitatore utilizzando l&#39;[ordine di operazioni standard](overview.md): `vid`, quindi `aid`, `mid`, `fid` e infine l&#39;indirizzo IP e l&#39;agente utente. Con l&#39;API di inserimento dati in genere si imposta direttamente uno dei tre identificatori seguenti: ECID (`mid`), ID visitatore di Analytics (`aid`) o ID visitatore personalizzato (`vid`).

## Utilizzo dell’ECID (consigliato)

L&#39;ECID (inviato come `mid`) è l&#39;identificatore del visitatore moderno e multisoluzione, condiviso tra Adobe Analytics, Adobe Target e Adobe Audience Manager. Adobe consiglia di utilizzarlo laddove possibile.

Ottieni l&#39;ECID con [Servizio ID visitatore](https://experienceleague.adobe.com/it/docs/id-service/using/home) (`VisitorAPI.js`). In un browser, inizializza il servizio con il tuo ID organizzazione IMS utilizzando [`getInstance`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getinstance), quindi leggi l&#39;ECID con [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid):

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

Invia tale valore su ogni hit come parametro di query `mid`, insieme all&#39;ID organizzazione IMS come parametro `mcorgid` in modo che l&#39;ECID venga risolto correttamente. Se i dati vengono inoltrati ad Audience Manager, invia anche l&#39;area geografica da [`getLocationHint`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getlocationhint) come parametro `aamlh`. Per associare i propri identificatori cliente al visitatore, utilizzare [`setCustomerIDs`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/setcustomerids).

Per la raccolta lato server, ottieni l’ECID sul client e invialo al server per l’invio a ogni hit. Per generare un ECID interamente lato server, senza client, utilizza l&#39;[integrazione diretta](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) del servizio ID.

## Utilizzo dell’ID visitatore di Analytics

L&#39;ID visitatore di Analytics (`aid`) è memorizzato nel cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Quando un hit arriva senza un identificatore, il server di raccolta assegna un `aid` e tenta di impostare un cookie contenente tale identificatore. Alcuni [tipi di risposta](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) includono anche questo identificatore nel corpo della risposta.

* **Lato client (richieste di immagini dirette).** Il browser memorizza il cookie `s_vi` restituito dal server e lo invia ogni volta che viene presentata una richiesta allo stesso dominio di raccolta. Il visitatore viene quindi riconosciuto automaticamente, senza `aid` impostarsi. Poiché questo modello dipende dai cookie, presenta gli stessi limiti di durata di qualsiasi identità basata su cookie. Vedi [Identificazione del visitatore tramite AppMeasurement](appmeasurement.md) per il comportamento dei cookie di prime parti rispetto a quelli di terze parti e [ordine delle operazioni](overview.md) per la scelta dell&#39;identificatore da utilizzare da parte di Adobe. Adobe consiglia di utilizzare un ECID per l’identità durevole.

  >[!NOTE]
  >
  >Se l&#39;ID visitatore viene letto direttamente dal cookie `s_vi`, il cookie racchiude l&#39;ID in dati aggiuntivi (ad esempio, `[CS]v1|<id>[CE]`), quindi estrae solo la porzione `<id>`. La lettura dell’ID da una risposta del visitatore lo restituisce direttamente, senza analisi.

* **Lato server.** Un server non dispone di un file JAR dei cookie, pertanto l&#39;utente archivia e invia nuovamente `aid` personalmente, digitando il codice all&#39;utente:

  1. Cercare `aid` archiviato per l&#39;utente.
  1. Se disponibile, inviarlo come parametro di query `aid`.
  1. In caso contrario, invia l&#39;hit senza identificatore, richiedendo un tipo di risposta che restituisca l&#39;assegnato `aid`, quindi memorizzalo per la prossima volta.

  Il primo hit privo di identificatore è già attribuito al `aid` restituito dal server, pertanto non perdi dati inviandoli prima di avere un ID. Per i tipi di risposta che restituiscono l&#39;ID (`3` per JavaScript, `11` per XML, `10` per JSON) e il formato della richiesta, vedi [Tipo di risposta](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) nella documentazione sull&#39;API di inserimento dati.

  Una richiesta lato server non contiene cookie visitatore e il suo indirizzo IP e il suo agente utente appartengono al mittente. Per attribuire correttamente gli hit, inoltra anche l&#39;indirizzo IP reale del visitatore (intestazione `X-Forwarded-For`) e l&#39;agente utente (intestazione `User-Agent`).

## Utilizzo di un ID visitatore personalizzato

Se disponi già di un identificatore durevole completamente controllato, puoi inviarlo come [`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`) a ogni hit e alla propria identità end-to-end. Questa funzione è adatta alle piattaforme non basate su browser che forniscono un identificatore di dispositivo stabile. Ad esempio, un&#39;applicazione Unity può inviare il proprio identificatore di dispositivo come `vid`.

>[!IMPORTANT]
>
>Usa `vid` solo quando puoi garantire un valore stabile su ogni hit:
>
>* **I browser non sono idonei.** Un browser non dispone di un identificatore durevole che è possibile compilare in modo affidabile, pertanto un set di browser `vid` tende a frammentarsi o a entrare in conflitto. Utilizza invece il modello lato client basato su cookie.
>* **Presta attenzione agli identificatori di autenticazione.** Non disponi di un identificatore prima che un utente acceda e, se l’utente si disconnette, gli hit successivi vengono attribuiti a un visitatore diverso. Queste azioni dividono l’attività di una persona tra più visitatori.

Vedere [`visitorID`](/help/implement/vars/config-vars/visitorid.md) per il formato e i vincoli di un ID visitatore personalizzato.
