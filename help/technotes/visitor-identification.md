---
description: Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.
keywords: Analytics Implementation
subtopic: Visitors
title: Identificare visitatori unici
topic: Developer and implementation
translation-type: tm+mt
source-git-commit: f7c2a366b409995c1fe790db97de5c708882ab3d
workflow-type: tm+mt
source-wordcount: '1902'
ht-degree: 10%

---


# Identificare visitatori unici

Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.

## Ordine di identificazione degli ID visitatore in Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics offre diversi metodi per identificare i visitatori. Nella tabella seguente sono elencati i diversi modi in cui un visitatore può essere identificato in Analytics (in ordine di preferenza):

| Ordine utilizzato | Parametro query (metodo di raccolta) | Presente quando |
|---|---|---|
| 1 | vid (s.visitorID) | s.visitorID è impostato |
| 2 | aid (cookie s_vi) | Il visitatore aveva un cookie s_vi esistente prima dell’implementazione del servizio ID visitatore, oppure era configurato un periodo di tolleranza ID visitatore. |
| 3 | mid (cookie AMCV_ impostato dal servizio ID visitatori di Experience Cloud) | Il browser del visitatore accetta i cookie (di prime parti) |
| 4 | fid (cookie di fallback) | Il browser del visitatore accetta i cookie (di prime parti) |
| 5 | Indirizzo IP, agente utente, indirizzo IP gateway | Il browser del visitatore non accetta i cookie. |

In molti scenari potrebbero essere presenti due o tre ID diversi in una chiamata, ma Analytics utilizzerà il primo ID presente nella tabella precedente come ID visitatore ufficiale. Ad esempio, se imposti un ID visitatore personalizzato (incluso nel parametro di query “vid”), questo ID verrà usato prima degli altri ID visualizzati per lo stesso hit.

>[!NOTE] Ogni ID visitatore di Analytics è associato a un profilo visitatore sui server Adobe. I profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, indipendentemente dalla scadenza dei cookie dell’ID visitatore.

## ID visitatore personalizzato

Puoi implementare un metodo personalizzato per identificare i visitatori impostando la variabile s.visitorID.

Un ID visitatore personalizzato può essere utilizzato sui siti in cui hai un modo univoco per identificare i visitatori. Un esempio è costituito da un ID generato quando un utente accede al sito Web utilizzando un nome utente e una password.

Se hai la capacità di derivare e gestire i [!UICONTROL visitor IDs] tuoi utenti, puoi usare i seguenti metodi per impostare l’ID:

| Metodo | Descrizione |
|---|---|
| [s.visitorID](../implement/vars/config-vars/visitorid.md) , variabile | Se JavaScript è utilizzato nel browser, o se utilizzi un&#39;altra libreria AppMeasurement, puoi impostare l&#39;ID visitatore in una variabile di raccolta dati. |
| Parametro della stringa di query sulla richiesta di immagine | Questo consente di trasmettere il file [!UICONTROL visitor ID] ad Adobe tramite il [!UICONTROL vid query string] parametro su una richiesta di immagine hardcoded. |
| API di inserimento dati | Sui dispositivi che utilizzano protocolli wireless che non accettano JavaScript, potete inviare un post XML contenente l&#39;elemento `<visitorid/>` XML ai server di raccolta Adobe dai vostri server. |
| Riscrittura URL e VISTA | Alcune architetture di distribuzione supportano l&#39;utilizzo della riscrittura URL per mantenere lo stato di sessione quando non è possibile impostare un cookie. In tali casi, i servizi tecnici Adobe possono implementare una [!DNL VISTA] regola che cerca il valore della sessione nell’URL della pagina, quindi formattarlo e inserirlo nei [!UICONTROL visid] valori. |
>[!CAUTION]
>**Gli ID visitatore personalizzati devono essere sufficientemente granulari/univoci **: Un&#39;implementazione non valida degli ID visitatore personalizzati può portare a dati errati e a prestazioni di reporting scadenti. Se l’ID visitatore personalizzato non è univoco o granulare abbastanza, o se non è impostato in modo corretto su un valore predefinito comune come la stringa &quot;NULL&quot; o &quot;0&quot;, gli hit di molti visitatori diversi saranno visualizzati da Adobe Analytics come un singolo visitatore. Questa situazione genera dati errati, con i conteggi dei visitatori troppo bassi e i segmenti che non funzionano correttamente per quel visitatore. Un ID visitatore personalizzato non sufficientemente granulare impedisce inoltre la corretta diffusione dei dati tra i nodi del cluster di reporting di Analytics. In questa situazione, un nodo diventa sovraccarico e non può elaborare le richieste di report in modo tempestivo. Alla fine tutti i report per la suite per report avranno esito negativo.<br>Gli ID visitatore personalizzati implementati male potrebbero non influenzare immediatamente le prestazioni di reporting, perché Analytics spesso può gestire diversi mesi di dati non bilanciati; tuttavia, nel tempo un ID visitatore personalizzato implementato in modo non corretto può diventare problematico al punto da richiedere ad Analytics di disabilitare l&#39;elaborazione per le suite di rapporti interessate.</br><br>Gli implementatori devono seguire le linee guida secondo cui un singolo valore ID visitatore personalizzato non deve mai essere accreditato per più dell&#39;1% del traffico della suite di rapporti. Anche se la linea guida dell&#39;1% è sufficiente per la maggior parte delle suite di rapporti, il limite effettivo che potrebbe causare l&#39;impatto delle prestazioni di reporting potrebbe essere inferiore all&#39;1% per le suite di rapporti molto grandi.</br>

## ID visitatore Analytics

Quando un utente visita il sito, un cookie permanente viene impostato dal server Web Adobe includendo il cookie nella risposta HTTP al browser. Questo cookie viene impostato sul dominio di raccolta dati specificato.

When a request is sent to the Adobe data collection server, the header is checked for the visitor ID cookie ( `s_vi`). Se il cookie è presente nella richiesta, viene utilizzato per identificare il visitatore. Se il cookie non è presente, il server genera un ID visitatore univoco, lo imposta come cookie nell’intestazione della risposta HTTP e lo invia nuovamente insieme alla richiesta. Il cookie viene memorizzato nel browser e inviato di nuovo al server di raccolta dati durante le visite successive al sito, consentendo al visitatore di essere identificato attraverso le visite.

### Record di cookie e CNAME di terze parti {#section_61BA46E131004BB2B75929C1E1C93139}

Alcuni browser, come Apple Safari, non memorizzano più i cookie impostati nell’intestazione HTTP da domini che non corrispondono al dominio del sito Web corrente (si tratta di un cookie utilizzato in un contesto di terze parti o di un cookie di terze parti). Ad esempio, se accedi a `mysite.com` e il server di raccolta dati è `mysite.omtrdc.net` il cookie restituito nell&#39;intestazione HTTP da `mysite.omtrdc.net` potrebbe essere rifiutato dal browser.

Per evitare questo problema, molti clienti hanno implementato record CNAME per i propri server di raccolta dati nell&#39;ambito di un&#39;implementazione [di cookie](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-first-party.html)di prime parti. If a CNAME record is configured to map a hostname on the customer&#39;s domain to the data collection server (for example, mapping `metrics.mysite.com` to `mysite.omtrdc.net`), the visitor ID cookie is stored since the data collection domain now matches the domain of the website. Questo aumenta la probabilità che il cookie dell’ID visitatore venga memorizzato, ma introduce alcuni overhead in quanto è necessario configurare i record CNAME e mantenere i certificati SSL per i server di raccolta dati.

### Cookie su dispositivi mobili {#section_7D05AE259E024F73A95C48BD1E419851}

Quando i dispositivi mobili vengono tracciati utilizzando i cookie, è possibile utilizzare alcune impostazioni per modificare il modo in cui si verifica la misurazione. La durata predefinita del cookie è di 5 anni, ma è possibile utilizzare la variabile param della query CL ( `s.cookieLifetime`) per modificare questa impostazione predefinita. Per impostare la posizione del cookie per le implementazioni del nome, utilizzate la stringa di query CDP `s.cookieDomainPeriods`. Il valore predefinito è 2 se non viene specificato alcun valore. e il percorso predefinito è domain.com. Per le implementazioni che non utilizzano CNAME, il percorso del cookie dell’ID visitatore si trova nel dominio 207.net.

## Servizio identità

Il servizio identità sostituisce il meccanismo legacy di ID visitatore di Analytics ed è richiesto dalla misurazione [!UICONTROL Heartbeat] video, da Analytics per Target e dai servizi e integrazioni di base futuri di Experience Cloud.

Consulta Servizio [](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) identità per la documentazione di prodotto su questo servizio.

## Identificare i dispositivi mobili

La maggior parte dei dispositivi mobili accetta i cookie del browser. Tuttavia, nei casi in cui i dispositivi non accettano i cookie, viene utilizzato un altro metodo per identificare in modo univoco i dispositivi wireless.

Adobe ha identificato una serie di intestazioni di ID di sottoscrittore HTTP che identificano in modo univoco la maggior parte dei dispositivi mobili. Tali intestazioni includono spesso il numero di telefono del dispositivo (o una versione con hash del numero), o altri identificatori. La maggior parte dei dispositivi correnti dispone di una o più intestazioni che identificano in modo univoco il dispositivo, e tutti i server di raccolta dati Adobe utilizzano automaticamente tali intestazioni al posto di un ID visitatore.

In una tipica richiesta di immagine, un &#39;1&#39; nel percorso ( `/b/ss/rsid/1`) fa sì che i server Adobe restituiscano un&#39;immagine gif e tentino di impostare un [!UICONTROL visitor ID] cookie persistente ( `AMCV_` o `s_vi`). Tuttavia, se il dispositivo è riconosciuto come dispositivo mobile basato sulle intestazioni HTTP, viene trasmesso un &quot;5&quot; al posto di &quot;1&quot;, il che indica che deve essere restituita un&#39;immagine in formato wbmp e che il nostro elenco di intestazioni wireless riconosciute (non un cookie) deve essere utilizzato per identificare il dispositivo.

Nella tabella seguente è riportato l’ordine dei metodi ID utilizzati in base al valore del tipo di immagine restituito (&#39;1&#39; o &#39;5&#39;) nel percorso:

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

Potete anche passare un &#39;1&#39; o un &#39;5&#39; nelle richieste di immagini manuali, ma tenete presente che questi codici si escludono a vicenda, pertanto, se si passa sempre &#39;5&#39; non si utilizza un cookie quando è supportato. È possibile includere un meccanismo personalizzato per determinare se un dispositivo supporta i cookie e, in tal caso, passare un &#39;1&#39; nell&#39;immagine anziché un &#39;5&#39;. Il miglioramento della precisione in questa situazione è limitato al numero di dispositivi mobili che supportano i cookie.

### Intestazioni ID sottoscrittore {#section_60D6EAC0D16945A89DD5A7ADF3B8298D}

Il metodo subscriber ID è generalmente più affidabile di un cookie per l’identificazione dell’utente a causa dell’eliminazione dei cookie, dei problemi di accettazione dei cookie e dei problemi di gestione dei cookie del gateway.

Puoi migliorare le modifiche nell’identificazione di un visitatore aggiungendo all’elenco di destinatari consentito dai visitatori del tuo dispositivo mobile. Per accedere all&#39;ID visitatore del vettore, contatta il vettore per aggiungere il tuo dominio al suo elenco consentito. Se ti trovi nell&#39;elenco delle autorizzazioni di un vettore, puoi accedere anche alle intestazioni dell&#39;ID utente iscritto alle quali altrimenti non potrai accedere.

Il seguente elenco di intestazioni viene utilizzato per identificare i dispositivi wireless. L&#39;algoritmo per l&#39;elaborazione delle intestazioni è:

1. estraete la chiave di intestazione HTTP (il nome dell’intestazione, ad esempio, &quot;X-Up-Calling-Line-ID&quot;)
1. rifilare tutti i caratteri non alfa (A-Z e a-z)
1. converti il tasto di intestazione in minuscolo
1. confronta la fine della chiave con quelle nella tabella seguente per trovare una corrispondenza:

| Intestazione | Tipo | Esempio |
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

Ad esempio, &quot;callinglineid&quot; corrisponderebbe a &quot;X-Up-Calling-Line-ID&quot; e &quot;nokia-callinglineid&quot;. Il tipo di intestazione indica cosa aspettarsi nell’intestazione. L’ordine di priorità dell’intestazione è riportato di seguito (se è presente un’intestazione &quot;callinglineid&quot;, viene utilizzato invece di &quot;subno&quot;).

È possibile utilizzare Variabili [](../implement/vars/page-vars/dynamic-variables.md) dinamiche per estrarre valori specifici da un&#39;intestazione.

## Metodi di fallback ID

Se altri metodi ID visitatore non riescono, Adobe imposta un cookie di fallback o utilizza una combinazione di indirizzo IP e agente utente per identificare il visitatore.

### Metodo di identificazione del visitatore fallback {#section_2BA15E4FA6034C3EBF43859406343EB6}

AppMeasurement per JavaScript 1.x e JavaScript H.25.3 (rilasciato a gennaio 2013) contiene un nuovo metodo di identificazione del visitatore fallback per i visitatori il cui browser blocca il cookie impostato dai server di raccolta dati di Adobe (denominato `s_vi`). In precedenza, se non era possibile impostare un cookie, i visitatori venivano identificati utilizzando una combinazione dell&#39;indirizzo IP e della stringa agente utente durante la raccolta dei dati.

With this update, if the standard `s_vi` cookie is unavailable, a fallback cookie is created on the domain of the website with a randomly generated unique ID. This cookie, named `s_fid`, is set with a 2 year expiration and is used as the fallback identification method going forward. Questa modifica dovrebbe comportare una maggiore precisione nei conteggi delle visite e dei visitatori in situazioni in cui non è possibile impostare il cookie principale ( `AMCV_` o `s_vi`).

Il totale delle visite include tutti i visitatori identificati dal `s_vi` cookie o mediante un metodo di fallback.

### Indirizzo IP, agente utente, indirizzo IP gateway {#section_104819D74C594ECE879144FCC5DEF4BF}

. Se non è possibile impostare il cookie `AMCV_` o `s_vi` e i `s_fid` cookie, i visitatori vengono identificati utilizzando una combinazione di indirizzo IP e agente utente.
