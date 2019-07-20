---
seo-title: Configurare un account pubblicitario
title: Configurare un account pubblicitario
uuid: 4 e 37 caa 3-e 4 a 5-43 ad -97 c 0-12 db 62 ad 5283
translation-type: tm+mt
source-git-commit: 463e28e9d710cc41e4ab4ace5e3861b8ae8fbdcc

---


# Configurare un account pubblicitario

Gli amministratori di Adobe Analytics possono creare nuovi account pubblicitari e mappare più account a più suite di rapporti (1:1, 1: Molti, molti: Molti).

Administrators can also [grant access to non-admins](../../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) for setting up advertising accounts.

![](assets/aa_accounts.png)

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Advertising Accounts]**.
1. (Solo per uso iniziale) Accettate i termini del contratto di licenza per l'utente finale.
1. Fai clic su **[!UICONTROL + Add]**.
1. The [!UICONTROL New Search Engine Account] dialog displays:

   ![](assets/aa_new_se_account.png)

1. Fill in the **[!UICONTROL Search Engine Settings]** following these guidelines:

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
      <td colname="col2"> <p>Sono disponibili 2 opzioni: Google adwords e Microsoft Bing Ads. </p> <p>Nota: Yahoo Gemini è stato assorbito da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome account </p> </td> 
      <td colname="col2"> <p>Potete scegliere di impostare questo nome account su qualsiasi nome adatto. Questo è il nome descrittivo dell'account che verrà visualizzato nell'interfaccia utente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Token oauth </p> </td> 
      <td colname="col2"> <p>Nota: Oauth è uno standard aperto per la delega di accesso, comunemente utilizzato per concedere ai siti Web o alle applicazioni l'accesso alle proprie informazioni su altri siti Web, senza però trasmettere loro le password. </p> <p>Nota: Noterete che verrete indirizzati a un URL di terze parti (efrontier.com). Adobe utilizza la frontiera per attivare il processo di autenticazione oauth per tutti e tre i motori di ricerca. </p> <p>Nota: Se utilizzate Internet Explorer 11 (o versione precedente), non potrete recuperare il token Oauth per i tre motori di ricerca. Utilizzare invece altri browser Web. </p> <p>Clicking<span class="uicontrol"> Retrieve Token</span> launches the OAuth2 authentication process. Ciò significa che ti verrà chiesto di accedere all'account di ricerca Google/Bing utilizzando le tue credenziali. A seconda del motore di ricerca scelto, il processo è leggermente diverso: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: Fornisci ID account Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: Fornisci ID account Bing e ID cliente Bing. </li> 
        </ul> <p>Refer to <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md#concept_F7F67448F3B44342967E0419E96F384D" format="dita" scope="local"> Locate your Account ID</a> for information on these IDs. </p> <p>Dopo aver eseguito l'accesso, il campo Token oauth verrà visualizzato 
        <systemoutput>
          Recuperato
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. In the **[!UICONTROL Tracking]** section, you provide information on how the Search Engine data is tracked by your Adobe Analytics implementation. Questo è un passaggio obbligatorio per potenziare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
Fill in the **[!UICONTROL Tracking Settings]** following these guidelines:

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
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Automatico</span>: Consente al motore della pubblicità di stabilire in che modo i parametri di tracciamento vengono aggiunti ai modelli di tracciamento/URL di tracciamento del motore di ricerca. Questo è l'approccio più semplice, ma potrebbe non dare luogo al miglior set di dati integrato. <p>Importante: Per configurare un account del motore di ricerca in modalità automatica, è necessario effettuare le azioni seguenti: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">Il parametro "s_ kwcid" e il valore verranno aggiunti al tracciamento dell'account o agli URL delle pagine di destinazione nell'account aggiunto. Verrà inserita alla fine dell'URL. Di conseguenza, se il server Web richiede una determinata coppia chiave = valore alla fine dell'URL o un aggiornamento per supportare qualsiasi nuova coppia chiave = valore nell'URL, potrebbe essere necessaria un'azione aggiuntiva. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">Inoltre, le parole chiave possono essere inserite nell'URL di destinazione come parte del valore "s_ kwcid", quindi se contengono caratteri speciali o simboli, confermate che il server Web possa supportare tali caratteri (un esempio di caratteri speciali comuni è " +" che viene utilizzato nelle parole chiave "Corrispondenza ampia"). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manuale</span>: Consente di gestire il modo in cui i parametri di tracciamento vengono aggiunti ai modelli di tracciamento/URL di tracciamento del motore di ricerca. <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md#concept_87B28BA9E7F84BA5972F69E6F3482A33" format="dita" scope="local"> Consultate questi esempi di tracciamento manuale per ogni motore di ricerca</a>. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. In the **[!UICONTROL Mapping]** section, you choose which report suite(s) to link to this search engine account. Prima di poter salvare l'account pubblicitario, devi fornire almeno una suite di rapporti. Puoi mappare più account a più suite di rapporti (1:1, 1: Molti, molti: Molti). I dati che AMO dal motore di ricerca vengono semplicemente copiati in qualsiasi suite di rapporti mappati, pertanto non si verifica alcuna suddivisione dei dati.

   >[!IMPORTANT]
   >
   >Only report suites that have been [mapped to an Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) will be available for selection. If you do not see your report suite listed, refer to [Troubleshoot Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   For the **[!UICONTROL Mapping Settings]** following these guidelines:

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
      <td colname="col2"> <p>La mappatura suite di rapporti determina la suite di rapporti che viene collegata a questo account del motore di ricerca. In altre parole, determina in quale suite di rapporti vengono inviati i dati del motore di ricerca. </p> <p>If you do not see your report suite listed, you can <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html" format="html" scope="external"> map your report suite to an Experience Cloud organization</a> using this tool. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Save]**.
1. Dopo aver salvato, una dichiarazione di non responsabilità visualizza un elenco di avvertenze. Ti viene chiesto di confermare che hai letto e di avere compreso questo accordo. Click the checkbox, then click **[!UICONTROL OK]**.

   You are now taken to the Advertising Accounts [Management UI](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md#concept_531B99165A4E47B4B8849376B532AFDB), where your newly created account should be listed.

>[!NOTE]
>
>È prevista almeno 24 ore prima che i dati del motore di ricerca inizino a compilare i report di Analytics.

