---
description: Informazioni necessarie sulla migrazione degli ID utente di Analytics all’Admin Console in Adobe Experience Cloud.
title: Migrazione degli utenti di Analytics all’Admin Console
uuid: 7d020713-693b-4945-aa52-3669a631aacb
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '3127'
ht-degree: 98%

---


# Migrazione degli utenti di Analytics all’Admin Console {#analytics-user-migration-to-the-admin-console}

Informazioni necessarie sulla migrazione degli ID utente di Analytics all’Admin Console in Adobe Experience Cloud.

Per assistenza generica sugli argomenti relativi all’Admin Console (non correlati alla migrazione di Analytics), vedi la [Guida utente di Admin Console](https://helpx.adobe.com/it/enterprise/administering/user-guide.html).

Dopo la migrazione, puoi [gestire gli utenti e i prodotti Experience Cloud](https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html) nella Admin Console.

## Cos’è la migrazione degli ID utente di Analytics? {#section-adbe49aba10c4e62afa836a97894107c}

La migrazione degli ID utente di Analytics permette agli amministratori di trasferire facilmente gli account utente in Gestione utenti di Analytics ad Adobe Admin Console. Dopo la migrazione, gli utenti potranno accedere alle soluzioni e ai servizi di base disponibili in Experience Cloud. La migrazione verrà resa disponibile ai clienti in più fasi.

I benefici dell’utilizzo della Admin Console includono:

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
   <td colname="col2"> <p>Gli utenti di Analytics possono accedere a Experience Cloud e a tutte le soluzioni tramite il proprio Adobe ID o Enterprise ID. Questo accesso permette di utilizzare i servizi core e le soluzioni integrate in Experience Cloud. </p> <p>Dopo la migrazione, gli utenti che tenteranno di accedere con i metodi legacy (<span class="filepath">my.omniture.com</span> e <span class="filepath">sc.omniture.com</span>) verranno reindirizzati su <span class="filepath">experiencecloud.adobe.com</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestione delle autorizzazioni e delle identità utente </p> </td> 
   <td colname="col2"> <p>Gli amministratori di Analytics possono gestire gli utenti e le autorizzazioni esclusivamente nell’<a href="http://adminconsole.adobe.com/enterprise/"> Admin Console</a> (http://adminconsole.adobe.com/enterprise/). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gestire i prodotti e i servizi core </p> </td> 
   <td colname="col2"> 
    <ul id="ul_01043FEF271E4B27BF34980D629D1932"> 
     <li id="li_DC31AE8BAAB843F39A7CC9EB047265D5">Invitare nuovi utenti </li> 
     <li id="li_73724DD7D79E41F8A1D58C74E37674BA">Creare profili di prodotto </li> 
     <li id="li_7E75FC68E0F84873A9A211D2707B6DE7">Concedere agli utenti l’autorizzazione a prodotti e servizi specifici </li> 
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
   <th colname="col1" class="entry"> Domanda/attività </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Sono un amministratore di Analytics e ho ricevuto l’e-mail di notifica della migrazione. Cosa devo fare innanzitutto? </p> </td> 
   <td colname="col2"> <p>Verifica di avere un Adobe ID e di poter accedere all’<a href="https://adminconsole.adobe.com/enterprise/"> Admin Console di Experience Cloud</a>. </p> <p>In caso contrario, contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. Contatta prima il tuo amministratore di prodotto o di sistema che può invitarti nell’organizzazione appropriata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integrazioni di AEM con Analytics </p> </td> 
   <td colname="col2"> <p> Gli utenti di AEM con una integrazione ad Analytics dovranno modificare la propria configurazione per utilizzare il segreto condiviso di Analytics, anziché la password. </p> <p> È opportuno farlo prima che la migrazione sia abilitata. Una volta disabilitata la migrazione, la password originariamente configurata non sarà più valida. </p> <p><b>Per ottenere il segreto condiviso in Analytics</b> </p> <p> Il segreto condiviso può essere ottenuto da Analytics (<span class="uicontrol"> Analytics</span> &gt; <span class="uicontrol"> Gestione utenti</span>) ed è differente per ciascun utente. </p> <p><b>Per aggiornare la tua configurazione di AEM con il segreto condiviso</b> </p> <p>Consulta <a href="https://helpx.adobe.com/it/experience-manager/6-3/sites/administering/using/adobeanalytics-connect.html"> Collegamento ad Adobe Analytics e creazione di framework</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiornare Report Builder </p> </td> 
   <td colname="col2"> <p> <p>Importante: è necessario aggiornare l’installazione di <a href="https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/t-install-arb.html"> Report Builder</a> all’ultima versione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quando inizia la migrazione? </p> </td> 
   <td colname="col2"> <p>Adobe invierà agli amministratori di Analytics un’e-mail con la data di inizio della migrazione. </p> <p>Le migrazioni all’Admin Console verranno eseguite a scaglioni. Il giorno della migrazione, Adobe avvisa gli amministratori di Analytics e garantisce loro accesso allo strumento di migrazione. Se la società di accesso soddisfa i criteri definiti per ciascuno scaglione di migrazione, Adobe esegue queste azioni: </p> 
    <ul id="ul_D7DDC62A08AB4407B122985EDEA6ABD1"> 
     <li id="li_BA0AD50DCDC14C90ADD513DEF6F78180">Imposta le date di inizio e di fine per la migrazione della società. </li> 
     <li id="li_C048A5C64FAA46C4BB41EF24F1CEDF62">Invia un’e-mail di notifica agli attuali amministratori di Analytics della società circa 30 giorni prima della migrazione. </li> 
     <li id="li_476265B24CE2404B995201170C75D674">Mostra una notifica all’interno del prodotto per comunicare agli amministratori la data di inizio della migrazione. </li> 
    </ul> <p> Il giorno della migrazione, i tuoi gruppi di autorizzazioni precedenti vengono automaticamente copiati nell’Admin Console. Non potrai più invitare nuovi utenti o creare nuovi gruppi in Strumenti di amministrazione di Analytics. </p> <p>Dopo la migrazione: </p> 
    <ul id="ul_4639963EB08F407F8C18ACE2B3D30223"> 
     <li id="li_7F24A3FC900146C3B2E988D399C859EA">Gli amministratori utilizzeranno l’Admin Console per gestire i propri utenti e le autorizzazioni di Analytics. (Non potrai più utilizzare l’interfaccia di gestione degli utenti in Analytics &gt; Amministratore &gt; Gestione utente.) </li> 
     <li id="li_5B5234D4F94A4B96A8920F6A5831A64C">Gli utenti accederanno ad Analytics con il proprio Adobe ID o Enterprise ID mediante Experience Cloud anziché tramite <span class="filepath"> my.omniture.com</span>. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa succede nella data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Alle 10:00 UTC della data di inizio della migrazione: </p> 
    <ul id="ul_25D1DBDF5C804D048E741F31550FF5F3"> 
     <li id="li_418476105FE341229CE146E730AAB33D">I tuoi gruppi di autorizzazioni esistenti in Analytics verranno automaticamente replicati nell’Admin Console come profili di prodotto, incluse la loro descrizione e le autorizzazioni granulari nelle suite di rapporti, nelle metriche, nelle dimensioni, in Analytics e negli strumenti delle suite di rapporti. </li> 
     <li id="li_412F88C454B0455A8F3BC8016226855C">Se qualcuno dei tuoi utenti di Analytics attuali è stato creato nell’Admin Console e dispone quindi di un Adobe/Enterprise ID collegato, verrà aggiunto ai profili di prodotto appropriati nell’Admin Console. </li> 
     <li id="li_8A05137EC05C4FD5910E73FE58300DCB">La sezione Gestione utente della scheda Amministratore in Analytics verrà impostata per la <span class="term"> sola lettura</span>. Potrai creare nuovi utenti o gruppi di autorizzazioni solo nell’Admin Console. Per ulteriori informazioni, vedi <a href="/help/admin/user-management2/user-migration/c-migration-tool.md#section-928ffba27a0446e0af575b720434ef56"> Funzioni di Analytics non supportate nell’Admin Console</a>. </li> 
     <li id="li_2742DE69E9B547198A58E1F33E908361">In quanto amministratore, avrai accesso allo strumento di <a href="https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/user-management/migrate-users/t-migrate-users.html">Migrazione degli ID utente</a>. Inoltre, all’interno del prodotto verrà visualizzata una notifica con la data di fine della migrazione (che generalmente corrisponde al sessantesimo giorno dall’inizio del processo) e con i collegamenti al contenuto della guida e alle domande frequenti. </li> 
     <li id="li_095D42E3A3544FC59A60A8C8F94C971B">Avrai accesso alla scheda Autorizzazioni dell’Admin Console da cui puoi creare i profili di prodotto con tutte le opzioni granulari che ti sono familiari in Analytics. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Come si effettua la migrazione degli ID utente? </p> </td> 
   <td colname="col2"> <p> Fai clic su <a href="/help/admin/user-management2/user-migration/t-migrate-users.md#task-f3355f3b14a340feae58cfa04c0ba1c9"> Esegui migrazione ID utente</a> nella sezione Gestione utente della pagina Amministratore. Utilizza lo strumento per aggiungere utenti ai profili di prodotto nell’Admin Console (replicati dai gruppi di autorizzazioni in Analytics). Puoi eseguire la migrazione degli ID utente con le tempistiche che preferisci. </p> <p>Sono richiesti i privilegi di amministratore. Non è possibile invertire il processo di migrazione dopo il suo completamento. </p> <p>Alla data di fine della migrazione, l’accesso mediante <span class="filepath"> my.omniture.com</span> verrà disattivato per gli utenti che fanno parte della tua società di accesso. Gli utenti (inclusi quelli per cui non è stata ancora eseguita la migrazione) verranno reindirizzati per l’accesso tramite il nuovo URL di Experience Cloud: <span class="filepath">experiencecloud.adobe.com</span>. </p> <p>Nota: Adobe consiglia di eseguire un controllo degli utenti e dei gruppi prima di eseguire la migrazione. Elimina gli account obsoleti e inutilizzati o gli account che non devono avere più accesso al prodotto (ad esempio, gli ex dipendenti). </p> <p>Argomento correlato: <a href="/help/admin/user-management2/user-migration/migrate-enterprise.md"> Eseguire la migrazione degli account utente di Analytics per Enterprise e Federated ID</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La migrazione influisce sull’implementazione di Analytics o sulla modalità di raccolta dei dati? </p> </td> 
   <td colname="col2"> <p>No. </p> <p>Lo strumento di migrazione serve a semplificare la transizione delle autorizzazioni e degli ID utente dal sistema di gestione degli utenti di Analytics all’<a href="https://adminconsole.adobe.com/enterprise/"> Admin Console di Experience Cloud</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quanto tempo è necessario per completare la migrazione? </p> </td> 
   <td colname="col2"> <p>Tutti gli amministratori correnti di Analytics riceveranno un’e-mail di notifica quattro settimane prima dell’inizio della migrazione. La data di inizio effettiva verrà visualizzata nell’interfaccia di Analytics. </p> <p>Dopo l’inizio della migrazione, gli amministratori hanno a disposizione 60 giorni per completare il processo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso accelerare la migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Tuttavia, Adobe consiglia di eseguire queste azioni prima dell’inizio della migrazione: </p> 
    <ul id="ul_52C7EC44A5534975BFD7A6F37A829C25"> 
     <li id="li_8CFFF72877E8456DAC3241143AD648AD">Verifica di essere un amministratore di prodotto di Analytics nell’Admin Console. </li> 
     <li id="li_25DAA8D1EEDA45A0B5B59472BD8896C4">Comunica alla tua base di utenti che la loro esperienza di accesso cambierà dopo l’inizio della migrazione. </li> 
     <li id="li_5B50F942F6A8483FAFA500AFF428702C">Controlla i tuoi utenti e le autorizzazioni correnti ed esegui attività di pulizia. </li> 
    </ul> <p>Per accelerare la migrazione, contatta il tuo Customer Success Manager presso l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a> e invia una richiesta per anticipare la data di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Sono un amministratore di Analytics, ma non ho accesso all’Admin Console. A chi posso rivolgermi per ottenere l’accesso? </p> </td> 
   <td colname="col2"> <p>Qualsiasi amministratore di prodotto o di sistema che ha accesso all’Admin Console della tua organizzazione può concederti l’accesso. Se non sai chi dispone dei privilegi di amministratore nella console all’interno della tua organizzazione, contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso posticipare la data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Contatta l’<a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"> Assistenza clienti di Adobe</a>. </p><p>Di seguito trovi una descrizione delle modifiche apportate alla gestione corrente degli utenti e delle autorizzazioni di Analytics alla data di inizio. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Adesso che la mia società sta eseguendo la migrazione all’Admin Console, dove posso creare nuovi utenti e gruppi di autorizzazioni prima della data di inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>Prima della data di inizio della migrazione, puoi creare gli utenti nell’Admin Console o in Analytics &gt; Gestione utente. </p> <p>Dopo l’inizio della migrazione, puoi creare utenti e gruppi di autorizzazioni solo nell’Admin Console. </p><p>Per ulteriori informazioni su cosa accade alla data di inizio della migrazione, consulta la sezione Migrazione (in basso. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Quando posso implementare il Single Sign-On utilizzando i Federated ID? </p> </td> 
   <td colname="col2"> <p> Presto nell’Admin Console sarà disponibile uno strumento che ti permetterà di modificare il tipo di ID da Adobe ID a Federated ID. Durante la migrazione non puoi trasferire gli utenti come Federated ID. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cosa bisogna sapere durante la migrazione (FAQ) {#section-d394524aa6d046d79025bbd7499792bc}

Informazioni importanti sul processo di migrazione e sull’impatto sulla gestione degli utenti correnti.

<table id="table_0E37BB1DEA6143F0B5F4E861FCFA7189"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>In che modo vengono replicati i gruppi di autorizzazioni nell’Admin Console? Cosa succede ai miei utenti? </p> </td> 
   <td colname="col2"> <p>Nell’Admin Console, un gruppo di Analytics migrato viene chiamato <i>profilo di prodotto</i>. Le impostazioni delle autorizzazioni per il gruppo originale vengono mantenute con la migrazione. Tuttavia, per gli utenti assegnati al gruppo non viene eseguita la migrazione. Quando un utente appartenente a tale gruppo viene trasferito tramite lo strumento di migrazione, allora viene assegnato a quel profilo di prodotto. </p> <p>Ad esempio, il gruppo di autorizzazioni West Coast Operations che ha autorizzato i propri membri a Report Builder e ad Analysis Workspace (con determinate suite di rapporti, metriche e dimensioni) diventerà il profilo di prodotto West Coast Operations. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso delegare la procedura di migrazione a un altro amministratore? </p> </td> 
   <td colname="col2"> <p>Dopo che la migrazione ha avuto inizio, qualsiasi amministratore che accede all’istanza di Analytics mediante Experience Cloud può utilizzare lo strumento di migrazione per iniziare (o continuare) la migrazione degli utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso aggiornare l’iscrizione a un gruppo di autorizzazioni per gli utenti di cui non è stata eseguita la migrazione? </p> </td> 
   <td colname="col2"> <p>Sì. Puoi modificare l’iscrizione al gruppo degli utenti non trasferiti dalla sezione Gestione utente di Analytics. </p><p>In attesa di ulteriori chiarimenti da parte di Ashok. </p>
   </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso creare gruppi di autorizzazioni e utenti in Analytics dopo l’inizio della migrazione e poi utilizzare lo strumento di migrazione per spostarli nell’Admin Console? </p> </td> 
   <td colname="col2"> <p> No. Dopo l’inizio della migrazione, tutti i nuovi utenti e gruppi di autorizzazioni (chiamati profili di prodotto nell’Admin Console) devono essere creati nell’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli utenti che trasferisco mediante lo strumento di migrazione avranno le stesse autorizzazioni che avevano in Analytics? </p> </td> 
   <td colname="col2"> <p>Sì. Agli utenti trasferiti con lo strumento verranno assegnate le autorizzazioni di cui disponevano in Analytics. Inoltre, continueranno ad avere accesso alle proprie risorse di Analytics (come segmenti, progetti, metriche calcolate e così via) quando accedono ad Analytics mediante Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli utenti che trasferisco nell’Admin Console continueranno ad avere accesso ad Analytics attraverso <span class="filepath"> my.omniture.com</span>? </p> </td> 
   <td colname="col2"> <p>Sì. Gli utenti trasferiti continueranno ad avere accesso ad Analytics utilizzando il nome utente e la password esistenti mediante <span class="filepath"> my.omniture.com</span> fino alla data di fine della migrazione, a meno che tu non disattivi l’accesso legacy tramite lo strumento di migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Due o più utenti della mia organizzazione hanno lo stesso ID e-mail nel record di Analytics. Cosa succede se li trasferisco? </p> </td> 
   <td colname="col2"> <p>Poiché nell’Admin Console gli account utente possono avere un ID e-mail univoco, ti verrà mostrato un errore “ID e-mail duplicato” quando tenti di eseguire la migrazione di più di uno di questi utenti. Puoi aggiornare gli ID e-mail degli utenti non trasferiti nella sezione Gestione utente (legacy) prima di riprovare a eseguire la migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Cosa devo fare dopo aver eseguito la migrazione dei miei utenti? </p> </td> 
   <td colname="col2"> <p>Disattiva l’accesso legacy tramite <span class="filepath"> my.omniture.com</span>. Non potrai disattivare l’accesso legacy se non hai trasferito gli utenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posso monitorare il processo di migrazione? </p> </td> 
   <td colname="col2"> <p>Lo strumento di migrazione include una dashboard che mostra il numero di utenti di cui è stata eseguita la migrazione e il numero di utenti per cui è stato disattivato l’accesso legacy. </p> <p> Idealmente, avrai completato la migrazione all’Admin Console della tua società di accesso quando per il 100% dei tuoi utenti sarà stata completata la migrazione e sarà stato disattivato l’accesso legacy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Devo gestire le autorizzazioni e gli utenti durante il processo di migrazione. Quale strumento posso usare? </p> </td> 
   <td colname="col2"> <p>Dopo l’inizio della migrazione, devi utilizzare l’Admin Console per creare e gestire nuovi utenti e profili di prodotto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Come vengono avvisati i miei utenti quando ne eseguo la migrazione tramite lo strumento? </p> </td> 
   <td colname="col2"> <p>Riceveranno un’e-mail di benvenuto al proprio ID e-mail indicato nel record utente di Analytics, che li informa del nuovo metodo di accesso ad Analytics mediante Experience Cloud. Se non dispongono di un Adobe ID, verranno invitati a crearne uno in modo da poter accedere alla soluzione utilizzando il proprio Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Per trasferire i miei utenti, posso usare le API invece dello strumento di migrazione? </p> </td> 
   <td colname="col2"> <p>No. Devi utilizzare lo strumento di migrazione affinché tutti i tuoi utenti esistenti siano trasferiti nell’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Quali funzioni di gestione degli utenti di Analytics non sono disponibili nell’Admin Console? </p> </td> 
   <td colname="col2"> 
    <ul id="ul_3F3747D4C1D3420699F7D28EC0CA1AA0"> 
     <li id="li_BD943B3245FF47E7A0DDA6107EA1EF89">Trasferimento risorse </li> 
     <li id="li_2DF7004D67ED4C6CB40461EEFB038A5A">Scadenza utenti </li> 
     <li id="li_980E3F5B98F344A492B0EBAD7F1DA60C">Registri utenti </li> 
    </ul> <p>Queste funzioni rimarranno disponibili nella sezione Gestione utente di Analytics. </p> <p>Per ulteriori informazioni, vedi <a href="/help/admin/user-management2/user-migration/c-migration-tool.md"> Funzioni di Analytics non supportate nell’Admin Console</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Abbiamo creato diverse configurazioni nell’Admin Console e le abbiamo mappate con i gruppi di autorizzazioni di Analytics. Cosa succederà a queste configurazioni dopo l’inizio della migrazione? </p> </td> 
   <td colname="col2"> <p>I gruppi di autorizzazioni di Analytics vengono ricreati nell’Admin Console come profili di prodotto, esattamente come per tutti gli altri tuoi gruppi. Ciò significa che vedrai due profili di prodotto nella console che hanno sostanzialmente le stesse autorizzazioni duplicate. Puoi eliminare i profili di prodotto duplicati dall’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qual è il passaggio successivo alla migrazione di un utente? </p> </td> 
   <td colname="col2"> <p>Dopo avere trasferito un utente o un insieme di utenti, devi disattivare il suo accesso legacy mediante <span class="filepath"> my.omniture.com</span>. A tale scopo, seleziona l’utente nello strumento di migrazione e fai clic sull’opzione contestuale “Disattiva accesso legacy” mostrata nella parte superiore dello schermo. Tieni presente che questa opzione è visibile soltanto quando selezioni un utente o un insieme di utenti che sono stati tutti trasferiti nell’Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cosa succede nella data di fine della migrazione? </p> </td> 
   <td colname="col2"> <p>Dopo la data di fine della migrazione (60 giorni dall’inizio del processo), tutti gli utenti all’interno della tua società di accesso vengono reindirizzati sulla pagina di accesso di Experience Cloud per accedere utilizzando i propri Adobe ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non sono riuscito a trasferire tutti i miei utenti entro la data di fine della migrazione. Gli utenti di cui non ho eseguito la migrazione perderanno l’accesso ad Analytics? </p> </td> 
   <td colname="col2"> <p>Gli utenti che non sono stati trasferiti entro la data di fine verranno reindirizzati alla pagina di accesso di Experience Cloud (experiencecloud.adobe.com) e non potranno accedere ad Analytics. Tuttavia, continuerai ad avere accesso allo strumento di migrazione per trovare e trasferire questi utenti e ripristinare il loro accesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cosa bisogna sapere dopo la migrazione (FAQ) {#section-9681baa01b8c41cdb9659b73b70b50ff}

<table id="table_F48CC9DFE3424AC9AD76A16882701C8F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda/problema </th> 
   <th colname="col2" class="entry"> Risposte </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Eliminare gli utenti dall’Admin Console </p> </td> 
   <td colname="col2"> <p> In Analytics, un utente eliminato è impostato come <span class="term"> scaduto</span> ma l’account continua a esistere. La conservazione dell’account consente il trasferimento di risorse, ad esempio segmenti, metriche calcolate, rapporti pianificati, progetti e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scadenze account </p> </td> 
   <td colname="col2"> <p> Puoi impostare manualmente una data di scadenza dell’account in Analytics mediante gli Strumenti di amministrazione. Una volta raggiunta la data di scadenza, l’utente non sarà in grado di accedere ad Analytics, ma il suo effettivo account utente Experience Cloud (ad esempio, Adobe ID, Enterprise ID, Federated ID, ecc.) non scade. L’utente potrà comunque accedere a Experience Cloud, ma non potrà più fare clic su Analytics. </p> </td> 
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
   <th colname="col1" class="entry"> Domanda/problema </th> 
   <th colname="col2" class="entry"> Risposte </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Accesso come </p> </td> 
   <td colname="col2"> <p> Gli amministratori che eseguono la migrazione nell’Admin Console non potranno più utilizzare la funzione “Accesso come” per accedere agli account utente non amministratore che hanno trasferito nell’Admin Console. Questa funzione è obsoleta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scadenza utenti e trasferimento risorse </p> </td> 
   <td colname="col2"> <p> L’Admin Console non supporta la scadenza utenti e il trasferimento risorse. Gli amministratori utilizzeranno la sezione Risorse e utenti di Analytics in Strumenti di amministrazione per usufruire di entrambe le funzioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ultimo accesso </p> </td> 
   <td colname="col2"> <p> I dettagli relativi alla data e all’ora dell’ultimo accesso degli utenti saranno disponibili al collegamento Risorse e utenti di Analytics, non nell’Admin Console. La data dell’ultimo accesso in Analytics si riferisce alla data in cui gli utenti hanno eseguito l’accesso ad Analytics mediante Experience Cloud e non alla data/ora in cui hanno eseguito l’accesso a Experience Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>API di gestione utenti <a href="https://helpx.adobe.com/it/enterprise/help/identity.html"> Tipi di identità supportati da Adobe</a> </p> </td> 
   <td colname="col2"> <p> Gli amministratori che eseguono la migrazione all’Admin Console devono configurare <a href="https://www.adobe.io/apis/cloudplatform/usermanagement/docs/gettingstarted.html">le API di gestione utenti</a> offerte in Adobe I/O per l’accesso programmatico agli account utente nell’Admin Console. </p> <p>Le API delle autorizzazioni di Analytics vengono disattivate quando l’utente è abilitato per la migrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Credenziali per i servizi Web </p> </td> 
   <td colname="col2"> <p> Le credenziali per i servizi Web degli utenti (e i relativi segreti condivisi) non saranno disponibili nell’Admin Console e vi si potrà accedere facendo clic sull’utente specifico dalla sezione Risorse e utenti di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Single Sign-On </p> </td> 
   <td colname="col2"> <p> Le configurazioni del Single Sign-On in Analytics verranno rimosse al completamento della migrazione. Rimarranno invece attive durante il processo di migrazione. I clienti che utilizzano il Single Sign-On in Analytics devono eseguire l’upgrade all’<a href="https://helpx.adobe.com/it/enterprise/help/identity.html"> Adobe Federated ID</a>. </p> <p>Analytics consiglia di eseguire la migrazione degli utenti innanzitutto come Adobe ID, in modo da creare facilmente gli account Experience Cloud, e successivamente di convertire tali account in utenti con accesso singolo con Federated ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Download dei gruppi di autorizzazioni </p> </td> 
   <td colname="col2"> <p> Non sarà più possibile scaricare i dati dei gruppi di autorizzazioni in Strumenti di amministrazione di Analytics o nell’Admin Console di Adobe. I clienti dovranno utilizzare le API di gestione utenti di adobe.io per scaricare in massa i dati dei gruppi di autorizzazioni. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data creazione account </p> </td> 
   <td colname="col2"> <p>La data di creazione dell’account non sarà più indicata in Strumenti di amministrazione di Analytics o nell’Admin Console di Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>E-mail di massa </p> </td> 
   <td colname="col2"> <p>Non sarà più possibile inviare e-mail di massa agli utenti né in Strumenti di amministrazione di Analytics né nell’Admin Console di Adobe. I clienti possono esportare in massa gli indirizzi e-mail dei propri utenti dall’Admin Console di Adobe e inviare un’e-mail utilizzando il client di posta elettronica desiderato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Come avvisare gli utenti della migrazione {#section-f3b25f672a3a4d03b0559656fd99d20a}

Potresti voler comunicare proattivamente questo piano di migrazione ai tuoi utenti correnti. Qui puoi trovare un modello personalizzabile da inviare a tutti i tuoi utenti di Analytics:

Per inviare un messaggio e-mail a tutti gli utenti, passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL User Management]** > [Invia e-mail agli utenti](https://docs.adobe.com/help/en/analytics/admin/user-product-management/t-email-users.html).

**Oggetto:** Disponibile a breve: nuovo metodo di accesso per Adobe Analytics e Adobe Experience Cloud.

**Corpo del messaggio:** A tutti gli utenti di Adobe Analytics:

La nostra società inizierà la migrazione di tutti gli account Adobe Analytics da [!DNL https://my.omniture.com/login/] ad Adobe Experience Cloud ([experiencecloud.adobe.com](http://experiencecloud.adobe.com/)). Con questa migrazione, il vostro account Adobe Analytics verrà aggiornato per poter accedere ad Analytics mediante Adobe Experience Cloud. Anche se cambierà il metodo di accesso ad Analytics, tutte le vostre autorizzazioni esistenti per gli strumenti e le suite di rapporti verranno preservate.

**Prossime operazioni:** inizieremo a eseguire la migrazione degli utenti a partire dal giorno **INSERISCI DATA**. Riceverete un messaggio di benvenuto con le nuove credenziali all’ID e-mail indicato nel vostro account Analytics. Se non avete collegato un [Adobe ID](https://helpx.adobe.com/it/x-productkb/global/adobe-id-account-change.html) al vostro indirizzo e-mail, vi verrà chiesto di configurare un account.

**Risorse utili:**

[Accesso e gestione delle impostazioni del profilo](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/getting-started-experience-cloud.html).

Per eventuali domande o dubbi, contattate i vostri amministratori di Analytics.

Cordiali saluti,

Amministratore di Analytics
