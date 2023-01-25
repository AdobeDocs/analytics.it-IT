---
description: Panoramica della funzionalità di utilizzo delle chiamate al server Adobe Analytics.
title: Panoramica sull’utilizzo delle chiamate al server
feature: Server Call Usage
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: ht
source-wordcount: '1029'
ht-degree: 100%

---

# Panoramica sull’utilizzo delle chiamate al server

## Perché monitorare l’utilizzo delle chiamate al server e inviare avvisi? {#section_060C29BF1D00444B85892AD1FCF55290}

L’utilizzo delle chiamate al server Adobe Analytics soddisfa le richieste di trasparenza nei dati di utilizzo delle chiamate sia al browser che al server mobile. Consente di accedere a:

* Un dashboard dell’utilizzo delle chiamate server che tiene traccia dei dati di consumo delle chiamate al server e li confronta con il limite contrattuale. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* Un tipo di avviso per l’utilizzo delle chiamate al server nel generatore di avvisi che consente di impostare avvisi per evitare interruzioni (**[!UICONTROL Analytics > Components >Alerts]**)

Alcuni dei vantaggi principali dell’utilizzo delle chiamate al server:

* **Visibilità** nei dati relativi a utilizzo e impegno delle chiamate al server, compreso il consumo mobile rispetto al limite di utilizzo contrattuale delle chiamate al server.
* **Avvisi** per essere informati se si rischia, o se avviene, un superamento e prepararsi o agire nel caso in cui si verifichi.

In precedenza, benché fosse possibile accedere ai dati mensili sul consumo delle chiamate al server in  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]**, questi dati venivano aggiornati solo 6 giorni dopo la chiusura della fatturazione per quel mese. Inoltre, i dati non includevano il consumo mobile. Questa funzione sostituirà anche l’attuale rapporto **[!UICONTROL Billing Information]** in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** .

## Prerequisiti {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Autorizzazioni:** per accedere al dashboard sull’utilizzo delle chiamate al server e al generatore o alla gestione degli avvisi, devi essere un amministratore Adobe Analytics.
* **Autorizzazioni:** gli amministratori possono concedere l’accesso agli utenti non amministratori: l’autorizzazione si chiama **[!UICONTROL Server Call Usage]**. Vedi [Autorizzazione per l’utilizzo delle chiamate al server](/help/admin/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminologia importante {#section_CBA348A039F34563B097CD8890AB358D}

Ecco una breve introduzione alla terminologia essenziale per l’utilizzo delle chiamate al server:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termine </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chiamata al server </p> </td> 
   <td colname="col2"> <p>Una chiamata al server, nota anche come “hit” o “richiesta di immagine”, è un’istanza in cui i dati vengono inviati ai server di Adobe per essere elaborati. Il tipo più comune di chiamata al server è la visualizzazione di una pagina. Una visualizzazione di pagina si verifica quando un visitatore visualizza una pagina sul tuo sito Web e viene generata una chiamata al server in Adobe, in cui le informazioni vengono raccolte, elaborate e quindi incluse nelle metriche del rapporto. </p> <p>Esistono altri tipi di chiamata al server, inclusi i collegamenti di uscita e i download dei file, in cui i dati vengono inviati ad Adobe per l’elaborazione, ma non vengono registrati come nuova visualizzazione di pagina. Anche le visualizzazioni di pagina “escluse” (ad esempio, escluse dai rapporti in base a un intervallo di indirizzi IP configurato) sono chiamate al server perché vengono ricevute ed elaborate da Adobe ma non vengono mai visualizzate nei rapporti. </p> <p><b>Chiamata al server primaria</b>: richieste ricevute direttamente dai browser dei visitatori del sito Web o dall’API di inserimento dati. Include gli hit primari (visualizzazioni di pagina), gli eventi personalizzati primari, gli eventi di download primari e gli eventi di uscita primari. </p> <p><b>Chiamata al server secondaria</b>: copie delle chiamate al server primarie create da tag multisuite o copiate/spostate da una regola VISTA. Se una chiamata al server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono detratte dalle chiamate al server primarie. </p> <p><b>Chiamata al server primaria mobile </b> </p> <p>Richieste ricevute direttamente da uno degli SDK mobili. Sono inclusi trackAction, trackState, trackApp Crashes, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Chiamata al server secondaria mobile</b> </p> <p>Copie delle chiamate al server primarie create da tag multisuite o copiate/spostate da una regola VISTA. Se una chiamata al server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono detratte dalle chiamate al server primarie. </p> <p>Nota: se l’azienda ha diritto contrattualmente solo alle chiamate a Mobile Server (primarie o secondarie), sia l’utilizzo sul Web che quello su dispositivi mobili verrà conteggiato nell’impegno specifico per Mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di fatturazione (ID fatturazione) </p> </td> 
   <td colname="col2"> <p>Persona giuridica a cui vengono addebitate le chiamate al server. Ad esempio, adobe.com. Ciascuna società di fatturazione dispone di un ID fatturazione utilizzato per identificare in modo univoco il cliente di fatturazione. Un ID fatturazione può essere associato a più organizzazioni Experience Cloud, non esiste sempre una relazione 1:1 tra un’organizzazione e un ID fatturazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di accesso </p> </td> 
   <td colname="col2"> <p>Una società di fatturazione può avere <a href="https://helpx.adobe.com/it/analytics/kb/multiple-login-companies.html"> più società di accesso </a>. Una società di accesso è una raccolta di suite di rapporti utilizzata dall’organizzazione. Alcune organizzazioni dispongono di più società di accesso che si applicano a parti diverse dell’organizzazione. Questo è particolarmente utile per le grandi organizzazioni che gestiscono diverse unità aziendali in cui molte suite di rapporti non sono applicabili ad altri nell’azienda. </p> <p>Spesso si tratta delle filiali regionali di un’azienda. Questo esempio mostra le società di accesso e le relative suite di rapporti associate: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.worldwide: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Nota: i dati relativi all’utilizzo delle chiamate al server per <u>tutte</u> le suite di rapporti all’interno di una società di fatturazione sono visibili a tutti gli utenti con l’appropriata <a href="/help/admin/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369">autorizzazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organizzazione Experience Cloud </p> </td> 
   <td colname="col2"> <p>Un’organizzazione è l'entità che consente all’amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L'organizzazione funziona come una società di accesso che abbraccia tutti i prodotti e le soluzioni Experience Cloud. </p> <p>Nella maggior parte dei casi, un’organizzazione è il nome dell’azienda. Tuttavia, un’azienda può avere più organizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impegno sulle chiamate al server </p> </td> 
   <td colname="col2"> <p>Quando la tua azienda firma un contratto con Adobe, il team di vendita di Adobe identifica con te, il cliente, i tipi (primaria, secondaria, primaria mobile, secondaria mobile) e il numero approssimativo delle chiamate al server che prevedi di effettuare nel corso del periodo contrattuale. Questo è il tuo impegno totale per le chiamate al server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo di utilizzo </p> </td> 
   <td colname="col2"> <p>Ai fini del monitoraggio dell’utilizzo delle chiamate al server, questo impegno totale delle chiamate al server viene suddiviso in periodi di utilizzo più piccoli (ad esempio 3 mesi) per facilitare i confronti su base annua. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo di contratto </p> </td> 
   <td colname="col2"> <p>I periodi di contratto possono durare più anni. Supponiamo che la tua azienda abbia un impegno di chiamata al server di 6 milioni di chiamate per un contratto di 3 anni. Ai fini del monitoraggio dell’utilizzo delle chiamate al server, questo periodo di 3 anni può essere suddiviso in periodi di utilizzo più piccoli per facilitare i confronti su base annua. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Autorizzazione per l’utilizzo delle chiamate al server {#section_FCC58EB635954A32990D4E67B52B4369}

L&#39;autorizzazione per l’utilizzo delle chiamate al server viene concessa automaticamente agli amministratori di Analytics. Consente agli utenti di visualizzare il dashboard e creare avvisi per le chiamate al server. Gli amministratori possono scegliere di concedere questa autorizzazione agli utenti non amministratori.

>[!NOTE]
>
>L&#39;azienda può scegliere quali società di accesso possono accedere all’utilizzo delle chiamate al server.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome autorizzazione </th> 
   <th colname="col3" class="entry"> Concedere l’autorizzazione se è stato effettuato l’accesso ad Adobe Analytics (accesso legacy) </th> 
   <th colname="col4" class="entry"> Concedere l’autorizzazione se è stato effettuato l’accesso ad Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilizzo chiamate al server </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Accedi ad Analytics tramite sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Passa a <span class="ignoretag"> <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol"> Tutti gli amministratori </span>  &gt; <span class="uicontrol"> Gestione utenti </span> &gt; <span class="uicontrol"> Gruppi </span> &gt; <span class="uicontrol"> Modifica accesso a tutti i rapporti </span> &gt; <span class="uicontrol"> Strumenti di Analytics </span>  &gt; <span class="uicontrol"> Personalizza </span> &gt; <span class="uicontrol"> Utilizzo delle chiamate al server </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Accedi a login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Fai clic su <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Passa a <span class="ignoretag"> <span class="uicontrol"> Prodotti </span> &gt; <span class="uicontrol"> Profilo prodotto </span> &gt; <span class="uicontrol"> Autorizzazioni </span> &gt; <span class="uicontrol"> Strumenti di Analytics </span> &gt; <span class="uicontrol"> Utilizzo delle chiamate al server </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
