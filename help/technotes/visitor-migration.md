---
description: La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio all’altro.
keywords: Implementazione di Analytics
title: Migrazione dei visitatori
topic-fix: Developer and implementation
feature: Analytics Basics
exl-id: d44628c8-902f-4e60-b819-41d5537407d8
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# Migrazione dei visitatori

La migrazione dei visitatori è un processo in cui il cookie dell’ID visitatore viene migrato da un dominio all’altro.

La migrazione dei visitatori consente di mantenere i cookie di identificazione dei visitatori quando si modificano i domini di raccolta dati. I domini di raccolta dati potrebbero cambiare per i seguenti motivi:

* Spostamento da `2o7.net` a `adobedc.net`.

* Stai implementando [Servizio ID visitatore Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it) e si stanno spostando da un dominio di raccolta dati CNAME/prime parti a `adobedc.net`, `2o7.net` o `omtrdc.net`

* Passaggio a una raccolta dati cname/prime parti ( [Cookie di prime parti)](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html?lang=it).

* Passaggio da un CNAME a un altro (modifica dei domini).

Dopo aver configurato la migrazione dei visitatori, quando un utente visita il nuovo dominio senza un cookie ID visitatore, il server reindirizzerà al nome host di raccolta dati precedente, recupererà eventuali cookie ID visitatore disponibili e quindi reindirizzerà al nuovo dominio. Se non viene trovato un ID visitatore nel nome host precedente, viene generato un nuovo ID. Ciò si verifica solo una volta per visitatore.

## Processo di migrazione visitatore {#section_FF0C5C5CAEF343FFA1892B29311F7160}

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
   <td colname="col1"> <p> <b>Per iniziare:</b> <a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html"  > Contatta l’Assistenza clienti </a> con i domini di cui vuoi eseguire la migrazione e il periodo di migrazione da abilitare (30, 60 o 90 giorni). Accertati di includere i domini non sicuri e sicuri. </p> </td> 
   <td colname="col3"> <p>Creare un elenco con <i>esatto</i> sintassi per i domini dai quali eseguire la migrazione e la migrazione. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">example.112.2o7.net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">example.102.112.2o7.net &gt; smetrics.example.com </li> 
    </ul> <p>I nomi host di migrazione sono configurati nel server di raccolta dati Adobe. L’Assistenza clienti ti informerà quando verrà effettuata la modifica in modo da poter pianificare il passaggio successivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Più di 6 ore dopo la modifica della configurazione</b>: aggiorna il <code> s.trackingServer</code> e <code> s.trackingServerSecure</code> variabili nel codice JavaScript di Analytics per utilizzare i nuovi server di raccolta dati. </p> </td> 
   <td colname="col3"> <p>Dopo aver apportato questa modifica, utilizza <a href="https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=it"> Debugger Experience Cloud</a> per verificare che la richiesta di immagine Analytics stia andando al server di raccolta dati aggiornato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Immediatamente dopo l’aggiornamento del codice Analytics</b>: esegui il test del sito per verificare che sia in corso il reindirizzamento al dominio di raccolta dati precedente. </p> </td> 
   <td colname="col3"> <p>Utilizza un <a href="../implement/validate/packet-monitor.md"> monitor pacchetto</a> per verificare che quando accedi al sito per la prima volta o dopo aver cancellato i cookie, vengano visualizzati due codici di stato HTTP 302 (reindirizzamento) prima del codice di stato HTTP 200 (OK). Se uno di questi reindirizzamenti non riesce, contatta immediatamente l’Assistenza clienti per assicurarti che la migrazione sia configurata correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Per l’intero periodo di migrazione</b>: mantiene attivo il record DNS per il nome host precedente. </p> </td> 
   <td colname="col3"> <p>Il nome host precedente deve essere risolto tramite DNS, altrimenti la migrazione dei cookie non verrà eseguita. </p> </td> 
  </tr> 
 </tbody> 
</table>
