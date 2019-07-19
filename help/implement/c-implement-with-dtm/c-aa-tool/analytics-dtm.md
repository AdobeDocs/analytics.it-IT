---
description: Implementa Adobe Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe Analytics e configurando il codice della pagina in modo automatico o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; strumento Analisi,proprietà; tipo di strumento; nome dello strumento; metodo di configurazione; analytics premium; evar; eventi
seo-description: Implementa Adobe Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe Analytics e configurando il codice della pagina in modo automatico o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.
seo-title: Strumento Aggiungi Adobe Analytics
solution: Analytics
title: Strumento Aggiungi Adobe Analytics
topic: Sviluppatore e implementazione
uuid: 1 c 54331 e-de 03-4 f 44-8002-a 19723 c 585 b 0
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Strumento Aggiungi Adobe Analytics

Implementa Adobe Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe Analytics e configurando il codice della pagina in modo automatico o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.

>[!NOTE]
>
>For improved visitor tracking, we strongly recommend that you enable [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Add an Adobe Analytics Tool {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Click  **[!UICONTROL  *`Web Property Name`*]**&gt;**[!UICONTROL Overview]**&gt;**[!UICONTROL Add a Tool]**&gt;**[!UICONTROL Adobe Analytics]**.

   ![](assets/dtm-add-analytics-tool.png)

1. Compila i campi:

<table id="table_1CFB53FE72E74CCB8CAA5D4E3873D286"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tipo di strumento </p> </td> 
   <td colname="col2">The type of tool, such as <span class="keyword"> Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome dello strumento </p> </td> 
   <td colname="col2">Un nome descrittivo per questo strumento. This name displays on the <span class="wintitle"> Overview</span> tab under <span class="wintitle"> Installed Tools</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Metodo di configurazione </p> </td> 
   <td colname="col2"> <p> <b>Automatic</b> (Recommended): Use dynamic tag management to manage the configuration. This method enables automatic synchronization of <span class="keyword"> Adobe Analytics</span> report suites via a <span class="keyword"> Experience Cloud</span> login or Web Services ID, and manages the [!DNL AppMeasurement] code. </p> <p>After the accounts are connected, Dynamic Tag Management pulls the <span class="keyword"> Adobe Analytics</span> report suite IDs and names into the tool configuration interface, allowing for increased speed in tool deployment with less possibility for user errors. </p> <p> <p>Note: You must choose the <span class="wintitle"> Automatic</span> option if you are an <span class="keyword"> Adobe Analytics Premium</span> customer. See <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#section_AEAA44566B5A46D2922E17A11D7EA217" format="dita" scope="local"> Enabling Adobe Analytics Premium</a> below. </p> </p> <p>Compila i campi specifici della configurazione automatica: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (Impostazione predefinita) Usa <span class="keyword"> il single sign-on di Experience Cloud</span> . Specifica il tuo Experience Cloud ID e la password. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Servizi Web</b>: Specifica il nome utente Servizi Web e il segreto condiviso. </p> <p>Shared secret credentials are located in <span class="uicontrol"> Admin Tools</span> &gt; <span class="uicontrol"> Company Settings</span> &gt; <a href="https://microsite.omniture.com/t2/help/en_US/reference/web_services_admin.html" format="html" scope="external"> Web Services</a>. </p> <p>Developers, see <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api" format="https" scope="external"> Get Web Service Access to the Enterprise API</a> for help with obtaining Web Services credentials. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manuale</b>: Gestire manualmente [! DNL appmeasurement]. You can download the <span class="keyword"> Analytics</span><span class="keyword"> AppMeasurement</span> code from <span class="ignoretag"><span class="uicontrol"> Admin Tools</span> &gt; <span class="uicontrol"> Code Manager</span></span>. </p> <p>Click <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html" format="https" scope="external"> JavaScript (new)</a> for information about downloading the code locally to copy and paste in the <span class="wintitle"> Edit Code</span> field in <a href="../../../implement/c-implement-with-dtm/c-aa-tool/library-management.md#concept_24654766343B4E82A9416A112D2125FE" format="dita" scope="local"> Library Management</a>. </p> <p>Compila i campi specifici di una configurazione manuale: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID account produzione: </b>(Obbligatorio) L'account di produzione per la raccolta dati. Per Analytics, si tratta dell'ID suite di rapporti. Gestione tag dinamica installa automaticamente l'account corretto nell'ambiente di produzione e di staging. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID account di verifica: </b>(Obbligatorio) Utilizzato nell'ambiente di sviluppo o di prova. Per Analytics, si tratta dell'ID suite di rapporti. Un account di verifica mantiene i dati di verifica separati dalla produzione. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Server di tracciamento: </b>Specifica le informazioni per il server di tracciamento. </p> <p>The <span class="wintitle"> Tracking Server</span> and <span class="wintitle"> SSL Tracking Server</span> variables are used for first-party cookie implementation to specify the domain at which the image request and cookie is written. For more information, see the <a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"> Correctly Populate the trackingServer and trackingServerSecure Variable</a> article. </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL Tracking Server: </b>Specificate le informazioni per il server di tracciamento SSL. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Click **[!UICONTROL Create Tool]** to create the tool and display it for editing.

   Tools are displayed on the [!UICONTROL Overview] tab, under [!UICONTROL Installed Tools].

1. (Conditional) Configure the tool further as necessary by following the directions in the links below ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies], and [!UICONTROL Customize Page Code]).

See [Frequently Asked Questions About the Adobe Analytics Tool](../../../implement/faq.md#concept_00DF9AF14D30469BB986BF56A448806B) for additional information about this tool.

## Edit an Existing Adobe Analytics Tool {#section_148B16AF429B4949B06238D90635B726}

Potete modificare un strumento Adobe Analytics esistente per modificarne le impostazioni di configurazione.

1. Click the  ![](assets/settings_gear.png) icon next to an installed tool from the [!UICONTROL Overview] tab.
1. Modificate i campi come desiderato.

   La tabella seguente include solo gli elementi che differiscono dagli elementi disponibili quando si crea uno strumento Analytics, come descritto in precedenza. Tuttavia, è possibile modificare qualsiasi elemento della pagina, come descritto in entrambe le tabelle.

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Abilita configurazione automatica </p> </td> 
   <td colname="col2"> <p>Note: Enabling this setting changes a manually configured implementation to the automatic configuration method described in <span class="term"> Configuration Method</span>. </p> <p>This option lets Dynamic Tag Management automatically retrieve your <span class="keyword"> Adobe Analytics</span> account's configuration. </p> <p>La più recente disponibile [! DNL appmeasurement] viene utilizzato e le notifiche di aggiornamento vengono visualizzate per la selezione quando diventano disponibili nuove versioni. Potete anche ripristinare precedente [! DNL appmeasurement], in base alle esigenze, ad esempio per motivi di compatibilità. Vengono visualizzate fino a cinque versioni precedenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna credenziali </p> </td> 
   <td colname="col2"> <p>Aggiornate l'API, ad esempio, per aggiornare le suite di rapporti associate a un utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Conditional) Configure the tool further as necessary by following the directions in the links below ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies], and [!UICONTROL Customize Page Code]).
1. Fai clic su **[!UICONTROL Save Changes]**.
