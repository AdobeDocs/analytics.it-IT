---
description: La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio all’altro.
keywords: Analytics Implementation
title: Migrazione dei visitatori
topic: Developer and implementation
uuid: af31928c-85d7-407f-a583-0c8f2852ceb3
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 6%

---


# Migrazione dei visitatori

La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio all’altro.

La migrazione dei visitatori consente di mantenere i cookie di identificazione dei visitatori quando si modificano i domini di raccolta dei dati. I domini di raccolta dati potrebbero essere modificati per i motivi seguenti:

* Spostarsi da `2o7.net` a `adobedc.net`.

* Stai implementando il servizio [ID visitatori di](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) Experience Cloud e stai passando da un dominio di raccolta dati CNAME/di prime parti a `adobedc.net`, `2o7.net` oppure `omtrdc.net`

* Passaggio a una raccolta di dati di prime parti (cookie di [prime parti)](https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-first-party.html).

* Passaggio da un CNAME a un altro (modifica dei domini).

Dopo la configurazione della migrazione dei visitatori, quando un utente visita il nuovo dominio senza un cookie ID visitatore, il server reindirizza al nome host di raccolta dati precedente, recupera tutti i cookie ID visitatore disponibili e quindi reindirizza al nuovo dominio. Se non viene trovato un ID visitatore sul nome host precedente, viene generato un nuovo ID. Ciò si verifica solo una volta per visitatore.

## Processo di migrazione dei visitatori {#section_FF0C5C5CAEF343FFA1892B29311F7160}

Nella tabella seguente sono elencate le attività richieste per la migrazione dei visitatori:

<table id="table_7B2535FC3E264216A299686415C6B21C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attività </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Per iniziare:</b> <a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"  > Contatta l’Assistenza clienti </a> con i domini che vuoi trasferire e il periodo di migrazione che desideri attivare (30, 60 o 90 giorni). Accertatevi di includere i domini non sicuri e protetti. </p> </td> 
   <td colname="col3"> <p>Create un elenco con la sintassi <i>esatta</i> per i domini da cui eseguire la migrazione. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metriche.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetriche.example.com </li> 
    </ul> <p>I nomi host di migrazione sono configurati  server di raccolta dati di Adobe. L'Assistenza clienti ti informerà quando è stata apportata la modifica per pianificare il passaggio successivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6+ ore dopo la modifica</b>della configurazione: Aggiorna le variabili <code> s.trackingServer</code> e <code> s.trackingServerSecure</code> il codice JavaScript di Analytics per utilizzare i nuovi server di raccolta dati. </p> </td> 
   <td colname="col3"> <p>Dopo aver apportato questa modifica, usa il debugger <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=en"> di Experience Cloud</a>  per verificare che la richiesta di immagine di Analytics vada al server di raccolta dati aggiornato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immediatamente dopo aver aggiornato il codice</b>Analytics: Verificare il sito per verificare che si verifichi il reindirizzamento al dominio di raccolta dati precedente. </p> </td> 
   <td colname="col3"> <p>Usate un <a href="../implement/validate/packet-monitor.md"> monitor</a> pacchetti per verificare che quando accedete al sito per la prima volta, o dopo aver cancellato i cookie, vengano visualizzati due codici di stato HTTP 302 (reindirizzamento) prima del codice di stato HTTP 200 (OK). Se uno di questi reindirizzamenti non riesce, contatta immediatamente l'Assistenza clienti per verificare che la migrazione sia configurata correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Per l’intero periodo</b>di migrazione: Mantenere attivo il record DNS per il nome host precedente. </p> </td> 
   <td colname="col3"> <p>Il nome host precedente deve essere risolto tramite DNS o la migrazione dei cookie non verrà eseguita. </p> </td> 
  </tr> 
 </tbody> 
</table>
