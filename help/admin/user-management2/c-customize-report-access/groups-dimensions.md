---
description: Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.
keywords: gruppi;autorizzazioni
subtopic: Users and groups
title: Personalizzare le autorizzazioni della dimensione
feature: Admin Tools
uuid: aaf164ad-3863-4129-864e-39ec71c6a8eb
exl-id: 51c4193a-426e-46a0-8494-163b58588157
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 48%

---

# Personalizzare le autorizzazioni della dimensione

>[!IMPORTANT]
>
>La gestione di utenti e prodotti sta passando all&#39; [Admin Console](https://helpx.adobe.com/it/enterprise/using/admin-console.html). Adobe ti avviserà quando è il tuo momento di eseguire la migrazione degli utenti. Dopo la migrazione di tutti i clienti, i contenuti della guida per **[!UICONTROL Analytics]** > **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** verranno ritirati.

Personalizza nel dettaglio le opzioni di accesso degli utenti, ad esempio per eVar, rapporti sul traffico, rapporti sulle soluzioni e rapporti di percorsi.

**[!UICONTROL User Management]** >  **[!UICONTROL Groups]** >  **[!UICONTROL Report Access]** >  **[!UICONTROL Dimensions]** >  **[!UICONTROL Customize]**

>[!IMPORTANT]
>
>Al momento alcune dimensioni non sono consentite. Queste dimensioni sono: Lunghezza segnalibro mobile; Numero del dispositivo mobile; DRM mobile; Mobile Information Services; VM Java mobile; Decoration Mail Mobile; Protocolli di rete mobili; Sistema operativo mobile; Spingi mobili per parlare.
>
>Queste dimensioni sono disponibili per tutti gli utenti, indipendentemente da altre autorizzazioni.

Le impostazioni di questa pagina si riferiscono alle suite di rapporti selezionate nella pagina [!UICONTROL Define User Groups] .

![](assets/permissions-dimensions.png)

Comprendi le seguenti informazioni sulla categoria Dimension per le autorizzazioni.

* Le eVar 1-250 dispongono di autorizzazioni individuali.
* Tutti i rapporti sul traffico riguardano la categoria delle dimensioni.
* I rapporti video e mobili sono dimensioni, nonché altri rapporti delle soluzioni Analytics (ad Experience Manager, Advertising Cloud, Social e così via).
* I rapporti sui percorsi sono disponibili se un utente dispone dell&#39;accesso alle dimensioni dell&#39;elemento padre.
* Tutte le dimensioni e le metriche correnti all&#39;interno dei gruppi personalizzati sono state migrate automaticamente nelle nuove categorie. Se un gruppo esistente dispone di metriche abilitate, per impostazione predefinita gli verranno assegnate tutte le dimensioni (sulla base delle eVar e dei contenuti) e le metriche a cui sono state appena assegnate delle autorizzazioni.
* Autorizzazioni per Importazione classificazioni (in precedenza SAINT): l&#39;accesso alle classificazioni è determinato dall&#39;accesso alla [variabile](https://docs.adobe.com/content/help/it-IT/analytics/components/classifications/c-classifications.html) su cui è basata la classificazione.

Per ulteriori informazioni, consulta [Modifiche alle autorizzazioni utente e gruppo](https://docs.adobe.com/content/help/it-IT/analytics/admin/user-product-management/user-management/permissions-changes.html).

**Personalizzare i Dimension**

Gli elementi seguenti sono dimensioni che puoi autorizzare.

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
   <td colname="col2"> <p>Le eVar 1-250 dispongono di autorizzazioni individuali. Le eVar sono variabili di conversione personalizzate utilizzate per segmentare le metriche di successo della conversione nei rapporti personalizzati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/evar.html"> Proprietà </a> </p> </td> 
   <td colname="col2"> <p>Le proprietà sono variabili di traffico personalizzate. </p> <p>Consulta <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/evar.html"> Proprietà di traffico ed eVar di conversione </a> in Implementazione di Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html"> Gerarchia </a> </p> </td> 
   <td colname="col2"> <p> La variabile gerarchia (hierN) determina la posizione di una pagina nella gerarchia o nella struttura di pagina del sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/page-variables.html"> Listvar  </a> </p> </td> 
   <td colname="col2"> <p> Analogamente alla funzione Proprietà elenco, le variabili elenco consentono più valori all’interno della stessa richiesta di immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> </td> 
   <td colname="col2"> <p>Si riferisce alle dimensioni standard (pronte all’uso) in Analytics. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/it/support/experience-manager.html"> AEM </a> </p> </td> 
   <td colname="col2"> <p>Adobe Experience Manager </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://helpx.adobe.com/it/support/advertising-cloud.html"> AMO  </a> </p> </td> 
   <td colname="col2"> <p>Adobe Advertising Cloud </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/it-IT/analytics/analyze/activity-map/activity-map.html"> Activity Map </a> </p> </td> 
   <td colname="col2"> <p> Dimensioni di reporting di Activity Map: Pagina Activity Map; Collegamento Activity Map; Regione Activity Map; Collegamento Activity Map Per Regione; Activity Map XY </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/it-IT/media-analytics/using/media-overview.html"> Mobile </a> </p> </td> 
   <td colname="col2"> <p>Adobe Mobile Services </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Commento </p> </td> 
   <td colname="col2"> <p>Questa integrazione dei partner non è più attiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <a href="https://docs.adobe.com/content/help/en/media-analytics/using/media-overview.html"> Nielsen </a> </p> </td> 
   <td colname="col2"> <p>Questa integrazione dei partner non è più attiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> Social </p> </td> 
   <td colname="col2"> <p>Non utilizzato. </p> </td> 
  </tr> 
 </tbody> 
</table>
