---
description: Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.
keywords: gruppi;autorizzazioni
seo-description: Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.
seo-title: Personalizzare le autorizzazioni della dimensione
solution: Analytics
subtopic: Utenti e gruppi
title: Personalizzare le autorizzazioni della dimensione
topic: Strumenti di amministrazione
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Personalizzare le autorizzazioni della dimensione

> [!IMPORTANT] La gestione di utenti e prodotti passa ad [Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html). Adobe ti informerà quando è il momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin Tools]** &gt; **[!UICONTROL User Management]** verranno ritirati.

Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.

**[!UICONTROL User Management]** &gt; **[!UICONTROL Groups]** &gt; **[!UICONTROL Report Access]** &gt; **[!UICONTROL Dimensions]** &gt; **[!UICONTROL Customize]**

> [!IMPORTANT] Alcune dimensioni al momento non sono consentite. Tali dimensioni sono: Lunghezza Segnalibro Mobile; Numero dispositivo mobile; DRM mobile; Mobile Information Services; VM Java mobile; Decorazione della posta mobile; Protocolli di Mobile Net; Sistema operativo mobile; Invia push per cellulare per parlare.
>
>Queste dimensioni sono disponibili per tutti gli utenti, indipendentemente dalle altre autorizzazioni.

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate sulla [!UICONTROL Define User Groups] pagina.

![](assets/permissions-dimensions.png)

Informazioni sulla categoria Dimensione per le autorizzazioni.

* Le eVar 1-250 dispongono di autorizzazioni individuali.
* Tutti i rapporti sul traffico riguardano la categoria delle dimensioni.
* I rapporti video e mobili sono dimensioni, nonché altri rapporti sulle soluzioni Analytics (Experience Manager, Advertising Cloud, Social e così via).
* I rapporti sui percorsi sono disponibili se un utente dispone dell'accesso alle dimensioni dell'elemento padre.
* Tutte le dimensioni e le metriche correnti all'interno dei gruppi personalizzati sono state migrate automaticamente nelle nuove categorie. Se un gruppo esistente dispone di metriche abilitate, per impostazione predefinita gli verranno assegnate tutte le dimensioni (sulla base delle eVar e dei contenuti) e le metriche a cui sono state appena assegnate delle autorizzazioni.
* Autorizzazioni per Importazione classificazioni (in precedenza SAINT): l'accesso alle classificazioni è determinato dall'accesso alla [variabile](https://marketing.adobe.com/resources/help/en_US/reference/c_classifications.html) su cui è basata la classificazione.

Per ulteriori informazioni, consultare [Frequently Asked Questions about Permission Changes](https://marketing.adobe.com/resources/help/en_US/reference/permissions_faq.html) (Domande frequenti sulle modifiche delle autorizzazioni).

**Personalizza dimensioni**

I seguenti elementi sono dimensioni consentite.

<table id="table_F37D74A1619A4560A5F5651E855DAF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Elemento </th> 
   <th colname="col2" class="entry"> Descrizioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <a href="/help/admin/admin/conversion-var-admin/conversion-var-admin.md"> eVar </a> </p> </td> 
   <td colname="col2"> <p>Le eVar 1-250 dispongono di autorizzazioni individuali. Le eVar sono variabili di conversione personalizzate da utilizzare per segmentare le metriche di successo della conversione nei report personalizzati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html"> Proprietà </a> </p> </td> 
   <td colname="col2"> <p>Le proprietà sono variabili di traffico personalizzate. </p> <p>Consulta <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html"> Proprietà di traffico e eVar di conversione </a> nell'implementazione di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/hierN.html"> Gerarchia </a> </p> </td> 
   <td colname="col2"> <p> La variabile gerarchica (hierN) determina la posizione di una pagina nella gerarchia o nella struttura di pagina del sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/listN.html"> Listvar </a> </p> </td> 
   <td colname="col2"> <p> Simile alla funzione Elenco proprietà, le variabili elenco consentono più valori all’interno della stessa richiesta di immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Si riferisce alle dimensioni standard (pronte all’uso) in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/em/"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/media-optimizer/"> AMO </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensioni di reporting Activity Map: Activity Map Page; Collegamento Activity Map; Regione Activity Map; Collegamento Activity Map Per Regione; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/mobile/"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Comscore </p> </td> 
   <td colname="col2"> <p>Questa integrazione con i partner non è più attiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Questa integrazione con i partner non è più attiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Non utilizzato. </p> </td> 
  </tr> 
 </tbody> 
</table>
