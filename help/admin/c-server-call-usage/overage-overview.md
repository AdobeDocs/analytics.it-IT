---
description: Panoramica della funzionalità di utilizzo delle chiamate al server Adobe Analytics.
title: Panoramica sull'utilizzo delle chiamate server
uuid: 6e014364-efc1-4769-a0b5-cf105c0ed9b1
exl-id: d3d64f1e-f01b-4b9e-9aee-c14e574fc40b
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 5%

---

# Panoramica sull&#39;utilizzo delle chiamate server

## Perché monitorare e inviare avvisi all’utilizzo delle chiamate al server? {#section_060C29BF1D00444B85892AD1FCF55290}

L&#39;utilizzo delle chiamate al server Adobe Analytics soddisfa le richieste di trasparenza sia nei dati di utilizzo delle chiamate al browser che nei dati di utilizzo delle chiamate al server mobile. Ti consente di accedere a:

* Dashboard dell&#39;utilizzo delle chiamate server che tiene traccia dei dati di consumo delle chiamate server e li confronta con il limite contrattuale. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* Un tipo di avviso Utilizzo chiamate server nel Generatore di avvisi che consente di impostare avvisi per evitare interruzioni (**[!UICONTROL Analytics > Components >Alerts]**)

I principali vantaggi dell&#39;utilizzo delle chiamate server includono:

* **** Visibilità dei dati sul consumo e sull’impegno delle chiamate al server, compreso il consumo mobile rispetto al limite di utilizzo contrattuale delle chiamate al server.
* **** Avvisi di avvisarti del rischio o del verificarsi di un&#39;overage e prepararti per/agire sulla possibilità di incorrere in overage.

In precedenza, mentre era possibile accedere ai dati mensili sul consumo delle chiamate al server in **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Billing]** , questi dati erano stati aggiornati solo 6 giorni dopo la chiusura della fatturazione per quel mese. Inoltre, i dati non includevano il consumo mobile. Questa funzione sostituirà anche il rapporto corrente **[!UICONTROL Billing Information]** in **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** .

## Prerequisiti {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Autorizzazioni:** per accedere al Dashboard dell&#39;utilizzo delle chiamate al server e al Generatore/Gestione avvisi, devi essere un amministratore di Adobe Analytics.
* **Autorizzazioni:** gli amministratori possono concedere l’accesso agli utenti non amministratori: si chiama il permesso  **[!UICONTROL Server Call Usage]**. Vedere [Autorizzazione per l&#39;utilizzo delle chiamate server](/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Terminologia importante {#section_CBA348A039F34563B097CD8890AB358D}

Ecco una breve introduzione alla terminologia essenziale per l&#39;utilizzo delle chiamate server:

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
   <td colname="col2"> <p>Una chiamata al server, nota anche come "hit" o "richiesta di immagine", è un’istanza in cui i dati vengono inviati ai server di Adobe da elaborare. Il tipo più comune di chiamata al server è la visualizzazione di una pagina. Una visualizzazione di pagina si verifica quando un visitatore visualizza una pagina sul tuo sito web e una chiamata al server viene generata in un Adobe, in cui le informazioni vengono raccolte, elaborate e quindi incluse nelle metriche del rapporto. </p> <p>Esistono altri tipi di chiamate server, inclusi i collegamenti di uscita e i download dei file, in cui i dati vengono inviati ad Adobe per l’elaborazione, ma non vengono registrati come una nuova visualizzazione di pagina. Anche le visualizzazioni di pagina "escluse" (escluse dai rapporti tramite un intervallo di indirizzi IP configurato, ad esempio) sono chiamate al server perché vengono ricevute ed elaborate per Adobe ma non vengono mai visualizzate nei rapporti. </p> <p><b>Chiamata</b> server principale: Richieste ricevute direttamente dai browser visitatori del sito web o dall’API di inserimento dati. Include gli hit principali (visualizzazioni pagina), gli eventi personalizzati principali, gli eventi di download principali e gli eventi di uscita principali. </p> <p><b>Chiamata</b> server secondaria: Copie delle chiamate server principali create da tag con più suite o copiate/spostate da una regola VISTA. Se una chiamata al server secondario è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono detratte dalle chiamate al server principale. </p> <p><b>Chiamata al server principale mobile  </b> </p> <p>Richieste ricevute direttamente da uno degli SDK di Mobile. Includi trackAction, trackState, trackApp Crash, trackActionFromBackground, trackLocation, trackBeacon, trackPushMessageClickThrough, trackTimedActionBacklog, trackLifetimeValueIncrease.</p> <p><b>Chiamata al server secondario mobile</b> </p> <p>Copie delle chiamate server principali create da tag con più suite o copiate/spostate da una regola VISTA. Se una chiamata al server secondario è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono detratte dalle chiamate al server principale. </p> <p>Nota:  Se l'azienda ha diritto contrattualmente solo alle chiamate al server mobile (primario o secondario), sia l'utilizzo specifico per il web che per quello per dispositivi mobili sarà considerato in base all'impegno specifico per Mobile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di fatturazione (ID fatturazione) </p> </td> 
   <td colname="col2"> <p>Persona giuridica fatturata per le chiamate server. Ad esempio, adobe.com. Ciascuna società di fatturazione dispone di un Billing ID (ID fatturazione) utilizzato per identificare in modo univoco il cliente di fatturazione. Un ID di fatturazione può essere associato a più organizzazioni di Experience Cloud; non esiste sempre una relazione 1:1 tra un’organizzazione e un ID di fatturazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di accesso </p> </td> 
   <td colname="col2"> <p>Una società di fatturazione può avere <a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html"> più società di accesso </a>. Una società di accesso è una raccolta di suite di rapporti utilizzate dall’organizzazione. Alcune organizzazioni dispongono di più società di accesso che si applicano a parti diverse dell'organizzazione. Questo è particolarmente utile per le grandi organizzazioni che si occupano di business unit diverse, dove molte suite di rapporti non sono applicabili ad altre aziende. </p> <p>Spesso si tratta delle filiali regionali di una società. Questo esempio mostra le società di accesso e le relative suite di rapporti associate: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe.world: RS1, RS2, RS3, RS4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe.us: RS1, RS2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe.in: RS3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe.de: RS4 </li> 
    </ul> <p>Nota:  I dati di utilizzo delle chiamate al server per <u>tutte le suite di rapporti</u> all'interno di una società di fatturazione sono visibili a tutti gli utenti con l'autorizzazione <a href="/help/admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369"> appropriata</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organizzazione Experience Cloud </p> </td> 
   <td colname="col2"> <p>Un'organizzazione è l'entità che consente all'amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L’organizzazione funziona come una società di accesso che si estende su tutti i prodotti e le soluzioni Experience Cloud. </p> <p>Nella maggior parte dei casi, un’organizzazione è il nome dell’azienda. Tuttavia, un’azienda può avere più organizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impegno sulle chiamate server </p> </td> 
   <td colname="col2"> <p>Quando l'azienda firma un contratto con l'Adobe, il team Vendite Adobi si identifica con l'utente, il cliente, i tipi (primario, secondario, principale mobile, secondario mobile) e il numero approssimativo di chiamate server che si prevede di effettuare nel corso del periodo contrattuale. Questo è il tuo impegno totale di chiamata al server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo di utilizzo </p> </td> 
   <td colname="col2"> <p>Ai fini del monitoraggio dell’utilizzo delle chiamate al server, questo impegno totale delle chiamate al server viene suddiviso in periodi di utilizzo più piccoli (ad esempio 3 mesi) per facilitare i confronti su base annua. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo contratto </p> </td> 
   <td colname="col2"> <p>I periodi di contratto possono durare più anni. Supponiamo che la tua azienda abbia un impegno di chiamata al server di 6 milioni di chiamate per un contratto di 3 anni. Ai fini del monitoraggio dell’utilizzo delle chiamate al server, questo periodo di 3 anni può essere suddiviso in periodi di utilizzo più piccoli per facilitare i confronti su base annua. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Autorizzazione per l&#39;utilizzo delle chiamate server {#section_FCC58EB635954A32990D4E67B52B4369}

L&#39;autorizzazione Utilizzo chiamate server viene concessa automaticamente agli amministratori di Analytics. Consente agli utenti di visualizzare il dashboard e creare avvisi sulle chiamate al server. Gli amministratori possono scegliere di concedere questa autorizzazione agli utenti non amministratori.

>[!NOTE]
>
>L&#39;azienda può scegliere quali società di accesso hanno accesso a Server Call Usage (Utilizzo chiamate al server).

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome autorizzazione </th> 
   <th colname="col3" class="entry"> Concedere l’autorizzazione se hai effettuato l’accesso ad Adobe Analytics (accesso legacy) </th> 
   <th colname="col4" class="entry"> Concedere l’autorizzazione se è stato effettuato l’accesso ad Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilizzo delle chiamate server </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Accedi ad Analytics tramite sc.omniture.com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Passa a <span class="ignoretag"> <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol"> Amministratore </span> &gt; <span class="uicontrol"> Gestione utente </span> &gt; <span class="uicontrol"> Gruppi </span> &gt; <span class="uicontrol"> Modifica accesso a tutti i rapporti </span> &gt; <span class="uicontrol"> Strumenti di analisi </span> &gt; &lt;a1 3/&gt; Personalizza </span> &gt; <span class="uicontrol"> Uso delle chiamate server </span> </span><span class="uicontrol"> </span></li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Accedi a login.experiencecloud.adobe.com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Fai clic su <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Passa a <span class="ignoretag"> <span class="uicontrol"> Prodotti </span> &gt; <span class="uicontrol"> Profilo prodotto </span> &gt; <span class="uicontrol"> Autorizzazioni </span> &gt; <span class="uicontrol"> Strumenti di Analytics </span> &gt; <span class="uicontrol"> Utilizzo chiamate server </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
