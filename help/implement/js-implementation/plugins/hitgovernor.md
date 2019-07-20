---
description: Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.
seo-description: Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.
seo-title: Hitboar
title: Hitboar
uuid: d 9091 eae -005 a -43 c 2-b 419-980 b 795 bc 2 a 9
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# Hitboar

Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.

## hitGovernor {#topic_56B636A42A624B38A0A446C607ACD700}

Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.

Sebbene il traffico da bot, spider, agenti utente specifici o un elenco specifico di indirizzi IP possa essere identificato come traffico bot o escluso dal reporting, può esserci traffico acquisito nelle suite di rapporti che altrimenti non dovrebbe essere conteggiato. Ad esempio, un numero elevato di clic o di visualizzazioni di pagina durante una quantità di tempo ragionevole (ovvero circa una richiesta al secondo) potrebbe essere un traffico duplicato.

L'utilizzo di questo plug-in consente che il traffico venga bloccato automaticamente per il resto della durata del visitatore e che il traffico possa essere identificato in modo dinamico all'interno dei report.

## How the Hit Governor Plugin Works {#section_541BC639E31442D09B1C85A2FFCDC02C}

Il plug-in incrementa il valore di un cookie ogni volta che viene inviata una richiesta di immagine ai server di tracciamento e traccia questo su un intervallo di tempo continuo. Il tempo predefinito è di un minuto, anche se tale intervallo può essere ignorato. (See [Implementation](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2), below.) If the total number of hits during that time frame exceeds the default hit threshold (60), a final custom link image request is sent to set the *`exceptionFlag`* context data variable. Anche la soglia predefinita degli hit può essere ignorata.

Se necessario, da quel momento in poi, potrebbe non essere possibile raccogliere il traffico per quel visitatore specifico per un periodo predefinito di sessanta giorni. Il blocco del traffico richiede un'ulteriore riga di codice nella funzione doplugins, come descritto di seguito. È possibile regolare anche l'intervallo di tempo. The logic allows time to either include that visitor's IP address, User Agent, or [!DNL Experience Cloud] Visitor ID in the proper permanent exception logic, or to reset the timeout period after the sixty days have elapsed. Se il traffico viene identificato come fraudolento dal plug-in dopo sessanta giorni, il traffico viene contrassegnato di nuovo come eccezione e non viene raccolto per altri sessanta giorni.

## Generazione di rapporti  {#section_E742F19B528041808454744DB2C7007C}

Non è necessario configurare variabili o eventi predefiniti. Tuttavia, consigliamo vivamente di configurare logica delle regole di elaborazione per impostare di conseguenza variabili ed eventi. Tali variabili ed eventi personalizzati potrebbero includere:

* [!DNL Experience Cloud] Visitor ID
* Indirizzo IP
* Agente utente
* Evento eccezione segnalata

La creazione di segmenti per queste variabili consente di creare segmenti e suite di rapporti virtuali per visualizzare l'impatto complessivo del sito di questi hit ambigui.

Consigliamo di utilizzare i valori acquisiti nel reporting per aggiornare le regole bot, le regole DB VISTA o le esclusioni IP della società.

## Implementazione {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

Per implementare il plug-plugin hitdeck:

1. Modifica la libreria appmeasurement.

   To initialize the plugin, include this line of code (in bold) within the `registerPostTrackCallback` function in the AppMeasurement library code.

   >[!NOTE]
   >
   >Although the `registerPostTrackCallback` functionality is included in AppMeasurement libraries 1.8.0+, it is not included in any custom code configuration by default. It is included after and *outside of* the doPlugins function.

   ```
    s.registerPostTrackCallback(function(){ 
   
<b> s. boar();</b>});
```
Below the doPlugins section of your AppMeasurement file, include the plugin code contained in [Plugin Source Code](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0), below.

The hit limit threshold, hit timing threshold, and traffic exclusion time frames can all be overridden by setting these variables, outside of the plugin itself and preferably with your other configuration variables:

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
<thead> 
<tr> 
<th colname="col1" class="entry"> Variable </th> 
<th colname="col2" class="entry"> Syntax </th> 
<th colname="col3" class="entry"> Description </th> 
</tr> 
</thead>
<tbody> 
<tr> 
<td colname="col1"> <p>Hit Limit Threshold </p> </td> 
<td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
<td colname="col3"> <p>The total number of hits that should not be exceeded during a given timeframe. </p> </td> 
</tr> 
<tr> 
<td colname="col1"> <p>Hit Time Threshold </p> </td> 
<td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
<td colname="col3"> <p>The window, in seconds, for when hits are recorded. This number is divided by six to determine the rolling timing windows. </p> </td> 
</tr> 
<tr> 
<td colname="col1"> <p>Exclusion Threshold </p> </td> 
<td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
<td colname="col3"> <p>Number of days that the exclusion cookie is set for that visitor. </p> </td> 
</tr> 
</tbody> 
</table>

>[!NOTE]
>
>Your implementation might use a different object name than the default analytics "s" object. If so, please update the object name accordingly.

1. Configure processing rules.

This plugin records flagged exceptions as context data in a link tracking image request. As such, processing rules must be configured to assign track those flagged exceptions into appropriate variables like those below.

![](assets/hitgov-config.png)

1. (Optional) Include the traffic-blocking code in doPlugins.

After traffic has been identified as an exception, any subsequent hits from that visitor can be blocked entirely by including this code within the `doPlugins` function:
```
//Check for hit seminar flag
if (s. Util. cookieread ('s_ hg ') = = 9) s. abort = true;
```
If this code is not included, traffic from that visitor will be flagged but not blocked. 

## Plugin Source Code {#reference_76423C81A7A342B2AC4BE41490B27DE0}

This code should be added below the doPlugins section of your AppMeasurement library.
```
//Hit Governatore (versione 0.1 BETA, 11-13-17)
s. governatore = new Function (","
+ "var s = this; if (typeof s. hl = ='undefined ') {s. hl = 60;} if (typeof s. ht = ='u "
+" ndefined ') {s. ht = 60;} if (typeof s. = undefined ') {s. he = 60;} if (s. Util "
+". cookieread ('s_ hg ') = = 8) {var i = new Date (), y = i. getfullyear (), m = i. getm "
+" onth (), d = i. getdate (), i = new Date (y, m, d + s. he); s. Util. cookiewrite ('s_ h "
+" g ', 9, i); return;} var f = s. Util. cookieread ('s_ hc '), g = Number (s. Util. coo "
+" kieread ('s_ ht '), h = Math. floor ((new Date ()). gettime ()), ha = f!=''?f.sp"
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return "
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util"
+".cookieWrite('s_ht',h);if(i&lt;s.hl){if(j&gt;=1){if(j&gt;=6){ha=[0,0,0,0,0];"
+"}else{for(var k=0;k&lt;j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr"
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+="
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';"
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h"
+"a.join('|'));");

```


