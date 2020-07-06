---
description: Distribuite Adobe  Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe  Analytics e configurando il codice di pagina automaticamente o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;analytics tool;property;tool type;tool name;configuration method;analytics premium;evars;events
title: Aggiunta dello strumento Adobe Analytics
topic: Developer and implementation
uuid: 1c54331e-de03-4f44-8002-a19723c585b0
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 13%

---


# Aggiunta dello strumento Adobe Analytics

Distribuite Adobe  Analytics utilizzando Gestione tag dinamica creando lo strumento Adobe  Analytics e configurando il codice di pagina automaticamente o manualmente. Il metodo automatico è consigliato per la maggior parte degli utenti.

>[!NOTE]
>
>Per migliorare il tracciamento dei visitatori, ti consigliamo vivamente di abilitare [Identity Service](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html).

## Add an Adobe Analytics Tool {#section_D5066B21581B4F7F811AD0027BF44EA5}

1. Fai clic su  **[!UICONTROL  *`Web Property Name`*]** > **[!UICONTROL Overview]** > **[!UICONTROL Add a Tool]** > **[!UICONTROL Adobe Analytics]** .

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
   <td colname="col2">Tipo di strumento, ad esempio <span class="keyword"> Adobe  Analytics</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome dello strumento </p> </td> 
   <td colname="col2">Un nome descrittivo per lo strumento. Questo nome viene visualizzato nella scheda <span class="wintitle"> Panoramica</span> in <span class="wintitle"> Strumenti</span>installati. </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> <p>Metodo di configurazione </p> </td> 
   <td colname="col2"> <p> <b>Automatico</b> (consigliato): Utilizzate la gestione tag dinamica per gestire la configurazione. Questo metodo abilita la sincronizzazione automatica delle suite di rapporti <span class="keyword"> Adobe  Analytics</span> tramite un <span class="keyword"> login Experience Cloud</span>  o un ID di servizi Web e gestisce il codice AppMeasurement. </p> <p>Una volta connessi gli account, Gestione tag dinamica porta gli ID e i nomi delle suite di rapporti <span class="keyword"> Adobe  Analytics</span> nell'interfaccia di configurazione dello strumento, consentendo una maggiore velocità nella distribuzione degli strumenti con minori possibilità di errori da parte degli utenti. </p> <p> <p>Nota: È necessario scegliere l'opzione <span class="wintitle"> Automatico</span> se siete un cliente <span class="keyword"> Adobe  Analytics Premium</span> . </p> </p> <p>Compila i campi specifici per la configurazione automatica: </p> 
    <ul id="ul_8D9797B01E444B9C85B862A9F96B447C"> 
     <li id="li_0AC84C1F37B24C658F2178E50ECCC4B0"> <p> <b>Experience Cloud</b>: (Impostazione predefinita) Utilizza <span class="keyword"> Single Sign-On Experience Cloud</span> . Specificate il vostro ID Experience Cloud  e la relativa password. </p> </li> 
     <li id="li_6C80468835D04CC09F4AEC46D1300310"> <p><b>Servizi</b>Web: Specifica il tuo nome utente Servizi Web e il segreto condiviso. </p> <p>Shared secret credentials are located in <span class="uicontrol"> Admin </span> &gt; <span class="uicontrol"> Company Settings</span> &gt; <a href="https://docs.adobe.com/content/help/en/analytics/admin/company-settings/web-services-admin.html"> Web Services</a>. </p> <p>Per informazioni su come ottenere le credenziali dei servizi Web, vedere <a href="https://marketing.adobe.com/developer/en_US/get-started/enterprise-api/c-get-web-service-access-to-the-enterprise-api"> Accesso ai servizi Web nell'API</a> Enterprise. </p> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p> <b>Manuale</b>: Gestisci manualmente il codice AppMeasurement. You can download the <span class="keyword"> Analytics</span><span class="keyword"> AppMeasurement</span> code from <span class="ignoretag"><span class="uicontrol"> Admin Tools</span> &gt; <span class="uicontrol"> Code Manager</span></span>. </p> <p>Fate clic su <a href="https://docs.adobe.com/content/help/en/analytics/implementation/js/migrate-from-hcode.html"> JavaScript (nuovo)</a> per informazioni su come scaricare localmente il codice per copiare e incollare nel campo <span class="wintitle"> Modifica codice</span> in Gestione <a href="/help/implement/other/dtm/c-aa-tool/library-management.md"></a>libreria. </p> <p>Compila i campi specifici per una configurazione manuale: </p> 
    <ul id="ul_CFB6CE78AEB743EF8B47BAAC42E2DB0A"> 
     <li id="li_5B7046CD95AB416F8C113B381A264D91"> <p><b>ID account produzione: </b>(Obbligatorio) Account di produzione per la raccolta dei dati. Per Analytics, questo è l’ID della tua suite di rapporti. Dynamic Tag Management installa automaticamente l’account corretto nell’ambiente di produzione e di staging. </p> </li> 
     <li id="li_14E840FD79A0451BABEDD15DC0584768"> <p><b>ID account di gestione temporanea: </b>(Obbligatorio) Utilizzato nell'ambiente di sviluppo o di test. Per Analytics, questo è l’ID della tua suite di rapporti. Un account di staging mantiene i dati di test separati dalla produzione. </p> </li> 
     <li id="li_69E6C6A41F5240E1ABE8ABE0B9D151FC"> <p><b>Server di tracciamento: </b>Specifica le informazioni per il server di tracciamento. </p> <p>Le variabili <span class="wintitle"> Tracking Server</span> e <span class="wintitle"> SSL Tracking Server</span> vengono utilizzate per l’implementazione dei cookie di prime parti per specificare il dominio in cui vengono scritti la richiesta di immagine e il cookie. Per ulteriori informazioni, consulta <a href="https://helpx.adobe.com/it/analytics/kb/determining-data-center.html"> Aggiunta corretta delle variabili trackingServer e trackingServerSecure</a> . </p> </li> 
     <li id="li_1A7271C68205428F8CA5548A96CACBEC"> <p><b>Server di tracciamento SSL: </b>Specificate le informazioni per il server di tracciamento SSL. </p> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

1. Fate clic **[!UICONTROL Create Tool]** per creare lo strumento e visualizzarlo per la modifica.

   Gli strumenti sono visualizzati nella [!UICONTROL Overview] scheda, sotto [!UICONTROL Installed Tools].

1. (Condizionale) Configurate ulteriormente lo strumento seguendo le indicazioni riportate di seguito ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]e [!UICONTROL Customize Page Code]).

Per ulteriori informazioni su questo strumento, consulta [Domande frequenti su Adobe  Analytics Tool](/help/implement/faq.md) .

## Modificare uno strumento Adobe  Analytics esistente {#section_148B16AF429B4949B06238D90635B726}

Potete modificare uno strumento Adobe  Analytics esistente per modificarne le impostazioni di configurazione.

1. Fare clic sull&#39; ![](assets/settings_gear.png) icona accanto a uno strumento installato dalla [!UICONTROL Overview] scheda.
1. Modificate i campi nel modo desiderato.

   La tabella seguente include solo gli elementi che differiscono dagli elementi disponibili durante la creazione di uno strumento Analytics , come descritto in precedenza. Tuttavia, è possibile modificare qualsiasi elemento della pagina, come descritto in entrambe le tabelle.

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
   <td colname="col2"> <p>Nota: Se si abilita questa impostazione, un'implementazione configurata manualmente viene modificata in base al metodo di configurazione automatico descritto in <span class="term"> Metodo</span>di configurazione. </p> <p>Questa opzione consente a Gestione tag dinamica di recuperare automaticamente la configurazione dell'account <span class="keyword"> Adobe  Analytics</span> . </p> <p>Viene utilizzato l’ultimo codice AppMeasurement disponibile e le notifiche di aggiornamento vengono visualizzate per la selezione man mano che diventano disponibili nuove versioni. Puoi anche ripristinare le versioni precedenti di AppMeasurement, se necessario, ad esempio per motivi di compatibilità. Vengono visualizzate fino a cinque versioni precedenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna credenziali </p> </td> 
   <td colname="col2"> <p>Aggiornate l'API, ad esempio, per aggiornare le suite di rapporti associate a un utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. (Condizionale) Configurate ulteriormente lo strumento seguendo le indicazioni riportate di seguito ( [!UICONTROL General], [!UICONTROL Library Management], [!UICONTROL Global Variables], [!UICONTROL Pageviews & Content], [!UICONTROL Link Tracking], [!UICONTROL Referrers & Campaigns], [!UICONTROL Cookies]e [!UICONTROL Customize Page Code]).
1. Fai clic su **[!UICONTROL Save Changes]**.
