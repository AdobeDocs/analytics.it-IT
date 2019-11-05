---
seo-title: Configurare un account Advertising
title: Configurare un account Advertising
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Configurare un account Advertising

Gli amministratori di Adobe Analytics possono creare nuovi account pubblicitari e mappare più account a più suite di rapporti (1:1, 1:Molti, Molti:Molti).

Gli amministratori possono anche [concedere l'accesso agli utenti non amministratori](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) per l'impostazione di account pubblicitari.

![](assets/aa_accounts.png)

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Advertising Accounts]**.
1. (Solo per uso iniziale) Accettate i termini del contratto di licenza con l'utente finale.
1. Fai clic su **[!UICONTROL + Add]**.
1. Viene [!UICONTROL New Search Engine Account] visualizzata la finestra di dialogo:

   ![](assets/aa_new_se_account.png)

1. Compila i **[!UICONTROL Search Engine Settings]** seguenti orientamenti:

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Impostazione </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Sono disponibili due opzioni: Google AdWords e Microsoft Bing Ads. </p> <p>Nota: Yahoo Gemini è stato assorbito da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome account </p> </td> 
      <td colname="col2"> <p>Potete scegliere di impostare questo nome account su qualsiasi nome adatto. Questo è il nome descrittivo dell'account che verrà visualizzato nell'interfaccia utente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Token OAuth </p> </td> 
      <td colname="col2"> <p>Nota:  OAuth è uno standard aperto per la delega di accesso, comunemente utilizzato come modo per garantire ai siti Web o alle applicazioni l'accesso alle loro informazioni su altri siti Web, ma senza dare loro le password. </p> <p>Nota:  Noterete che verrete indirizzati a un URL di terze parti (efrontier.com). Adobe utilizza Edge per alimentare il processo di autenticazione OAuth per tutti e tre i motori di ricerca. </p> <p>Nota:  Se si utilizza Internet Explorer 11 (o versioni precedenti), non sarà possibile recuperare correttamente il token Oauth per nessuno dei tre motori di ricerca. Utilizzate altri browser Web. </p> <p>Facendo clic<span class="uicontrol"> su Recupera token</span> si avvia il processo di autenticazione OAuth2. Questo significa che ti verrà chiesto di accedere al tuo account di ricerca Google/Bing utilizzando le tue credenziali. A seconda del motore di ricerca scelto, il processo è leggermente diverso: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: Fornite l'ID account Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: Fornite l'ID account Bing e l'ID cliente Bing. </li> 
        </ul> <p>Per informazioni su questi ID, consultate <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Individuare l'ID</a> account. </p> <p>Dopo aver eseguito l'accesso, viene visualizzato il campo Token OAuth 
        <systemoutput>
          Recuperato
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Nella **[!UICONTROL Tracking]** sezione , fornisci informazioni su come i dati del motore di ricerca vengono tracciati dall’implementazione di Adobe Analytics. Si tratta di un passaggio necessario per incrementare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
Compila i **[!UICONTROL Tracking Settings]** seguenti orientamenti:

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Impostazione </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Auto</span>: Consente al motore di Advertising Cloud di decidere in che modo i parametri di tracciamento vengono aggiunti ai modelli di tracciamento/agli URL di destinazione del motore di ricerca. Questo è l'approccio più semplice, ma non può portare al miglior set di dati integrato. <p>Importante: Per configurare un account del motore di ricerca in modalità automatica, è necessario effettuare le seguenti operazioni: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">Il parametro e il valore "s_kwcid" verranno aggiunti ai modelli di tracciamento dell'account o agli URL delle pagine di destinazione nell'account che si sta aggiungendo. Questo verrà inserito alla fine dell’URL. Di conseguenza, potrebbe essere necessaria un'azione aggiuntiva da parte dell'utente se il server Web richiede una coppia chiave=valore alla fine dell'URL OPPURE un aggiornamento per supportare qualsiasi nuova coppia chiave=valore nell'URL. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">Inoltre, le parole chiave possono essere inserite nell'URL di destinazione come parte del valore "s_kwcid", quindi se contengono caratteri speciali o simboli, si prega di confermare che il server Web può supportare tali caratteri (un esempio di caratteri speciali comuni è "+", utilizzato nelle parole chiave "Broad Match Modified"). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manuale</span>: Consente di gestire il modo in cui i parametri di tracciamento vengono aggiunti ai modelli di tracciamento/agli URL di destinazione del motore di ricerca. <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md"  > Fare riferimento a questi esempi di tracciamento manuale per ciascun motore</a>di ricerca. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. Nella **[!UICONTROL Mapping]** sezione, scegliete le suite di rapporti da collegare a questo account del motore di ricerca. Devi fornire almeno una suite di rapporti prima di poter salvare l'account pubblicitario. Potete mappare più account a più suite di rapporti (1:1, 1:Molti, Molti:Molti). Notate che i dati che AMO estrae dal motore di ricerca vengono semplicemente copiati in qualsiasi suite di rapporti mappata, quindi non c'è divisione dei dati.

   >[!IMPORTANT]
   >
   >Solo le suite di rapporti che sono state [mappate a un'organizzazione](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) Experience Cloud saranno disponibili per la selezione. Se la suite di rapporti non è elencata, consulta [Risoluzione dei problemi relativi ad Analisi](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md)pubblicitaria.

   Per i **[!UICONTROL Mapping Settings]** seguenti orientamenti:

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Impostazione </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Mappatura suite di rapporti </p> </td> 
      <td colname="col2"> <p>La mappatura della suite di rapporti determina la suite di rapporti che viene collegata a questo account del motore di ricerca. In altre parole, determina in quali suite di rapporti vengono inviati i dati del motore di ricerca. </p> <p>Se la suite di rapporti non è elencata, puoi <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html"  > mappare la tua suite di rapporti su un'organizzazione</a> Experience Cloud utilizzando questo strumento. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Save]**.
1. Dopo il salvataggio, una liberatoria visualizza un elenco di avvertenze. Vi verrà chiesto di confermare di aver letto e di comprendere il presente contratto. Click the checkbox, then click **[!UICONTROL OK]**.

   Ora puoi passare all’interfaccia utente [di](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)gestione degli account pubblicitari, in cui deve essere elencato l’account appena creato.

> [!NOTE] Devi aspettare almeno 24 ore prima che i dati del motore di ricerca inizino a compilare i report di Analytics.

