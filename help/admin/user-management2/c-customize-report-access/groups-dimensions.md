---
description: Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.
keywords: gruppi; permissions
seo-description: Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.
seo-title: Personalizzare le autorizzazioni della dimensione
solution: Analytics
subtopic: Utenti e gruppi
title: Personalizzare le autorizzazioni della dimensione
topic: Strumenti di amministrazione
uuid: aaf 164 ad -3863-4129-864 e -39 ec 71 c 6 a 8 eb
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Personalizzare le autorizzazioni della dimensione

>[!IMPORTANT]
>
>User and product management is moving to the [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe ti informerà quando sarà il momento di eseguire la migrazione degli utenti. After all customers have migrated, help content for **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** will be retired.

Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.

**[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL Report Access]** &gt; **[!UICONTROL Dimensions]** &gt; **[!UICONTROL Customize]**

>[!IMPORTANT]
>
>Al momento alcune dimensioni non sono peribili. Queste dimensioni sono: Lunghezza segnalibro mobile; Numero dispositivo mobile; DRM Mobile; Mobile Information Services; Mobile Java VM; Mobile Mail Decoration; Protocolli di Mobile Net; Sistema operativo Mobile; Push push per parlare.
>
>Queste dimensioni sono disponibili per tutti gli utenti, indipendentemente da altre autorizzazioni.

The settings on this page pertain to the report suites selected on the [!UICONTROL Define User Groups] page.

![](assets/permissions-dimensions.png)

Comprendi le seguenti informazioni sulla categoria Dimensione per le autorizzazioni.

* Le eVar 1-250 dispongono di autorizzazioni individuali.
* Tutti i rapporti sul traffico riguardano la categoria delle dimensioni.
* I rapporti Video e mobili sono dimensioni e altri rapporti sulle soluzioni Analytics (Experience Manager, Advertising Cloud, Social e così via).
* I rapporti sui percorsi sono disponibili se un utente dispone dell'accesso alle dimensioni dell'elemento padre.
* Tutte le dimensioni e le metriche correnti all'interno dei gruppi personalizzati sono state migrate automaticamente nelle nuove categorie. Se un gruppo esistente dispone di metriche abilitate, per impostazione predefinita gli verranno assegnate tutte le dimensioni (sulla base delle eVar e dei contenuti) e le metriche a cui sono state appena assegnate delle autorizzazioni.
* Autorizzazioni per Importazione classificazioni (in precedenza SAINT): l'accesso alle classificazioni è determinato dall'accesso alla [variabile](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html) su cui è basata la classificazione.

Per ulteriori informazioni, consultare [Frequently Asked Questions about Permission Changes](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html) (Domande frequenti sulle modifiche delle autorizzazioni).

**Personalizza dimensioni**

I seguenti elementi sono dimensioni che puoi autorizzare.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="../../../admin/admin/conversion-var-admin/conversion-var-admin.md#concept_C02F7AA01DE242F1AA1A4E74022BE9DE" format="dita" scope="local"> Evar </a> </p> </td> 
   <td colname="col2"> <p>Le eVar 1-250 dispongono di autorizzazioni individuali. Le evar sono variabili di conversione personalizzate che puoi utilizzare per segmentare le metriche di successo conversione nei rapporti personalizzati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external"> Proprietà </a> </p> </td> 
   <td colname="col2"> <p>Le proprietà sono variabili di traffico personalizzate. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external"> Traffic props and conversion eVars </a> in Analytics Implementation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html" format="html" scope="external"> Gerarchia </a> </p> </td> 
   <td colname="col2"> <p> La variabile gerarchia (hiern) determina la posizione di una pagina nella gerarchia o nella struttura della pagina del sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html" format="html" scope="external"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Simile alla funzione Elenco proprietà, le variabili dell'elenco consentono più valori all'interno della stessa richiesta di immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Si riferisce alle dimensioni standard (out of the-box) in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/" format="https" scope="external"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/" format="https" scope="external"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/" format="https" scope="external"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensioni di reporting Activity Map: Pagina Mappa dell'attività; Collegamento Mappa dell'attività; Regione Activity Map; Collegamento Mappa dell'attività per regione; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/" format="https" scope="external"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Score (Punteggio) </p> </td> 
   <td colname="col2"> <p>L'integrazione di questo Partner non è più attiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html" format="html" scope="external"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Integrazioni di partner. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Non utilizzato. </p> </td> 
  </tr> 
 </tbody> 
</table>

