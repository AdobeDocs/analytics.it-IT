---
description: nulle
seo-description: nulle
seo-title: Flusso di lavoro sulla privacy dei dati di Adobe Analytics
title: Flusso di lavoro sulla privacy dei dati di Adobe Analytics
uuid: f24e8be3-8b5c-409b-ad6b-770198ae2549
translation-type: tm+mt
source-git-commit: 45e3330adb562ec795d287ae1c1fa6b03a2b2a31

---


# Flusso di lavoro sulla privacy dei dati di Adobe Analytics

Benvenuti in Adobe Analytics e la privacy dei dati disponibili! Questo flusso di lavoro illustra i passaggi necessari per rendere l'implementazione di Adobe Analytics pronta a supportare l'accesso alla privacy dei dati e i diritti di eliminazione degli interessati.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Descrizione dell’attività </th> 
   <th colname="col3" class="entry"> Collegamenti alle istruzioni e ad altre informazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" /> Assicurati che qualsiasi suite di rapporti che possa contenere dati rilevanti per la privacy dei dati sia mappata sulla tua organizzazione Experience Cloud (o IMS). </p> <p>Le richieste di privacy dei dati vengono inviate tramite un’organizzazione Experience Cloud e verranno applicate a tutte le suite di rapporti richieste da tale organizzazione. Le richieste non verranno applicate alle suite di rapporti che non sono state mappate nell'organizzazione, anche se fanno parte della società di accesso. </p> </td> 
   <td colname="col3"> <p>Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Mappatura di suite di rapporti per un’organizzazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Imposta i criteri di conservazione dei dati. </p> </td> 
   <td colname="col3"> <p>Affinché Adobe possa soddisfare le richieste di accesso/eliminazione dei dati sulla privacy dei dati, è necessario che sia in vigore un criterio di conservazione dei dati. </p> <p>Per altre informazioni consulta le <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Domande frequenti sulla conservazione dei dati in Analytics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Acquisisci familiarità con etichette DULE/Data Privacy, ID Adobe Analytics, spazi dei nomi ed espansione ID. </p> </td> 
   <td colname="col3"> <p> Leggi questi argomenti nella presente documentazione: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><!--<a href="/help/admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Data Privacy Labels for Analytics Variables</a>--> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Voce di elenco </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>--> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti. </p> <p>Nota: ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti Web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. </p> </td> 
   <td colname="col3"> <p> Segui le istruzioni in <!--<a href="/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Label Report Suite Data</a>-->. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Connettiti all’API Adobe Data Privacy e invia richieste di accesso ed eliminazione. </p> </td> 
   <td colname="col3"> <p>As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the <a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external"> Adobe Experience Cloud Data Privacy API</a>. </p> <p>You can submit any Analytics identifiers (as described in the section <!--<a href="/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Labeling Best Practices</a>-->) in the requests along with their respective namespace IDs (data source IDs). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Visualizza e gestisci le impostazioni Privacy dei dati della suite di rapporti. </p> </td> 
   <td colname="col3"> <p>Segui le istruzioni in <!--<a href="/help/admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> View Report Suite's Data Governance Settings</a>-->. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Descrizione dell’attività | Collegamenti alle istruzioni e ad altre informazioni |
|--- |--- |
| **Passaggio 1**: Assicurati che qualsiasi suite di rapporti che possa contenere dati rilevanti per la privacy dei dati sia mappata sulla tua organizzazione Experience Cloud (o IMS).  Le richieste di privacy dei dati vengono inviate tramite un’organizzazione Experience Cloud e verranno applicate a tutte le suite di rapporti richieste da tale organizzazione. Le richieste non verranno applicate alle suite di rapporti che non sono state mappate nell'organizzazione, anche se fanno parte della società di accesso. | Consulta [Mappatura di suite di rapporti per un’organizzazione.](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html) |
| **Passaggio 2:** imposta i criteri di conservazione dei dati. | Affinché Adobe possa soddisfare le richieste di accesso/eliminazione dei dati sulla privacy dei dati, è necessario che sia in vigore un criterio di conservazione dei dati.  Per altre informazioni consulta le [Domande frequenti sulla conservazione dei dati in Analytics.](/help/technotes/data-retention.md) |
| **Passaggio 3**: Acquisisci familiarità con etichette DULE/Data Privacy, ID Adobe Analytics, spazi dei nomi ed espansione ID. | Leggi questi argomenti nella presente documentazione:<ul><li>[Etichette sulla privacy dei dati per le variabili Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)</li></ul> |
| **Passaggio 4:** assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti.  Nota: ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. | Segui le istruzioni riportate in [Etichettare i dati della suite di rapporti.](/help/admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731) |
| **Passaggio 5**: Connettiti all’API Adobe Data Privacy e invia richieste di accesso ed eliminazione. | As an Adobe Analytics customer, you can submit individual Data Privacy requests to access and delete customer data, by calling the [Adobe Experience Cloud Data Privacy API.](https://www.adobe.io/apis/experienceplatform/gdpr.html) Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](/help/admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E)) insieme ai rispettivi ID dei namespace (ID dell’origine dati). |
| **Passaggio 6**: Visualizza e gestisci le impostazioni Privacy dei dati della suite di rapporti. | Segui le istruzioni riportate in [Visualizzare impostazioni di governance dei dati della suite di rapporti.](/help/admin/c-data-governance/gdpr-view-settings.md) |
