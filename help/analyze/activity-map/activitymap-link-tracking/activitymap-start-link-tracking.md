---
description: Passaggi per avviare il tracciamento dei collegamenti in Activity Map o clickmap legacy.
seo-description: Passaggi per avviare il tracciamento dei collegamenti in Activity Map o clickmap legacy.
seo-title: Avviare il tracciamento dei collegamenti
solution: Analytics
title: Avviare il tracciamento dei collegamenti
topic: Activity map
uuid: 425 cb 287-f 76 e -4430-802 f -288499711 ba 9
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Avviare il tracciamento dei collegamenti

Passaggi per avviare il tracciamento dei collegamenti in Activity Map o clickmap legacy.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per avviare il tracciamento dei collegamenti in… </th> 
   <th colname="col2" class="entry"> Effettua questa operazione… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Add the following content from the Appmeasurement.js file: 
    <code>
     /*
      START Activity Map MODULE The following module enables Activity Map tracking in Adobe Analytics.Activity Map consente di visualizzare sovrapposizioni di dati sui collegamenti e i contenuti per comprendere in che modo gli utenti interagiscono con il tuo sito Web.Se non intendi utilizzare Activity Map, puoi rimuovere il seguente blocco di codice dal file appmeasurement. js.
  Additional documentation on how to configure Activity Map is available at:
      https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/getting-started-admins.html
     */
     function AppMeasurement_Module_Activity Map(g){func
     ...
     /* END Activity Map MODULE */
    </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Clickmap (precedentemente Visitor clickmap) </td> 
   <td colname="col2"> <p>Set the <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external"> trackInlineStats</a> variable to true. The syntax reads as follows: 
     <code>
       s.trackInlineStats=true
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

