---
description: Il plug-in s.hitGovernatore tiene traccia del numero totale di richieste di immagini Analytics inviate durante un intervallo di tempo continuo predefinito e può eseguire logica aggiuntiva se tale totale supera una determinata soglia.
title: hitGovernor
uuid: d9091eae-005a-43c2-b419-980b795bc2a9
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# hitGovernor

Il plug-in s.hitGovernatore tiene traccia del numero totale di richieste di immagini Analytics inviate durante un intervallo di tempo continuo predefinito e può eseguire logica aggiuntiva se tale totale supera una determinata soglia.

Anche se il traffico da bot, spider, specifici agenti utente o un elenco specifico di indirizzi IP può essere identificato come traffico bot o altrimenti escluso dal reporting, può esserci del traffico catturato nelle suite di rapporti che altrimenti non dovrebbe essere conteggiato. Ad esempio, un numero elevato di clic o visualizzazioni di pagina durante un periodo di tempo irragionevole (ovvero circa una richiesta al secondo) potrebbe rappresentare un traffico duplicato.

L'utilizzo di questo plug-in consente di bloccare automaticamente il traffico per il resto della durata del visitatore e inoltre di identificare in modo dinamico il traffico all'interno dei report.

## Come funziona il plugin di Hit Governatore {#section_541BC639E31442D09B1C85A2FFCDC02C}

Il plug-in incrementa il valore di un cookie ogni volta che una richiesta di immagine viene inviata ai server di tracciamento e lo tiene traccia di tale operazione in un intervallo di tempo continuo. L’intervallo di tempo predefinito è un minuto, anche se tale intervallo può essere ignorato. (vedere [Implementazione](/help/implement/js-implementation/plugins/hitgovernor.md#task_D4BDB524AA294C139AFCAE2B61FEA3F2), di seguito). Se il numero totale di hit durante tale intervallo di tempo supera la soglia di hit predefinita (60), viene inviata una richiesta di immagine collegamento personalizzata finale per impostare la variabile di dati di *`exceptionFlag`* contesto. È inoltre possibile ignorare la soglia di hit predefinita.

Se lo desiderate, da quel momento in poi, è possibile impedire che il traffico venga raccolto per quel visitatore specifico per un periodo predefinito di sessanta giorni. Per bloccare il traffico è necessaria una riga di codice aggiuntiva nella funzione doPlugins, come indicato di seguito. È inoltre possibile regolare l'intervallo di tempo. La logica consente il tempo necessario per includere l'indirizzo IP del visitatore, l'agente utente o l'ID [!DNL Experience Cloud] visitatore nella logica di eccezione permanente corretta, oppure per ripristinare il periodo di timeout dopo che sono trascorsi i sessanta giorni. Se il traffico è identificato come fraudolento dal plug-in dopo sessanta giorni, il traffico viene nuovamente contrassegnato come eccezione e non viene raccolto per altri sessanta giorni.

## Generazione di rapporti {#section_E742F19B528041808454744DB2C7007C}

Non è necessario impostare variabili o eventi predefiniti. Tuttavia, consigliamo vivamente di impostare la logica delle regole di elaborazione per impostare variabili ed eventi di conseguenza. Tali variabili ed eventi personalizzati possono includere:

* [!DNL Experience Cloud] Visitor ID
* Indirizzo IP
* Agente utente
* Evento eccezione contrassegnata

La creazione di segmenti per tali variabili consentirebbe di creare segmenti e suite di rapporti virtuali per visualizzare l’impatto complessivo sul sito di tali hit ambigui.

È consigliabile utilizzare i valori acquisiti nel reporting per aggiornare le regole bot, le regole DB VISTA o le esclusioni dell'IP della società.

## Implementazione {#task_D4BDB524AA294C139AFCAE2B61FEA3F2}

Per implementare il plug-in hitGovernatore:

1. Modifica la libreria AppMeasurement.

   Per inizializzare il plug-in, includi questa riga di codice (in grassetto) all'interno della `registerPostTrackCallback` funzione nel codice libreria AppMeasurement.

   >[!NOTE]
   >
   >Sebbene la `registerPostTrackCallback` funzionalità sia inclusa nelle librerie AppMeasurement 1.8.0+, per impostazione predefinita non è inclusa in alcuna configurazione di codice personalizzata. È incluso dopo e *all'esterno* della funzione doPlugins.

   ```
    s.registerPostTrackCallback(function(){ 
    s.governor();
   }); 
   ```

   Sotto la sezione doPlugins del file AppMeasurement, includi il codice plug-in contenuto nel codice [origine](/help/implement/js-implementation/plugins/hitgovernor.md#reference_76423C81A7A342B2AC4BE41490B27DE0)plug-in, sotto.

   È possibile sovrascrivere la soglia di hit, la soglia di hit e i fotogrammi temporali di esclusione del traffico impostando queste variabili, al di fuori del plug-in stesso e preferibilmente con le altre variabili di configurazione:

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
   <td colname="col2"> <p> <code> s.hl = 60; </code> </p> </td> 
   <td colname="col3"> <p>Il numero totale di hit che non devono essere superati in un dato intervallo di tempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia tempo hit </p> </td> 
   <td colname="col2"> <p> <code> s.ht = 10; </code> </p> </td> 
   <td colname="col3"> <p>La finestra, in secondi, per la registrazione degli hit. Questo numero è diviso per sei per determinare le finestre dei tempi di scorrimento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Soglia di esclusione </p> </td> 
   <td colname="col2"> <p> <code> s.he = 60; </code> </p> </td> 
   <td colname="col3"> <p>Numero di giorni in cui il cookie di esclusione è impostato per quel visitatore. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>L'implementazione potrebbe utilizzare un nome oggetto diverso dall'oggetto "s" di analisi predefinito. In tal caso, aggiornare di conseguenza il nome dell'oggetto.

1. Configurare le regole di elaborazione.

   Questo plug-in registra le eccezioni segnalate come dati contestuali in una richiesta di immagine di tracciamento dei collegamenti. Di conseguenza, le regole di elaborazione devono essere configurate per assegnare il tracciamento delle eccezioni segnalate nelle variabili appropriate come quelle riportate di seguito.

   ![](assets/hitgov-config.png)

1. (Facoltativo) Includere il codice di blocco del traffico nei doPlugins.

   Dopo che il traffico è stato identificato come un’eccezione, tutti gli hit successivi da quel visitatore possono essere bloccati completamente includendo questo codice nella `doPlugins` funzione:

   ```
   //Check for hit governor flag 
         if(s.Util.cookieRead('s_hg')==9)s.abort=true;
   ```

   Se questo codice non è incluso, il traffico da quel visitatore sarà contrassegnato ma non bloccato.

## Codice origine plug-in {#reference_76423C81A7A342B2AC4BE41490B27DE0}

Questo codice deve essere aggiunto sotto la sezione doPlugins della libreria AppMeasurement.

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

