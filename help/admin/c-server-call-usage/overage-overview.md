---
description: 'null'
title: Panoramica sull'utilizzo delle chiamate server
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1020'
ht-degree: 5%

---


# Panoramica sull&#39;utilizzo delle chiamate server

## Perché monitorare e inviare avvisi all&#39;utilizzo delle chiamate server? {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe  Analytics Server Call Usage risolve le richieste di trasparenza sia nei dati di utilizzo delle chiamate del browser che nei dati di utilizzo delle chiamate dei server mobili. Consente di accedere a:

* Pannello Utilizzo chiamate server che tiene traccia dei dati di consumo delle chiamate server e li confronta con il limite contrattuale. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* Un tipo di avviso Utilizzo chiamate server nel Generatore di avvisi che consente di impostare avvisi per evitare sovrapposizioni (**[!UICONTROL Analytics > Components >Alerts]**)

I vantaggi principali dell&#39;utilizzo delle chiamate server sono:

* **Visibilità** dei dati relativi al consumo e all&#39;impegno delle chiamate al server, compreso il consumo mobile rispetto al limite di utilizzo contrattuale delle chiamate al server.
* **Avvisi** per avvisarvi del rischio o del verificarsi di un&#39;overage e prepararvi/agire sulla possibilità di incorrere in sovracompensazioni.

Precedentemente, mentre era possibile accedere ai dati di consumo delle chiamate server mensili in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , questi dati venivano aggiornati solo 6 giorni dopo la chiusura della fatturazione per quel mese. Inoltre, i dati non includevano il consumo mobile. Questa funzione sostituirà anche il rapporto corrente **[!UICONTROL Billing Information]** in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** .

## Prerequisiti {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Autorizzazioni:** Per accedere al Dashboard sull&#39;utilizzo delle chiamate server e al Generatore di avvisi/Manager, è necessario essere un amministratore Adobe  Analytics.
* **Autorizzazioni:** Gli amministratori possono concedere l’accesso agli utenti non amministratori: si chiama il permesso **[!UICONTROL Server Call Usage]**. Consulta Autorizzazione [utilizzo chiamata](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369)server.

## Terminologia importante {#section_CBA348A039F34563B097CD8890AB358D}

Di seguito è riportato un breve primate sulla terminologia essenziale per l&#39;utilizzo delle chiamate server:

<table id="table_4E97F85F13344A2C962FA4FA5A51642E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Termine </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Chiamata server </p> </td> 
   <td colname="col2"> <p>Una chiamata server, detta anche "hit" o "image request" (richiesta immagine), è un'istanza in cui i dati vengono inviati ai server Adobe per l'elaborazione. Il tipo più comune di chiamata server è una visualizzazione pagina. Una visualizzazione di pagina si verifica quando un visitatore visualizza una pagina sul sito Web e viene generata una chiamata al server ad Adobe, dove le informazioni vengono raccolte, elaborate e quindi incluse nelle metriche del rapporto. </p> <p>Esistono altri tipi di chiamate server, inclusi collegamenti di uscita e download di file, in cui i dati vengono inviati ad Adobe per l'elaborazione, ma non vengono registrati come nuova visualizzazione di pagina. Anche le visualizzazioni di pagina "escluse" (escluse dai rapporti dall’intervallo di indirizzi IP configurato, ad esempio) sono chiamate server perché vengono ricevute ed elaborate da Adobe ma non vengono mai visualizzate nei rapporti. </p> <p><b>Chiamata</b>server principale: Richieste ricevute direttamente dai browser dei visitatori del sito Web o dall’API di inserimento dati. Include gli hit principali (Visualizzazioni di pagina), gli eventi personalizzati principali, gli eventi di download principali e gli eventi di uscita principali. </p> <p><b>Chiamata</b>server secondaria: Copie di chiamate server primarie create da tag con più suite o copiate/spostate da una regola VISTA. Se una chiamata al server secondario è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono detratte dalle chiamate al server principale. </p> <p><b>Chiamata al server principale mobile </b> </p> <p>Richieste ricevute direttamente da uno degli SDK di Mobile. Include trackAction, trackState, trackApp Crash, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Chiamata al server secondario mobile</b> </p> <p>Copie di chiamate server primarie create da tag con più suite o copiate/spostate da una regola VISTA. Se una chiamata al server secondario è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono detratte dalle chiamate al server principale. </p> <p>Nota:  Se l'azienda ha diritto contrattualmente solo alle chiamate per Mobile Server (Primarie o Secondarie), sia l'utilizzo specifico per Web che per dispositivi mobili verrà conteggiato in base all'impegno specifico per Mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di fatturazione (ID fatturazione) </p> </td> 
   <td colname="col2"> <p>Persona giuridica fatturata per le chiamate server. Ad esempio, adobe.com. Ogni società di fatturazione dispone di un Billing ID utilizzato per identificare in modo univoco il cliente di fatturazione. Un ID di fatturazione potrebbe essere associato a più organizzazioni Experience Cloud ; non esiste sempre una relazione 1:1 tra un'organizzazione e un ID di fatturazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di accesso </p> </td> 
   <td colname="col2"> <p>Una società di fatturazione può avere <a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html"> più società di accesso </a>. Una società di accesso è una raccolta di suite di rapporti utilizzata dalla vostra organizzazione. Alcune organizzazioni dispongono di più società di accesso che si applicano a parti diverse dell'organizzazione. Questo è particolarmente utile per le grandi organizzazioni che si occupano di business unit diverse, dove molte suite di rapporti non sono applicabili ad altre nell'azienda. </p> <p>Spesso si tratta delle filiali regionali di una società. Questo esempio mostra le società di accesso e le relative suite di rapporti associate: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.world: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Nota:  I dati di utilizzo delle chiamate server per <u>tutte</u> le suite di rapporti all’interno di una società di fatturazione sono visibili a tutti gli utenti che dispongono dell’ <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369"> autorizzazione</a>appropriata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organizzazione Experience Cloud </p> </td> 
   <td colname="col2"> <p>Un'organizzazione è l'entità che consente all'amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L'organizzazione funziona come una società di accesso che si estende su tutti i prodotti e le soluzioni Experience Cloud . </p> <p>Nella maggior parte dei casi, un’organizzazione è il nome dell’azienda. Tuttavia, un’azienda può avere molte organizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impegno di chiamata server </p> </td> 
   <td colname="col2"> <p>Quando l'azienda firma un contratto con Adobe, il team Vendite Adobe si identifica con l'utente, il cliente, i tipi (Primario, Secondario, Primario mobile, Secondario mobile) e il numero approssimativo di chiamate server che si prevede di effettuare nel corso del periodo contrattuale. Questo è il totale del vostro impegno di chiamata server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo di utilizzo </p> </td> 
   <td colname="col2"> <p>Ai fini del monitoraggio dell’utilizzo delle chiamate server, questo impegno totale delle chiamate server è suddiviso in periodi di utilizzo più brevi (ad esempio 3 mesi) per facilitare i confronti su base annua. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo contratto </p> </td> 
   <td colname="col2"> <p>I periodi di contratto possono durare più anni. Supponiamo che la tua azienda abbia un impegno di chiamate server di 6 milioni di chiamate per un periodo contrattuale di 3 anni. Ai fini del monitoraggio dell’utilizzo delle chiamate server, questo periodo di 3 anni può essere suddiviso in periodi di utilizzo più brevi per facilitare i confronti su base annua. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Server Call Usage Permission {#section_FCC58EB635954A32990D4E67B52B4369}

L&#39;autorizzazione Utilizzo chiamate server viene concessa automaticamente agli  Analytics Admins. Consente agli utenti di visualizzare il dashboard e creare avvisi relativi alle chiamate al server. Gli amministratori possono scegliere di concedere questa autorizzazione agli utenti non amministratori.

>[!NOTE]
>
>La società può scegliere quali società di accesso hanno accesso a Utilizzo chiamate server.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome autorizzazione </th> 
   <th colname="col3" class="entry"> Concedi l'autorizzazione se hai effettuato l'accesso ad Adobe  Analytics (accesso legacy) </th> 
   <th colname="col4" class="entry"> Concedere l’autorizzazione se è stato effettuato l’accesso ad Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilizzo delle chiamate server </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Accedete a  Analytics tramite sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Andate in <span class="ignoretag"> Admin <span class="uicontrol"> &gt; </span> User Management <span class="uicontrol"> &gt; </span> Groups (Gestione utenti) &gt; <span class="uicontrol"> Edit All Report Access (Modifica accesso a tutti i rapporti) </span> &gt;  Analytics Tools (Strumenti) &gt; <span class="uicontrol"> </span> <span class="uicontrol"> </span> <span class="uicontrol"> </span> <span class="uicontrol"> Customize (Personalizza) &gt; (Utilizzo chiamate server) </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Effettuate l'accesso a login.experienceCloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Fate clic su <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Andate a <span class="ignoretag"> Products <span class="uicontrol"> &gt; </span> Product Profile <span class="uicontrol"> &gt; </span> Permissions (Prodotti) &gt;  Analytics Tools (Autorizzazioni) <span class="uicontrol"> &gt; </span> Server Call Usage (Strumenti &gt; <span class="uicontrol"> </span> <span class="uicontrol"> Server Call Usage) </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

