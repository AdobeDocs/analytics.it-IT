---
description: La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio a un altro.
keywords: Implementazione di Analytics
title: Migrazione dei visitatori
topic-fix: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 6%

---

# Migrazione dei visitatori

La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio a un altro.

La migrazione dei visitatori ti consente di conservare i cookie di identificazione dei visitatori quando modifichi i domini di raccolta dati. I domini di raccolta dati potrebbero cambiare per i motivi seguenti:

* Passaggio da `2o7.net` a `adobedc.net`.

* Stai implementando il [Servizio ID visitatore di Experience Cloud](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) e stai passando da un dominio di raccolta dati CNAME/di prime parti a `adobedc.net`, `2o7.net` o `omtrdc.net`

* Passaggio a una raccolta dati di prima parte ( [Cookie di prima parte)](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-first-party.html).

* Passaggio da un CNAME a un altro (modifica dei domini).

Dopo la configurazione della migrazione dei visitatori, quando un utente visita il nuovo dominio senza un cookie ID visitatore, il server reindirizza al nome host della raccolta dati precedente, recupera eventuali cookie ID visitatore disponibili e quindi reindirizza al nuovo dominio. Se non viene trovato un ID visitatore sul nome host precedente, viene generato un nuovo ID. Questo si verifica solo una volta per visitatore.

## Processo di migrazione dei visitatori {#section_FF0C5C5CAEF343FFA1892B29311F7160}

Nella tabella seguente sono elencate le attività necessarie per la migrazione dei visitatori:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Per iniziare: </b> <a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"  > contatta l’Assistenza clienti  </a> con i domini che desideri trasferire e il periodo di migrazione che desideri abilitare (30, 60 o 90 giorni). Accertati di includere i domini non sicuri e sicuri. </p> </td> 
   <td colname="col3"> <p>Crea un elenco con la sintassi <i>esatta</i> per i domini a cui vuoi eseguire la migrazione e da cui vuoi eseguire la migrazione. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetriche.example.com </li> 
    </ul> <p>I nomi host di migrazione sono configurati su Adobe Data Collection Server. L’Assistenza clienti ti informerà quando la modifica è stata apportata in modo da poter pianificare il passaggio successivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6+ ore dopo la modifica</b> della configurazione: Aggiorna le variabili  <code> s.trackingServer</code> e  <code> s.trackingServerSecure</code> nel codice JavaScript di Analytics per utilizzare i nuovi server di raccolta dati. </p> </td> 
   <td colname="col3"> <p>Dopo aver apportato questa modifica, utilizza il <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=en"> debugger di Experience Cloud</a> per verificare che la richiesta di immagine Analytics vada al server di raccolta dati aggiornato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immediatamente dopo aver aggiornato il codice</b> Analytics: Verifica il sito per verificare che il reindirizzamento al dominio di raccolta dati precedente si verifichi. </p> </td> 
   <td colname="col3"> <p>Utilizza un <a href="../implement/validate/packet-monitor.md"> packet monitor</a> per verificare che quando accedi al tuo sito per la prima volta o dopo aver cancellato i cookie, visualizzi due codici di stato HTTP 302 (reindirizzamento) prima del codice di stato HTTP 200 (OK). Se uno di questi reindirizzamenti non riesce, contatta immediatamente l’Assistenza clienti per assicurarti che la migrazione sia configurata correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Per l’intero periodo</b> di migrazione: Mantieni attivo il record DNS del nome host precedente. </p> </td> 
   <td colname="col3"> <p>Il nome host precedente deve essere risolto tramite DNS, altrimenti la migrazione dei cookie non verrà eseguita. </p> </td> 
  </tr> 
 </tbody> 
</table>
