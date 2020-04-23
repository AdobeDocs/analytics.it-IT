---
description: Informazioni necessarie sulla migrazione degli ID utente di Analytics all’Admin Console in Adobe Experience Cloud.
title: Migrazione degli utenti di Analytics all’Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Migrazione degli utenti di Analytics all’Admin Console {#analytics-user-migration-to-the-admin-console}

Informazioni necessarie sulla migrazione degli ID utente di Analytics all’Admin Console in Adobe Experience Cloud.

Per assistenza generica sugli argomenti relativi all’Admin Console (non correlati alla migrazione di Analytics), vedi la [Guida utente di Admin Console](https://helpx.adobe.com/it/enterprise/administering/user-guide.html).

Dopo la migrazione, puoi [gestire utenti e prodotti](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html) Experience Cloud in Admin Console.

## Cos’è la migrazione degli ID utente di Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

La migrazione degli ID utente di Analytics consente agli amministratori di trasferire facilmente gli account utente in Gestione utente di Analytics nell’Admin Console di Adobe. Dopo la migrazione, gli utenti potranno accedere alle soluzioni e ai servizi di base disponibili in Experience Cloud. La migrazione verrà implementata ai clienti in più fasi.

I vantaggi dell&#39;utilizzo di Admin Console includono:

<table id="table_E4465796E224474680D750CAC5434ED3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Vantaggio </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On </p> </td> 
   <td colname="col2"> <p>Gli utenti di Analytics possono accedere a Experience Cloud e a tutte le soluzioni utilizzando il proprio Adobe ID o Enterprise ID. Questo accesso consente di accedere alle soluzioni integrate e ai servizi di base in Experience Cloud. </p> <p>Dopo la migrazione, gli utenti che tenteranno di accedere con i metodi legacy (<span class="filepath">my.omniture.com</span> e <span class="filepath">sc.omniture.com</span>) verranno reindirizzati su <span class="filepath">experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestione delle autorizzazioni e delle identità utente </p> </td> 
   <td colname="col2"> <p>Gli amministratori di Analytics possono gestire gli utenti e le autorizzazioni esclusivamente nell’<a href="http://adminconsole.adobe.com/enterprise/"> Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestione di prodotti e servizi di base </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invito di nuovi utenti </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Creare profili di prodotto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Concedere agli utenti l'autorizzazione per prodotti e servizi specifici </li> 
     <li id="li_9C8A340A7C9A45A98EC0BD4AF9E100FF">Accedere ai <a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/experience-cloud.html"> servizi core delle diverse soluzioni</a> disponibili in Adobe Experience Cloud </li> 
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
   <td colname="col1"> <p>Sono un amministratore di Analytics e ho ricevuto un messaggio e-mail di pre-migrazione. Cosa faccio prima? </p> </td> 
   <td colname="col2"> <p>Verifica di avere un Adobe ID e di poter accedere all’<a href="https://adminconsole.adobe.com/enterprise/"> Admin Console di Experience Cloud</a>. </p> <p>In caso contrario, contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. Contatta prima il tuo amministratore di prodotto o di sistema che può invitarti nell’organizzazione appropriata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrazioni di AEM con Analytics </p> </td> 
   <td colname="col2"> <p> Gli utenti AEM che dispongono di un'integrazione con Analytics dovranno cambiare la configurazione per utilizzare il segreto condiviso di Analytics invece della password. </p> <p> È necessario eseguire questa operazione prima che la migrazione sia abilitata. Una volta disattivata la migrazione, la password configurata in origine non sarà più valida. </p> <p><b>Per ottenere il segreto condiviso in Analytics</b> </p> <p> Il segreto condiviso può essere ottenuto da Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Gestione utenti</span>) ed è differente per ciascun utente. </p> <p><b>Per aggiornare la tua configurazione di AEM con il segreto condiviso</b> </p> <p>Consulta <a href="https://helpx.adobe.com/it/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Collegamento ad Adobe Analytics e creazione di framework</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiornare Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: è necessario aggiornare l’installazione di <a href="https://marketing.adobe.com/resources/help/it_IT/arb/t_install_arb.html"> Report Builder</a> all’ultima versione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quando inizia la migrazione? </p> </td> 
   <td colname="col2"> <p>Adobe invierà agli amministratori di Analytics un messaggio e-mail con istruzioni su quando avrà inizio la migrazione. </p> <p>Le migrazioni ad Admin Console avverranno a ondate. Il giorno della migrazione, Adobe avvisa gli amministratori di Analytics e concede loro l’accesso allo strumento di migrazione. Dopo che una società di accesso soddisfa i criteri definiti per ogni ondata di migrazione, Adobe: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Imposta le date di inizio e di fine per la migrazione della società. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Invia una notifica e-mail agli attuali amministratori di Analytics della società circa 30 giorni prima della migrazione. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Visualizza una notifica interna al prodotto per informare gli amministratori della data di inizio della migrazione. </li> 
    </ul> <p> Il giorno della migrazione, i tuoi gruppi di autorizzazioni precedenti vengono automaticamente copiati nell’Admin Console. Non potrai più invitare nuovi utenti o creare nuovi gruppi in Strumenti di amministrazione di Analytics. </p> <p>Dopo la migrazione: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Gli amministratori utilizzeranno l'Admin Console per gestire i propri utenti e autorizzazioni di Analytics. (non utilizzerete più l'interfaccia di gestione utenti in Analytics &gt; Amministratore &gt; Gestione utente.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Gli utenti accederanno ad Analytics con il proprio Adobe ID o Enterprise ID mediante Experience Cloud anziché tramite <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa succederà alla data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Alle 10:00 UTC della data di inizio della migrazione: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">I tuoi gruppi di autorizzazioni esistenti in Analytics verranno replicati automaticamente nell'Admin Console come profili di prodotto, inclusi la descrizione e le autorizzazioni granulari nelle suite di rapporti, nelle metriche, nelle dimensioni, in Analytics e negli strumenti delle suite di rapporti. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Se uno dei tuoi utenti Analytics correnti è stato creato nell’Admin Console (ovvero dispone di un Adobe/Enterprise ID collegato), verrà aggiunto ai profili di prodotto appropriati nell’Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La sezione Gestione utente della scheda Amministratore in Analytics verrà impostata per la <span class="term"> sola lettura</span>. Potrai creare nuovi utenti o gruppi di autorizzazioni solo nell’Admin Console. Per ulteriori informazioni, vedi <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> Funzioni di Analytics non supportate nell’Admin Console</a>. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">In qualità di amministratore, ti verrà concesso l’accesso allo strumento <a href="https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/t_migrate-users.html">di migrazione degli ID</a>utente. Inoltre, viene visualizzata una notifica interna al prodotto che include la data di fine della migrazione (generalmente 60 giorni in futuro) oltre ai collegamenti ai contenuti della guida e alle domande frequenti. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Potrai accedere a una scheda Autorizzazioni nell’Admin Console per creare profili di prodotto con tutte le opzioni granulari che ti sono familiari in Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Come si effettua la migrazione degli ID utente? </p> </td> 
   <td colname="col2"> <p> Click <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Migrate User IDs</a> on the Admin page, under User Management. Utilizza lo strumento per aggiungere utenti ai profili di prodotto nell’Admin Console (replicato dai gruppi di autorizzazioni in Analytics). Puoi eseguire la migrazione degli ID utente secondo i tuoi tempi. </p> <p>Sono richiesti i privilegi di amministrazione. Una volta completata la migrazione, questa non può essere annullata. </p> <p>Alla data di fine della migrazione, l’accesso mediante <span class="filepath"> my.omniture.com</span> verrà disattivato per gli utenti che fanno parte della tua società di accesso. Gli utenti (inclusi quelli per cui non è stata ancora eseguita la migrazione) verranno reindirizzati per l’accesso tramite il nuovo URL di Experience Cloud: <span class="filepath">experiencecloud.adobe.com</span>. </p> <p>Nota: Adobe consiglia di eseguire un controllo degli utenti e dei gruppi prima di eseguire la migrazione. Elimina gli account obsoleti e inutilizzati o gli account che non devono avere più accesso al prodotto (ad esempio, gli ex dipendenti). </p> <p>Argomento correlato: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Eseguire la migrazione degli account utente di Analytics per Enterprise e Federated ID</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La migrazione influenzerà l'implementazione di Analytics o la modalità di raccolta dei dati? </p> </td> 
   <td colname="col2"> <p>No. </p> <p>Lo strumento di migrazione serve a semplificare la transizione delle autorizzazioni e degli ID utente dal sistema di gestione degli utenti di Analytics all’<a href="https://adminconsole.adobe.com/enterprise/"> Admin Console di Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quanto tempo richiede il processo di migrazione? </p> </td> 
   <td colname="col2"> <p>Tutti gli attuali amministratori di Analytics riceveranno un messaggio e-mail di notifica quattro settimane prima della migrazione. (La data di inizio effettiva verrà visualizzata nell'interfaccia di Analytics.) </p> <p>All’inizio della migrazione, gli amministratori disporranno di 60 giorni per completare il processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso accelerare la migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Tuttavia, Adobe consiglia di utilizzare l’ora prima dell’inizio della migrazione: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verifica di essere un amministratore di prodotto Analytics nell'Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunica alla tua base di utenti che la loro esperienza di accesso cambierà all’inizio della migrazione. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Controlla gli utenti e le autorizzazioni correnti ed esegui attività di pulizia. </li> 
    </ul> <p>Per accelerare la migrazione, contatta il tuo Customer Success Manager presso l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a> e invia una richiesta per anticipare la data di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sono un amministratore di Analytics senza accedere ad Admin Console. Chi può aiutarmi ad accedere ad Admin Console? </p> </td> 
   <td colname="col2"> <p>Qualsiasi amministratore di prodotto o di sistema che ha accesso all’Admin Console della tua organizzazione può concederti l’accesso. Se non sai chi dispone dei privilegi di amministratore nella console all’interno della tua organizzazione, contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso posticipare la data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. </p> 
    <draft-comment> 
     <p>Di seguito trovi una descrizione delle modifiche apportate alla gestione corrente degli utenti e delle autorizzazioni di Analytics alla data di inizio. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora che la mia azienda sta effettuando la migrazione ad Admin Console, dove posso creare nuovi utenti e gruppi di autorizzazioni prima della data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Prima della data di inizio della migrazione, puoi creare utenti nell’Admin Console o in Analytics &gt; Gestione utente. </p> <p>Dopo l’inizio della migrazione, puoi creare utenti e gruppi di autorizzazioni solo nell’Admin Console. </p> 
    <draft-comment> 
     <p>Per ulteriori informazioni su cosa accade alla data di inizio della migrazione, consulta la sezione Migrazione (in basso). </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quando posso implementare il single sign-on utilizzando i Federated ID? </p> </td> 
   <td colname="col2"> <p> Presto nell'Admin Console sarà disponibile uno strumento che ti consentirà di cambiare i tipi di ID da Adobe ID a Federated ID. Durante la migrazione, non puoi trasferire gli utenti come Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cosa bisogna sapere durante la migrazione (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Informazioni importanti sul processo di migrazione e sull’impatto sulla gestione corrente degli utenti.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>In che modo vengono replicati i gruppi di autorizzazioni nell'Admin Console? E i miei utenti? </p> </td> 
   <td colname="col2"> <p>Un gruppo di Analytics migrato è denominato profilo <i>di</i> prodotto nell’Admin Console. Le impostazioni delle autorizzazioni per il gruppo originale vengono mantenute nella migrazione. Tuttavia, gli utenti assegnati al gruppo non vengono migrati. Quando un utente appartenente a tale gruppo viene migrato utilizzando lo strumento di migrazione, tale utente viene assegnato a tale profilo di prodotto. </p> <p>Ad esempio, un gruppo di autorizzazioni West Coast Operations che ha autorizzato i propri membri a Generatore di report e ad Analysis Workspace (con determinate suite di rapporti, metriche e dimensioni) diventerà un profilo di prodotto West Coast Operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso delegare lo sforzo di migrazione a un altro amministratore? </p> </td> 
   <td colname="col2"> <p>Una volta avviata la migrazione, qualsiasi amministratore che accede all’istanza di Analytics tramite Experience Cloud può utilizzare lo strumento di migrazione per iniziare (o continuare) la migrazione degli utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso aggiornare l'iscrizione al gruppo di autorizzazioni per gli utenti non trasferiti? </p> </td> 
   <td colname="col2"> <p>Sì. Potete modificare l'appartenenza al gruppo di utenti non trasferiti dalla sezione Gestione utente di Analytics. </p> 
    <draft-comment> 
     <p>In attesa di ulteriori chiarimenti da parte di Ashok. </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso creare utenti e gruppi di autorizzazioni in Analytics dopo l’inizio della migrazione, quindi utilizzare lo strumento di migrazione per spostarli nell’Admin Console? </p> </td> 
   <td colname="col2"> <p> No. Una volta avviata la migrazione, tutti i nuovi utenti e gruppi di autorizzazioni (denominati Profili di prodotto nell’Admin Console) devono essere creati nell’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli utenti che trasferisco con lo strumento di migrazione avranno le stesse autorizzazioni che avevano in Analytics? </p> </td> 
   <td colname="col2"> <p>Sì. Agli utenti migrati con lo strumento verranno assegnate le autorizzazioni di cui dispongono attualmente in Analytics. Inoltre, continueranno ad accedere alle proprie risorse Analytics (come segmenti, progetti, metriche calcolate e così via) quando accedono ad Analytics tramite Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli utenti che trasferisco nell’Admin Console continueranno ad avere accesso ad Analytics attraverso <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sì. Gli utenti trasferiti continueranno ad avere accesso ad Analytics utilizzando il nome utente e la password esistenti mediante <span class="filepath"> my.omniture.com</span> fino alla data di fine della migrazione, a meno che tu non disattivi l’accesso legacy tramite lo strumento di migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Due o più utenti della mia organizzazione hanno lo stesso ID e-mail nel record di Analytics. Cosa succede se li trasferisco? </p> </td> 
   <td colname="col2"> <p>Poiché gli account utente in Admin Console richiedono ID e-mail univoci, quando tenti di migrare più di uno di questi utenti verrai visualizzato in un errore "ID e-mail duplicato". Potete aggiornare gli ID e-mail degli utenti non trasferiti nella sezione Gestione utente (legacy) prima di riprovare la migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cosa devo fare dopo la migrazione degli utenti? </p> </td> 
   <td colname="col2"> <p>Disattiva l’accesso legacy tramite <span class="filepath"> my.omniture.com</span>. Non potrai disattivare l'accesso legacy se non hai trasferito i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso monitorare il processo di migrazione? </p> </td> 
   <td colname="col2"> <p>Lo strumento di migrazione include un dashboard che mostra quanti degli utenti hanno completato la migrazione e quanti di loro hanno disattivato l'accesso legacy. </p> <p> Idealmente, avrai eseguito la migrazione della tua società di accesso ad Admin Console quando un 100% degli utenti avrà completato la migrazione e avrà disabilitato i loro accessi legacy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo gestire utenti e autorizzazioni durante la migrazione. Quale strumento posso utilizzare per eseguire questa operazione? </p> </td> 
   <td colname="col2"> <p>Dopo l'inizio della migrazione, utilizzerai l'Admin Console per creare e gestire nuovi utenti e profili di prodotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa sperimentano i miei utenti quando li trasferisco con lo strumento? </p> </td> 
   <td colname="col2"> <p>Riceveranno un'e-mail di benvenuto indirizzata all'ID e-mail nel record utente di Analytics, con la notifica del nuovo modo di accedere ad Analytics tramite Experience Cloud. Se non dispongono di un Adobe ID, gli verrà richiesto di crearne uno, al termine del quale potranno accedere alla soluzione utilizzando il proprio Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso usare le API per migrare i miei utenti invece di usare lo strumento di migrazione? </p> </td> 
   <td colname="col2"> <p>No. Devi usare lo strumento di migrazione per fare in modo che tutti i tuoi utenti esistenti vengano trasferiti nell’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quali funzioni di gestione degli utenti di Analytics non sono disponibili nell’Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Trasferimento risorse </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Scadenza utente </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Registri utente </li> 
    </ul> <p>Queste funzionalità rimarranno disponibili nella gestione degli utenti di Analytics. </p> <p>Per ulteriori informazioni, vedi <a href="/help/admin/user-management2/user-migration/c-migration-tool.md"> Funzioni di Analytics non supportate nell’Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Abbiamo creato diverse configurazioni nell'Admin Console e le abbiamo mappate ai gruppi di autorizzazioni di Analytics. Cosa succederà a queste configurazioni all'inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>I gruppi di autorizzazioni di Analytics vengono ricreati nell’Admin Console come profili di prodotto, proprio come tutti gli altri gruppi. Ciò significa che vedrai due profili di prodotto nella console che sostanzialmente dispongono di autorizzazioni duplicate. Puoi eliminare profili di prodotto duplicati dall’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual è il passaggio successivo alla migrazione di un utente? </p> </td> 
   <td colname="col2"> <p>Dopo avere trasferito un utente o un insieme di utenti, devi disattivare il suo accesso legacy mediante <span class="filepath"> my.omniture.com</span>. Per farlo, selezionate questi utenti nello strumento di migrazione e fate clic sull’opzione contestuale "Disattiva login legacy" che viene visualizzata nella parte superiore dello schermo. Tieni presente che questa opzione è visibile solo quando selezioni un utente o un set di utenti che sono stati tutti trasferiti nell’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa succede alla data di fine della migrazione? </p> </td> 
   <td colname="col2"> <p>Dopo la data di fine della migrazione (60 giorni dall’inizio della migrazione), tutti gli utenti all’interno della società di accesso vengono reindirizzati per accedere tramite la pagina di accesso di Experience Cloud utilizzando i loro Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non sono riuscito a trasferire tutti i miei utenti entro la data di fine della migrazione. Gli utenti non trasferiti perderanno l'accesso ad Analytics? </p> </td> 
   <td colname="col2"> <p>Gli utenti che non sono stati trasferiti entro la data di fine verranno reindirizzati alla pagina di accesso di Experience Cloud (experiencecloud.adobe.com) e non potranno accedere ad Analytics. Tuttavia, continuerai ad avere accesso allo strumento di migrazione per trovare e trasferire questi utenti e ripristinare il loro accesso. </p> </td> 
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
   <td colname="col1"> <p>Eliminazione di utenti da Admin Console </p> </td> 
   <td colname="col2"> <p> In Analytics, un utente eliminato è impostato come <span class="term"> scaduto</span> ma l’account continua a esistere. La salvaguardia dell'account consente il trasferimento delle risorse, come segmenti, metriche calcolate, rapporti pianificati, progetti e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scadenza account </p> </td> 
   <td colname="col2"> <p> Puoi impostare manualmente una data di scadenza account in Analytics in Strumenti di amministrazione. Una volta raggiunta la data di scadenza, l'utente non sarà in grado di accedere ad Analytics, ma al suo account utente Experience Cloud effettivo (ad esempio, Adobe ID, Enterprise ID, Federated ID, ecc.) non scade. Possono comunque accedere a Experience Cloud, ma non potranno fare clic su Analytics. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Funzioni di Analytics non supportate nell’Admin Console {#section-928ffba27a0446e0af575b720434ef56}

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
   <td colname="col1"> <p>Login come </p> </td> 
   <td colname="col2"> <p> Gli amministratori che eseguono la migrazione nell'Admin Console non potranno più utilizzare la funzione "Accesso come" per accedere agli account utente non amministratore che sono stati migrati nell'Admin Console. Questa funzione è stata rimossa da Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scadenza utenti e trasferimento risorse </p> </td> 
   <td colname="col2"> <p> L’Admin Console non supporta la scadenza utente o il trasferimento di risorse. Gli amministratori utilizzeranno la sezione Risorse e utenti di Analytics in Strumenti di amministrazione in Analytics per entrambe le funzioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultimo accesso </p> </td> 
   <td colname="col2"> <p> I dettagli relativi alla data e all'ora dell'ultimo accesso di un utente saranno disponibili nel collegamento Risorse e utenti di Analytics e non nell'Admin Console. La data dell’ultimo accesso in Analytics si riferisce alla data in cui gli utenti hanno eseguito l’accesso ad Analytics mediante Experience Cloud e non alla data/ora in cui hanno eseguito l’accesso a Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API di gestione utenti <a href="https://helpx.adobe.com/it/enterprise/help/identity.html"> Tipi di identità supportati da Adobe</a> </p> </td> 
   <td colname="col2"> <p> Gli amministratori che eseguono la migrazione all’Admin Console devono configurare <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">le API di gestione utenti</a> offerte in Adobe I/O per l’accesso programmatico agli account utente nell’Admin Console. </p> <p>Le API delle autorizzazioni di Analytics verranno disattivate quando l'utente sarà abilitato per la migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenziali servizio Web </p> </td> 
   <td colname="col2"> <p> Le credenziali del servizio Web degli utenti (e il relativo segreto condiviso) non saranno disponibili nell'Admin Console e vi sarà possibile accedere facendo clic sull'utente specifico dalla sezione Risorse e utenti di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On </p> </td> 
   <td colname="col2"> <p> Le configurazioni del Single Sign-On di Analytics verranno rimosse al termine della migrazione. Rimarranno attivi durante la migrazione. I clienti che utilizzano il Single Sign-On in Analytics devono eseguire l’upgrade all’<a href="https://helpx.adobe.com/it/enterprise/help/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics consiglia di migrare gli utenti come Adobe ID prima per creare facilmente gli account Experience Cloud, quindi di convertire tali account in utenti con accesso singolo con Federated. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Download dei gruppi di autorizzazioni </p> </td> 
   <td colname="col2"> <p> Il download delle informazioni del gruppo di autorizzazioni non sarà più supportato né in Strumenti di amministrazione di Analytics né nell’Admin Console di Adobe. I clienti devono utilizzare le API di gestione utenti di adobe.io per ottenere in massa informazioni sui gruppi di autorizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data creazione account </p> </td> 
   <td colname="col2"> <p>Le informazioni sulla data di creazione dell'account non sono più supportate né negli Strumenti di amministrazione di Analytics né nell'Admin Console di Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-mail di massa </p> </td> 
   <td colname="col2"> <p>Le e-mail di massa agli utenti non saranno più supportate né nell'Admin Console di Analytics né nell'Admin Console di Adobe. I clienti possono esportare in massa gli indirizzi e-mail dei propri utenti da Adobe Admin Console e inviare un messaggio e-mail utilizzando il client e-mail desiderato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come avvisare gli utenti della migrazione {#section-f3b25f672a3a4d03b0559656fd99d20a}

Potresti voler comunicare proattivamente questo piano di migrazione agli utenti correnti. Ecco un modello che puoi personalizzare per inviare a tutti i tuoi utenti Analytics:

Per inviare un messaggio e-mail a tutti gli utenti, passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > [Invia e-mail agli utenti](https://marketing.adobe.com/resources/help/en_US/reference/t_email_users.html).

**Oggetto:** Disponibile a breve: nuovo metodo di accesso per Adobe Analytics e Adobe Experience Cloud.

**Corpo del messaggio:** A tutti gli utenti di Adobe Analytics:

La nostra società inizierà la migrazione di tutti gli account Adobe Analytics da [!DNL https://my.omniture.com/login/] ad Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Con questa migrazione, il tuo account Adobe Analytics verrà aggiornato per abilitare l&#39;accesso ad Analytics tramite Adobe Experience Cloud. Anche se cambierà il metodo di accesso ad Analytics, tutte le autorizzazioni esistenti per le suite di rapporti e gli strumenti verranno mantenute.

**Prossime operazioni:** inizieremo a eseguire la migrazione degli utenti a partire dal giorno **INSERISCI DATA**. Riceverete un messaggio di benvenuto con il nuovo login indirizzato all&#39;ID e-mail indicato nel vostro account Analytics. Se non avete impostato un [Adobe ID](https://helpx.adobe.com/it/x-productkb/global/adobe-id-account-change.html) collegato al vostro indirizzo e-mail, vi verrà chiesto di impostare un account.

**Risorse utili:**

[Accesso e gestione delle impostazioni del profilo](https://marketing.adobe.com/resources/help/it_IT/mcloud/getting-started-experience-cloud.html).

[Cloud, servizi di base e soluzioni](https://marketing.adobe.com/resources/help/it_IT/mcloud/solutions_capability_names.html) in Experience Cloud

Per domande o dubbi, contattate i vostri amministratori di Analytics.

Migliore,

Amministratore di Analytics
