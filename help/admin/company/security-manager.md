---
description: Consente di controllare l'accesso ai dati di reporting. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail.
seo-description: Consente di controllare l'accesso ai dati di reporting. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail.
seo-title: Sicurezza Manager
solution: Analytics
title: Sicurezza Manager
topic: Strumenti di amministrazione
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: cc87c5a7b193fe8a36ce7409a833cc0b91b8af60

---


# Sicurezza Manager

Consente di controllare l'accesso ai dati di reporting. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail.

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
   <td colname="col1"> <span class="wintitle"> Richiedi password complesse </span> </td> 
   <td colname="col2">Impone agli utenti di creare password più sicure che rispettino le seguenti regole: 
    <ul id="ul_100CC57EB4374DAA87B2074BA8B46F26"> 
     <li id="li_4D9102C361044FADBC14402A8398F2F3">Deve contenere almeno otto caratteri. </li> 
     <li id="li_AFE9568C14894E93BFDFDC84DCD2838D">Contiene almeno un simbolo/numero di carattere tra il primo e l'ultimo carattere. </li> 
     <li id="li_ECA05BEF7BFD4430B09D4A953B41D2A6">Ha almeno un carattere alfa. </li> 
     <li id="li_6928045588E94E28851BB15991C8D51E">Impossibile trovare in un dizionario o contenere parole da un dizionario (inglese). </li> 
     <li id="li_C3DD4608CA6F43E4B1E4FCFC6D116371">Potrebbe non includere tre (3) caratteri consecutivi dal nome utente di accesso. </li> 
     <li id="li_687838CA01B94EE29EF4C09F485C5537">Deve essere diversa dalle 10 password precedenti. </li> 
    </ul> <p>Nota:  Questa funzione viene applicata anche alle nuove password. Non controlla le password esistenti o obbliga gli utenti a cambiare quelle esistenti. Per questo motivo, è consigliabile abilitare la scadenza della password per obbligare gli utenti a cambiare la password e ad aderire alle regole per la password complessa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Scadenza password</span> </td> 
   <td colname="col2"> Impone agli utenti di cambiare regolarmente la password dell'account utente. È possibile specificare l'intervallo di scadenza delle password e forzare la scadenza immediata delle password. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Applica limitazioni di accesso IP</span> </td> 
   <td colname="col2"> <p>Questa funzionalità non sarà più disponibile a gennaio 2020. Limita l'accesso al report a indirizzi IP o intervalli di indirizzi IP specifici. </p> <p>È possibile aggiungere fino a 100 voci nell'elenco Filtro indirizzi IP e ogni voce può essere un indirizzo specifico o un intervallo di indirizzi. </p> <p> <span class="wintitle"> Applica restrizioni</span> di accesso IP non viene applicata finché non è presente almeno una voce nell'elenco Filtro indirizzi IP. </p> <p> <span class="uicontrol"> Indirizzo</span>IP accettato: Per specificare un intervallo di indirizzi IP, racchiudere l'intervallo tra parentesi (ad esempio, <code>
       192.168.10.[20-240]
     </code>). È inoltre possibile utilizzare i caratteri jolly (*) per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, <code>
       192.168.[10-14].*
     </code>) </p> <p>Gli accessi non riusciti vengono registrati e visualizzati dal registro <a href="../../admin/admin/logs.md#section_6FBAF92D9EA244809C45A78A2F0A7232" format="dita" scope="local"></a>di utilizzo e accesso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Applica limitazioni dominio e-mail</span> </td> 
   <td colname="col2"> <p>Filtra gli indirizzi e-mail e i domini in cui Analytics invia segnalibri, rapporti scaricabili e avvisi. </p> <p>L'elenco dei filtri e-mail supporta fino a 100 voci e ogni voce può essere un indirizzo e-mail o un intero dominio e-mail. </p> <p>Se in un report pianificato è presente una destinazione e-mail non approvata, Analytics invia una notifica e-mail del problema e un collegamento per annullare la pianificazione del report. </p> <p> <span class="wintitle"> Applica restrizioni</span> dominio e-mail non viene applicata finché non è presente almeno una voce nell'elenco Filtro <span class="wintitle"> dominio e-mail</span> accettato. </p> <p> <span class="uicontrol"> Indirizzo e-mail e domini</span>accettati: Per specificare un intervallo di indirizzi IP, racchiudere l'intervallo tra parentesi (ad esempio, <code>
       192.168.10.[20-240]
     </code>). È inoltre possibile utilizzare i caratteri jolly (*) per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, <code>
       192.168.[10-14].*
     </code>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Notifica recupero password</span> </td> 
   <td colname="col2"> <p>Notifica agli amministratori specificati quando un utente tenta di reimpostare la password di un account utente. </p> <p> <span class="uicontrol"> Amministratori</span>disponibili: Visualizza tutti gli amministratori. Per selezionare più amministratori, tenete premuto Ctrl e Maiusc e fate clic. </p> <p> <span class="uicontrol"> Membri</span>e-mail: Visualizza il gruppo di e-mail attualmente definito. </p> </td> 
  </tr> 
 </tbody> 
</table>

