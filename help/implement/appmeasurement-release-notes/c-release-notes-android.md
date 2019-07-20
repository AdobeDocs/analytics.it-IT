---
description: Note sulla versione cumulative per la libreria mobile Android.
seo-description: Note sulla versione cumulative per la libreria mobile Android.
seo-title: Android
solution: Analytics, Marketing Cloud
subtopic: Note sulla versione
title: Android
topic: Sviluppatore e implementazione
uuid: 32232 d 28-3459-4 f 78-bb 00-ca 3163 c 63461
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Android{#android}

Note sulla versione cumulative per la libreria mobile Android.

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivare la registrazione di debug.

Mobile library downloads are available on [GitHub](https://github.com/Adobe-Marketing-Cloud/mobile-services) and on [Developer Connection](https://marketing.adobe.com/developer/gallery/app-measurement-for-android-1).

## Version 4.13.4 {#section_E4743079D8E64B9C890180A025C94B44}

The [!DNL Android] SDK version 4.13.4 (Feb 16, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C0197701CB9B45E596818AF0BE5AC4F2"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Messaggistica in-app </p> </td> 
   <td colname="2"> <p> È stato corretto un problema che impediva l’utilizzo della versione corretta dell’app al momento dell’individuazione del tipo di pubblico. Questo problema si verificava se l’utente aveva effettuato un aggiornamento della versione dell’app senza un nuovo lancio Ciclo di vita. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Ciclo di vita </p> </td> 
   <td colname="2"> <p> È stato corretto un problema che poteva impedire il corretto reporting dell’aggiornamento della versione dell’app. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisizione </p> </td> 
   <td colname="2"> <p> È stato corretto un bug a causa del quale i collegamenti profondi differiti non venivano attivati al primo avvio. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.3 {#section_1C235192E9FB46E2A651017C1CF24A7F}

The [!DNL Android] SDK version 4.13.3 (Jan 19, 2017) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_5E744C8C9D064E999EB5055A8E3A99C5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Messaggistica in-app </p> </td> 
   <td colname="2"> <p> È stato risolto un problema che impediva la visualizzazione di messaggi di avviso senza pulsante click-through. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Analytics</span> </p> </td> 
   <td colname="2"> <p> è stata migliorata la gestione dell’accesso in sola lettura al database. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Collegamenti universali </p> </td> 
   <td colname="2"> <p> È stato corretto un bug a causa del quale i collegamenti profondi differiti allegati ai dati di acquisizione venivano attivati per avvii consecutivi. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.2 {#section_CEA2FF01EA414A32A8D164D981FBE71F}

The [!DNL Android] SDK version 4.13.2 (Nov 10, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Servizio ID visitatori </p> </td> 
   <td colname="2"> <p>Aggiunta della marca temporale e dell’ID Marketing Cloud dell’organizzazione al parametro <code>adobe_mc</code>. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Collegamenti profondi </p> </td> 
   <td colname="2"> <p>Quando si chiama <code>trackAdobeDeepLink</code>, le variabili con i prefissi "<code>adb</code>" e "<code>ctx</code>" vengono ora gestite correttamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.13.1 {#section_647C43BA95A3485381AC2E8DEAA6D2E4}

The [!DNL Android] SDK version 4.13.1 (Oct 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_1D1AFD90F8BB4F59869FD417ED9C45AB"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisizione </p> </td> 
   <td colname="2"> The SDK now supports custom acquisition data to be returned appropriately by <code> AdobeDataCallback</code> invocations. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Acquisizione </p> </td> 
   <td colname="2"> The SDK now stores Google Play Referrer variables and custom variables and returns them appropriately in <code> AdobeDataCallback</code> invocations. </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Target </p> </td> 
   <td colname="2"> Visitor ID Service parameters are now passed in <span class="keyword"> Target</span> requests via <code> mboxParams</code>. </td> 
  </tr> 
 </tbody> 
</table>

**Correzioni di bug**

* È stato corretto un bug a causa del quale le richieste di dati al telefono venivano talvolta timeout.

## Version 4.13.0 {#section_03370D8F93AE4B7A81C4B03910086556}

The [!DNL Android] SDK version 4.13.0 (Sept 15, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_AACF8B9BE89A4057B0396F487F82CF99"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Messaggistica in-app </p> </td> 
   <td colname="2"> <p>Nuova funzionalità: Aggiunto un nuovo tipo di messaggio che apre un URI di collegamento profondo. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Tracciamento dei collegamenti profondi (deep link) </p> </td> 
   <td colname="2"> <p>Nuova funzionalità: Aggiunta la possibilità di abilitare il tracciamento dei collegamenti profondi differiti 3 rd party. </p> <p> 
     <ul id="ul_DA54F09098A546B6A320E6B9F2937DAD"> 
      <li id="li_B483AEBE02F34E21B2CC731FC77448E8"><code> processAdobeDeepLink</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.12.0 {#section_3FBC1C24267141C08A60E288662160D8}

The [!DNL Android] SDK version 4.12.0 (Aug 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_3BDD15254859475CBE5E27870619FF3A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Servizio ID visitatori </p> </td> 
   <td colname="2"> <p> Aggiunto nuovo metodo per aggiungere l'identità dei visitatori a un dato URL per trasferire l'identità a un'implementazione basata sul Web. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.11.0 {#section_34B295F3697F4AD6B6A6B8DD70AD1ECA}

The [!DNL Android] SDK version 4.11.0 (June 22, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C3DC3890E81744828DE8946AE8067E1A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Metodi di Target </p> </td> 
   <td colname="2"> <p>You can now use the following new <span class="keyword"> Target</span> method: </p> <p> 
     <ul id="ul_D0594A9ABFD8448186DED87599A0E50E"> 
      <li id="li_A4B0ECDF200C438BB1AB24D613453A68"><code> loadRequest</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.10.0 {#section_262928ABA971490EA6B8E277E17BDD89}

The [!DNL Android] SDK version 4.10.0 (May 20, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E6B19BD9903A41D9AAF0035CD66756B5"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Metodi di Target </td> 
   <td colname="2"> <p>Added new syntax and example for the <code> loadRequest</code> method. </p> <p>Added the following new <span class="keyword"> Target</span> methods: </p> <p> 
     <ul id="ul_B32C3B3931764F21948E36384B775642"> 
      <li id="li_3421E7F78F3A4DDA8FF004903FC8C75E">setThirdPartyID </li> 
      <li id="li_0836075699C5480EB3D6B742FCF6D508">getThirdPartyID </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.9.0 {#section_7393D3A5EA61431D9E7C07ECE176D17C}

The [!DNL Android] SDK version 4.9.0 (May 5, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_7D893A6E12554E9CA9AF2B03DA4C1A4B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Impostazioni di esclusione e privacy </td> 
   <td colname="2"> <p>Puoi implementare collegamenti profondi nelle applicazioni per indirizzare gli utenti verso destinazioni di collegamenti Web o app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.3 {#section_9BB3DFBECC434AC6B3D7C18AA9BC895C}

The [!DNL Android] SDK version 4.8.3 (February 18, 2016) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_6DE145BC30154B9FADCE584A9737018D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Impostazioni di esclusione e privacy </td> 
   <td colname="2"> <p>Starting with <span class="keyword"> Android</span> SDK 4.8.3, privacy settings set via the <code> setPrivacyStatus</code> method affect activity from <span class="keyword"> Analytics</span>, <span class="keyword"> Target</span> , and <span class="keyword"> Audience Manager</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.8.0 {#section_18FA091344644B43AA0E226241FF90DC}

The [!DNL Android] SDK version 4.8.0 (November 2, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_C47B9AEB2BB649CFA1D5CF04093B497B"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> Nuovi metodi del servizio ID visitatore Marketing Cloud </td> 
   <td colname="2"> <p>Sono stati aggiunti i seguenti metodi: </p> 
    <ul id="ul_6B85F8A4826642BEB373225CA760D799"> 
     <li id="li_72B94B8CECB94229827BFCB06671DFC9"><code> syncIdentifer</code> </li> 
     <li id="li_CD0C6B6CEA064FDD8B109E01AEC63F5C"><code> syncIdentifiers</code> </li> 
     <li id="li_620A2D94F97A4451919F0867CA82B25D"><code> getIdentifiers</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> Nuova variabile di configurazione ADBMobile JSON </td> 
   <td colname="2"> <p>È stata aggiunta la seguente variabile: </p> 
    <ul id="ul_7FF76521C59343A4ABC9573C3CD5DC38"> 
     <li id="li_1381E3EF082B4D7DBD131D8EC62F94D2"><code> analyticsForwardingEnabled</code> </li> 
    </ul> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"><span class="keyword"> Metodi</span> plug-in phonegap </td> 
   <td colname="2"> <p>Sono stati aggiunti i seguenti metodi </p> <p><b>Metodi di Configurazione</b> </p> <p> 
     <ul id="ul_98C5E7B5C79446EEA00F0E7CBC213301"> 
      <li id="li_B403C06E57A0450CBB4ABAD45170C681">setPushIdentifier </li> 
      <li id="li_6D76C40601544D4FA13FD44F390C83CE">setAdvertisingIndentifier </li> 
      <li id="li_7D03005DBD9E4AC7BB78BA162CDC8153">keepLifecycleSessionAlive </li> 
      <li id="li_3DDE07508B764E679AF2ACECC4D935CB">trackingSendQueuedHits </li> 
     </ul> </p> <p><b>Metodi di Target</b> </p> <p> 
     <ul id="ul_9B6002F5642B4D888FBD0A8D44EF32DB"> 
      <li id="li_5C1C9EA770E048E48723528F346712B4">targetClearCookies </li> 
     </ul> </p> <p><b>Metodi di Acquisizione</b> </p> <p> 
     <ul id="ul_2015BFF019E64D5685A25E20D4B4A79B"> 
      <li id="li_D450F60189904C43BDAC5D658324AEAA">acquisitionCampaignStartForApp </li> 
     </ul> </p> <p><b>Metodi di Audience Manager</b> </p> <p> 
     <ul id="ul_7D5F339A1A004593AE1D5C26A5A495C5"> 
      <li id="li_2F44037A508D49308F42961FDFB6486C">audienceGetVisitorProfile </li> 
      <li id="li_4F8F43C875384A74ADD48D4197C2ACFD">audienceGetDpuuid </li> 
      <li id="li_B38B6700AF2F4B9FA80CC6774B5B14E7">audienceGetDpid </li> 
      <li id="li_12579B472B404ABAA12DFBDBB22A0C30">audienceSetDpidAndDpuuid </li> 
      <li id="li_2CA997AF9FE241FD961BB0A9B50E14D9">audienceSignalWithData </li> 
      <li id="li_3545CB51B6B7409D8CE2B97E291267E6">audienceReset </li> 
     </ul> </p> <p><b>Metodi del servizio ID visitatori</b> </p> <p> 
     <ul id="ul_746B8A36715D4075B11C42F9FE82F538"> 
      <li id="li_A15AFA632E8C4C8D931CAB48B9A29ADB">visitorGetMarketingCloudId </li> 
      <li id="li_D80DD8DDE6AB4CB6BEE37DAA9BB28A98">visitorSyncIdentifiers </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6.1 {#section_98CC97CF0F0C48F7855130044386845A}

The [!DNL Android] SDK version 4.6.1 (September 24, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_80693083398F472F8A4E7861606E602D"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Android</span> SDK versione 4.6.1 </p> </td> 
   <td colname="2"> <p>SDK 4.6.0 or earlier supports <span class="keyword"> Android</span> 2.2(API 8) - <span class="keyword"> Android</span> 5.1.1 (API 22) </p> <p>SDK 4.6.1 or later supports <span class="keyword"> Android</span> 2.3(API 9) or later </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.6 {#section_ADF6F871CF3C4E2381464D62DA6E1EB1}

The [!DNL Android] SDK version 4.6 (September 17, 2015) includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_35D0692698EF49AE8204F2AEB57CABD7"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Push Messaging to <span class="keyword"> Analytics</span> Segments </p> </td> 
   <td colname="2"> <p><span class="keyword"> Adobe Mobile Services</span> e l'SDK <span class="keyword"> di Adobe Mobile</span> consentono di inviare messaggi push ai <span class="keyword"> segmenti Analytics</span> . La SDK vi consente anche di segnalare facilmente gli utenti che hanno aperto la vostra app a seguito dell'apertura del messaggio push. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Metodi di acquisizione </p> </td> 
   <td colname="2"> <p>Consente agli sviluppatori di avviare una campagna di acquisizione app, come se l’utente avesse fatto clic su un collegamento. È utile per creare collegamenti di acquisizione manuali e gestire autonomamente il ridirezionamento all'app store. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Postback </p> </td> 
   <td colname="2"> <p>I postback ti consentono di inviare i dati raccolti dall'SDK a un server di terze parti separato. Sfruttando le caratteristiche e gli attivatori utilizzati per visualizzare un messaggio in app, puoi configurare l'SDK per l'invio di dati personalizzati a una destinazione terza. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Identificatori </p> </td> 
   <td colname="2"> <p>Sono stati aggiunti i seguenti identificatori: </p> <p> 
     <ul id="ul_84AD959FC65C445BB119F69657AB4AF8"> 
      <li id="li_418FD9EE570F491F9704F72AC70EEE8D"><code> setPushIdentifier</code> </li> 
      <li id="li_B350606A504449E5AAE208B1E590E2CA"> <code> submitAdvertisingIdentifierTask</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.5 {#section_6E7614D4AEA24B7E81C4FC094882F062}

The [!DNL Android] SDK version 4.5 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_BF98A1E904EB4314828AC58A2A6E7016"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p><span class="keyword"> Estensione</span> wearable Android </p> </td> 
   <td colname="2"> <p>Starting in <span class="keyword"> Android</span> SDK version 4.5, a new <span class="keyword"> Android</span> extension lets you collect data from your <span class="keyword"> Android</span> Wearable app. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.4 {#section_8D7FC183081E4BCFA8ADC33FB55E057C}

The [!DNL Android] SDK version 4.4 includes the following changes:

<table frame="all" colsep="1" rowsep="1" id="table_E8628F3806E24A0FB7157847D97C7B7A"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Dati personalizzati con metriche del ciclo di vita </p> </td> 
   <td colname="2"> <p>Ora puoi includere variabili di dati di contesto personalizzate con metriche del ciclo di vita. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap</span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon</code> and <code> clearCurrentBeacon</code> calls are now available in <span class="keyword"> PhoneGap</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Version 4.3 {#section_789F3DA3DD3146CAA126B303F62D1A1A}

Data di rilascio: **24 novembre 2014**

* Nuovo - Integrazione con Adobe Marketing Cloud ID
* Registri di debug migliorati per chiarezza
* È stato risolto un arresto potenziale durante la verifica dei messaggi in-app

## Version 4.2 {#section_EDF95BA0301C4B54AAE839768917D439}

Data di rilascio: **16 ottobre 2014**

* Nuovo - In Funzionalità Messaggistica app.
* Nuovo - È ora possibile specificare la posizione per il file di configurazione durante l'avvio dell'app.
* Nuovo: ora è possibile aggiornare automaticamente i punti di interesse senza richiedere un nuovo file di configurazione.
* New - [!DNL Analytics] calls are now sent as HTTP POST requests.
* È stato risolto un problema che poteva causare il mancato tracciamento anomalo dell'app in determinati scenari.
* Cancellazione dei messaggi di registro, aggiunta di registrazione più dettagliata quando debuglogging è abilitato.
* Più miglioramenti a prestazioni e stabilità.

## Version 4.1.7 {#section_DD98F9A4F00A457AA79D223CB1113A06}

Release Date: **August 4, 2014**

* È stato risolto un problema che potrebbe causare la mancata invio dell'hit Ciclo di vita quando il timeout del referente era &gt; = 5 secondi e il tracciamento offline era disattivato.

## Version 4.1.6 {#section_B665DF1A4FB249539D73569B52FA8786}

Data di rilascio:**17 luglio 2014**

* Sono state aggiunte protezioni attorno alle eccezioni che si verificano se il database viene danneggiato o non è stato possibile crearlo.
* Sono state aggiunte protezioni per problemi che possono verificarsi quando la configurazione non può essere caricata (generalmente a causa di un contesto null).
* Sono state aggiunte protezioni per le eccezioni che potevano verificarsi quando si aggiornano i dati contestuali di un'azione temporizzata.

## Version 4.1.1 {#section_E5EFA05CEE9D486BA6B5C12B1102C117}

Data di rilascio:**23 aprile 2014**

* Risolto un problema potenziale che poteva verificarsi se il tracciamento del referente è abilitato e una chiamata di tracciamento viene effettuata prima del ciclo di vita.

## Version 4.1.0 {#section_266B62F5B6A44F5F8E6AB8ED1870C4A3}

Data di rilascio:**17 aprile 2014**

* Nuovo - Tracciamento dei beacon Bluetooth.
* Nuovo: le app con marca temporale abilitata, gli hit degli arresti vengono retrodatati alla sessione corretta.
* Nuovo: le app abilitate, la sessione precedente viene inviata in un hit retrodatato alla sessione corretta. (nessuna sessione precedente).
* Nuovo - Invio in batch.
* Corretto il tracciamento dei referenti di Google Play con un timeout configurabile per consentire i dati di riferimento google ritardati.
* Sono stati risolti avvisi strictmode che potevano verificarsi in scenari specifici.
* È stato risolto un problema che poteva causare molto raramente la blocco della libreria se alcuni metodi venivano chiamati in un ordine specifico.

## Version 4.0.4 {#section_DCFAC758872D42F0BF0CCFCDDEA05E41}

Data di rilascio:**24 febbraio 2014**

* È stato risolto un problema che poteva causare la riproduzione di tempo multimediale esteso se l'interruzione veniva chiamata e la chiusura era chiamata successivamente senza chiamate tra.
* È stato risolto un problema per il quale un hit di chiusura multimediale veniva inviato anche se il supporto non veniva riprodotto per un periodo di tempo prolungato.

## Version 4.0.3 {#section_FCC3D7D22EBF4A2FA949A4E88AD89F5C}

Data di rilascio:**20 febbraio 2014**

* Added safety to network code to prevent crash caused by [!DNL Android] bug: https://code.google.com/p/android/issues/detail?id=54072

## Version 4.0.2 {#section_5A7F4D5D9CBD4B79B3B590A2C3F4D0F9}

Release Date: **January 30, 2014**

* È stato risolto un problema che poteva causare l'invio di più hit quando il database era danneggiato.
* È stato risolto un problema che poteva causare medie di lunghezza sessione grandi se un dispositivo aveva impostazioni di tempo errate.

## Version 3.2.5 {#section_A6E60DB42241481DA62F660344128F53}

Release Date: **30 January, 2014**

* Sono state aggiunte protezioni nei database danneggiati che causavano la ripetizione degli hit.
* Limite massimo di lunghezza sessione per evitare sessioni particolarmente grandi quando i tempi del dispositivo non sono corretti.

## Version 4.0.1 {#section_5F58DBABDAA049FE9070E46989B2E9A9}

Release Date: **14 November, 2013**

* È stata risolta la formattazione errata dei dati tracklocation in impostazioni internazionali specifiche.

## Version 4.0.0 {#section_79DCFAAF1DCB404898E3BE389AC835A6}

Release Date: **27 September, 2013**

[!DNL Android] SDK 4. x per soluzioni Marketing Cloud è ora disponibile fornendo le seguenti nuove funzioni:

* Miglioramenti significativi delle prestazioni. Tutte le elaborazioni vengono eseguite su thread di sfondo, l'SDK è completamente sicuro per i thread.
* Geolocalità e punti di interesse
* Valore del ciclo di vita
* Eventi temporizzati
* Gestione di consenso e rinuncia
* Supporto di Audience Manager
* Lifecycle metrics passed to [!DNL Target] as mbox parameters
* Standardizzato sui dati contestuali e sulle regole di elaborazione

## Version 3.2.3 {#section_E3464DDC3B4844CF9CC5FC3E35C5C785}

Release Date: **23 September, 2013**

* È stato corretto un bug in Audience Manager che non consentiva valori null o chiavi nel parametro.

## Version 3.2.2 {#section_7D631AA2474F4DBAA043703629E3ECC6}

Release Date: **12 September, 2013**

* È stato corretto un bug a causa del quale gli eventi dei supporti negli eventi linktrackevents non venivano aggiunti alla richiesta.
* È stata risolta una potenziale eccezione correlata a contextdata che venivano modificati dopo essere passati in una chiamata di tracciamento.

## Version 3.2.1 {#section_D269F9145B2844B6855423A30B125D5C}

Release Date: **16 August, 2013**

* Le connessioni SSL usano la convalida rigorosa dell'host
* È stato corretto un bug a causa del quale gli hit riprovavano rapidamente per alcuni secondi quando la connessione di rete scompariva e offlinetracking era disattivato.

## Versione 3.2 {#section_ABD4D192E3FF4240B1451262EAEE4F17}

Release Date: **6 August, 2013**

* Aggiunto supporto per Adobe Audience Manager.
* I dati del ciclo di vita vengono ora inviati con le richieste Mbox di Target quando è abilitato il tracciamento del ciclo di vita.
* È stato risolto un problema che poteva causare la chiusura di cursori di chiusura da parte di sqlite, generando voci di registro superflue.

## Versione 3.1.0 {#section_836B4F580B1C436FABD524A91857F882}

Release Date: **13 June, 2013**

* Aggiornamento offline per l'utilizzo di sqlite.
* È stato corretto un bug a causa del quale il limite offline poteva reimpostare il valore predefinito (1000).
* Aggiornato startactivity per accettare un contesto Attività o Applicazione.
* È stato corretto un bug a causa del quale l'impostazione di lifcyclesessiontimeout a 0 generava più eventi di avvio nell'app.

## Version 3.0.8 {#section_51F50CD81C6A40C8BCF62F6F332A0800}

Release Date: **18 April, 2013**

* È stato corretto un problema di codifica con alcuni caratteri UTF 8.

## Version 3.0.7 {#section_0F3FEE2886EB4AB7BA288891FF6B6BCD}

Release Date: **18 April, 2013**

* È stato corretto un problema a causa del quale la durata della sessione precedente veniva calcolata in modo errato.
* I nuovi ID visitatore non saranno più basati su deviceid o subscriberid.
* È stato corretto un arresto potenziale durante la codifica di caratteri speciali nelle variabili.

## Version 3.0.6 {#section_72F3F9CB95BF4076AD882B3270F77B87}

Release Date: **21 March, 2013**

* Problema risolto: visitorid non poteva essere letto senza impostarlo per primo.
* Sono state modificate le convenzioni di denominazione in alcuni messaggi di registro errori per migliorare la chiarezza.
* È stata modificata l'accessibilità di più classi base per evitare confusione.
* Miglioramenti a livello di prestazioni

## Version 3.0.5 {#section_0540FF6477D74D1F8274E9340EDE7E16}

Release Date: **21 February, 2013**

* Deprecated `offlineThrottleDelay` as the setting is no longer necessary due to thread optimization. L'impostazione esiste ancora per mantenere compatibilità con versioni precedenti, ma non ha più effetti.
* Risolto un problema di sincronizzazione potenziale sulla cache hit offline.
* Messaggio di avviso chiarito durante l'impostazione delle variabili gerarchiche sopra # 5.
* Fixed issue that could cause OSVersion to be misreported on versions of [!DNL Android] &gt; 4.0.
* Miglioramenti a livello di prestazioni.
* Risolto un problema potenziale che poteva essere causato da un URL corrotto.

## Version 3.0.4 {#section_69ADA2ACD9DE436692152C3836B14EEF}

Release Date: **November 2012**

* Added a `lifecycleSessionTimeout` configuration variable that lets you specify the length of time, in seconds, that must elapse between app launches before the launch is considered a new session.
* Added ability to set the timeout value for the session length calculation, using a `lifecycleSessionTimeout` configuration setting.
* Sono stati corretti dei problemi relativi alla sicurezza.

## Version 3.0.3 {#section_F16E1A36AE3F4CBC92E4925D6DCCFADE}

Release Date: **October 2012**

* Added support for [Google Play Campaign Tracking](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/android/index.html?f=referrer).

## Version 3.0.2 {#section_CB24859B34804F9391BA1BF8DF29CC86}

Release Date: **September 2012**

* È stato risolto un problema che a volte poteva causare una condizione loop nel monitor multimediale.

## Version 3.0.1 {#section_541CE15B340E414AA018A0EFAEE459F0}

Release Date: **August 2012**

* Context override parameters are now sent in as `Hashmap<String, Object>` (they were formerly `Hashmap<String, String>`).

## Versione 3.0 {#section_2955C0AF3A23476B8CF06C469DE3284C}

Release Date: **July 2012**

Versione iniziale.

## Previous Android Version (1.x) {#section_F2CC015616184D55AC6D6529DFC9A18B}

The following release notes apply to the 1.x version of [!DNL AppMeasurement] for [!DNL Android]. Consigliamo ai clienti di effettuare l'aggiornamento alla versione 3. x, quando possibile.

## Version 1.2.3 {#section_5189CCE11EEF4350844B1490D0A9F534}

Release Date: **March 2012**

* È stato risolto un problema che causava un'eccezione in alcune circostanze durante il passaggio dei dati utilizzando Dati contestuali.

## Version 1.2.2 {#section_C42925D94F3A429EB1299B96A6EEF6DF}

Release Date: **February 2012**

È stato risolto un problema che causava chiamate di tracciamento dei collegamenti per codificare doppio URL con i valori pev 1 - pev 3.

Aggiunto il timestamp alle variabili utilizzate con chiamate di tracciamento chiaro (tracklight).

## Version 1.2.1 {#section_21845E8A7D0C48B38CB90F0D4C5696AF}

Release Date: **January 2012**

* Added [!DNL Android] 3.x and 4.x compatibility.
* Implemented a UUID for visitor ID on [!DNL Android] devices that do not have SIM cards (For example, Kindle Fire).

## Version 1.2 {#section_EC83BE1F00BF481EA1C74A63E4B90F65}

Release Date: **June 2011**

* Aggiornamento della libreria per utilizzare l'ID dispositivo per il valore ID visitatore quando nel dispositivo non viene inserita alcuna scheda SIM. Per impostazione predefinita, la libreria utilizza l'ID utente iscritto come ID visitatore che non è presente se non viene inserita alcuna scheda SIM.

## Version 1.1.4 {#section_C602EC5C11594669A8797B736D240D2C}

Release Date: **April 2011**

* Supporto per tutti i tablet incluso Xoom.
* Possibilità di cercare suite di rapporti e metriche durante l'esecuzione di un report.
* Supporto per contextdata che fornisce regole di elaborazione lato server (solo v 15).
* Supporto per chiamate server chiaro (attualmente nella versione beta).
