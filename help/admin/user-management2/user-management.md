---
description: Gestisci utenti, gruppi e prodotti Analytics nell’Admin Console.
subtopic: Users and groups
title: Gestione di utenti e prodotti
feature: Admin Tools
uuid: 891a8cb3-b77d-46f6-ab23-cbed49f215b5
exl-id: c0fbbb3a-0011-49d2-89a2-70fce11e0fb2
source-git-commit: 1c066c0ebdf581c7a85b532534cf3088877fd046
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 15%

---

# Gestione di utenti e prodotti

Gestisci utenti, gruppi e prodotti Analytics nell’Admin Console.

>[!IMPORTANT]
>
>La gestione di utenti e prodotti è stata spostata in [Adobe Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Adobe ti avviserà quando è il tuo momento di eseguire la migrazione degli utenti.

## Risorse di aiuto per gli amministratori di Admin Console {#section_C13BBB89E4F248F193358BB3A59DD502}

| Attività o risorsa | Descrizione |
| --- | --- |
| Migrazione degli ID utente di Analytics a Adobe Admin Console | Adobe aiuta gli amministratori di Analytics a trasferire gli ID utente ad Adobe Admin Console. Questo sforzo avverrà a ondate. Quando toccherà a te trasferire i tuoi utenti, Adobe invierà agli amministratori di Analytics una notifica via e-mail con le istruzioni. Uno strumento di migrazione è disponibile in [Gestione utente di Analytics](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html) per semplificare questa attività.<p>**Importante**: Il giorno della migrazione degli utenti, i tuoi gruppi di autorizzazioni precedenti vengono automaticamente copiati nell’Admin Console. Non potrai più invitare nuovi utenti o creare nuovi gruppi in Strumenti di amministrazione di Analytics. Consulta le Domande frequenti e aiuto in Migrazione utenti di Analytics ad Adobe Admin Console per informazioni su come prepararsi alla migrazione e sulle funzioni amministrative interessate. |
| Avvia Adobe Admin Console | Dopo la migrazione degli account utente, puoi gestire utenti e prodotti in tutte le soluzioni dell’Admin Console. Passa a: `https://adminconsole.adobe.com/enterprise/`. Fai riferimento anche a [Gestione di utenti e prodotti Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/administration/admin-getting-started.html). |
| Gestione di profili di prodotto, utenti e autorizzazioni di Adobe Analytics | Fai riferimento a [Analytics in Adobe Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/home.html?lang=it). |

<!---
## User Management Descriptions {#section_7C19842A3D4249109A9399D4DF18DE75}

The following table describes elements on the [!UICONTROL Users] tab in [!UICONTROL User Management].

<table id="table_6F81D1095EB945D8995FF971B65BA52A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins available</span> </td> 
   <td colname="col2"> The maximum number of user accounts you can create for this company. If necessary, you can contact your Account Representative or Customer Care to increase this number at no charge. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins in use</span> </td> 
   <td colname="col2"> The number of user accounts currently in use for this company. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Number of User Logins Remaining</span> </td> 
   <td colname="col2"> The difference between the user account maximum and the number of existing user accounts. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Add New User</span> </td> 
   <td colname="col2"> <p>Lets you add a user account to the company. This link is available only if the Number of User Logins Remaining is greater than 0. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Download Report</span> </td> 
   <td colname="col2">Exports the contents of the <span class="wintitle"> Users</span> table to a tab-delimited file. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Login</span> </td> 
   <td colname="col2"> <p>The user name. You can click the user name to edit the user account properties. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> First Name</span> </td> 
   <td colname="col2"> The user's first (given) name. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Name</span> </td> 
   <td colname="col2"> The user's surname (family name). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Title</span> </td> 
   <td colname="col2"> The user's job title. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Admin</span> </td> 
   <td colname="col2"> Specifies if the user account has administrative privileges. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Last Login</span> </td> 
   <td colname="col2"> Displays a timestamp of the last login for this user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Create Time</span> </td> 
   <td colname="col2"> Shows the date and time when the login account was created. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Expires</span> </td> 
   <td colname="col2"> Displays the account expiration account, if applicable. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Manage</span> </td> 
   <td colname="col2"> Provides links for user account management. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Edit</span> </td> 
   <td colname="col2"> <p>Edit user account settings. </p> <p>See <a href="/help/admin/user-management2/c-user-management/users.md"> Users</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Delete</span> </td> 
   <td colname="col2"> Delete the user account. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <span class="wintitle"> Transfer</span> </td> 
   <td colname="col2">Assign the privileges (permissions and resource access) of one user account to another. <p>See <a href="/help/admin/user-management2/c-user-management/t-transfer-user-accout-privileges.md"> Transfer user account privileges</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><span class="wintitle"> Login as this user</span> </td> 
   <td colname="col2"> <p>Allows admins to impersonate and log in as a non-admin account. Admin accounts cannot be impersonated. </p> </td> 
  </tr> 
 </tbody> 
</table>
-->