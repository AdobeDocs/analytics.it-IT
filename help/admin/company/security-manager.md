---
description: Consente di controllare l'accesso ai dati di reporting. Le opzioni includono password complesse, scadenza password, limitazioni di accesso IP e limitazioni per il dominio e-mail.
seo-description: Consente di controllare l'accesso ai dati di reporting. Le opzioni includono password complesse, scadenza password, limitazioni di accesso IP e limitazioni per il dominio e-mail.
seo-title: Security Manager
solution: Analytics
title: Security Manager
topic: Strumenti di amministrazione
uuid: b 3 fbdba 0-e 2 bf -4 d 67-92 e 3-ef 05711141 d 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Security Manager

Consente di controllare l'accesso ai dati di reporting. Le opzioni includono password complesse, scadenza password, limitazioni di accesso IP e limitazioni per il dominio e-mail.

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Security]**

<table id="table_F1AD9DE5094A4FC2B9DA8D01198F944B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Richiedi password rigorose </span> </td> 
   <td colname="col2">Impone agli utenti di creare password più sicure che rispettano le regole seguenti: 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">Devono contenere almeno otto caratteri. </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">Contiene almeno un carattere simbolo/numero tra il primo e l'ultimo carattere. </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">Ha almeno un carattere alfa. </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">Non è possibile trovare un dizionario né contenere parole da un dizionario (inglese). </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">Potrebbe non includere tre caratteri consecutivi (3) dal nome utente di accesso. </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">Deve essere diverso dalle precedenti 10 password. </li> 
    </ul> <p>Nota: Questa funzione è applicata sulle nuove password che vanno avanti. Non controlla le password esistenti o forza gli utenti a modificare le password esistenti. Per questo motivo, è consigliabile abilitare la scadenza della password per obbligare gli utenti a cambiare password e a rispettare le severe regole per la password. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Scadenza password</span> </td> 
   <td colname="col2"> Impone agli utenti di modificare regolarmente la password dell'account utente. Puoi specificare l'intervallo di scadenza delle password e forzare la scadenza immediata delle password. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Applicazione delle restrizioni di accesso IP</span> </td> 
   <td colname="col2"> <p>Limita l'accesso ai rapporti a indirizzi IP specifici o intervalli di indirizzi IP. </p> <p>Potete aggiungere fino a 100 voci nell'elenco dei filtri IP e ogni voce può essere un indirizzo specifico o un intervallo di indirizzi. </p> <p> <span class="wintitle"> L'applicazione delle restrizioni</span> di accesso IP non viene applicata finché non vi è almeno una voce nell'elenco Filtro indirizzo IP. </p> <p> <span class="uicontrol"> Indirizzo IP accettato</span>: Per specificare un intervallo di indirizzi IP, racchiudere l'intervallo tra parentesi (ad esempio, <code>
 
 192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> <p>Failed logins are logged and viewable from the <a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local"> Usage and Access Log</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Applica limitazioni per il dominio e-mail</span> </td> 
   <td colname="col2"> <p>Filtra gli indirizzi e-mail e i domini in cui Analytics invia segnalibri, rapporti scaricabili e avvisi. </p> <p>L'elenco dei filtri e-mail supporta fino a 100 voci e ogni voce può essere un indirizzo e-mail o un intero dominio e-mail. </p> <p>Se un rapporto pianificato dispone di una destinazione e-mail non approvata, Analytics invia una notifica e-mail del problema e un collegamento per l'annullamento della pianificazione del rapporto. </p> <p> <span class="wintitle"> L'opzione Applica limitazioni</span> del dominio e-mail non viene applicata finché non è presente almeno una voce nell' <span class="wintitle"> elenco Filtro</span> dominio e-mail accettato. </p> <p> <span class="uicontrol"> Indirizzo e-mail e domini accettati</span>: Per specificare un intervallo di indirizzi IP, racchiudere l'intervallo tra parentesi (ad esempio, <code>
 
 192.168.10.[20-240]
     </code>). You can also use wildcards (*) to specify any number from 0 to 255 (for example, 
     <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notifica di recupero password</span> </td> 
   <td colname="col2"> <p>Notifica agli amministratori specificati quando un utente tenta di ripristinare una password di account utente. </p> <p> <span class="uicontrol"> Amministratori disponibili</span>: Visualizza tutti gli amministratori. Per selezionare più amministratori, tenete premuto Ctrl e Maiusc e fate clic. </p> <p> <span class="uicontrol"> Membri e-mail</span>: Visualizza il gruppo di posta elettronica attualmente definito. </p> </td> 
  </tr> 
 </tbody> 
</table>

