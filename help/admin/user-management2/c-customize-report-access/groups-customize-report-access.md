---
description: Personalizza l’autorizzazione del gruppo per gli strumenti di Analytics, gli strumenti della suite di rapporti, le metriche e le dimensioni.
keywords: gruppi;autorizzazioni
subtopic: Users and groups
title: Panoramica di personalizzazione accesso ai rapporti
feature: Strumenti di amministrazione
uuid: 818a7196-8b43-4654-8d5f-800b3122aad3
exl-id: f70b53b5-1399-4b9b-ad09-df8425baeca4
source-git-commit: d198e8ef0ec8415a4a555d3c385823baad6104fe
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 34%

---

# Panoramica di personalizzazione accesso ai rapporti

>[!IMPORTANT]
>
>La gestione di utenti e prodotti è stata spostata nell&#39; [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** verranno ritirati.

Personalizza l’autorizzazione del gruppo per gli strumenti di Analytics, gli strumenti della suite di rapporti, le metriche e le dimensioni.

**[!UICONTROL Add New Group]** > **[!UICONTROL Report Access]**

La sezione [!UICONTROL Report Access] della pagina [!UICONTROL Define User Group] fornisce categorie di accesso che consentono di personalizzare le autorizzazioni a livello granulare.

![](assets/report-access.png)

Ad esempio, puoi creare un gruppo con accesso a più strumenti di Analytics ( [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics] e [!UICONTROL Report Builder]), con l’autorizzazione per metriche e dimensioni specifiche (comprese le eVar) e funzionalità come la creazione di segmenti o metriche calcolate.

## Informazioni sulle autorizzazioni {#section_3D25D4A5BD044008870C5B98F696244E}

<table id="table_DB7806E05E2040EC9A4CB7C3596879EC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Accesso amministratore/gruppi predefiniti </p> </td> 
   <td colname="col2"> <p> I gruppi predefiniti non sono più necessari per gli amministratori. Gli amministratori ora possono accedere a tutti gli elementi (strumenti, metriche, dimensioni), nonché all’accesso al servizio Web, al Report Builder e ad Activity Map. </p> <p>Lo scopo dei gruppi è quello di concedere o limitare l'accesso agli utenti non amministrativi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gruppi personalizzati </p> </td> 
   <td colname="col2"> <p> I gruppi personalizzati hanno sostituito i gruppi predefiniti. I gruppi predefiniti esistenti verranno migrati a gruppi personalizzati utilizzando lo stesso nome di gruppo. Eventuali gruppi personalizzati creati, incluse le relative impostazioni, verranno mantenuti. Tuttavia, noterai che la posizione delle impostazioni sarà stata spostata. Ad esempio, le impostazioni aziendali (in Personalizza Admin Console) ora si trovano in <a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md"> Personalizza strumenti di Analytics</a>. </p> <p> Gli utenti appartenenti a <span class="term"> All Report Access</span> sono stati migrati a un gruppo personalizzato con accesso a: </p> 
    <ul id="ul_7E1B443DEEF7452E85FEB30CA0BBC8BE"> 
     <li id="li_A510C2A4129340E0AB08EEBDBE4AEAD9">Tutte le dimensioni </li> 
     <li id="li_8BA1D7A2527C4F10AC93108B9E87F418">Tutte le metriche </li> 
     <li id="li_265830A2C6B94AF28720DA99980EAA51">Tutte le suite di rapporti </li> 
     <li id="li_685B99DEAB814D7B9C11B14AA4CB8CD4">Rapporto canale </li> 
     <li id="li_B35420302AAB42509BD6AF0FA6349BF8">Rilevamento delle anomalie </li> 
     <li id="li_3787E4696C454D3ABD1D75F6C282A9A2">Rapporto in tempo reale </li> 
     <li id="li_3797DF9C40D1426588819116362962F5">Accesso in Analysis Workspace </li> 
    </ul> <p>Gli amministratori possono eliminare i gruppi personalizzati e crearne uno proprio, in quanto tutte le impostazioni precedentemente disponibili in gruppi predefiniti sono disponibili per la personalizzazione nelle impostazioni <span class="wintitle"> Accesso ai rapporti</span> in Definisci gruppi di utenti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni a livello di Dimension </p> </td> 
   <td colname="col2"> <p>Puoi personalizzare le autorizzazioni per includere o escludere l’accesso alle dimensioni (oltre alle metriche). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>Tutte le dimensioni e le metriche correnti all'interno dei gruppi personalizzati sono state migrate automaticamente nelle nuove categorie. Se un gruppo esistente dispone di metriche abilitate, per impostazione predefinita gli verranno assegnate tutte le dimensioni (sulla base delle eVar e dei contenuti) e le metriche a cui sono state appena assegnate delle autorizzazioni. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Autorizzazioni per Importazione classificazioni (in precedenza SAINT): l'accesso alle classificazioni è determinato dall'accesso alla <a href="https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/c-classifications.html">variabile</a> su cui è basata la classificazione. </li> 
    </ul> <p>Consulta <a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md"> Personalizzare le autorizzazioni di Dimension</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://helpx.adobe.com/enterprise/using/admin-console.html"> Adobe Admin Console</a> </p> </td> 
   <td colname="col2"> <p>Consigliato solo per i nuovi clienti o clienti con le società <a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/about-core-services/core-services.html"> fornite nell'Experience Cloud</a>. È pianificata una migrazione dei clienti <span class="keyword"> Analytics</span> esistenti al sistema di gestione delle identità <span class="keyword"> Experience Cloud</span> . </p> <p>Ulteriori informazioni sono disponibili in <a href="https://docs.adobe.com/content/help/it-IT/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html"> Migrazione degli utenti di Analytics all'Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>In base al contenuto </p> </td> 
   <td colname="col2"> <p>In base al contenuto sono incluse le variabili che consentono di gestire le autorizzazioni sulle metriche relative alle integrazioni di soluzioni Experience Cloud. Puoi gestire le autorizzazioni su <span class="keyword"> Social</span>, <span class="keyword"> Mobile</span> o su qualsiasi altro dato inserito tramite un'integrazione <span class="keyword"> Experience Cloud</span>. Queste verranno abilitate per impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni/rapporti disattivati </p> </td> 
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
