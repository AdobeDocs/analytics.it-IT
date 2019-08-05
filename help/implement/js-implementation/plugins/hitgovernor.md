---
description: Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.
seo-description: Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.
seo-title: Hitboar
title: Hitboar
uuid: d 9091 eae -005 a -43 c 2-b 419-980 b 795 bc 2 a 9
translation-type: tm+mt
source-git-commit: 5abac13c231659108a26b8513a3bb32e4e530b94

---


# Hitboar

Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.

## Hitboar {#topic_56B636A42A624B38A0A446C607ACD700}

Il plug-plugin s. hitdeck tiene traccia del numero totale di richieste di immagini di Analytics inviate durante un intervallo di tempo predefinito, e può eseguire una logica aggiuntiva se il totale supera una certa soglia.

Sebbene il traffico da bot, spider, agenti utente specifici o un elenco specifico di indirizzi IP possa essere identificato come traffico bot o escluso dal reporting, può esserci traffico acquisito nelle suite di rapporti che altrimenti non dovrebbe essere conteggiato. Ad esempio, un numero elevato di clic o di visualizzazioni di pagina durante una quantità di tempo ragionevole (ovvero circa una richiesta al secondo) potrebbe essere un traffico duplicato.

L'utilizzo di questo plug-in consente che il traffico venga bloccato automaticamente per il resto della durata del visitatore e che il traffico possa essere identificato in modo dinamico all'interno dei report.

## Funzionamento del plugin del governatore Hit {#section_541BC639E31442D09B1C85A2FFCDC02C}

Il plug-in incrementa il valore di un cookie ogni volta che viene inviata una richiesta di immagine ai server di tracciamento e traccia questo su un intervallo di tempo continuo. Il tempo predefinito è di un minuto, anche se tale intervallo può essere ignorato. (Vedi [Implementazione](../../../implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2), di seguito.) Se il numero totale di hit nel periodo di tempo supera la soglia di hit predefinita (60), viene inviata una richiesta di immagine collegamento personalizzata finale per impostare la *`exceptionFlag`* variabile di dati di contesto. Anche la soglia predefinita degli hit può essere ignorata.

Se necessario, da quel momento in poi, potrebbe non essere possibile raccogliere il traffico per quel visitatore specifico per un periodo predefinito di sessanta giorni. Il blocco del traffico richiede un'ulteriore riga di codice nella funzione doplugins, come descritto di seguito. È possibile regolare anche l'intervallo di tempo. La logica consente di includere l'indirizzo IP di quel visitatore, l'agente utente o l'ID [!DNL Experience Cloud] visitatore nella logica corretta delle eccezioni, oppure di ripristinare il periodo di timeout dopo che sono trascorsi i sessanta giorni. Se il traffico viene identificato come fraudolento dal plug-in dopo sessanta giorni, il traffico viene contrassegnato di nuovo come eccezione e non viene raccolto per altri sessanta giorni.

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

   Per inizializzare il plug-plugin, includi questa riga di codice (in grassetto) all'interno della `registerPostTrackCallback` funzione nel codice della libreria appmeasurement.

   >[!NOTE]
   >
   >Anche se la `registerPostTrackCallback` funzionalità è inclusa nelle librerie appmeasurement 1.8.0 +, per impostazione predefinita non è inclusa in alcuna configurazione di codice personalizzata. Viene incluso dopo e *all'esterno* della funzione doplugins.

   ```
    s.registerPostTrackCallback(function(){ 
    s.governor();
   }); 
   ```

   Sotto la sezione doplugins del file appmeasurement, includi il codice plug-plugin contenuto nel [codice](../../../implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0)di origine plug-in, di seguito.

   La soglia di limite hit, la soglia di temporizzazione e i fotogrammi di esclusione del traffico possono essere sostituiti impostando queste variabili, all'esterno del plug-in stesso e preferibilmente con le altre variabili di configurazione:

<table id="table_9959A40F5F0B40B39DB86E21D03E25FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Sintassi </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Soglia limite hit </p> </td> 
   <td colname="col2"> <p> <code> s. hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>Il numero totale di hit che non devono essere superati nel periodo temporale specificato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia tempo hit </p> </td> 
   <td colname="col2"> <p> <code> s. ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>La finestra, in secondi, per la registrazione degli hit. Questo numero è diviso per sei volte per determinare le finestre di temporizzazione a scorrimento continuo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia di esclusione </p> </td> 
   <td colname="col2"> <p> <code> s. he = 60; </code> </p> </td> 
   <td colname="col3"> <p>Numero di giorni impostati per il cookie di esclusione per quel visitatore. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>L'implementazione può utilizzare un nome oggetto diverso da quello dell'oggetto di analisi predefinito. In tal caso, aggiornare il nome dell'oggetto di conseguenza.

1. Configura le regole di elaborazione.

   Questo plug-in registra le eccezioni segnalate come dati contestuali in una richiesta di immagine tracciamento collegamenti. Di conseguenza, le regole di elaborazione devono essere configurate per assegnare le eccezioni segnalate a tali eccezioni in variabili appropriate come quelle riportate di seguito.

   ![](assets/hitgov-config.png)

1. (Facoltativo) Includete il codice di blocco del traffico in doplugins.

   Dopo che il traffico è stato identificato come eccezione, tutti gli hit successivi da quel visitatore possono essere bloccati completamente includendo questo codice all'interno `doPlugins` della funzione:

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   Se questo codice non è incluso, il traffico da quel visitatore verrà segnalato ma non bloccato.

## Codice sorgente plug-in {#reference_76423C81A7A342B2AC4BE41490B27DE0}

Questo codice deve essere aggiunto sotto la sezione doplugins della libreria appmeasurement.

```
//Hit Governor (Version 0.1 BETA, 11-13-17) 
s.governor=new Function("","" 
+"var s=this;if(typeof s.hl=='undefined'){s.hl=60;}if(typeof s.ht=='u" 
+"ndefined'){s.ht=60;}if(typeof s.he=='undefined'){s.he=60;}if(s.Util" 
+".cookieRead('s_hg')==8){var i=new Date(),y=i.getFullYear(),m=i.getM" 
+"onth(),d=i.getDate(),i=new Date(y,m,d+s.he);s.Util.cookieWrite('s_h" 
+"g',9,i);return;}var f=s.Util.cookieRead('s_hc'),g=Number(s.Util.coo" 
+"kieRead('s_ht')),h=Math.floor((new Date()).getTime()),ha=f!=''?f.sp" 
+"lit('|').map(Number):[0,0,0,0,0],i=ha.reduce(function(ha,b){return " 
+"ha+b;},0),j=g==0?0:Math.floor(((h-g)/(s.ht/6))/1000);if(g==0)s.Util" 
+".cookieWrite('s_ht',h);if(i<s.hl){if(j>=1){if(j>=6){ha=[0,0,0,0,0];" 
+"}else{for(var k=0;k<j;k++){ha.unshift(0);ha.pop();}}s.Util.cookieWr" 
+"ite('s_ht',h);}}else{s.Util.cookieWrite('s_hg',8);s.linkTrackVars+=" 
+"',contextData.exceptionFlag';s.contextData['exceptionFlag']='true';" 
+"s.tl(this,'o','exceptionFlag');}ha[0]++;s.Util.cookieWrite('s_hc',h" 
+"a.join('|'));"); 
```

