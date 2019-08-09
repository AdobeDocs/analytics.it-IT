---
description: nulle
seo-description: nulle
seo-title: Flusso di lavoro di Adobe Analytics per il RGPD
title: Flusso di lavoro di Adobe Analytics per il RGPD
uuid: f 24 e 8 be 3-8 b 5 c -409 b-ad 6 b -770198 ae 2549
translation-type: tm+mt
source-git-commit: fc9dbf8e2590ca3d89b295be03ec8ef7dc511c72

---


# Flusso di lavoro di Adobe Analytics per il RGPD

Benvenuti alla preparazione di Adobe Analytics per il RGPD. Questo flusso di lavoro delinea la procedura da seguire per preparare l'implementazione di Adobe Analytics al fine di supportare i diritti di accesso e la cancellazione delle persone interessate in base al RGPD.

<table id="table_0E561F62247A4D01B6E7180560082DC9"> 
 <thead> 
  <tr> 
   <th colname="col2" class="entry"> Descrizione dell'attività </th> 
   <th colname="col3" class="entry"> Collegamenti alle istruzioni e ad altre informazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step1_icon.png" id="image_15849358972A4846A54FCB51997576D5" />Assicurati che tutte le suite di rapporti che potrebbero contenere dati relativi al RGPD siano state mappate nell'organizzazione Experience Cloud (o IMS). </p> <p>Le richieste del RGPD vengono inviate usando un'organizzazione Experience Cloud e verranno applicate a tutte le suite di rapporti richieste dall'organizzazione. Le richieste non verranno applicate alle suite di rapporti che non sono state mappate nell'organizzazione, anche se fanno parte della società di accesso. </p> </td> 
   <td colname="col3"> <p>Consulta <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html" format="html" scope="external">Mappatura di suite di rapporti per un'organizzazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step2_icon.png" id="image_372B2C65DFAD46E39AE4D715313ABD0E"/> Imposta i criteri di conservazione dei dati. </p> </td> 
   <td colname="col3"> <p>È necessario impostare i criteri di conservazione dei dati affinché Adobe possa soddisfare le richieste di accesso o di cancellazione dei dati del RGPD. </p> <p>Per altre informazioni consulta le <a href="https://marketing.adobe.com/resources/help/en_US/reference/data-retention-client-table-faq.html" format="html" scope="external">Domande frequenti sulla conservazione dei dati in Analytics</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step3_icon.png" id="image_30DB956290CC4E64A7085B46364BE059" /> Acquisisci familiarità con le etichette DULE/GDPR, gli ID di Adobe Analytics, i namespace e l'espansione dell'ID. </p> </td> 
   <td colname="col3"> <p> Leggi questi argomenti nella presente documentazione: 
     <ul id="ul_F6E94B9281D446DB8F1F859F6056543B"> 
      <li id="li_6389D094B4B04CA181E5F077BF8C0F8E"><a href="../../admin/c-data-governance/gdpr-labels.md#concept_F4061E29353446B5B0A7CF248D54E6F2" format="dita" scope="local"> Etichette del RGPD per le variabili di Analytics</a> </li> 
      <li id="li_CEEF2106E37845A49E0EA1225D5CFF14">Elemento elenco </li> 
      <li id="li_0B79CEBD074A4C68923EE9C9766D4B9D"><a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local"> Tecniche di etichettatura consigliate</a> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img  src="assets/step4_icon.png" id="image_FE2039B8345248BCA303B44C10B68EA1" placement="break" /> Assegna etichette di identità, riservatezza e governance dei dati a ciascuna variabile in una suite di rapporti. </p> <p>Nota: ricorda che l'etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all'interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti Web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. </p> </td> 
   <td colname="col3"> <p> Segui le istruzioni in <a href="../../admin/c-data-governance/gdpr-setup-reportsuite.md#concept_FAA948AD8CEA4BC38CB482EAF3648731" format="dita" scope="local"> Etichetta dati suite di rapporti</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step5_icon.png" id="image_E9BEF83BF30F4528A030F23F71E5E5D8" /> Collegati all'API RGPD di Adobe e invia le richieste di accesso e cancellazione. </p> </td> 
   <td colname="col3"> <p>In qualità di cliente di Adobe Analytics, puoi inviare singole richieste RGPD per accedere e cancellare i dati di un cliente, richiamando l'<a href="https://www.adobe.io/apis/cloudplatform/gdpr.html" format="html" scope="external">API RGPD di Adobe Experience Cloud</a>. </p> <p>Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione <a href="../../admin/c-data-governance/gdpr-analytics-ids.md#concept_1BC4CA94B559481F8B08776DA100B23E" format="dita" scope="local">Tecniche di etichettatura consigliate</a>) insieme ai rispettivi ID dei namespace (ID dell'origine dati). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p><img placement="break"  src="assets/step6_icon.png" id="image_5CF03706FECD4F8BBAE0D0C19F98B8BB" /> Visualizza e gestisci le impostazioni RGPD della suite di rapporti. </p> </td> 
   <td colname="col3"> <p>Segui le istruzioni in <a href="../../admin/c-data-governance/gdpr-view-settings.md#concept_7759BAD6F3174901A94116D189AEF80E" format="dita" scope="local"> Visualizza impostazioni della governance dati di Rapporti</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Descrizione dell'attività | Collegamenti alle istruzioni e ad altre informazioni |
|--- |--- |
| **Passaggio 1**: Assicurati che una qualsiasi suite di rapporti che potrebbe contenere dati relativi al GDPR sia mappata sulla tua organizzazione Experience Cloud (o IMS). Le richieste del RGPD vengono inviate usando un'organizzazione Experience Cloud e verranno applicate a tutte le suite di rapporti richieste dall'organizzazione. Le richieste non verranno applicate alle suite di rapporti che non sono state mappate nell'organizzazione, anche se fanno parte della società di accesso. | Consulta [Mappatura di suite di rapporti per un'organizzazione](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/report-suite-mapping.html). |
| **Passaggio 2**: imposta il criterio di conservazione dei dati. | È necessario impostare i criteri di conservazione dei dati affinché Adobe possa soddisfare le richieste di accesso o di cancellazione dei dati del RGPD.  Per altre informazioni consulta le [Domande frequenti sulla conservazione dei dati in Analytics](/help/technotes/data-retention.md). |
| **Passaggio 3**: Acquisire familiarità con etichette DULE/GDPR, ID Adobe Analytics, spazi di nomi e espansione ID. | Leggi questi argomenti nella presente documentazione:<ul><li>[Etichette del RGPD per le variabili di Analytics](/help/admin/c-data-governance/gdpr-labels.md)</li><li>[Tecniche di etichettatura consigliate](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-analytics-ids.html#concept_1BC4CA94B559481F8B08776DA100B23E)</li></ul> |
| **Passaggio 4**: Assegna etichette di identità, sensibilità e governance dati a ciascuna variabile in una suite di rapporti. Nota: ricorda che l'etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata la nuova variabile all'interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti Web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette. | Segui le istruzioni in [Etichetta dati suite di rapporti](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-setup-reportsuite.html#concept_FAA948AD8CEA4BC38CB482EAF3648731). |
| **Passaggio 5**: Connettetevi all'API Adobe GDPR e inviate le richieste di accesso ed eliminazione. | In qualità di cliente di Adobe Analytics, puoi inviare singole richieste RGPD per accedere e cancellare i dati di un cliente, richiamando l'[API RGPD di Adobe Experience Cloud](https://www.adobe.io/apis/experienceplatform/gdpr.html).  Nelle richieste puoi inviare qualsiasi identificatore di Analytics (come descritto nella sezione [Tecniche di etichettatura consigliate](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-analytics-ids.html#concept_1BC4CA94B559481F8B08776DA100B23E)) insieme ai rispettivi ID dei namespace (ID dell'origine dati). |
| **Passaggio 6**: Visualizza e gestisci le impostazioni GDPR della tua suite di rapporti. | Segui le istruzioni in [Visualizza impostazioni della governance dati di Rapporti](/help/admin/c-data-governance/gdpr-view-settings.md). |