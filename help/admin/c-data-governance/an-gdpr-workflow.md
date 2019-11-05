---
description: nulle
seo-description: nulle
seo-title: Flusso di lavoro sulla privacy dei dati di Adobe Analytics
title: Flusso di lavoro sulla privacy dei dati di Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Flusso di lavoro sulla privacy dei dati di Adobe Analytics

Benvenuti alla preparazione di Adobe Analytics per la privacy dei dati. Questo flusso di lavoro delinea la procedura da seguire per preparare l’implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base alla Privacy dei dati.

<!--
<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Task Description </th> 
   <th colname="col3" class="entry"> Links to Instructions and More Information </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Ensure that any of your report suites that might contain Data Privacy-relevant data are mapped to your Experience Cloud (or IMS) organization. </p> <p>Data Privacy requests are submitted using an Experience Cloud Organization and will be applied to all report suites claimed by that Organization. Requests will not apply to report suites not mapped to that Organization, even if they are part of your login company. </p> </td> 
   <td colname="col3"> <p>Refer to <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html"> Map report suites to an organization</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Set your data retention policy. </p> </td> 
   <td colname="col3"> <p>A data retention policy needs to be in place in order for Adobe to service Data Privacy data access/delete requests. </p> <p>For more information, see this <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html"> Analytics Data Retention FAQ</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Familiarize yourself with DULE/Data Privacy labels, Adobe Analytics IDs, namespaces, and ID expansion. </p> </td> 
   <td colname="col3"> <p> Read these topics in this documentation set: 
     <ul> 
      <li><a href="/help/admin/c-data-governance/gdpr-labels.md"> Data Privacy Labels for Analytics Variables</a> </li> 
      <li><a href="/help/admin/c-data-governance/gdpr-analytics-ids.md"> Labeling Best Practices</a>--> </li>
    &lt;/ul&gt; &lt;/p&gt; &lt;/td&gt;
</tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti. </p> <p>Nota: ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. </p> </td> 
   <td colname="col3"> <p> Segui le istruzioni riportate in <a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md">Etichettare i dati della suite di rapporti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Collegati all’API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione. </p> </td> 
   <td colname="col3"> <p>In qualità di cliente di Adobe Analytics, puoi inviare singole richieste di Privacy dei dati per accedere e cancellare i dati di un cliente, richiamando l’<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html">API Privacy dei dati di Adobe Experience Cloud</a>. </p> <p>Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione <a href="/help/admin/c-data-governance/gdpr-analytics-ids.md">Tecniche di etichettatura consigliate</a>) insieme ai rispettivi ID dei namespace (ID dell’origine dati). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti. </p> </td> 
   <td colname="col3"> <p>Segui le istruzioni riportate in <a href="/help/admin/c-data-governance/gdpr-view-settings.md">Visualizzare impostazioni di governance dei dati della suite di rapporti</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
--&gt;

| Descrizione dell’attività | Collegamenti alle istruzioni e ad altre informazioni |
|--- |--- |
| **Passaggio 1**: assicurati che tutte le suite di rapporti che potrebbero contenere dati relativi alla Privacy dei dati siano state mappate nell’organizzazione Experience Cloud (o IMS).  Le richieste di Privacy dei dati vengono inviate usando un’organizzazione Experience Cloud e verranno applicate a tutte le suite di rapporti richieste dall’organizzazione. Le richieste non verranno applicate alle suite di rapporti che non sono state mappate nell’organizzazione, anche se fanno parte della società di accesso. | Consulta [Mappatura di suite di rapporti per un’organizzazione.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Passaggio 2**: Imposta i criteri di conservazione dei dati. | È necessario impostare i criteri di conservazione dei dati affinché Adobe possa soddisfare le richieste di accesso o di cancellazione dei dati in base alla Privacy dei dati.  Per altre informazioni consulta le [Domande frequenti sulla conservazione dei dati in Analytics.](/help/technotes/data-retention.md) |
| **Passaggio 3**: acquisisci familiarità con le etichette DULE/Privacy dei dati, gli ID di Adobe Analytics, i namespace e l’espansione dell’ID. | Leggi questi argomenti nella presente documentazione:<ul><li>[Etichette Privacy dei dati per le variabili di Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md)</li></ul> |
| **Passaggio 4:** assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.  Nota: ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. | Segui le istruzioni riportate in [Etichettare i dati della suite di rapporti.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md) |
| **Passaggio 5**: collegati all’API Privacy dei dati di Adobe e invia le richieste di accesso e cancellazione. | In qualità di cliente di Adobe Analytics, puoi inviare singole richieste di Privacy dei dati per accedere e cancellare i dati di un cliente, richiamando l’[API Privacy dei dati di Adobe Experience Cloud.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md)) insieme ai rispettivi ID dei namespace (ID dell’origine dati). |
| **Passaggio 6**: visualizza e gestisci le impostazioni di Privacy dei dati della suite di rapporti. | Segui le istruzioni riportate in [Visualizzare impostazioni di governance dei dati della suite di rapporti.](/help/admin/c-data-governance/gdpr-view-settings.md) |
