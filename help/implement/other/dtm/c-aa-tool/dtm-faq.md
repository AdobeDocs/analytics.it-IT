---
description: Domande frequenti sulla configurazione automatica della distribuzione Adobe Analytics . Il metodo di configurazione automatico gestisce il codice AppMeasurement per voi.
keywords: Dynamic Tag Management;plug-ins;staging;effect on current settings;revision history;potential pitfalls;report suite id;currency code;tracking server;ssl tracking server;custom code;library management
solution: Experience Cloud,Analytics,Target
title: Domande frequenti sullo strumento Adobe Analytics
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 4%

---


# Domande frequenti sullo strumento Adobe Analytics

Domande frequenti sulla configurazione automatica della distribuzione Adobe Analytics . Il metodo di configurazione automatica gestisce il [!DNL AppMeasurement] codice.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Dove si posizionano i plug-in durante l'implementazione  Adobe Analytics tramite DTM? </p> </td> 
   <td colname="col2"> <p> Se utilizzate Gestione dinamica dei tag per ospitare manualmente i <code> s_code</code>, i plug-in possono essere aggiunti nello stesso editor in hosting <code> s_code</code>, esattamente come per una tipica implementazione Adobe Analytics . </p> <p>Tuttavia, è anche possibile inserire i plug-in nell’editor nella sezione <span class="term"> Personalizza codice</span> pagina delle impostazioni dello strumento. Entrambi i metodi di attuazione dovrebbero essere altrettanto efficaci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se si apportano modifiche alla configurazione nella nuova versione dello strumento, è possibile eseguire il test nell'area di gestione temporanea prima della pubblicazione in produzione? </p> </td> 
   <td colname="col2"> <p>Sì. </p> <p>Tutte le modifiche possono essere testate nell'area di gestione temporanea, come avviene normalmente prima dell'implementazione in un ambiente di produzione. Se scegliete di non pubblicare, poiché notate dei problemi nell'area di gestione temporanea, il codice di produzione continuerà a funzionare come prima del rilascio della nuova integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se passo dalla configurazione manuale (impostazione predefinita per gli strumenti esistenti) alla configurazione automatica, le impostazioni correnti saranno influenzate? </p> </td> 
   <td colname="col2"> <p>No. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se si passa dalla gestione manuale della libreria a Gestito da  Adobe, le impostazioni o il codice correnti saranno interessati? </p> </td> 
   <td colname="col2"> <p>Il codice utente specificato viene sovrascritto con la libreria <span class="keyword"> AppMeasurement</span> di base. È necessario spostare questo codice nella nuova sezione Codice <span class="wintitle"></span> pagina personalizzato alla fine della configurazione dello strumento in modo che il codice continui ad essere eseguito. Questo metodo consente di gestire (e aggiornare) la libreria <span class="keyword"> AppMeasurement</span> separatamente dal codice personalizzato dell'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La cronologia delle revisioni per <span class="keyword"> lo strumento Adobe Analytics</span>  verrà mantenuta al momento del rilascio della nuova integrazione? </p> </td> 
   <td colname="col2"> <p>Sì. </p> </td> 
  </tr> 
 </tbody> 
</table>

Consultate [Aggiungere  Adobe Analytics Tool](/help/implement/other/dtm/c-aa-tool/analytics-dtm.md) per informazioni sulla configurazione.

## Potenziali insidie {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Esiste una piccola possibilità che l&#39;integrazione possa causare problemi di raccolta dei dati se si utilizza [!DNL Adobe Analytics]. Questi problemi possono presentarsi solo se la libreria viene pubblicata in produzione dopo il rilascio. (il codice di produzione rimane intatto finché non viene effettuata la pubblicazione).

Per evitare questi problemi, assicurati che:

* Gli ID suite di rapporti vengono immessi correttamente nello strumento.
* Gli ID suite di rapporti nello strumento corrispondono agli ID nel [!DNL AppMeasurement] codice.
* I campi di configurazione del codice valuta, del set di caratteri, del server di tracciamento e del server di tracciamento SSL sono impostati correttamente con i valori supportati.
* Il codice personalizzato è definito in [!DNL Library Management].

