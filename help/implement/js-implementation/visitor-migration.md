---
description: La migrazione dei visitatori è un processo in cui il cookie ID visitatore viene migrato da un dominio all'altro.
keywords: Implementazione di Analytics
seo-description: La migrazione dei visitatori è un processo in cui il cookie ID visitatore viene migrato da un dominio all'altro.
seo-title: Migrazione dei visitatori
solution: Analytics
title: Migrazione dei visitatori
topic: Sviluppatore e implementazione
uuid: af 31928 c -85 d 7-407 f-a 583-0 c 8 f 2852 ceb 3
translation-type: tm+mt
source-git-commit: 85dbc654643f63e30cb20df7e6e9e4cff8660c05

---


# Migrazione dei visitatori

La migrazione dei visitatori è un processo in cui il cookie ID visitatore viene migrato da un dominio all'altro.

La migrazione dei visitatori consente di mantenere i cookie di identificazione dei visitatori durante la modifica dei domini di raccolta dati. I domini di raccolta dati potrebbero cambiare per i motivi seguenti:

* Moving from `2o7.net` to `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/)).

* You are implementing the [Experience Cloud Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) and are moving from a CNAME/first-party data collection domain to `2o7.net` or `omtrdc.net` ( [Regional Data Collection](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/))

* Moving from `2o7.net` or `omtrdc.net` to a cname/first-party data collection ( [First-Party Cookies)](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/).

* Passaggio da un CNAME a un altro (modifica dei domini).

Dopo che la migrazione dei visitatori è configurata, quando un utente visita il nuovo dominio senza cookie ID visitatore, il server reindirizza al nome host precedente della raccolta dati, recupera i cookie ID visitatore disponibili, quindi reindirizza nuovamente al nuovo dominio. Se un ID visitatore non viene trovato sul nome host precedente, viene generato un nuovo ID. Questo avviene solo una volta per visitatore.

## Visitor Migration Process {#section_FF0C5C5CAEF343FFA1892B29311F7160}

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
   <td colname="col1"> <p> <b>Per iniziare:</b><a href="https://helpx.adobe.com/marketing-cloud/contact-support.html" format="http" scope="external"> Contatta l'Assistenza </a> clienti con i domini che desideri migrare e il periodo di migrazione che desideri abilitare (30, 60 o 90 giorni). Assicurati di includere domini sicuri e protetti. </p> </td> 
   <td colname="col3"> <p>Create a list with the <i>exact</i> syntax for the domains you want to migrate to and migrate from. </p> 
    <ul id="ul_067EC5C7619141A6BDFBC209C9FD47E2"> 
     <li id="li_0723D948465A49C1871B81207AEDC4DC">esempio .112 .2 o 7. net &gt; metrics.example.com </li> 
     <li id="li_B0CA15A593BD4AB9802E33A3FF037C7A">esempio .102 .112 .2 o 7. net &gt; smetrics.example.com </li> 
    </ul> <p>I nomi host di migrazione sono configurati sul server di raccolta dati Adobe. L'Assistenza clienti ti permetterà di sapere quando viene apportata la modifica per pianificare il passaggio successivo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>6 ore dopo la modifica della configurazione</b>: Aggiorna le <code> variabili s. trackingserver</code> e <code> s. trackingserversecure</code> nel codice javascript di Analytics per utilizzare i nuovi server di raccolta dati. </p> </td> 
   <td colname="col3"> <p>After you make this change, use a <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Packet Analyzer</a> to verify that the Analtyics image request is going to the updated data collection server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Subito dopo aver aggiornato il codice Analytics</b>: Verifica il tuo sito per verificare che venga eseguito il reindirizzamento al dominio di raccolta dati precedente. </p> </td> 
   <td colname="col3"> <p>Use a <a href="../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258" format="dita" scope="local"> Packet Analyzer</a> to verify that when you access your site for the first time, or after clearing cookies, you see two 302 (redirect) HTTP status codes before the 200 (OK) HTTP status code. Se uno di questi reindirizzamenti non riesce, contatta immediatamente l'Assistenza clienti per accertarti che la migrazione sia configurata correttamente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Per l'intero periodo di migrazione</b>: Mantenere attivo il record DNS per il nome host precedente. </p> </td> 
   <td colname="col3"> <p>Il nome host precedente deve risolvere il DNS o la migrazione dei cookie non si verifica. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Deprecated visitorMigrationKey and visitorMigrationServer Variables {#section_32FCEE2575944D039EA0FEBFB5814259}

As of March 2013, the `visitorMigrationKey`, `visitorMigrationServer`, and `visitorMigrationServerSecure` data collection variables are deprecated and no longer used. I dati contenuti in precedenza in queste variabili sono ora memorizzati sui server Adobe per una maggiore protezione.
