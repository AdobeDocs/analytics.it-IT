---
description: Personalizza l'autorizzazione del gruppo agli strumenti Analytics, agli strumenti delle suite di rapporti, alle metriche e alle dimensioni.
keywords: gruppi; permissions
seo-description: Personalizza l'autorizzazione del gruppo agli strumenti Analytics, agli strumenti delle suite di rapporti, alle metriche e alle dimensioni.
seo-title: Personalizzare l'accesso ai rapporti
solution: Analytics
subtopic: Utenti e gruppi
title: Personalizzare l'accesso ai rapporti
topic: Strumenti di amministrazione
uuid: 818 a 7196-8 b 43-4654-8 d 5 f -800 b 3122 aad 3
translation-type: tm+mt
source-git-commit: f608acafd77fd6469f553f30c45f54484028890a

---


# Personalizzare l'accesso ai rapporti

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe ti informerà quando sarà il momento di eseguire la migrazione degli utenti. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Personalizza l'autorizzazione del gruppo agli strumenti Analytics, agli strumenti delle suite di rapporti, alle metriche e alle dimensioni.

**[!UICONTROL Add New Group]** &gt; **[!UICONTROL Report Access]**

The [!UICONTROL Report Access] section on the [!UICONTROL Define User Group] page provides access categories that enable you to customize permissions at a granular level.

![](assets/report-access.png)

For example, you can create a group with access to multiple Analytics tools ( [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], and [!UICONTROL Report Builder]), with permission to specific metrics and dimensions (including eVars), and capabilities like segment or calculated metrics creation.

## What You Should Know about Permissions {#section_3D25D4A5BD044008870C5B98F696244E}

<table id="table_DB7806E05E2040EC9A4CB7C3596879EC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Accesso all'amministratore/gruppi predefiniti </p> </td> 
   <td colname="col2"> <p> I gruppi predefiniti non sono più richiesti per gli amministratori. Gli amministratori ora hanno accesso a tutti gli elementi (strumenti, metriche, dimensioni), oltre che a Servizio Web, Generatore di report, Activity Map e Analisi ad hoc. </p> <p>Lo scopo dei gruppi è concedere o limitare l'accesso agli utenti non amministrativi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gruppi personalizzati </p> </td> 
   <td colname="col2"> <p> I gruppi personalizzati hanno sostituito i gruppi predefiniti. I gruppi predefiniti esistenti verranno migrati a gruppi personalizzati utilizzando lo stesso nome di gruppo. Eventuali gruppi personalizzati creati, comprese le impostazioni, verranno conservati. Tuttavia, noterete che la posizione delle impostazioni verrà spostata. For example, Company settings (in Customize Admin Console) are now in <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Customize Analytics Tools</a>. </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_7E1B443DEEF7452E85FEB30CA0BBC8BE"> 
     <li id="li_A510C2A4129340E0AB08EEBDBE4AEAD9">Tutte le dimensioni </li> 
     <li id="li_8BA1D7A2527C4F10AC93108B9E87F418">Tutte le metriche </li> 
     <li id="li_265830A2C6B94AF28720DA99980EAA51">Tutte le suite di rapporti </li> 
     <li id="li_685B99DEAB814D7B9C11B14AA4CB8CD4">Report canale </li> 
     <li id="li_B35420302AAB42509BD6AF0FA6349BF8">Rilevamento delle anomalie </li> 
     <li id="li_3787E4696C454D3ABD1D75F6C282A9A2">Report in tempo reale </li> 
     <li id="li_3797DF9C40D1426588819116362962F5">Accesso all'Area di lavoro Analisi </li> 
    </ul> <p>Administrators can delete custom groups and create their own, as all settings that were previously available in predefined groups are available for customization under the <span class="wintitle"> Report Access</span> settings in Define User Groups</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni a livello di dimensione </p> </td> 
   <td colname="col2"> <p>Puoi personalizzare le autorizzazioni per includere o escludere l'accesso alle dimensioni (oltre alle metriche). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>Tutte le dimensioni e le metriche correnti all'interno dei gruppi personalizzati sono state migrate automaticamente nelle nuove categorie. Se un gruppo esistente dispone di metriche abilitate, per impostazione predefinita gli verranno assegnate tutte le dimensioni (sulla base delle eVar e dei contenuti) e le metriche a cui sono state appena assegnate delle autorizzazioni. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Autorizzazioni per Importazione classificazioni (in precedenza SAINT): l'accesso alle classificazioni è determinato dall'accesso alla <a href="https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html" format="html" scope="external">variabile</a> su cui è basata la classificazione. </li> 
    </ul> <p>See <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/enterprise/using/admin-console.html" format="html" scope="external"> Adobe Admin Console</a> </p> </td> 
   <td colname="col2"> <p>Recommended only for new customers or customers with companies <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html" format="html" scope="external"> provisioned in the Experience Cloud</a>. A migration for existing <span class="keyword"> Analytics</span> customers to the <span class="keyword"> Experience Cloud</span> identity management system is planned. </p> <p>More information is available in <a href="https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/" format="html" scope="external"> Analytics User Migration to the Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In base al contenuto </p> </td> 
   <td colname="col2"> <p>In base al contenuto sono incluse variabili che consentono di gestire le autorizzazioni relative alle metriche correlate alle integrazioni di soluzioni Experience Cloud. You can manage permissions on <span class="keyword"> Social</span>, <span class="keyword"> Mobile</span>, or any other data that was inserted through a <span class="keyword"> Experience Cloud</span> integration. Queste verranno attivate per impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni/rapporti obsoleti </p> </td> 
   <td colname="col2"> <p>Verranno rimossi i seguenti rapporti obsoleti: </p> 
    <ul id="ul_C0415CFF0562472297272EC58ECC0774"> 
     <li id="li_62B1CE33B1454987B878B321EB40D62E">Riepilogo mensile </li> 
     <li id="li_71CD776D212540A18F9B083D2E11A296">Home page visitatori </li> 
     <li id="li_406200AD68C74D11B5F53988A4E76A68">Plug-in Netscape </li> 
     <li id="li_A124637D69C94C78921C8B028D890541">Visitatori principali </li> 
     <li id="li_5C26FF95371B4F3080FF75C7F8DE0F72">Pagine visualizzate dai visitatori principali </li> 
     <li id="li_E7E262BD0CF64E16B838F995F6A13B8A">Snapshot visitatori </li> 
     <li id="li_0EDC74625C0D4B1A992FCA49B648E4C0">DRM </li> 
     <li id="li_ACC92E6EA188409486E7C943F26B9DAC">Protocolli di rete </li> 
     <li id="li_6E18C4D12377416A8124BBD13164B03A">Versione Java </li> 
     <li id="li_1599265E59EF4F34BB406356410C9E68">Lunghezza URL segnalibro </li> 
     <li id="li_3035442010984C409089B21E03DB7BCC">Trasmissione numero dispositivo </li> 
     <li id="li_6B2163ED8FC84EBF933D97A504B4D527">PTT </li> 
     <li id="li_0EB8A4A7619B45DF87109B183A7C69C8">Supporto per Decoration Mail </li> 
     <li id="li_989FAC662F7344E6BDDC517B79D4581E">Informazioni </li> 
     <li id="li_F1FB7F8E415443F3B63F6D11D59A04AB">Servizio informazioni </li> 
    </ul> <p>Tali rapporti: </p> 
    <ul id="ul_F71505C59F734EA9B541BF8AB9F9388F"> 
     <li id="li_7D461907B895447280E69CF1520DF47C">Possono essere comunque aperti dai segnalibri. </li> 
     <li id="li_27BA2DD6BA4C446FBAA06B6C76CD171F">Non sono inclusi nella nuova categoria di autorizzazioni Dimensioni. </li> 
     <li id="li_504E9D8421714406A0F37DEF1E10E34B">Non è più possibile modificare le relative autorizzazioni. </li> 
     <li id="li_0022E8DCA07344C793847E8282EFBEEF">Manterranno l'accesso corrente per i gruppi personalizzati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

