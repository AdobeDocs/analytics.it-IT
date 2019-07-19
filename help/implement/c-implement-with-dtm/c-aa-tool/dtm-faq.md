---
description: Domande frequenti sulla configurazione automatica della distribuzione Adobe Analytics. Il metodo di configurazione automatico gestisce il codice appmeasurement.
keywords: Gestione tag dinamica; plug-in; staging; effetto sulle impostazioni correnti; cronologia revisioni; potenziali insidie; ID suite di rapporti; codice valuta; server di tracciamento; ssl tracking server; codice personalizzato; gestione libreria
seo-description: Domande frequenti sulla configurazione automatica della distribuzione Adobe Analytics. Il metodo di configurazione automatico gestisce il codice appmeasurement.
seo-title: Domande frequenti sullo strumento Adobe Analytics
solution: Marketing Cloud, Analytics, Target, Gestione tag dinamica
title: Domande frequenti sullo strumento Adobe Analytics
uuid: 8 fcef 893-e 305-4 a 95-a 033-9066 a 56 b 09 cd
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Domande frequenti sullo strumento Adobe Analytics

Domande frequenti sulla configurazione automatica della distribuzione Adobe Analytics. The automatic configuration method manages the [!DNL AppMeasurement] code for you.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Dove posso inserire i miei plug-in durante l'implementazione di Adobe Analytics tramite DTM? </p> </td> 
   <td colname="col2"> <p> If using DTM to manually host the <code> s_code</code>, plugins can be added in the same editor as the hosted <code> s_code</code>, just as it would be in a typical Adobe Analytics implementation. </p> <p>However, it is also an option to place the plugins in the editor within the <span class="term"> Customize Page Code</span> section of the tool settings. Entrambi i metodi di implementazione dovrebbero essere altrettanto efficaci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se esegui modifiche di configurazione nella nuova versione dello strumento, posso provare nello staging prima di pubblicare in produzione? </p> </td> 
   <td colname="col2"> <p>Sì.  </p> <p>Tutte le modifiche possono essere testate nello staging esattamente come faresti normalmente prima di distribuire in un ambiente di produzione. Se si decide di non pubblicare, poiché si notano problemi nello staging, il codice di produzione continuerà a funzionare come prima che venisse rilasciata la nuova integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se passaggio dalla configurazione manuale (impostazione predefinita degli strumenti esistenti) alla configurazione automatica, le impostazioni correnti saranno influenzate? </p> </td> 
   <td colname="col2"> <p>No. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se passa dalla gestione manuale delle librerie a Gestito da Adobe, le impostazioni o il codice correnti saranno interessati? </p> </td> 
   <td colname="col2"> <p>Any user code that you have specified is overwritten with the base <span class="keyword"> AppMeasurement</span> library. You must move this code to the new <span class="wintitle"> Custom Page Code</span> section at the end of the tool configuration so that the code continues executing. This method allows the <span class="keyword"> AppMeasurement</span> library to be managed (and upgraded) separately from the user's custom code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Will the revision history for the <span class="keyword"> Adobe Analytics</span> tool be retained when the new integration is released? </p> </td> 
   <td colname="col2"> <p>Sì.  </p> </td> 
  </tr> 
 </tbody> 
</table>

See [Add Adobe Analytics Tool](../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8) for configuration information.

## Potential Pitfalls {#section_201BF9E0EB7D4BC2B72A617543C2030B}

There is a small chance that the integration could cause data collection issues if you currently use [!DNL Adobe Analytics]. Questi problemi possono presentarsi solo se la libreria viene pubblicata in seguito alla pubblicazione. (Il codice di produzione rimane intatto fino alla pubblicazione.)

Per evitare questi problemi, assicurati che:

* Gli ID delle suite di rapporti vengono immessi correttamente nello strumento.
* Report suite IDs in the tool match the IDs in the [!DNL AppMeasurement] code.
* I campi della valuta, del set di caratteri, di tracciamento e del server di tracciamento SSL sono impostati correttamente con i valori supportati.
* Custom code is defined in [!DNL Library Management].

