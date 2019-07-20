---
description: La maggior parte dei dispositivi mobili accetta i cookie del browser. Tuttavia, se i dispositivi non accettano i cookie, un altro metodo viene utilizzato per identificare in modo univoco i dispositivi wireless.
keywords: Implementazione di Analytics
seo-description: La maggior parte dei dispositivi mobili accetta i cookie del browser. Tuttavia, se i dispositivi non accettano i cookie, un altro metodo viene utilizzato per identificare in modo univoco i dispositivi wireless.
seo-title: Identificare i dispositivi mobili
solution: Analytics
title: Identificare i dispositivi mobili
topic: Sviluppatore e implementazione
uuid: 22587 dd 1-cead -485 b-a 4 d 8-94 dfb 7 cd 9662
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Identificare i dispositivi mobili

La maggior parte dei dispositivi mobili accetta i cookie del browser. Tuttavia, se i dispositivi non accettano i cookie, un altro metodo viene utilizzato per identificare in modo univoco i dispositivi wireless.

Adobe has identified a number of HTTP [subscriber ID headers](../../../implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D) that uniquely identify a majority of mobile devices. Tali intestazioni spesso includono il numero di telefono del dispositivo (o una versione con hash del numero) o altri identificatori. La maggior parte dei dispositivi correnti dispone di una o più intestazioni che identificano in modo univoco il dispositivo e tutti i server di raccolta dati Adobe utilizzano automaticamente tali intestazioni al posto di un ID visitatore.

In a typical image request, a '1' in the path ( `/b/ss/rsid/1`) causes Adobe servers to return a gif image and to attempt to set a persistent [!UICONTROL visitor ID] cookie ( `AMCV_` or `s_vi`). Tuttavia, se il dispositivo viene riconosciuto come dispositivo mobile basato sulle intestazioni HTTP, viene passato un '5 'al posto del '1 ', che indica che deve essere restituito un formato wbmp e che l'elenco delle intestazioni wireless riconosciute (non un cookie) deve essere utilizzato per identificare il dispositivo.

La tabella seguente elenca l'ordine dei metodi ID utilizzati in base al valore del tipo di immagine restituito ('1 'o '5 ') nel percorso:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Ordine dei metodi ID </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> /1/</code> </td> 
   <td colname="col2"> <p>impostazione predefinita: </p> 
    <ul id="ul_E37E9919658A492C92187BAA18D33AB6"> 
     <li id="li_1A9E39C7CFB24C68AA07C8E85D33A858">ID visitatore personalizzato </li> 
     <li id="li_0DC8D17828C848BEB614C6E47C090064">Cookie </li> 
     <li id="li_52706792FAD14F459266E3A672F92EA1">Intestazione ID utente iscritto </li> 
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Indirizzo IP-Userip-Gateway-Gateway </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Device was identified as a wireless device, or <code> /5/</code> was manually sent in the image request: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID visitatore personalizzato </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Intestazione ID utente iscritto </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Indirizzo IP-utente Agente IP-Gateway </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Potete anche trasmettere un'impostazionè1 'o «5» in richieste manuali di immagini, ma tenete presente che questi codici sono mutualmente esclusivi; quindi, sempre passando «5» non viene sfruttato un cookie quando è supportato. Puoi incorporare un tuo meccanismo per determinare se un dispositivo supporta i cookie e, in tal caso, passa un '1 'nell'immagine anziché a '5 '. Il miglioramento della precisione in questa situazione è limitato al numero di dispositivi mobili che supportano i cookie.

## Subscriber ID Headers {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Il metodo ID utente è generalmente più affidabile di un cookie per l'identificazione degli utenti a causa di eliminazione dei cookie, problemi di accettazione dei cookie e problemi di gestione dei cookie del gateway.

È possibile migliorare le modifiche dell'identificazione di un visitatore aggiungendo alla white list quella utilizzata dai visitatori mobili. Per accedere all'ID visitatore del vettore, contatta il gestore per aggiungere il dominio alla white list. Se vi trovate nella white list di un gestore, potete anche accedere alle intestazioni ID sottoscritte che potrebbero non essere in grado di accedere.

Il seguente elenco di intestazioni viene utilizzato per identificare i dispositivi wireless. L'algoritmo per l'elaborazione delle intestazioni è

1. estraete la chiave dell'intestazione HTTP (il nome dell'intestazione, ad esempio "X-Up-Calling-Line-ID")
1. Eliminare tutti i caratteri non alfa (A-Z e a-z)
1. Convertire la chiave dell'intestazione in minuscolo
1. confrontare la fine della chiave con quelle della tabella seguente per trovare una corrispondenza:

| Intestazione | Type (Tipo) | Esempio  |
|---|---|---|
| callinglineid | ID | X-Up-Call-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_ 10448371100_ vmag. mysectular. net |
| clientid | ID | Clientid: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a 2 V 4 Uh 21 XQH 9 ECNN |
| clid | ID | X-Hts_ clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522 ae |
| forwardedfor | ID o indirizzo IP | X-Inoltr@-@ For: 127.0.0.1 |
| msisdn | ID o indirizzo IP | X-Wap-msisdn: 8032618185 |
| clientip | Indirizzo IP | Client-ip: 10.9.41.2 |
| wapipaddr | Indirizzo IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Indirizzo IP | x-huawei-NASIP: 211.139.172.70 |
| userip | Indirizzo IP | Userip: 70.214.81.241 |
| ipaddress | Indirizzo IP | X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Indirizzo IP | X-SUBSCRIBER-INFO: IP = 10.103.132.128 |

Ad esempio «callinglineid» corrisponde a «X-Up-Calling-Line ID» e «nokia-callinglineid». Il tipo di intestazione indica cosa aspettarsi nell'intestazione. L'ordine della priorità dell'intestazione è elencato qui (se è presente un'intestazione "callinglineid", invece di "subno").

You can use [Dynamic Variables](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262) to extract specific values from a header.
