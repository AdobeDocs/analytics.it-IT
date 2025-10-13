---
description: La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio all’altro.
keywords: Implementazione di Analytics
title: Migrazione dei visitatori
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: d3d5b01fe17f88d07a748fac814d2161682837c2
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 1%

---

# Migrazione dei visitatori

>[!NOTE]
>
>Se hai già implementato il servizio ID visitatore di Experience Cloud, il periodo di tolleranza non è applicabile e non deve essere abilitato.

La migrazione dei visitatori è un processo in cui i cookie dell’ID visitatore (s_vi) vengono migrati da un dominio all’altro.

La migrazione dei visitatori consente di mantenere i cookie di identificazione dei visitatori quando si modificano i domini di raccolta dati. I domini di raccolta dati potrebbero cambiare per i seguenti motivi:

* Spostamento da `2o7.net` a `adobedc.net`.

* Stai implementando il [servizio ID visitatore di Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) e stai passando da un dominio di raccolta dati CNAME/prime parti a `adobedc.net`, `2o7.net` o `omtrdc.net`

* Spostamento in una raccolta dati cname/prime parti ( [Cookie di prime parti)](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it).

* Passaggio da un CNAME a un altro (modifica dei domini).

Dopo aver configurato la migrazione dei visitatori, quando un utente visita il nuovo dominio senza un cookie ID visitatore, il server reindirizzerà al nome host di raccolta dati precedente, recupererà eventuali cookie ID visitatore disponibili e quindi reindirizzerà al nuovo dominio. Se non viene trovato un ID visitatore nel nome host precedente, viene generato un nuovo ID. Ciò si verifica solo una volta per visitatore.

## Processo di migrazione visitatore {#process}

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
   <td colname="col1"> <p> <b>Per iniziare:</b> <a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"  > Contatta l'Assistenza clienti </a> con i domini di cui vuoi eseguire la migrazione e il periodo di migrazione da abilitare (30, 60 o 90 giorni). Accertati di includere i domini non sicuri e sicuri. </p> </td> 
   <td colname="col3"> <p>Crea un elenco con la sintassi <i>exact</i> per i domini da cui desideri eseguire la migrazione e migrare. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>I nomi degli host di migrazione sono configurati nel server di raccolta dati di Adobe. L’Assistenza clienti ti informerà quando verrà effettuata la modifica in modo da poter pianificare il passaggio successivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6+ ore dopo la modifica della configurazione</b>: aggiorna le variabili <code> s.trackingServer</code> e <code> s.trackingServerSecure</code> nel codice JavaScript di Analytics per utilizzare i nuovi server di raccolta dati. </p> </td> 
   <td colname="col3"> <p>Dopo aver apportato questa modifica, utilizzare il debugger <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it"> di Experience Cloud</a> per verificare che la richiesta di immagine di Analytics venga inviata al server di raccolta dati aggiornato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immediatamente dopo l'aggiornamento del codice Analytics</b>: verifica il sito per verificare che sia in corso il reindirizzamento al dominio di raccolta dati precedente. </p> </td> 
   <td colname="col3"> <p>Utilizzare un monitoraggio dei pacchetti <a href="../implement/validate/packet-monitor.md"></a> per verificare che quando si accede al sito per la prima volta o dopo aver cancellato i cookie, vengano visualizzati due codici di stato HTTP 302 (reindirizzamento) prima del codice di stato HTTP 200 (OK). Se uno di questi reindirizzamenti non riesce, contatta immediatamente l’Assistenza clienti per assicurarti che la migrazione sia configurata correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Per l'intero periodo di migrazione</b>: mantenere attivo il record DNS per il nome host precedente. </p> </td> 
   <td colname="col3"> <p>Il nome host precedente deve essere risolto tramite DNS, altrimenti la migrazione dei cookie non verrà eseguita. </p> </td> 
  </tr> 
 </tbody> 
</table>

| Attività | Descrizione |
|--- |--- |
| Per iniziare: contatta l’Assistenza clienti con i domini di cui vuoi eseguire la migrazione e il periodo di migrazione da attivare (30, 60 o 90 giorni). Accertati di includere i domini non sicuri e sicuri. | Crea un elenco con la sintassi esatta per i domini da cui vuoi eseguire la migrazione e da cui vuoi eseguire la migrazione.<ul><li>example.112.2o7.net > metrics.example.com</li><li>example.102.112.2o7.net > smetrics.example.com</li></ul>I nomi degli host di migrazione sono configurati nel server di raccolta dati di Adobe. L’Assistenza clienti ti informerà quando verrà effettuata la modifica in modo da poter pianificare il passaggio successivo. |
| 6+ ore dopo la modifica della configurazione: aggiorna le variabili `s.trackingServer` e `s.trackingServerSecure` nel codice JavaScript di Analytics per utilizzare i nuovi server di raccolta dati. | Dopo aver apportato questa modifica, utilizzare [Experience Cloud debugger](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it) per verificare che la richiesta di immagine di Analytics venga inviata al server di raccolta dati aggiornato. |
| Immediatamente dopo l’aggiornamento del codice di Analytics: verifica sul sito che sia in corso il reindirizzamento al dominio di raccolta dati precedente. | Utilizza un [monitoraggio pacchetti](../implement/validate/packet-monitor.md) per verificare che quando accedi al sito per la prima volta o dopo aver cancellato i cookie, vengano visualizzati due codici di stato HTTP 302 (reindirizzamento) prima del codice di stato HTTP 200 (OK). Se uno di questi reindirizzamenti non riesce, contatta immediatamente l’Assistenza clienti per assicurarti che la migrazione sia configurata correttamente. |
| Per l’intero periodo di migrazione: tieni attivo il record DNS per il nome host precedente. | Il nome host precedente deve essere risolto tramite DNS, altrimenti la migrazione dei cookie non verrà eseguita. |