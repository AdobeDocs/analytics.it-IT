---
description: Passaggi per interrompere il tracciamento dei collegamenti in Activity Map o clickmap legacy.
seo-description: Passaggi per interrompere il tracciamento dei collegamenti in Activity Map o clickmap legacy.
seo-title: Interrompere il tracciamento dei collegamenti
solution: Analytics
title: Interrompere il tracciamento dei collegamenti
topic: Activity map
uuid: e 17 fb 7 bd-d 6 ed -45 c 3-a 006-9150 d 5718 cff
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Interrompere il tracciamento dei collegamenti

Passaggi per interrompere il tracciamento dei collegamenti in Activity Map o clickmap legacy.

<table id="table_1745199B3105467CBA26F50B3B1CCE99"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per interrompere il tracciamento dei collegamenti in… </th> 
   <th colname="col2" class="entry"> Effettua questa operazione… </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Activity Map </td> 
   <td colname="col2"> Remove the following content from the Appmeasurement.js file: 
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
   <td colname="col2"> <p>Set the <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/trackInlineStats.html" format="https" scope="external"> trackInlineStats</a> variable to false (this is the default.) The syntax reads as follows: 
     <code>
       s.trackInlineStats=false
     </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

