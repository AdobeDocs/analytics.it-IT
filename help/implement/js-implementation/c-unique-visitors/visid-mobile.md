---
description: La maggior parte dei dispositivi mobili accetta i cookie del browser. Tuttavia, se i dispositivi non accettano i cookie, viene utilizzato un altro metodo per identificare in modo univoco i dispositivi wireless.
keywords: Analytics Implementation
solution: Analytics
title: Identificare i dispositivi mobili
topic: Developer and implementation
uuid: 22587dd1-cead-485b-a4d8-94dfb7cd9662
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Identificare i dispositivi mobili

La maggior parte dei dispositivi mobili accetta i cookie del browser. Tuttavia, se i dispositivi non accettano i cookie, viene utilizzato un altro metodo per identificare in modo univoco i dispositivi wireless.

Adobe ha identificato una serie di intestazioni [ID](/help/implement/js-implementation/c-unique-visitors/visid-mobile.md#section_60D6EAC0D16945A89DD5A7ADF3B8298D) sottoscrittore HTTP che identificano in modo univoco la maggior parte dei dispositivi mobili. Tali intestazioni includono spesso il numero di telefono del dispositivo (o una versione con hash del numero), o altri identificatori. La maggior parte dei dispositivi correnti dispone di una o più intestazioni che identificano in modo univoco il dispositivo, e tutti i server di raccolta dati Adobe utilizzano automaticamente tali intestazioni al posto di un ID visitatore.

In una tipica richiesta di immagine, un '1' nel percorso ( `/b/ss/rsid/1`) fa sì che i server Adobe restituiscano un'immagine gif e tentino di impostare un [!UICONTROL visitor ID] cookie persistente ( `AMCV_` o `s_vi`). Tuttavia, se il dispositivo è riconosciuto come dispositivo mobile basato sulle intestazioni HTTP, viene trasmesso un "5" al posto di "1", il che indica che deve essere restituita un'immagine in formato wbmp e che il nostro elenco di intestazioni wireless riconosciute (non un cookie) deve essere utilizzato per identificare il dispositivo.

Nella tabella seguente è riportato l’ordine dei metodi ID utilizzati in base al valore del tipo di immagine restituito ('1' o '5') nel percorso:

<table id="table_07B0E55D5DAA4552A5CBC6937D47A857"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Impostazione </th> 
   <th colname="col2" class="entry"> Ordine del metodo ID </th> 
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
     <li id="li_ECAD713D22314338BB5C92167DC0BB02"> Indirizzo IP - UserAgent-Gateway Indirizzo IP </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> /5/ /5.1/ /5.5/</code> </td> 
   <td colname="col2"> <p>Il dispositivo è stato identificato come dispositivo wireless o <code> /5/</code> è stato inviato manualmente nella richiesta dell’immagine: </p> 
    <ul id="ul_624BEDFA3E1243CF9B42081D8B8EFFFB"> 
     <li id="li_D65761D23B684DB59BC23E92C9098122">ID visitatore personalizzato </li> 
     <li id="li_ADBA806B74CA43EFA8612301E06106C6">Intestazione ID utente iscritto </li> 
     <li id="li_79DFD0DEAA1242C09A03E8134A40F799">Cookie </li> 
     <li id="li_A462B9120FC6443480D62F37D456747E">Indirizzo IP agente utente-indirizzo IP gateway </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Potete anche passare un '1' o un '5' nelle richieste di immagini manuali, ma tenete presente che questi codici si escludono a vicenda, pertanto, se si passa sempre '5' non si utilizza un cookie quando è supportato. Potete includere un meccanismo personalizzato per determinare se un dispositivo supporta i cookie e, in tal caso, trasmettere un '1' nell'immagine anziché un '5'. Il miglioramento della precisione in questa situazione è limitato al numero di dispositivi mobili che supportano i cookie.

## Intestazioni ID sottoscrittore {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Il metodo subscriber ID è generalmente più affidabile di un cookie per l’identificazione dell’utente a causa dell’eliminazione dei cookie, dei problemi di accettazione dei cookie e dei problemi di gestione dei cookie del gateway.

Potete migliorare le modifiche per identificare un visitatore aggiungendo alla white list del vettore utilizzato dai visitatori di dispositivi mobili. Per accedere all'ID visitatore del vettore, contatta il vettore per aggiungere il dominio alla sua white list. Se ti trovi nella white list di un vettore, puoi accedere anche alle intestazioni dell'ID utente iscritto alle quali altrimenti non potrai accedere.

Il seguente elenco di intestazioni viene utilizzato per identificare i dispositivi wireless. L'algoritmo per l'elaborazione delle intestazioni è:

1. estraete la chiave di intestazione HTTP (il nome dell’intestazione, ad esempio "X-Up-Calling-Line-ID")
1. rifilare tutti i caratteri non alfa (A-Z e a-z)
1. converti il tasto intestazione in minuscolo
1. confronta la fine della chiave con quelle nella tabella seguente per trovare una corrispondenza:

| Intestazione | Type (Tipo) | Esempio  |
|---|---|---|
| callinglineid | ID | X-Up-Calling-Line-ID: 8613802423312 |
| subno | ID | x-up-subno: swm_10448371100_vmag.mycingular.net |
| clientid | ID | ID client: eGtUpsqEO19zVHmbOkgaPVI-@sprintpcs.com |
| uid | ID | x-jphone-uid: a2V4Uh21XQH9ECNN |
| clid | ID | X-Hts_clid: 595961714786 |
| deviceid | ID | rim-device-id: 200522ae |
| inoltrato per | ID o indirizzo IP | X-Forwarded-For: 127.0.0.1 |
| msisdn | ID o indirizzo IP | X-Wap-msisdn: 8032618185 |
| clientip | Indirizzo IP | Elemento client-ip: 10.9.41.2 |
| wapipaddr | Indirizzo IP | X-WAPIPADDR: 10.48.213.162 |
| huaweinasip | Indirizzo IP | x-huawei-NASIP: 211.139.172.70 |
| userip | Indirizzo IP | IP utente: 70 214 81 241 |
| ipaddress | Indirizzo IP | Indirizzo X-Nokia-ipaddress: 212.97.227.125 |
| subscriberinfo | Indirizzo IP | X-SUBSCRIBER-INFO: IP=10.103.132.128 |

Ad esempio, "callinglineid" corrisponderebbe a "X-Up-Calling-Line-ID" e "nokia-callinglineid". Il tipo di intestazione indica cosa aspettarsi nell’intestazione. L’ordine di priorità dell’intestazione è riportato di seguito (se è presente un’intestazione "callinglineid", viene utilizzato invece di "subno").

È possibile utilizzare Variabili [](/help/implement/js-implementation/c-variables/dynvars-overview.md) dinamiche per estrarre valori specifici da un'intestazione.
