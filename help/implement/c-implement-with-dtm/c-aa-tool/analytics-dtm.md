---
description: Distribuisci Adobe Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe Analytics e configurando il codice di pagina automaticamente o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.
keywords: Analytics Implementation;metodo di implementazione;gestione tag dinamica;dtm;strumento di analisi;proprietà;tipo di strumento;nome strumento;metodo di configurazione;Analytics premium;evar;eventi
seo-description: Distribuisci Adobe Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe Analytics e configurando il codice di pagina automaticamente o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.
seo-title: Aggiunta dello strumento Adobe Analytics
solution: Analytics
title: Aggiunta dello strumento Adobe Analytics
topic: Sviluppatore e implementazione
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: 831ae375a90f021feddc6817a2602464be0d8414

---


# Aggiunta dello strumento Adobe Analytics

Distribuisci Adobe Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe Analytics e configurando il codice di pagina automaticamente o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.

>[!NOTE]
>
>Per migliorare il tracciamento dei visitatori, ti consigliamo vivamente di abilitare [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

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
   <td colname="col2">Tipo di strumento, ad esempio <span class="keyword"> Adobe Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome dello strumento </p> </td> 
   <td colname="col2">Un nome descrittivo per lo strumento. Questo nome viene visualizzato nella scheda <span class="wintitle"> Panoramica</span> in <span class="wintitle"> Strumenti</span>installati. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Metodo di configurazione </p> </td> 
   <td colname="col2"> <p> <b>Automatico</b> (consigliato): Utilizzate la gestione tag dinamica per gestire la configurazione. Questo metodo abilita la sincronizzazione automatica delle suite di rapporti <span class="keyword"> Adobe Analytics</span> tramite un accesso <span class="keyword"> Experience Cloud</span> o un ID di servizi Web e gestisce il codice [!DNL AppMeasurement]. </p> <p>Una volta connessi gli account, Gestione tag dinamica porta gli ID e i nomi delle suite di rapporti di <span class="keyword"> Adobe Analytics</span> nell'interfaccia di configurazione dello strumento, consentendo una maggiore velocità nella distribuzione degli strumenti con minori possibilità di errori da parte degli utenti. </p> <p> <p>Nota: È necessario scegliere l'opzione <span class="wintitle"> Automatico</span> se siete clienti <span class="keyword"> Adobe Analytics Premium</span> . Consultate <a href="../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#section_AEAA44566B5A46D2922E17A11D7EA217" format="dita" scope="local"> Abilitazione di Adobe Analytics Premium</a> di seguito. </p> </p> <p>Compila i campi specifici per la configurazione automatica: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (Impostazione predefinita) Utilizza il single sign-on <span class="keyword"> Experience Cloud</span> . Specifica il tuo Experience Cloud ID e la password. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Servizi</b>Web: Specifica il tuo nome utente Servizi Web e il segreto condiviso. </p> <p>Shared secret credentials are located in <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Company Settings</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html" format="html" scope="external"> Web Services</a>. </p> <p>Per informazioni su come ottenere le credenziali dei servizi Web, vedere <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api" format="https" scope="external"> Accesso ai servizi Web nell'API</a> Enterprise. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manuale</b>: Gestisci manualmente il codice [!DNL AppMeasurement]. Puoi scaricare il codice <span class="keyword"> Analytics</span><span class="keyword"> AppMeasurement</span> da Strumenti <span class="ignoretag"><span class="uicontrol"> di amministrazione &gt;</span> Gestionecodici <span class="uicontrol"></span></span>. </p> <p>Fate clic su <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/appmeasure_mjs.html" format="https" scope="external"> JavaScript (nuovo)</a> per informazioni su come scaricare localmente il codice per copiare e incollare nel campo <span class="wintitle"> Modifica codice</span> in Gestione <a href="../../../implement/c-implement-with-dtm/c-aa-tool/library-management.md#concept_24654766343B4E82A9416A112D2125FE" format="dita" scope="local"></a>libreria. </p> <p>Compila i campi specifici per una configurazione manuale: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID account produzione: </b>(Obbligatorio) Account di produzione per la raccolta dei dati. Per Analytics, questo è il tuo ID suite di rapporti. Gestione tag dinamica installa automaticamente l'account corretto nell'ambiente di produzione e di staging. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID account di gestione temporanea: </b>(Obbligatorio) Utilizzato nell'ambiente di sviluppo o di test. Per Analytics, questo è il tuo ID suite di rapporti. Un account di verifica mantiene i dati di test separati dalla produzione. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Server di tracciamento: </b>Specificate le informazioni per il server di tracciamento. </p> <p>The <span class="wintitle"> Tracking Server</span> and <span class="wintitle"> SSL Tracking Server</span> variables are used for first-party cookie implementation to specify the domain at which the image request and cookie is written. For more information, see the  Correctly Populate the trackingServer and trackingServerSecure Variable article.<a href="https://helpx.adobe.com/analytics/kb/determining-data-center.html" format="https" scope="external"></a> </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>SSL Tracking Server: </b>Specify the information for your SSL tracking server. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Click  to create the tool and display it for editing.**[!UICONTROL Create Tool]**

   Tools are displayed on the  tab, under .[!UICONTROL Overview][!UICONTROL Installed Tools]

1. (Conditional) Configure the tool further as necessary by following the directions in the links below ( , , , , , , , and ).[!UICONTROL General][!UICONTROL Library Management][!UICONTROL Global Variables][!UICONTROL Pageviews & Content][!UICONTROL Link Tracking][!UICONTROL Referrers & Campaigns][!UICONTROL Cookies][!UICONTROL Customize Page Code]

See Frequently Asked Questions About the Adobe Analytics Tool for additional information about this tool.[](../../../implement/faq.md#concept_00DF9AF14D30469BB986BF56A448806B)

## Edit an Existing Adobe Analytics Tool {#section_148B16AF429B4949B06238D90635B726}

You can edit an existing Adobe Analytics tool to change its configuration settings.

1. Click the   icon next to an installed tool from the  tab.![](assets/settings_gear.png)[!UICONTROL Overview]
1. Edit the fields as desired.

   The following table includes only those elements that differ from the elements available when you are creating an Analytics tool, as described above. However, you can change any element on the page, as described in both tables.

<table id="table_2B60CD109CFF4839AB7F91D61125EDFF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Enable Automatic Configuration </p> </td> 
   <td colname="col2"> <p>Nota: Enabling this setting changes a manually configured implementation to the automatic configuration method described in  Configuration Method.<span class="term"></span> </p> <p>Questa opzione consente a Gestione tag dinamica di recuperare automaticamente la configurazione dell'account <span class="keyword"> Adobe Analytics</span> . </p> <p>Viene utilizzato l'ultimo codice [!DNL AppMeasurement] disponibile e le notifiche di aggiornamento vengono visualizzate per la selezione man mano che diventano disponibili nuove versioni. Puoi anche ripristinare le versioni precedenti di [!DNL AppMeasurement], se necessario, ad esempio per motivi di compatibilità. Vengono visualizzate fino a cinque versioni precedenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna credenziali </p> </td> 
   <td colname="col2"> <p>Aggiornate l'API, ad esempio, per aggiornare le suite di rapporti associate a un utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Condizionale) Configurate ulteriormente lo strumento seguendo le indicazioni riportate di seguito ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]e [!UICONTROL Customize Page Code]).
1. Fai clic su **[!UICONTROL Save Changes]**.
