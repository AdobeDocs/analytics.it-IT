---
description: Domande frequenti sulla configurazione automatica della distribuzione di Adobe Analytics. Il metodo di configurazione automatico gestisce il codice AppMeasurement per voi.
keywords: Gestione tag dinamica;plugin;staging;effetto sulle impostazioni correnti;cronologia revisioni;potenziali insidie;ID suite di rapporti;codice valuta;server di tracciamento;ssl tracking server;codice personalizzato;gestione libreria
seo-description: Domande frequenti sulla configurazione automatica della distribuzione di Adobe Analytics. Il metodo di configurazione automatico gestisce il codice AppMeasurement per voi.
seo-title: Domande frequenti sullo strumento Adobe Analytics
solution: Experience Cloud,Analytics,Target,Gestione tag dinamica
title: Domande frequenti sullo strumento Adobe Analytics
uuid: 8fcef893-e305-4a95-a033-9066a56b09cd
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Domande frequenti sullo strumento Adobe Analytics

Domande frequenti sulla configurazione automatica della distribuzione di Adobe Analytics. Il metodo di configurazione automatica gestisce il [!DNL AppMeasurement] codice.

<table id="table_A50D00E2C47A473B92DA800FB08FE640"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> Dove si trovano i plug-in per l'implementazione di Adobe Analytics tramite DTM? </p> </td> 
   <td colname="col2"> <p> Se utilizzate Gestione dinamica dei tag per ospitare manualmente il <code> codice</code>s_code, i plug-in possono essere aggiunti nello stesso editor del codice <code> s_code</code>ospitato, esattamente come in una tipica implementazione di Adobe Analytics. </p> <p>Tuttavia, è anche possibile inserire i plug-in nell’editor nella sezione <span class="term"> Personalizza codice</span> pagina delle impostazioni dello strumento. Entrambi i metodi di attuazione dovrebbero essere altrettanto efficaci. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se si apportano modifiche alla configurazione nella nuova versione dello strumento, è possibile eseguire il test nell'area di gestione temporanea prima della pubblicazione in produzione? </p> </td> 
   <td colname="col2"> <p>Sì.  </p> <p>Tutte le modifiche possono essere testate nell'area di gestione temporanea, come avviene normalmente prima dell'implementazione in un ambiente di produzione. Se scegliete di non pubblicare, poiché notate dei problemi nell'area di gestione temporanea, il codice di produzione continuerà a funzionare come prima del rilascio della nuova integrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se passo dalla configurazione manuale (impostazione predefinita per gli strumenti esistenti) alla configurazione automatica, le impostazioni correnti saranno influenzate? </p> </td> 
   <td colname="col2"> <p>No. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se si passa dalla gestione manuale della libreria a quella gestita da Adobe, le impostazioni o il codice correnti saranno interessati? </p> </td> 
   <td colname="col2"> <p>Il codice utente specificato viene sovrascritto con la libreria <span class="keyword"> AppMeasurement</span> di base. È necessario spostare questo codice nella nuova sezione Codice <span class="wintitle"></span> pagina personalizzato alla fine della configurazione dello strumento in modo che il codice continui ad essere eseguito. Questo metodo consente di gestire (e aggiornare) la libreria <span class="keyword"> AppMeasurement</span> separatamente dal codice personalizzato dell'utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La cronologia delle revisioni per lo strumento <span class="keyword"> Adobe Analytics</span> verrà mantenuta al momento del rilascio della nuova integrazione? </p> </td> 
   <td colname="col2"> <p>Sì.  </p> </td> 
  </tr> 
 </tbody> 
</table>

Per informazioni sulla configurazione, consulta [Aggiunta di Adobe Analytics Tool](../../../implement/c-implement-with-dtm/c-aa-tool/analytics-dtm.md#concept_FBA6679A0B79490F8296437F11E5E4F8) .

## Potenziali insidie {#section_201BF9E0EB7D4BC2B72A617543C2030B}

Esiste una piccola possibilità che l'integrazione possa causare problemi di raccolta dei dati se si utilizza [!DNL Adobe Analytics]. Questi problemi possono presentarsi solo se la libreria viene pubblicata in produzione dopo il rilascio. (il codice di produzione rimane intatto finché non viene effettuata la pubblicazione).

Per evitare questi problemi, assicurati che:

* Gli ID suite di rapporti vengono immessi correttamente nello strumento.
* Gli ID suite di rapporti nello strumento corrispondono agli ID nel [!DNL AppMeasurement] codice.
* I campi di configurazione del codice valuta, del set di caratteri, del server di tracciamento e del server di tracciamento SSL sono impostati correttamente con i valori supportati.
* Il codice personalizzato è definito in [!DNL Library Management].

