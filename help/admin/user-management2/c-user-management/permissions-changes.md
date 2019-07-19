---
description: nulle
keywords: gruppi; permissions
seo-description: nulle
seo-title: Modifiche alle autorizzazioni Utente e Gruppo
solution: Analytics
subtopic: Utenti e gruppi
title: Modifiche alle autorizzazioni Utente e Gruppo
topic: Strumenti di amministrazione
uuid: 94 f 2727 b -17 e 4-4003-a 222-35 c 821 d 6959 e
translation-type: tm+mt
source-git-commit: 0837416ae67936fbf81af2b7051a7ed9f522f5b5

---


# Modifiche alle autorizzazioni Utente e Gruppo

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe ti informerà quando sarà il momento di eseguire la migrazione degli utenti. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

## Cosa è cambiato? {#section_2C205DE94155441B9E9D3E4C46CCF2EE}

**[!UICONTROL Admin]** &gt; **[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]**

>[!NOTE]
>
>A causa dell'elevato numero di combinazioni di autorizzazioni disponibili, non possiamo fornire la documentazione che descrive tutti i metodi API che possono essere utilizzati in tutte le combinazioni di autorizzazioni. In genere, i non amministratori ai quali è assegnato l'accesso ai servizi Web avranno accesso solo ai metodi API. Non avranno accesso in scrittura ai metodi.

Poiché l'API e l'interfaccia utilizzano lo stesso sistema di autorizzazioni, qualsiasi autorizzazione a un particolare non amministratore sia stata concessa da un amministratore nell'interfaccia (Adobe Admin Console), sarà le stesse autorizzazioni che l'utente ha nell'API.

<table id="table_D1DB0DE37752450BBCCA44DB760BB505"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Miglioramento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p id="reportaccess">Changes to the <span class="uicontrol"> Report Access</span> (Customize Groups) </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Aggiungi nuovo gruppo</span> &gt; <span class="uicontrol"> Accesso ai rapporti</span> </p> <p>The <span class="wintitle"> Report Access</span> section on the <span class="wintitle"> Define User Group</span> page has been streamlined to four categories, which enable you to customize permissions at a granular level. </p> <p><img  src="assets/report-access.png" id="image_CB83E5C7DB4343619421A1FAA61478D0"> </img> </p> <p>Elementi in precedenza </p> 
    <ul id="ul_16D5EF18D57D4608AEEDEC40D90D8828"> 
     <li id="li_F29E84C6228A464C8807F09205AEAAC6"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Strumenti di Analytics</a>: Abilita le autorizzazioni degli utenti per elementi generali (fatturazione, registri ecc.), gestione società, strumenti, accesso ai servizi Web, Generatore di report e integrazione dei connettori dati. </p> <p> <b>Nota:</b> le impostazioni aziendali della categoria Personalizza di Admin Console sono state trasferite negli strumenti di Analytics. </p> </li> 
     <li id="li_A6EB788162A2455E94CE54B9279A854D"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-report-suite-tools.md#concept_C94E9864349B428AB9CCE0CA4B0A40FF" format="dita" scope="local"> Strumenti suite di rapporti</a>: Abilita le autorizzazioni utente per servizi Web, gestione suite di rapporti, strumenti e rapporti e elementi dashboard. </p> </li> 
     <li id="li_EDB0255E009B4F1CAFAF53966B41363C"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-metrics.md#concept_05D54436430E4320A48C7C685D337FBE" format="dita" scope="local"> Metriche</a>: Abilitare le autorizzazioni per traffico, conversione, eventi personalizzati, eventi delle soluzioni, contenuto e così via. </p> </li> 
     <li id="li_8DAE87D1DEF54803A9C6FE31C01F0FB0"> <p> <a href="../../../admin/user-management2/c-customize-report-access/groups-dimensions.md#concept_68B36161345341369B6D01DC7DD42A22" format="dita" scope="local"> Dimensioni</a>: Personalizza l'accesso degli utenti a livello granulare, inclusi evar, rapporti sul traffico, rapporti sulle soluzioni e rapporti sui percorsi. </p> </li> 
    </ul> <p>For example, you can create a group with access to multiple Analytics tools (<span class="wintitle"> Analysis Workspace</span>, <span class="wintitle"> Reports &amp; Analytics</span>, and <span class="wintitle"> Report Builder</span>), with permission to specific metrics and dimensions (including eVars), and capabilities like segment or calculated metrics creation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifiche a gruppi predefiniti </p> </td> 
   <td colname="col2"> <p> <b>Accesso amministratore:</b> I gruppi predefiniti non sono più richiesti per gli amministratori. Gli amministratori ora hanno accesso a tutti gli elementi (strumenti, metriche, dimensioni), oltre che a Servizio Web, Generatore di report, Activity Map e Analisi ad hoc. </p> <p>In futuro, lo scopo dei gruppi è concedere o limitare l'accesso agli utenti non amministrativi. </p> <p> <b>Gruppi personalizzati:</b> I gruppi personalizzati hanno sostituito i gruppi predefiniti. I gruppi predefiniti esistenti verranno migrati a gruppi personalizzati utilizzando lo stesso nome di gruppo. Eventuali gruppi personalizzati creati, comprese le impostazioni, verranno conservati. Tuttavia, noterete che la posizione delle impostazioni verrà spostata. For example, Company settings (in Customize Admin Console) are now in <a href="../../../admin/user-management2/c-customize-report-access/groups-analytics-tools.md#concept_C4383A6C0F5E4130875FDD3756F2E2FC" format="dita" scope="local"> Customize Analytics Tools</a>. </p> <p> Users belonging to <span class="term"> All Report Access</span> have been migrated to a custom group with access to: </p> 
    <ul id="ul_696A9243F5FD4AF187352C2F4B1CFDC2"> 
     <li id="li_683A0A3BB7214CFFBC61D5A4CD237F48">Tutte le dimensioni </li> 
     <li id="li_D8FDBF6A32224731AB706315DEA0A03E">Tutte le metriche </li> 
     <li id="li_65ABE5C95D43444D88E63EE95C9AED05">Tutte le suite di rapporti </li> 
     <li id="li_7ED1505590144B38B3B9851BAA6BBB49">Autorizzazione per il rapporto sul canale </li> 
     <li id="li_F718FE1FCF9A4B05AB933CA3F105F3EC">Autorizzazione per il rapporto sul rilevamento delle anomalie </li> 
     <li id="li_527BD52007E846FE8B5F71AB3C12F695">Autorizzazione per il rapporto in tempo reale </li> 
     <li id="li_AFFB58C7FB644AC8A85E2D76BA7D51F5">Autorizzazione all'accesso ad Analysis Workspace </li> 
    </ul> <p>Administrators can delete custom groups and create their own, as all settings that were previously available in predefined groups are available for customization under the <span class="wintitle"> Report Access</span> settings in <a href="../c-user-groups/groups.md" format="dita" scope="local"> Define User Groups</a>. </p> </td> 
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
   <td colname="col1"> <p>Admin Console </p> </td> 
   <td colname="col2"> <p>Recommended only for new customers or customers with companies <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/core_services.html" format="html" scope="external"> provisioned in the Experience Cloud</a>. A migration for existing <span class="keyword"> Analytics</span> customers to the <span class="keyword"> Experience Cloud</span> identity management system is planned. </p> <p>More information is available in <a href="https://helpx.adobe.com/enterprise/using/manage-permissions-and-roles.html" format="html" scope="external"> Manage product permissions in the Admin Console</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Frequently Asked Questions about Permission Changes {#section_02809EFC95054B40A089E6C6E4FACA13}

Ecco nuove importanti informazioni su aggiornamenti nuovi e pianificati e su come influiscono sull'ambiente amministrativo.

<table id="table_1E93F45C66E841E6882FB602509F30A3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1">What permissions changes came in the <b>July 2016</b> release? </td> 
   <td colname="col2"> <p> <b>Accesso a tutte le suite di rapporti</b> </p> <p>When adding report suites to include in a group, you can specify <span class="uicontrol"> All Report Suite Access</span>. Questa impostazione applica le autorizzazioni del gruppo a tutte le suite di rapporti correnti e future. </p> <p>To enable this feature, navigate to <span class="uicontrol"> User Management</span> &gt; <span class="uicontrol"> Groups</span> &gt; <span class="uicontrol"> Add New User Group</span>, then select <span class="uicontrol"> All Report Suite Access</span>. </p> <p><img placement="break"  src="assets/all-report-suites.png" width="300px" id="image_9E814D412E87484C940F1100D6DE2B0F" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo utilizzare Admin Console per gestire gli utenti o la gestione utente di Analytics esistente? </p> </td> 
   <td colname="col2"> <p>Le modifiche effettuate in Analytics &gt; Amministratore &gt; Gestione utente non vengono riportate nell'Admin Console. Pertanto, solo i nuovi clienti che utilizzano già Admin Console per la gestione di utenti e gruppi devono continuare a farlo. È pianificata la migrazione per la gestione dei gruppi Analytics esistente ad Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>What Permissions changes were made in the <b>October 2016</b> release? </p> </td> 
   <td colname="col2"> <p>The following enhancements to the current <span class="wintitle"> Admin Tools</span> interface are available: </p> <p> 
     <ul id="ul_2A31E8DC17A94B7FABDBA9C87C3947EF"> 
      <li id="li_AE2ECCA01CC64D30B109BE74379EE474">Permission changes as described in <a href="../../../admin/user-management2/c-user-management/permissions-changes.md#concept_86581595B86B47D5B8F90282FC3E31EF" format="dita" scope="local"> Administrative Changes - Fall 2016</a>. </li> 
      <li id="li_33CB2B6A2E5F45BE97CC5E0983AF280E">Sono stati rimossi rapporti obsoleti sul traffico che non erano più presenti nel menu. </li> 
      <li id="li_57234CF27E1D405987DE89312CD62C52">Autorizzazioni classificazioni: L'accesso alle classificazioni sarà determinato dalla variabile per la classificazione. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C'è qualcosa che devo fare per migrare gli utenti? </p> </td> 
   <td colname="col2"> <p>No, tutte le migrazioni di autorizzazioni verranno eseguite in modo trasparente. </p> <p> 
     <ul id="ul_654F85286EC04416B3E0BA725EBE10AD"> 
      <li id="li_8050B8941F794103B82A0ADF0930D216">Tutti i rapporti sul traffico correnti in un gruppo personalizzato verranno trasferiti automaticamente alla nuova categoria Dimensione. </li> 
      <li id="li_B97079DB29A346B98D066F11AB7F94AF">Se un gruppo personalizzato dispone di metriche già abilitate, verranno automaticamente fornite tutte le dimensioni di nuova lettura (variabili evar e Soluzione). </li> 
      <li id="li_F1219EF490DA473BA15F2B215F2995AE"> A custom group with at least one metric will automatically be granted access to all eVars and other content-aware dimensions <b>except</b> the newly available traffic dimensions (formerly traffic reports). </li> 
      <li id="li_F494CE6144A04A6199CFBBA1D7BEA32B">Ogni gruppo predefinito viene trasformato in un'autorizzazione. These new permissions will be added to a new <span class="uicontrol"> Analytics Tools</span> category. </li> 
      <li id="li_2FCD9254FC3C4FD7871EEF9453E5CE1E">Tutti i gruppi personalizzati con qualsiasi metrica avranno aggiunto come nuove metriche tutti gli eventi Analytics Solution. </li> 
      <li id="li_34C4560769B64F28A4E83BAE71065DCC">Ogni utente che era utilizzato in Accesso ai report viene aggiunto al nuovo gruppo personalizzato. L'accesso ai rapporti non esiste più. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa cambia? </p> </td> 
   <td colname="col2"> <p>Gli attributi dei visitatori continueranno a non essere eseguiti. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Permissioning Quick Reference {#section_A3FDD8259F524B21A5489833533D1B28}

Nella tabella seguente sono elencate le attività e in cui possono essere svolte (a seconda dello stato della società).

>[!NOTE]
>
>A *`migrated user`* and *`Experience Cloud user`* refer to users who have accepted an email invitation to join the Experience Cloud. Se l'invito e-mail non viene accettato, gli utenti sono ancora utenti di Analytics e non possono essere gestiti nell'Admin Console. (The exception is if the migration is using [enterprise or federated IDs](https://helpx.adobe.com/enterprise/using/set-up-identity.html). In questo caso, l'utente viene migrato quando l'amministratore esegue la migrazione degli utenti a livello di singolo utente.

<table id="table_B68FD00FC5D24823A86BB69558C0327C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col2" class="entry"> Non migrazione della società di accesso </th> 
   <th colname="col3" class="entry"> Migrazione della società </th> 
   <th colname="col4" class="entry"> Migrazione della società di accesso completata </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Creare un utente </td> 
   <td colname="col2"> <p>Admin Console (creating a user and adding him or her to an Analytics <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> product configuration</a> also creates the user account in Analytics). </p> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Strumenti di amministrazione</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Admin Console</a> </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Admin Console</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modificare un utente </td> 
   <td colname="col2"> <p> <a href="../../../admin/user-management2/c-user-management/t-add-user-account.md#task_60F86F36CB86446699EA7C7E5FB03EA7" format="dita" scope="local"> Strumenti di amministrazione</a> </p> </td> 
   <td colname="col3"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Admin Console</a> </p> <p> Strumenti di amministrazione - La modifica in Strumenti di amministrazione per gli utenti migrati è limitata alla gestione delle chiavi API e all'eliminazione/trasferimento delle risorse. </p> </td> 
   <td colname="col4"> <p> <a href="https://adminconsole.adobe.com/enterprise/" format="http" scope="external"> Admin Console</a> </p> <p> Strumenti di amministrazione - Modifica è limitato alla gestione delle chiavi API ed elimina /transferring di risorse. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Eliminare un utente </td> 
   <td colname="col2"> <p>Admin Console - Per utenti Experience Cloud </p> <p>Strumenti di amministrazione: per tutti gli utenti, ma per gli utenti di Experience Cloud, elimina solo l'utente di Analytics mappato, non l'account Experience Cloud. </p> </td> 
   <td colname="col3"> <p>Admin Console - Per utenti migrati. </p> <p>Strumenti di amministrazione - Solo per utenti Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> <p> Strumenti di amministrazione: dopo l'eliminazione di un utente Experience Cloud o l'annullamento del collegamento del loro account in Admin Console, puoi eliminare l'accesso Analytics da Strumenti di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Accesso ad Analytics </td> 
   <td colname="col2"> <p> <b>Experience Cloud: </b><span class="filepath"> marketing.adobe.com</span>. Disponibile solo per gli utenti di Experience Cloud. </p> <p> <b>Analytics (legacy):</b><span class="filepath"> sc.omniture.com</span>. Solo per gli utenti di Analytics e per gli utenti di Experience Cloud con le loro credenziali Analytics </p> </td> 
   <td colname="col3"> <p> <span class="filepath"> marketing.adobe.com</span> - disponibile solo per gli utenti di Experience Cloud. </p> <p> <span class="filepath"> sc.omniture.com</span> - Solo per gli utenti e per gli utenti di Experience Cloud con le loro credenziali Analytics. </p> <p>During migration, admins can turn off <span class="filepath"> omniture.com</span> login ability for specific users. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Create un gruppo </td> 
   <td colname="col2"> <p>Admin Console: quando un gruppo viene creato in Admin Console, un gruppo mappato in Analytics viene visualizzato in Strumenti di amministrazione, ma non può avere il nome modificato da Strumenti di amministrazione o essere eliminato da Strumenti di amministrazione. </p> <p>Strumenti di amministrazione. </p> </td> 
   <td colname="col3"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
   <td colname="col4"> <p>Admin Console (<a href="https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html" format="html" scope="external"> create product configuration</a>) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modificare gli utenti in un gruppo </td> 
   <td colname="col2"> <p>Admin Console - Solo per utenti Experience Cloud </p> <p>Strumenti di amministrazione - Utenti di Analytics e abbonamento utenti di Experience Cloud a gruppi possono essere modificati da Strumenti di amministrazione. Tuttavia, se un utente Experience Cloud fa parte di un gruppo in Admin Console, non può essere rimosso dal gruppo in Strumenti di amministrazione. </p> </td> 
   <td colname="col3"> <p>Admin Console - Solo utenti Experience Cloud </p> <p> Strumenti di amministrazione - Gli accessi di Analytics possono comunque essere aggiunti o rimossi dai gruppi in Strumenti di amministrazione. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Modificare le autorizzazioni per un gruppo </td> 
   <td colname="col2"> <p>Admin Console: potete modificare i gruppi creati in Admin Console. </p> <p>Strumenti di amministrazione: potete modificare le autorizzazioni per qualsiasi gruppo. </p> </td> 
   <td colname="col3"> <p>Admin Console </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elimina gruppo </td> 
   <td colname="col2"> <p>Admin Console: puoi eliminare solo i gruppi creati in Admin Console. </p> <p>Strumenti di amministrazione: potete eliminare solo i gruppi creati da Strumenti di amministrazione. </p> </td> 
   <td colname="col3"> <p>Admin Console </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cambiare lo stato di amministrazione per l'utente </td> 
   <td colname="col2"> <p>Admin Console - Solo per gli utenti di Experience Cloud. </p> <p>Strumenti di amministrazione </p> </td> 
   <td colname="col3"> <p>Admin Console - Solo per gli utenti di Experience Cloud. </p> <p>Strumenti di amministrazione - Solo per gli utenti di Analytics. </p> </td> 
   <td colname="col4"> <p>Admin Console </p> </td> 
  </tr> 
 </tbody> 
</table>
