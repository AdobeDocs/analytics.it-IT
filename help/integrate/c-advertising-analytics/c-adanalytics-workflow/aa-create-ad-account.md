---
title: Come impostare un account Advertising in Advertising Analytics
description: Consente di creare nuovi account pubblicitari e di eseguire il mapping di più account a più suite di rapporti.
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '844'
ht-degree: 3%

---

# Configurare un account Advertising

Gli amministratori di Adobe Analytics possono creare nuovi account pubblicitari e mappare più account a più suite di rapporti (1:1, 1:Many, Many:Many).

Gli amministratori possono inoltre [concedere l&#39;accesso agli utenti non amministratori](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) per l&#39;impostazione di account pubblicitari.

![](assets/aa_accounts.png)

1. In Adobe Analytics, passa a **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. (Solo per uso iniziale) Accettare i termini del contratto di licenza con l’utente finale.
1. Fai clic su **[!UICONTROL + Add]**.
1. Viene visualizzata la finestra di dialogo [!UICONTROL New Search Engine Account]:

   ![](assets/aa_new_se_account.png)

1. Compila le seguenti **[!UICONTROL Search Engine Settings]** linee guida:

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
      <td colname="col2"> <p>Sono disponibili 2 opzioni: Google AdWords e Microsoft Bing Ads. </p> <p>Nota: Yahoo Gemini è stata assorbita da Microsoft Bing il 31 marzo 2019. Di conseguenza, l’opzione per l’account per annunci Yahoo Gemini non è più disponibile.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nome account </p> </td> 
      <td colname="col2"> <p>Puoi scegliere di impostare questo nome account su qualsiasi nome che desideri. Questo è il nome descrittivo dell’account che verrà visualizzato nell’interfaccia utente. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Token OAuth </p> </td> 
      <td colname="col2"> <p>Nota:  OAuth è uno standard aperto per la delega degli accessi, comunemente utilizzato come modo per garantire ai siti web o alle applicazioni l’accesso alle loro informazioni su altri siti web, ma senza fornire loro le password. </p> <p>Nota:  Noterai che verrai indirizzato a un URL di terze parti (efrontier.com). L’Adobe utilizza efrontier per alimentare il processo di autenticazione OAuth per tutti e tre i motori di ricerca. </p> <p>Nota:  Se si utilizza Internet Explorer 11 (o versioni precedenti), non sarà possibile recuperare correttamente il token Oauth per nessuno dei tre motori di ricerca. Usa altri browser web. </p> <p>Facendo clic su<span class="uicontrol"> Retrieve Token</span> si avvia il processo di autenticazione OAuth2. Questo significa che ti verrà chiesto di accedere al tuo account di ricerca Google/Bing utilizzando le tue credenziali. A seconda del motore di ricerca scelto, il processo è leggermente diverso: </p>
      <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
       <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: Fornisci l'ID account Google. </li> 
       <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: Fornire l’ID account Bing e l’ID cliente Bing. </li> 
       </ul> <p>Per informazioni su questi ID, consulta <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Individua il tuo ID account</a> . </p> <p>Dopo aver effettuato l’accesso, il campo del token OAuth viene visualizzato <code>Retrieved</code>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Nella sezione **[!UICONTROL Tracking]** fornisci informazioni su come i dati del motore di ricerca vengono tracciati dall’implementazione Adobe Analytics. Questo è un passaggio necessario per integrare correttamente i dati di Adobe Analytics con i dati del motore di ricerca.
Compila le seguenti **[!UICONTROL Tracking Settings]** linee guida:

   | Impostazione | Descrizione |
   |--- |--- |
   | Tipo | <ul><li>**Automatico:** consente al motore di Advertising Cloud di decidere in che modo i parametri di tracciamento vengono aggiunti ai modelli di tracciamento o agli URL di destinazione del motore di ricerca. Questo è l’approccio più semplice, ma potrebbe non tradursi in un set di dati integrato ottimale.<br>**Importante:** per configurare un account del motore di ricerca in &quot;Modalità automatica&quot;, sei responsabile di intraprendere le seguenti azioni:<br> - Il parametro e il valore &quot;s_kwcid&quot; verranno aggiunti ai modelli di tracciamento dell’account o agli URL della pagina di destinazione nell’account aggiunto. Questo verrà inserito alla fine dell’URL. Di conseguenza, potrebbe essere necessaria un&#39;azione aggiuntiva da parte dell&#39;utente se il server web richiede una determinata coppia chiave=valore alla fine dell&#39;URL OPPURE un aggiornamento per supportare una nuova coppia chiave=valore nell&#39;URL. **Nota:** ulteriori informazioni su se aggiungere questo parametro ai criteri sulla sicurezza dei  [contenuti](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html).<br>- Inoltre, le parole chiave possono essere inserite nell’URL di destinazione come parte del valore &quot;s_kwcid&quot;, quindi se contengono caratteri o simboli speciali, si prega di confermare che il server web può supportare tali caratteri (un esempio di caratteri speciali comuni è &quot;+&quot; che viene utilizzato nelle parole chiave &quot;Broad Match Modified&quot;).</li><li>**Manuale:** consente di gestire l’aggiunta dei parametri di tracciamento ai modelli di tracciamento o agli URL di destinazione del motore di ricerca. [Fai riferimento a questi esempi di tracciamento manuale per ogni motore](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md) di ricerca.</li></ul> |

1. Nella sezione **[!UICONTROL Mapping]** scegli le suite di rapporti da collegare a questo account del motore di ricerca. Devi fornire almeno una suite di rapporti prima di poter salvare l’account Advertising. Puoi mappare più account a più suite di rapporti (1:1, 1:Many, Many:Many). Tieni presente che i dati richiamati da AMO dal motore di ricerca vengono semplicemente copiati in qualsiasi suite di rapporti mappata, in modo che non vi sia divisione dei dati.

   >[!IMPORTANT]
   >
   >Solo le suite di rapporti mappate [a un&#39;organizzazione Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html) saranno disponibili per la selezione. Se la suite di rapporti non è elencata, consulta [Risoluzione dei problemi relativi ad Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Per **[!UICONTROL Mapping Settings]** seguire le seguenti linee guida:

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Impostazione </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Mappatura di suite di rapporti </p> </td> 
      <td colname="col2"> <p>La mappatura della suite di rapporti determina la suite di rapporti che viene collegata a questo account del motore di ricerca. In altre parole, determina in quali suite di rapporti vengono inviati i dati del motore di ricerca. </p> <p>Se la suite di rapporti non è elencata, è possibile <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/report-suite-mapping.html"  > mappare la suite di rapporti su un'organizzazione di Experience Cloud</a> utilizzando questo strumento. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Fai clic su **[!UICONTROL Save]**.
1. Dopo il salvataggio, una liberatoria visualizza un elenco di avvertenze. Ti viene chiesto di confermare di aver letto e di comprendere questo accordo. Fai clic sulla casella di controllo, quindi fai clic su **[!UICONTROL OK]**.

   Ora vieni indirizzato agli account pubblicitari [Interfaccia utente di gestione](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md), dove deve essere elencato l&#39;account appena creato.

>[!NOTE]
>
>Attendi almeno 24 ore prima che i dati del motore di ricerca inizino a popolare i rapporti di Analytics.
