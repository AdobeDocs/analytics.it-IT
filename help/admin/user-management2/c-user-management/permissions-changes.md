---
description: 'null'
keywords: groups;permissions
subtopic: Users and groups
title: Modifiche alle autorizzazioni Utente e Gruppo
topic: Admin tools
uuid: 94f2727b-17e4-4003-a222-35c821d6959e
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1553'
ht-degree: 15%

---


# Modifiche alle autorizzazioni Utente e Gruppo

>[!IMPORTANT]
>
>La gestione di utenti e prodotti sta passando all&#39; [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Adobe ti informerà quando è il momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** verranno ritirati.

## Cosa è cambiato? {#section_2C205DE94155441B9E9D3E4C46CCF2EE}

**[!UICONTROL Admin]** (Workspace) > **[!UICONTROL User Management]** (Progetto) > **[!UICONTROL Groups]** (Annulla/Ripeti)

>[!NOTE]
>
>A causa del numero elevato di possibili combinazioni di autorizzazioni disponibili, non è possibile fornire documentazione che descriva tutti i metodi API utilizzabili in ogni combinazione di autorizzazioni. Generalmente, gli utenti che non dispongono dell&#39;accesso ai servizi Web avranno accesso in sola lettura ai metodi API. Non avranno accesso in scrittura ai metodi.

Poiché l&#39;API e l&#39;interfaccia utilizzano lo stesso sistema di autorizzazioni, indipendentemente dalle autorizzazioni concesse a un particolare non amministratore da un amministratore nell&#39;interfaccia (Adobe  Admin Console), saranno le stesse autorizzazioni di cui dispone l&#39;utente nell&#39;API.

<table id="table_D1DB0DE37752450BBCCA44DB760BB505"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Miglioramento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p id="reportaccess">Modifiche all'accesso <span class="uicontrol"> al</span> report (Personalizza gruppi) </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Aggiungi nuovo gruppo</span> &gt; Accesso ai <span class="uicontrol"> rapporti</span> </p> <p>The <span class="wintitle"> Report Access</span> section on the <span class="wintitle"> Define User Group</span> page has been streamlined to four categories, which enable you to customize permissions at a granular level. </p> <p><img  src="assets/report-access.png" id="image_CB83E5C7DB4343619421A1FAA61478D0"> </img> </p> <p>Elementi precedentemente in </p> 
    <ul id="ul_16D5EF18D57D4608AEEDEC40D90D8828"> 
     <li id="li_F29E84C6228A464C8807F09205AEAAC6"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md">  Analytics Tools</a>: Attiva le autorizzazioni utente per gli elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Generatore di report e integrazione dei connettori dati. </p> <p> <b>Nota:</b> le impostazioni aziendali della categoria Personalizza di Admin Console sono state trasferite negli strumenti di Analytics. </p> </li> 
     <li id="li_A6EB788162A2455E94CE54B9279A854D"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-report-suite-tools.md"> Strumenti</a>suite di rapporti: Attiva le autorizzazioni utente per i servizi Web, la gestione delle suite di rapporti, gli strumenti e i rapporti e gli elementi del dashboard. </p> </li> 
     <li id="li_EDB0255E009B4F1CAFAF53966B41363C"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-metrics.md"> Metriche</a>: Attiva le autorizzazioni per il traffico, la conversione, gli eventi personalizzati, gli eventi delle soluzioni, in base al contenuto e così via. </p> </li> 
     <li id="li_8DAE87D1DEF54803A9C6FE31C01F0FB0"> <p> <a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md"> Dimensioni</a>: Personalizza l'accesso degli utenti a un livello granulare, comprese eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti sui percorsi. </p> </li> 
    </ul> <p>For example, you can create a group with access to multiple Analytics tools (<span class="wintitle"> Analysis Workspace</span>, <span class="wintitle"> Reports &amp; Analytics</span>, and <span class="wintitle"> Report Builder</span>), with permission to specific metrics and dimensions (including eVars), and capabilities like segment or calculated metrics creation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifiche ai gruppi predefiniti </p> </td> 
   <td colname="col2"> <p> <b>Accesso amministratore:</b> I gruppi predefiniti non sono più necessari per gli amministratori. Gli amministratori possono ora accedere a tutti gli elementi (strumenti, metriche, dimensioni), nonché a Servizio Web, Generatore di report, Activity Map  e  Ad hoc analysis. </p> <p>In futuro, lo scopo dei gruppi è quello di concedere o limitare l'accesso agli utenti non amministrativi. </p> <p> <b>Gruppi personalizzati:</b> I gruppi personalizzati hanno sostituito i gruppi predefiniti. I gruppi predefiniti esistenti verranno migrati in gruppi personalizzati, utilizzando lo stesso nome di gruppo. Eventuali gruppi personalizzati creati, comprese le relative impostazioni, verranno mantenuti. Tuttavia, noterete che la posizione delle impostazioni sarà stata spostata. Ad esempio, le impostazioni Azienda (in Personalizza  Admin Console) ora si trovano in <a href="/help/admin/user-management2/c-customize-report-access/groups-analytics-tools.md"> Personalizza  Strumenti</a>Analytics. </p> <p> Gli utenti appartenenti a <span class="term"> All Report Access (Accesso</span> a tutti i rapporti) sono stati migrati in un gruppo personalizzato con accesso a: </p> 
    <ul id="ul_696A9243F5FD4AF187352C2F4B1CFDC2"> 
     <li id="li_683A0A3BB7214CFFBC61D5A4CD237F48">Tutte le dimensioni </li> 
     <li id="li_D8FDBF6A32224731AB706315DEA0A03E">Tutte le metriche </li> 
     <li id="li_65ABE5C95D43444D88E63EE95C9AED05">Tutte le suite di rapporti </li> 
     <li id="li_7ED1505590144B38B3B9851BAA6BBB49">Autorizzazione per il rapporto sul canale </li> 
     <li id="li_F718FE1FCF9A4B05AB933CA3F105F3EC">Autorizzazione per il rapporto sul rilevamento delle anomalie </li> 
     <li id="li_527BD52007E846FE8B5F71AB3C12F695">Autorizzazione per il rapporto in tempo reale </li> 
     <li id="li_AFFB58C7FB644AC8A85E2D76BA7D51F5">Autorizzazione all'accesso ad Analysis Workspace </li> 
    </ul> <p>Gli amministratori possono eliminare i gruppi personalizzati e crearne uno proprio, poiché tutte le impostazioni precedentemente disponibili in gruppi predefiniti sono disponibili per la personalizzazione in base alle impostazioni <span class="wintitle"> Accesso</span> ai <a href="/help/admin/user-management2/c-user-groups/groups.md"> rapporti in</a>Definisci gruppiutenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Autorizzazioni a livello di dimensione </p> </td> 
   <td colname="col2"> <p>Puoi personalizzare le autorizzazioni per includere o escludere l’accesso alle dimensioni (oltre alle metriche). </p> 
    <ul id="ul_DA5A54223673474E9151AF979DA50659"> 
     <li id="li_C3E82F7BC07A4F2F83A85D3D511292CC"> <p>Tutte le dimensioni e le metriche correnti all'interno dei gruppi personalizzati sono state migrate automaticamente nelle nuove categorie. Se un gruppo esistente dispone di metriche abilitate, per impostazione predefinita gli verranno assegnate tutte le dimensioni (sulla base delle eVar e dei contenuti) e le metriche a cui sono state appena assegnate delle autorizzazioni. </p> </li> 
     <li id="li_CC56F9181CC14AB59318628E72F2E8C9"> Autorizzazioni per Importazione classificazioni (in precedenza SAINT): l'accesso alle classificazioni è determinato dall'accesso alla <a href="https://docs.adobe.com/content/help/en/analytics/components/classifications/c-classifications.html">variabile</a> su cui è basata la classificazione. </li> 
    </ul> <p>See <a href="/help/admin/user-management2/c-customize-report-access/groups-dimensions.md"> Customize Dimension Permissions</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Admin Console </p> </td> 
   <td colname="col2"> <p>Consigliato solo per nuovi clienti o clienti con aziende <a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/about-core-services/core-services.html"> predisposte nell'Experience Cloud</a>. È pianificata una migrazione per i clienti Analytics <span class="keyword">  esistenti al sistema di gestione dell'identità Experience Cloud</span> <span class="keyword"></span> . </p> <p>Ulteriori informazioni sono disponibili in <a href="https://helpx.adobe.com/it/enterprise/using/manage-permissions-and-roles.html"> Gestione delle autorizzazioni del prodotto nell'Admin Console</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequently Asked Questions about Permission Changes {#section_02809EFC95054B40A089E6C6E4FACA13}

Di seguito sono riportate nuove informazioni importanti sugli aggiornamenti nuovi e pianificati e sul loro impatto sull’ambiente amministrativo.

<table id="table_1E93F45C66E841E6882FB602509F30A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1">Quali modifiche alle autorizzazioni sono state introdotte nella release di <b>luglio 2016</b> ? </td> 
   <td colname="col2"> <p> <b>Accesso a tutte le suite di rapporti</b> </p> <p>Quando aggiungete delle suite di rapporti da includere in un gruppo, potete specificare <span class="uicontrol"> Accesso</span>a tutte le suite di rapporti. Questa impostazione applica le autorizzazioni del gruppo a tutte le suite di rapporti correnti e future. </p> <p>To enable this feature, navigate to <span class="uicontrol"> User Management</span> &gt; <span class="uicontrol"> Groups</span> &gt; <span class="uicontrol"> Add New User Group</span>, then select <span class="uicontrol"> All Report Suite Access</span>. </p> <p><img placement="break"  src="assets/all-report-suites.png" width="300px" id="image_9E814D412E87484C940F1100D6DE2B0F" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È necessario utilizzare l'Admin Console  per gestire gli utenti o la gestione  utenti Analytics esistente? </p> </td> 
   <td colname="col2"> <p>Le modifiche apportate in  Analytics &gt; Amministratore &gt; Gestione utente non vengono riportate nell’Admin Console . Pertanto, solo i nuovi clienti che già utilizzano l’Admin Console  per la gestione di utenti e gruppi devono continuare a farlo. È pianificata una migrazione per la gestione di gruppi di Analytics  esistente all'Admin Console . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quali modifiche alle autorizzazioni sono state apportate nella release di <b>ottobre 2016</b> ? </p> </td> 
   <td colname="col2"> <p>Sono disponibili i seguenti miglioramenti all'interfaccia <span class="wintitle"> Strumenti</span> di amministrazione: </p> <p> 
     <ul id="ul_2A31E8DC17A94B7FABDBA9C87C3947EF"> 
      <li id="li_AE2ECCA01CC64D30B109BE74379EE474">Modifiche alle autorizzazioni come descritto in Modifiche <a href="/help/admin/user-management2/c-user-management/permissions-changes.md"> amministrative - Autunno 2016</a>. </li> 
      <li id="li_33CB2B6A2E5F45BE97CC5E0983AF280E">Sono stati rimossi i rapporti sul traffico obsoleti che non erano più presenti nel menu. </li> 
      <li id="li_57234CF27E1D405987DE89312CD62C52">Autorizzazioni di classificazione: L'accesso alle classificazioni sarà determinato dall'accesso alla variabile per la quale è prevista la classificazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo fare qualcosa per migrare gli utenti? </p> </td> 
   <td colname="col2"> <p>No, tutte le migrazioni di autorizzazioni avverranno in modo trasparente. </p> <p> 
     <ul id="ul_654F85286EC04416B3E0BA725EBE10AD"> 
      <li id="li_8050B8941F794103B82A0ADF0930D216">Tutti i rapporti sul traffico correnti in un gruppo personalizzato verranno automaticamente migrati nella nuova categoria dimensione. </li> 
      <li id="li_B97079DB29A346B98D066F11AB7F94AF">Se un gruppo personalizzato dispone di metriche già abilitate, le verranno automaticamente assegnate tutte le nuove dimensioni consentite (variabili eVar e Soluzione). </li> 
      <li id="li_F1219EF490DA473BA15F2B215F2995AE"> A un gruppo personalizzato con almeno una metrica verrà automaticamente concesso l'accesso a tutte le eVar e ad altre dimensioni in base al contenuto, <b>ad eccezione</b> delle nuove dimensioni del traffico disponibili (precedentemente report sul traffico). </li> 
      <li id="li_F494CE6144A04A6199CFBBA1D7BEA32B">Ogni gruppo predefinito verrà modificato in un'autorizzazione. Queste nuove autorizzazioni verranno aggiunte a una nuova categoria <span class="uicontrol">  Analytics Tools</span> . </li> 
      <li id="li_2FCD9254FC3C4FD7871EEF9453E5CE1E">Ogni gruppo personalizzato con qualsiasi metrica avrà tutti  eventi della soluzione Analytics aggiunti come nuove metriche. </li> 
      <li id="li_34C4560769B64F28A4E83BAE71065DCC">Tutti gli utenti che si trovavano in  Accesso a tutti i rapporti  verranno aggiunti al nuovo gruppo personalizzato. L'accesso a tutti i report non esisterà più. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa non cambierà? </p> </td> 
   <td colname="col2"> <p>Gli attributi del visitatore continueranno a non essere autorizzati. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Guida di riferimento rapido per le autorizzazioni {#section_A3FDD8259F524B21A5489833533D1B28}

Nella tabella seguente sono elencate le attività e le aree in cui possono aver luogo (a seconda dello stato di una società).

>[!NOTE]
>
>A *`migrated user`* e *`Experience Cloud user`* fate riferimento agli utenti che hanno accettato un invito e-mail a partecipare all&#39;Experience Cloud . Se l&#39;invito e-mail non viene accettato, gli utenti restano  utenti Analytics e non possono essere gestiti nell&#39;Admin Console . (L&#39;eccezione è se la migrazione utilizza ID [Enterprise o Federated ID](https://helpx.adobe.com/it/enterprise/using/set-up-identity.html). In questo caso, l’utente viene migrato quando l’amministratore esegue la migrazione degli utenti in base all’utente.

<table id="table_B68FD00FC5D24823A86BB69558C0327C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col2" class="entry"> Società di accesso non di migrazione </th> 
   <th colname="col3" class="entry"> Migrazione società in corso </th> 
   <th colname="col4" class="entry"> Migrazione della società di accesso completata </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Creare un utente </td> 
   <td colname="col2"> <p> Admin Console (la creazione di un utente e l’aggiunta di tale utente a una configurazione <a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html"></a> di prodotto Analytics  crea anche l’account utente in  Analytics). </p> <p> <a href="/help/admin/user-management2/c-user-management/t-add-user-account.md"> Strumenti di amministrazione</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modificare un utente </td> 
   <td colname="col2"> <p> <a href="/help/admin/user-management2/c-user-management/t-add-user-account.md"> Strumenti di amministrazione</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> <p> Strumenti di amministrazione - La modifica in Strumenti di amministrazione per gli utenti trasferiti è limitata alla gestione delle chiavi API, nonché all’eliminazione e al trasferimento di risorse. </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a> </p> <p> Strumenti di amministrazione - La modifica è limitata alla gestione delle chiavi API ed è possibile eliminare o trasferire risorse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eliminare un utente </td> 
   <td colname="col2"> <p> Admin Console - Per  utenti Experience Cloud </p> <p>Strumenti di amministrazione: per tutti gli utenti, ma per  utenti Experience Cloud, elimina solo l'utente Analytics  mappato, non l'account Experience Cloud . </p> </td> 
   <td colname="col3"> <p> Admin Console - Per Utenti Migrati. </p> <p>Strumenti di amministrazione - Per  utenti esclusivamente Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> <p> Strumenti di amministrazione - Dopo aver eliminato un utente Experience Cloud  o aver scollegato il suo account in  Admin Console, puoi eliminare l’accesso  Analytics da Strumenti di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accedere a  Analytics </td> 
   <td colname="col2"> <p> <b>Experience Cloud: </b> <span class="filepath"> marketing.adobe.com</span>. Disponibile solo per  utenti Experience Cloud. </p> <p> <b>Analytics (precedente):</b> <span class="filepath"> sc.omniture.com</span>. Per  solo utenti Analytics e per  utenti Experience Cloud con le loro credenziali  Analytics </p> </td> 
   <td colname="col3"> <p> <span class="filepath"> marketing.adobe.com</span> - disponibile solo per  utenti Experience Cloud. </p> <p> <span class="filepath"> sc.omniture.com</span> - Per l'analisi solo gli utenti e per  gli utenti Experience Cloud con  credenziali Analytics. </p> <p>Durante la migrazione, gli amministratori possono disattivare la capacità di accesso di <span class="filepath"> omniture.com</span> per utenti specifici. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Create un gruppo </td> 
   <td colname="col2"> <p> Admin Console - Quando un gruppo viene creato in  Admin Console, un gruppo mappato in  Analytics verrà visualizzato in Strumenti di amministrazione, ma questo gruppo mappato non può avere il suo nome modificato da Strumenti di amministrazione o essere eliminato da Strumenti di amministrazione. </p> <p>Strumenti di amministrazione. </p> </td> 
   <td colname="col3"> <p> Admin Console (<a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html"> creare la configurazione</a>del prodotto) </p> </td> 
   <td colname="col4"> <p> Admin Console (<a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html"> creare la configurazione</a>del prodotto) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modificare gli utenti di un gruppo </td> 
   <td colname="col2"> <p> Admin Console - Solo per  utenti Experience Cloud </p> <p>Strumenti di amministrazione: è possibile modificare da Strumenti di amministrazione sia gli utenti  solo Analytics che  l’iscrizione di utenti Experience Cloud ai gruppi. Tuttavia, se un utente Experience Cloud  fa parte di un gruppo in  Admin Console, non può essere rimosso dal gruppo in Strumenti di amministrazione. </p> </td> 
   <td colname="col3"> <p> Admin Console -  solo utenti Experience Cloud </p> <p> Strumenti di amministrazione:  gli accessi esclusivamente Analytics possono essere aggiunti o rimossi dai gruppi in Strumenti di amministrazione. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modificare le autorizzazioni per un gruppo </td> 
   <td colname="col2"> <p> Admin Console - Potete modificare i gruppi creati in  Admin Console. </p> <p>Strumenti di amministrazione - Potete modificare le autorizzazioni per qualsiasi gruppo. </p> </td> 
   <td colname="col3"> <p>Admin Console </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elimina gruppo </td> 
   <td colname="col2"> <p> Admin Console - È possibile eliminare solo i gruppi creati in  Admin Console. </p> <p>Strumenti di amministrazione - È possibile eliminare solo i gruppi creati da Strumenti di amministrazione. </p> </td> 
   <td colname="col3"> <p>Admin Console </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modifica dello stato amministratore per l’utente </td> 
   <td colname="col2"> <p> Admin Console - Solo per  utenti Experience Cloud. </p> <p>Strumenti di amministrazione </p> </td> 
   <td colname="col3"> <p> Admin Console - Solo per  utenti Experience Cloud. </p> <p>Strumenti di amministrazione - Solo per  utenti Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
 </tbody> 
</table>
