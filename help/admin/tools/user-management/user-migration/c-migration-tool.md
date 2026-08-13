---
description: Informazioni necessarie sulla migrazione degli ID utente di Analytics ad Admin Console in Adobe CX Enterprise.
title: Migrazione degli utenti di Analytics all’Admin Console
feature: Admin Tools
exl-id: f4bc0e92-af53-40db-8138-44d29e4b25fe
role: Admin
TQID: https://experienceleague.adobe.com/bCf6DWIpIVALcGPAi3tL8zlZ5V8lzPR-9XNCm4HuFnY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: d124af73-4061-4b84-9063-ae2b60f2c1f3
  - id: e499b847-6dc4-408a-9f0b-70d35ce9b711
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 9e2c89f4188c723b4623a6e7859b74ede15e155b
workflow-type: tm+mt
source-wordcount: 2960
ht-degree: 19%

---

# Migrazione degli utenti di Analytics al Adobe Admin Console{#analytics-user-migration-to-the-admin-console}

Informazioni necessarie sulla migrazione degli ID utente di Analytics a Adobe Admin Console in Adobe CX Enterprise.

Per informazioni generali sugli argomenti relativi a Adobe Admin Console (non correlati alla migrazione di Analytics), consulta la [Guida utente di Admin Console](https://helpx.adobe.com/it/enterprise/administering/user-guide.html).

Dopo la migrazione, è possibile [gestire gli utenti e i prodotti CX Enterprise](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=it) in Adobe Admin Console.

## Cos’è la migrazione degli ID utente di Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

La migrazione degli ID utente di Analytics permette agli amministratori di trasferire facilmente gli account utente in Gestione utenti di Analytics ad Adobe Admin Console. Dopo la migrazione, gli utenti potranno accedere alle soluzioni e ai servizi di base disponibili in CX Enterprise. La migrazione viene implementata per i clienti in più fasi.

L&#39;utilizzo di Adobe Admin Console offre i seguenti vantaggi:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Beneficio </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On </p> </td> 
   <td colname="col2"> <p>Gli utenti di Analytics possono accedere a CX Enterprise e a tutte le soluzioni utilizzando il proprio Adobe ID o Enterprise ID. Questo accesso consente l'accesso alle soluzioni integrate e ai servizi principali di CX Enterprise. </p> <p>Dopo la migrazione, gli utenti che tenteranno di accedere con i metodi legacy (<span class="filepath">my.omniture.com</span> e <span class="filepath">sc.omniture.com</span>) verranno reindirizzati su <span class="filepath">experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestione delle autorizzazioni e delle identità utente </p> </td> 
   <td colname="col2"> <p>Gli amministratori di Analytics possono gestire gli utenti e le autorizzazioni esclusivamente nell’<a href="https://adminconsole.adobe.com/enterprise/"> Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestione di prodotti e servizi principali </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invita nuovi utenti </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Creare profili di prodotto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Concedere agli utenti l’autorizzazione per prodotti e servizi specifici </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Accedi a <a href="https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=it"> servizi core di più soluzioni</a> disponibili in Adobe CX Enterprise </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Cosa bisogna sapere (e fare) prima di eseguire la migrazione degli ID utente (FAQ) {#section-b0fc7f0bbd4b488e95b0c8e77ff077a9}

Risposte alle domande che potrebbero sorgere prima della migrazione.

<table id="table_36FD7EF1DAB44D359F4FC186D93147E5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda/Attività </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sono un amministratore di Analytics e ho ricevuto un’e-mail di pre-migrazione. Cosa faccio prima? </p> </td> 
   <td colname="col2"> <p>Verificare di disporre di un Adobe ID e di poter accedere a <a href="https://adminconsole.adobe.com/enterprise/"> CX Enterprise Admin Console</a>. </p> <p>In caso contrario, contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. Contatta prima il tuo amministratore di prodotto o di sistema che può invitarti nell’organizzazione appropriata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrazioni di AEM con Analytics </p> </td> 
   <td colname="col2"> <p> Gli utenti di AEM con un’integrazione in Analytics dovranno modificare la propria configurazione per utilizzare il segreto condiviso di Analytics invece della password. </p> <p> Esegui questa operazione prima di abilitare la migrazione. Una volta disattivata la migrazione, la password configurata originariamente non sarà più valida. </p> <p><b>Per ottenere il segreto condiviso in Analytics</b> </p> <p> Il segreto condiviso può essere ottenuto da Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Gestione utenti</span>) ed è differente per ciascun utente. </p> <p><b>Per aggiornare la tua configurazione di AEM con il segreto condiviso</b> </p> <p>Consulta <a href="https://helpx.adobe.com/it/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Collegamento ad Adobe Analytics e creazione di framework</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiornare Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: è necessario aggiornare l’installazione di <a href="/help/analyze/report-builder/report-builder-setup.md"> Report Builder</a> all’ultima versione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quando inizia la migrazione? </p> </td> 
   <td colname="col2"> <p>Adobe informerà gli amministratori di Analytics via e-mail con istruzioni su quando inizierà la migrazione. </p> <p>Le migrazioni a Adobe Admin Console avverranno a ondate. Il giorno della migrazione, Adobe invia una notifica agli amministratori di Analytics concedendo loro l’accesso allo strumento di migrazione. Dopo che una società di accesso soddisfa i criteri definiti per ogni ondata di migrazione, Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Imposta le date di inizio e di fine per la migrazione della società. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Invia una notifica e-mail agli amministratori Analytics correnti della società circa 30 giorni prima della migrazione. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Visualizza una notifica interna al prodotto che informa gli amministratori della data di inizio della migrazione. </li> 
    </ul> <p> Il giorno della migrazione, i gruppi di autorizzazioni precedenti vengono automaticamente copiati in Adobe Admin Console. Non potrai più invitare nuovi utenti o creare nuovi gruppi dagli strumenti di amministrazione di Analytics. </p> <p>Dopo la migrazione: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Gli amministratori utilizzeranno Adobe Admin Console per gestire gli utenti e le autorizzazioni di Analytics. Non utilizzerai più l’interfaccia di gestione utente in Analytics &gt; Amministratore &gt; Gestione utente. </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Gli utenti accederanno ad Analytics utilizzando il proprio Adobe o Enterprise ID tramite CX Enterprise invece di <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa accade alla data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Alle 10:00 UTC della data di inizio della migrazione: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">I gruppi di autorizzazioni esistenti in Analytics verranno replicati automaticamente in Adobe Admin Console come profili di prodotto, incluse la descrizione e le autorizzazioni granulari per le suite di rapporti, le metriche, le dimensioni, Analytics e gli strumenti delle suite di rapporti. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Se uno dei tuoi utenti attuali di Analytics è stato creato in Adobe Admin Console (ovvero ha un Adobe/Enterprise ID collegato), verrà aggiunto ai profili di prodotto appropriati in Adobe Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La sezione Gestione utente nella scheda Amministratore in Analytics verrà impostata su <span class="term"> di sola lettura</span>. Non potrai più creare nuovi utenti o gruppi di autorizzazioni qui e dovrai eseguire entrambe queste funzioni in Adobe Admin Console. Per ulteriori informazioni, vedere <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> funzionalità di Analytics non supportate in Adobe Admin Console</a>. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">In quanto amministratore, avrai accesso allo <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md">strumento di Migrazione degli ID utente</a>. Inoltre, viene visualizzata una notifica interna al prodotto che include la data di fine della migrazione (in genere 60 giorni nel futuro), oltre ai collegamenti al contenuto dell’Aiuto e alle domande frequenti. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">In Adobe Admin Console potrai accedere a una scheda Autorizzazioni che ti consente di creare profili di prodotto con tutte le opzioni granulari che conosci. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Come posso eseguire la migrazione degli ID utente? </p> </td> 
   <td colname="col2"> <p> Fare clic su <a href="/help/admin/tools/user-management/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migra ID utente</a> nella sezione Gestione utente della pagina Amministratore. Utilizza lo strumento per aggiungere utenti ai profili di prodotto in Adobe Admin Console (replicato dai gruppi di autorizzazioni in Analytics). Puoi eseguire la migrazione degli ID utente al tuo ritmo. </p> <p>Sono necessari privilegi di amministrazione. Una volta completata, la migrazione non può essere annullata. </p> <p>Alla data di fine della migrazione, l’accesso mediante <span class="filepath"> my.omniture.com</span> verrà disattivato per gli utenti che fanno parte della tua società di accesso. Gli utenti (inclusi quelli per cui non è stata ancora eseguita la migrazione) verranno reindirizzati all'accesso tramite il nuovo URL CX Enterprise (<span class="filepath"> experiencecloud.adobe.com</span>) </p> <p>Nota: Adobe consiglia di eseguire un controllo degli utenti e dei gruppi prima di eseguire la migrazione. Elimina gli account obsoleti e inutilizzati o gli account che non devono avere più accesso al prodotto (ad esempio, gli ex dipendenti). </p> <p>Argomento correlato: <a href="/help/admin/tools/user-management/user-migration/migrate-enterprise.md"> Eseguire la migrazione degli account utente di Analytics per Enterprise e Federated ID</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La migrazione influirà sull’implementazione di Analytics o sulla modalità di raccolta dei dati? </p> </td> 
   <td colname="col2"> <p>No. </p> <p>Lo strumento di migrazione consente di trasferire gli ID utente e le autorizzazioni da Gestione utenti di Analytics a <a href="https://adminconsole.adobe.com/enterprise/"> CX Enterprise Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quanto tempo richiede il processo di migrazione? </p> </td> 
   <td colname="col2"> <p>Quattro settimane prima della migrazione, tutti gli amministratori Analytics correnti riceveranno un’e-mail di notifica pre-migrazione. La data di inizio effettiva viene visualizzata nell’interfaccia di Analytics. </p> <p>All’inizio della migrazione, gli amministratori avranno 60 giorni per completare il processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso accelerare la migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Tuttavia, Adobe consiglia di utilizzare il tempo che precede l’inizio della migrazione per: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verifica di essere un amministratore di prodotto Analytics in Adobe Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunica alla tua base di utenti che la loro esperienza di accesso cambierà all’inizio della migrazione. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Controlla gli utenti e le autorizzazioni attuali ed esegui attività di pulizia. </li> 
    </ul> <p>Per accelerare la migrazione, contatta il team del tuo account Adobe all'indirizzo <a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Adobe Customer Care</a> e invia una richiesta per anticipare la data di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sono un amministratore di Analytics senza accesso a Adobe Admin Console. Chi può aiutarmi ad accedere al Adobe Admin Console? </p> </td> 
   <td colname="col2"> <p>Qualsiasi amministratore di sistema o di prodotto che ha accesso al Adobe Admin Console della tua organizzazione può concederti l’accesso. Se non sai chi dispone dei privilegi di amministratore nella console all’interno della tua organizzazione, contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso posticipare la data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. </p><p>Di seguito trovi una descrizione delle modifiche apportate alla gestione corrente degli utenti e delle autorizzazioni di Analytics alla data di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora che la mia azienda sta eseguendo la migrazione a Adobe Admin Console, dove posso creare nuovi utenti e gruppi di autorizzazioni prima della data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Prima della data di inizio della migrazione, puoi creare gli utenti in Adobe Admin Console o in Analytics &gt; Gestione utenti. </p> <p>Dopo l’inizio della migrazione, puoi creare utenti e gruppi di autorizzazioni solo in Adobe Admin Console. </p><p>Per ulteriori informazioni su cosa accade alla data di inizio della migrazione, consulta la sezione Migrazione in basso. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quando posso implementare il single sign-on utilizzando Federated ID? </p> </td> 
   <td colname="col2"> <p> Presto in Adobe Admin Console sarà disponibile uno strumento che consentirà di cambiare i tipi di ID da Adobe ID a Federated ID. Durante la migrazione, non è possibile eseguire la migrazione degli utenti come Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cosa bisogna sapere durante la migrazione (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Informazioni importanti sul processo di migrazione e su come influisce sulla gestione degli utenti corrente.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Come vengono replicati i gruppi di autorizzazioni in Adobe Admin Console? E i miei utenti? </p> </td> 
   <td colname="col2"> <p>Un gruppo Analytics migrato è un gruppo denominato <i>Profilo prodotto</i> in Adobe Admin Console. Le impostazioni delle autorizzazioni per il gruppo originale vengono mantenute durante la migrazione. Tuttavia, gli utenti assegnati al gruppo non vengono migrati. Quando si esegue la migrazione di un utente appartenente a tale gruppo utilizzando lo strumento di migrazione, l’utente viene assegnato a tale profilo di prodotto. </p> <p>Ad esempio, un gruppo di autorizzazioni per le operazioni sulla costa occidentale che ha autorizzato i propri membri a utilizzare Report Builder e Analysis Workspace (con determinate suite di rapporti, metriche, dimensioni) diventerà un profilo di prodotto per le operazioni sulla costa occidentale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso delegare l’impegno di migrazione a un altro amministratore? </p> </td> 
   <td colname="col2"> <p>Una volta iniziata la migrazione, qualsiasi amministratore che accede all’istanza Analytics tramite CX Enterprise può utilizzare lo strumento di migrazione per avviare (o continuare) la migrazione degli utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso aggiornare l’iscrizione al gruppo di autorizzazioni per gli utenti non trasferiti? </p> </td> 
   <td colname="col2"> <p>Sì. Puoi modificare l’iscrizione al gruppo degli utenti non migrati dall’interno della sezione Gestione utenti di Analytics. </p><p>In attesa di ulteriori chiarimenti da parte di Ashok. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso creare utenti e gruppi di autorizzazioni in Analytics dopo l’inizio della migrazione e quindi utilizzare lo strumento di migrazione per spostarli in Adobe Admin Console? </p> </td> 
   <td colname="col2"> <p> No. Una volta iniziata la migrazione, tutti i nuovi utenti e i gruppi di autorizzazioni (denominati Profili di prodotto in Adobe Admin Console) devono essere creati in Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agli utenti che eseguo la migrazione utilizzando lo strumento di migrazione verrebbero assegnate le stesse autorizzazioni di cui disponevano in Analytics? </p> </td> 
   <td colname="col2"> <p>Sì. Agli utenti migrati tramite questo strumento verranno concesse le autorizzazioni di cui dispongono attualmente in Analytics. Inoltre, quando accedono ad Analytics tramite CX Enterprise, conservano l’accesso alle loro risorse Analytics (come segmenti, progetti, metriche calcolate e così via). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli utenti che trasferisco in Adobe Admin Console continueranno ad avere accesso ad Analytics utilizzando <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sì. Gli utenti trasferiti continueranno ad avere accesso ad Analytics utilizzando il nome utente e la password esistenti mediante <span class="filepath"> my.omniture.com</span> fino alla data di fine della migrazione, a meno che tu non disattivi l’accesso legacy tramite lo strumento di migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Due o più dei miei utenti hanno lo stesso ID e-mail nei loro record di Analytics. Cosa succede se eseguo la migrazione? </p> </td> 
   <td colname="col2"> <p>Poiché gli account utente in Adobe Admin Console richiedono ID e-mail univoci, quando tenti di migrare più di uno di questi utenti, viene visualizzato un errore di tipo "Duplica ID e-mail". Prima di ritentare la migrazione, è possibile aggiornare gli ID e-mail degli utenti non trasferiti nella sezione Gestione utente (legacy). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cosa posso fare dopo aver trasferito gli utenti? </p> </td> 
   <td colname="col2"> <p>Disattiva l’accesso legacy tramite <span class="filepath"> my.omniture.com</span>. Non potrai disattivare l’accesso legacy a meno che non sia stata effettuata la migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso tenere traccia del processo di migrazione? </p> </td> 
   <td colname="col2"> <p>Lo strumento di migrazione include una dashboard che mostra quanti utenti sono stati migrati correttamente e quanti di loro hanno l’accesso legacy disabilitato. </p> <p> È consigliabile eseguire correttamente la migrazione della società di accesso a Adobe Admin Console quando il 100% degli utenti ha completato la migrazione e gli accessi legacy sono stati disabilitati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo eseguire la gestione di utenti e autorizzazioni durante la migrazione. Quale strumento posso utilizzare per eseguire questa attività? </p> </td> 
   <td colname="col2"> <p>Una volta iniziata la migrazione, potrai utilizzare Adobe Admin Console per creare e gestire nuovi utenti e profili di prodotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa sperimentano gli utenti quando eseguo la migrazione tramite lo strumento? </p> </td> 
   <td colname="col2"> <p>Riceveranno un’e-mail di benvenuto indirizzata all’ID e-mail nel record utente di Analytics, con una notifica sul nuovo modo di accedere ad Analytics tramite CX Enterprise. Se non dispone di un’Adobe ID esistente, gli verrà richiesto di crearne una, dopodiché potrà accedere alla soluzione utilizzando il proprio Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È possibile utilizzare le API per migrare gli utenti anziché utilizzare lo strumento di migrazione? </p> </td> 
   <td colname="col2"> <p>No. Utilizza lo strumento di migrazione per assicurarti che tutti gli utenti esistenti vengano migrati a Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quali funzioni di gestione degli utenti di Analytics non sono disponibili in Adobe Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Trasferimento risorse </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Scadenza utente </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Registri utente </li> 
    </ul> <p>Questi elementi resteranno disponibili per la gestione degli utenti di Analytics. </p> <p>Per ulteriori informazioni, vedere <a href="/help/admin/tools/user-management/user-migration/c-migration-tool.md"> funzionalità di Analytics non supportate in Adobe Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Abbiamo creato diverse configurazioni in Adobe Admin Console e le abbiamo mappate sui gruppi di autorizzazioni di Analytics. Cosa succederà a queste configurazioni quando inizia la migrazione? </p> </td> 
   <td colname="col2"> <p>I gruppi di autorizzazioni di Analytics vengono ricreati in Adobe Admin Console come profili di prodotto, proprio come tutti gli altri gruppi. Ciò significa che nella console verranno visualizzati due profili di prodotto con autorizzazioni essenzialmente duplicate. Puoi eliminare i profili di prodotto duplicati da Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual è il passaggio successivo dopo la migrazione dell’utente? </p> </td> 
   <td colname="col2"> <p>Dopo avere trasferito un utente o un insieme di utenti, devi disattivare il suo accesso legacy mediante <span class="filepath"> my.omniture.com</span>. Per farlo, seleziona questi utenti nello strumento di migrazione e fai clic sull’opzione contestuale "Disattiva accesso legacy" che viene visualizzata nella parte superiore dello schermo. Questa opzione è visibile solo quando si seleziona un utente o un set di utenti di cui è stata eseguita correttamente la migrazione a Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa succede alla data di fine della migrazione? </p> </td> 
   <td colname="col2"> <p>Dopo la data di fine della migrazione (60 giorni dall'inizio della migrazione), tutti gli utenti della società di accesso vengono reindirizzati per l'accesso tramite la pagina di accesso di CX Enterprise utilizzando i propri Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non sono riuscito a eseguire la migrazione di tutti i miei utenti entro la data di fine della migrazione. Gli utenti non trasferiti perderebbero l’accesso ad Analytics? </p> </td> 
   <td colname="col2"> <p>Gli utenti che non sono stati trasferiti entro la data di fine verranno reindirizzati alla pagina di accesso di CX Enterprise (experiencecloud.adobe.com) e non potranno accedere ad Analytics. Tuttavia, continuerai ad avere accesso allo strumento di migrazione per trovare e trasferire questi utenti e ripristinare il loro accesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cosa bisogna sapere dopo la migrazione (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda/Problema </th> 
   <th colname="col2" class="entry"> Risposte </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminazione di utenti da Adobe Admin Console </p> </td> 
   <td colname="col2"> <p> In Analytics, un utente eliminato è impostato come <span class="term"> scaduto</span>, ma l'account continua a esistere. Mantenere il conto consente il trasferimento delle risorse, ad esempio segmenti, metriche calcolate, rapporti pianificati, progetti e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scadenze account </p> </td> 
   <td colname="col2"> <p> Puoi impostare manualmente una data di scadenza dell’account in Analytics in Strumenti di amministrazione. Una volta raggiunta la data di scadenza, l’utente non potrà accedere ad Analytics, ma al suo account utente CX Enterprise effettivo (ad esempio Adobe ID, Enterprise ID, Federated ID, ecc.) non scade. Possono comunque accedere a CX Enterprise, ma non potranno fare clic su Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Funzioni di Analytics non supportate in Adobe Admin Console {#section-928ffba27a0446e0af575b720434ef56}

>[!IMPORTANT]
>
>Esamina i seguenti problemi che possono verificarsi durante il processo di migrazione.

<table id="table_88E2FA03D5F241B79AB54D12F64B51DA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda/Problema </th> 
   <th colname="col2" class="entry"> Risposte </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Accedi come </p> </td> 
   <td colname="col2"> <p> Gli amministratori che eseguono la migrazione al Adobe Admin Console non potranno più utilizzare la funzione "Accedi come" per accedere agli account utente non amministratori che sono stati trasferiti al Adobe Admin Console. Questa funzione è stata ritirata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scadenza utente e trasferimento risorse </p> </td> 
   <td colname="col2"> <p> Adobe Admin Console non supporta la scadenza degli utenti o il trasferimento delle risorse. Per entrambe le funzioni, gli amministratori utilizzeranno la sezione Utenti di Analytics e Assets in Strumenti di amministrazione in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultimo accesso (ultimo accesso) </p> </td> 
   <td colname="col2"> <p> I dettagli relativi alla data e all’ora dell’ultimo accesso degli utenti saranno disponibili nel collegamento Utenti di Analytics e Assets e non in Adobe Admin Console. La data dell'ultimo accesso in Analytics si riferisce alla data in cui gli utenti hanno effettuato l'accesso ad Analytics da CX Enterprise e non alla data/ora in cui hanno effettuato l'accesso a CX Enterprise. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API di gestione utenti <a href="https://helpx.adobe.com/it/enterprise/help/identity.html"> Tipi di identità supportati da Adobe</a> </p> </td> 
   <td colname="col2"> <p> Gli amministratori che eseguono la migrazione a Adobe Admin Console devono configurare le API di gestione utenti offerte su Adobe Developer per l’accesso programmatico agli account utente in Adobe Admin Console. </p> <p>Le API delle autorizzazioni di Analytics verranno disattivate quando si è abilitati per la migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenziali servizio Web </p> </td> 
   <td colname="col2"> <p> Le credenziali del servizio web degli utenti (e il loro segreto condiviso) non saranno disponibili in Adobe Admin Console e sono accessibili facendo clic sull’utente specifico nella sezione Utenti di Analytics e Assets. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On </p> </td> 
   <td colname="col2"> <p> Le configurazioni Single Sign-On di Analytics verranno rimosse al termine della migrazione. Rimarranno attivi durante la migrazione. I clienti che utilizzano il Single Sign-On in Analytics devono eseguire l’aggiornamento all’<a href="https://helpx.adobe.com/it/enterprise/help/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics consiglia di eseguire la migrazione degli utenti come Adobe ID per creare facilmente gli account CX Enterprise, quindi di convertirli in utenti Single Sign-On federati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Download dei gruppi di autorizzazioni </p> </td> 
   <td colname="col2"> <p> Il download delle informazioni sul gruppo di autorizzazioni non sarà più supportato negli strumenti di amministrazione di Analytics o in Adobe Admin Console. I clienti devono utilizzare le API di gestione utenti adobe.io per ottenere in blocco informazioni sui gruppi di autorizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data di creazione account </p> </td> 
   <td colname="col2"> <p>Le informazioni sulla data di creazione dell’account non sono più supportate negli strumenti di amministrazione di Analytics o in Adobe Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-mail in blocco </p> </td> 
   <td colname="col2"> <p>I messaggi e-mail in blocco agli utenti non saranno più supportati né negli Strumenti di amministrazione di Analytics né in Adobe Admin Console. I clienti possono esportare in blocco gli indirizzi e-mail dei propri utenti da Adobe Admin Console e inviare un messaggio e-mail utilizzando qualsiasi client e-mail desiderato. </p> </td> 
  </tr> 
 </tbody> 
</table>
