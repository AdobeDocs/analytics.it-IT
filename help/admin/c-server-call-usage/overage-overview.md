---
description: nulle
seo-description: nulle
seo-title: Panoramica utilizzo server server
title: Panoramica utilizzo server server
uuid: 6 e 014364-efc 1-4769-a 0 b 5-cf 105 c 0 ed 9 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Panoramica utilizzo server server

## Why Monitor and Alert to Server Call Usage? {#section_060C29BF1D00444B85892AD1FCF55290}

Adobe Analytics Server Call Usage (Utilizzo delle chiamate server di Adobe Analytics) consente di gestire le richieste di trasparenza sia nel browser che nei dati di utilizzo per i server mobili. Consente di accedere a:

* A Server Call Usage dashboard that tracks your server call consumption data and compares it to your contractual limit. (**[!UICONTROL Analytics > Admin > Server Call Usage]**)
* A Server Call Usage alert type in the Alert Builder that lets you set up alerts to prevent overages (**[!UICONTROL Analytics > Components >Alerts]**)

I vantaggi principali dell'utilizzo delle chiamate server includono:

* **Visibilità** nei dati relativi al consumo di chiamate server e ai relativi obblighi, incluso l'uso mobile rispetto al limite di utilizzo del server contrattuale.
* **Avvisi** per segnalare al rischio o all'occorrenza di un overage e preparare/agire sulla possibilità di ignorare gli eccessi.

Previously, while you could access monthly server call consumption data under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Billing]** , this data was only updated 6 days after billing had closed for that month. Inoltre, i dati non includevano l'uso mobile. This feature will also replace the current **[!UICONTROL Billing Information]** report under  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** .

## Prerequisiti {#section_49AE590FFC7C4E8A83C640C4AAA581AA}

* **Autorizzazioni**: Per accedere al dashboard Uso server e al Generatore di avvisi/Manager, dovete essere un amministratore di Adobe Analytics.
* **Autorizzazioni**: Gli amministratori possono concedere l'accesso agli utenti non amministratori: l'autorizzazione viene chiamata **[!UICONTROL Server Call Usage]**. See [Server Call Usage Permission](../../admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369).

## Important Terminology {#section_CBA348A039F34563B097CD8890AB358D}

Ecco un breve primer sulla terminologia essenziale per Utilizzo chiamate server:

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
   <td colname="col2"> <p>Una chiamata server, detta anche "hit" o "richiesta immagine", è un'istanza in cui i dati vengono inviati ai server Adobe per l'elaborazione. Il tipo più comune di chiamata server è una visualizzazione di pagina. Viene visualizzata una visualizzazione di pagina in cui un visitatore visualizza una pagina sul sito Web e una chiamata al server viene generata ad Adobe, dove le informazioni vengono raccolte, elaborate e quindi incluse nelle metriche del report. </p> <p>Esistono altri tipi di chiamate server, inclusi i collegamenti exit e i download di file, dove i dati vengono inviati ad Adobe per il processo, ma non sono registrati come nuova visualizzazione pagina. Anche le visualizzazioni di pagina «escluse» (escluse dai rapporti da un intervallo di indirizzi IP configurate, ad esempio) sono chiamate server perché vengono ricevute ed elaborate da Adobe ma non vengono mai visualizzate nei rapporti. </p> <p><b>Chiamata server principale</b>: Richieste ricevute direttamente dai browser dei visitatori del sito Web o dall'API di inserimento dati. Include Hit principali (Visualizzazioni pagina), Eventi personalizzati principali, Eventi di download principali e Exit Exit Events principali. </p> <p><b>Chiamata server secondaria</b>: Copie delle chiamate server principali create da tag multisuite o copiate/spostate da una regola VISTA. Se una chiamata server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono deformate dalle chiamate server principali. </p> <p><b>Chiamata server principale mobile </b> </p> <p>Richieste ricevute direttamente da uno degli SDK di Mobile. Include trackaction, trackstate, trackapp Crashes, trackactionfrombackground, tracklocation, trackbeacon, trackpushcon, trackpushmessageclickthrough, tracktimedacteincrease.</p> <p><b>Chiamata server secondaria mobile</b> </p> <p>Copie delle chiamate server principali create da tag multisuite o copiate/spostate da una regola VISTA. Se una chiamata server secondaria è stata spostata (non copiata) in una suite di rapporti diversa da una regola VISTA, le chiamate secondarie accumulate vengono deformate dalle chiamate server principali. </p> <p>Nota: Se l'azienda ha diritto a ricevere solo chiamate a chiamate server mobili (primaria o secondaria), sia il Web che l'utilizzo specifico per dispositivi mobili verranno conteggiati rispetto all'impegno specifico per dispositivi mobili. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società fatturazione (ID fatturazione) </p> </td> 
   <td colname="col2"> <p>L'entità legale che riceve la fatturazione per le chiamate al server. Ad esempio, adobe. com. Ogni società di fatturazione dispone di un ID fatturazione utilizzato per identificare in modo univoco il cliente di fatturazione. Un ID di fatturazione può essere associato a più organizzazioni Experience Cloud; non esiste sempre una relazione 1:1 tra un'organizzazione e un ID di fatturazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Società di accesso </p> </td> 
   <td colname="col2"> <p>One billing company can have <a href="https://helpx.adobe.com/analytics/kb/multiple-login-companies.html" format="html" scope="external"> multiple login companies </a>. Una società di accesso è una raccolta di suite per report utilizzate dall'organizzazione. Alcune organizzazioni dispongono di più società di accesso che si applicano a diverse parti dell'organizzazione. Ciò è particolarmente utile per le grandi aziende che gestiscono diverse unità aziendali in cui molte suite di rapporti non sono applicabili ad altri all'interno della società. </p> <p>Spesso si tratta di filiali regionali di una società. Questo esempio mostra le società di accesso e le relative suite di rapporti: </p> 
    <ul id="ul_8C756C7972D04F5E89D6E32BB06D26C3"> 
     <li id="li_EA6257FED7854B6FAA071926D0F8A07C">adobe. worldwide: RS 1, RS 2, RS 3, RS 4 </li> 
     <li id="li_3EAFB556849E4CCC9D96D5A3492EC898">adobe. us: RS 1, RS 2 </li> 
     <li id="li_572FFB3F4BF545BDB13102D82CE5E50C">adobe. in: RS 3 </li> 
     <li id="li_B6ACBA35E18A427AA83F76BD38E502D7">adobe. de: RS 4 </li> 
    </ul> <p>Note:  Server call usage data for <u>all</u> report suites within a billing company is visible to all users with the appropriate <a href="../../admin/c-server-call-usage/overage-overview.md#section_FCC58EB635954A32990D4E67B52B4369" format="dita" scope="local"> permission</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Organizzazione Experience Cloud </p> </td> 
   <td colname="col2"> <p>Un'organizzazione è l'entità che consente all'amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L'organizzazione funziona come una società di accesso che si estende su tutti i prodotti e le soluzioni Experience Cloud. </p> <p>Nella maggior parte dei casi, un'organizzazione è il nome dell'azienda. Tuttavia, un'azienda può avere molte organizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Engagement Call Commitment </p> </td> 
   <td colname="col2"> <p>Quando l'azienda firma un contratto con Adobe, il team Vendite Adobe identifica con voi, il cliente, i tipi (Primari, Secondari, Mobile Primaria, Secondaria mobile) e il numero approssimativo di chiamate server che prevedete di sostenere durante il periodo del contratto. Questo è il tuo impegno totale per chiamate server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo di utilizzo </p> </td> 
   <td colname="col2"> <p>Per il monitoraggio dell'utilizzo del server chiamate server, questo impegno totale per il server è suddiviso in periodi di utilizzo minori (ad esempio 3 mesi) per facilitare confronti annuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Periodo contrattuale </p> </td> 
   <td colname="col2"> <p>I periodi di contratto possono risalire più anni. Supponiamo che la tua azienda abbia un impegno di chiamata server di 6 milioni di chiamate per un periodo di contratto di 3 anni. Per il monitoraggio dell'utilizzo di chiamate server, questo periodo di 3 anni può essere suddiviso in periodi di utilizzo più piccoli per facilitare confronti annuali. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Server Call Usage Permission {#section_FCC58EB635954A32990D4E67B52B4369}

L'autorizzazione Utilizzo server server viene assegnata automaticamente agli amministratori di Analytics. Consente agli utenti di visualizzare il dashboard e di creare avvisi per chiamate server. Gli amministratori possono scegliere di concedere questa autorizzazione agli utenti non amministratori.

>[!NOTE]
>
>La società può scegliere quali società di accesso hanno accesso a Utilizzo server server.

<table id="table_86256AD8B4554F369439A8FDF2F545E1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome autorizzazione </th> 
   <th colname="col3" class="entry"> Concedere l'autorizzazione se hai effettuato l'accesso ad Adobe Analytics (accesso legacy) </th> 
   <th colname="col4" class="entry"> Concedere l'autorizzazione se hai effettuato l'accesso ad Adobe Experience Cloud </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Utilizzo delle chiamate server </p> </td> 
   <td colname="col3"> 
    <ol id="ol_13A984328D264488B7045DC7521A5F55"> 
     <li id="li_ACDA518C7D184084AC1DFA7B38C67314">Accedi ad Analytics tramite sc. omniture. com. </li> 
     <li id="li_066D90AB071941C3869EDAFCE981707A">Navigate to <span class="ignoretag"> <span class="uicontrol"> Admin </span>  &gt; <span class="uicontrol"> User Management </span>  &gt; <span class="uicontrol"> Groups </span>  &gt; <span class="uicontrol"> Edit All Report Access </span>  &gt; <span class="uicontrol"> Analytics Tools </span>  &gt; <span class="uicontrol"> Customize </span>  &gt; <span class="uicontrol"> Server Call Usage </span> </span> </li> 
    </ol> </td> 
   <td colname="col4"> 
    <ol id="ol_518673ED323A4C5993A3B9F4BA09E405"> 
     <li id="li_56FF685A3B454ECEA5F16BB591A60034">Accedi a login. experiencecloud. adobe. com.</li> 
     <li id="li_FA1AE0F19DEF4AB2AA77B22CCA2995F9">Click <span class="uicontrol"> Analytics </span>. </li> 
     <li id="li_22A4CBB84B5A451780873BBE67E6E6EF">Navigate to <span class="ignoretag"> <span class="uicontrol"> Products </span>  &gt; <span class="uicontrol"> Product Profile </span>  &gt; <span class="uicontrol"> Permissions </span>  &gt; <span class="uicontrol"> Analytics Tools </span>  &gt; <span class="uicontrol"> Server Call Usage </span> </span> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

