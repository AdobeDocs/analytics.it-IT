---
description: Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando attributi o valori corrispondono a condizioni definite, i valori possono essere impostati ed eliminati ed eventi.
seo-description: Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando attributi o valori corrispondono a condizioni definite, i valori possono essere impostati ed eliminati ed eventi.
seo-title: Funzionamento delle regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Funzionamento delle regole di elaborazione
topic: Strumenti di amministrazione
uuid: 19 c 31 f 94-c 8 d 8-47 b 1-97 fa -29 ed 87 ed 98
translation-type: tm+mt
source-git-commit: ad6ba22acf6996aa038c5a3252cae8bddbf0b36a

---


# Funzionamento delle regole di elaborazione

Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando attributi o valori corrispondono a condizioni definite, i valori possono essere impostati ed eliminati ed eventi.

Le regole di elaborazione vengono applicate ai dati durante la raccolta e le regole vengono applicate a tutti i dati che avvengono attraverso le librerie appmeasurement e tramite l'API di inserimento dati. Le regole di elaborazione sono valide anche per le origini dati complete e di registro. These sources contain data that represents a *`hit`* or an action that a user takes. Le regole di elaborazione non si applicano ad altre sorgenti dati.

## Important Concepts {#section_EB138775E7C64C74B0D1D3213F7A823C}

La tabella seguente contiene concetti chiave da comprendere quando si utilizzano le regole di elaborazione:

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Concept </p> </th> 
   <th colname="col2" class="entry"> <p>Dettagli </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Le regole si applicano a una singola suite di rapporti. </p> </td> 
   <td colname="col2"> <p> <a href="../../../../admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md#task_6E4B82FCA687409B88F17EAFC353755D" type="task" format="dita" scope="local"> Copiare le regole di elaborazione in un'altra suite di rapporti </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate nell'ordine elencato. </p> </td> 
   <td colname="col2"> <p>Se un'azione modifica un valore, le condizioni successive utilizzano il nuovo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate immediatamente alla suite di rapporti dopo che sono state salvate. </p> </td> 
   <td colname="col2"> <p>Le modifiche dalle regole di elaborazione devono essere visibili nella suite di rapporti entro minuti di salvataggio. When testing processing rules, we recommend configuring <a href="../../../../admin/admin/realtime/t-realtime-admin.md#task_1CD03E9B6BDB48B08E9E612183557F40" format="dita" scope="local"> real-time reports</a> in your test report suite so you can quickly see the results of a processing rule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione sono l'unico modo per accedere alle variabili di dati di contesto. </p> </td> 
   <td colname="col2"> <p> <a href="../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7" format="dita" scope="local"> Copiare una variabile dati di contesto in una evar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate prima delle regole VISTA e del canale di marketing. </p> </td> 
   <td colname="col2"> <p> <a href="../../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E" type="concept" format="dita" scope="local"> Ordine di elaborazione </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli hit non possono essere esclusi. </p> </td> 
   <td colname="col2"> <p>Puoi utilizzare le regole VISTA per escludere gli hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La stringa di prodotto, il referente e l'agente utente non possono essere modificati. </p> </td> 
   <td colname="col2"> <p>Il referente e l'agente utente sono di sola lettura. La stringa di prodotto non è disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli attributi e le classificazioni dei dispositivi mobili non sono disponibili. </p> </td> 
   <td colname="col2"> <p>La ricerca del dispositivo mobile si verifica prima delle regole di elaborazione, ma gli attributi non sono disponibili nelle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I parametri delle stringhe di query non possono essere letti oltre i primi 255 caratteri di un URL se javascript appmeasurement H .25 .2 o versioni precedenti è in esecuzione. Javascript appmeasurement H .25 .3 e versioni successive fornisce l'URL completo, inclusi tutti i parametri delle stringhe query alle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Effettua l'aggiornamento a H .25 .3 o versioni successive oppure leggi i parametri delle stringhe di query da lato client lungo e archivia i valori nelle variabili Dati di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I valori delle stringhe di query devono essere codificati in Unicode o UTF -8 per essere letti dalle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Ciò potrebbe influire sui caratteri multibyte che vengono passati utilizzando stringhe di query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sei limitato a 150 regole con 30 condizioni ciascuna per ogni suite di rapporti. </p> </td> 
   <td colname="col2"> <p>I limiti delle regole di elaborazione sono per suite di rapporti, non per azienda. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione devono essere configurate per recuperare le variabili di dati di contesto prima dell'invio dei dati. </p> </td> 
   <td colname="col2"> <p>Le regole di elaborazione vengono applicate come chiamate server. I valori memorizzati nelle variabili di dati di contesto vengono eliminati se non vengono copiati utilizzando le regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il confronto dei valori nell'interfaccia utente non fa distinzione tra maiuscole e minuscole. </p> </td> 
   <td colname="col2"> <p> <a href="../../../../admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md#concept_958E924BCCBB4BBA91CE91C977FE5151" type="concept" format="dita" scope="local"> Pulizia dei valori in un rapporto </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I nomi di variabile dati contestuali possono contenere solo caratteri alfanumerici, caratteri di sottolineatura e punti. Vengono rimossi eventuali caratteri aggiuntivi. </p> </td> 
   <td colname="col2"> <p>For example, The context data variable <code> login_page-home</code> automatically becomes <code> login_pagehome</code>. All data sent to the <code> login_page-home</code> variable is allocated under <code> login_pagehome</code>. </p> <p>Nell'interfaccia delle regole di elaborazione non è possibile aggiungere variabili di dati di contesto contenenti caratteri non supportati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caret (^) è un carattere speciale nel sistema delle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Per associare un singolo carattere caret, usate due caratteri caret (^ ^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Processing Rule Conditions {#section_387390EEE9BA4DA98698522A84326DB4}

Condizioni controllate le variabili di pagina per un valore corrispondente o se è presente un valore. È possibile aggiungere più condizioni ed è possibile selezionare se tutte le condizioni devono essere soddisfatte.

È possibile creare una regola senza condizioni per eseguire sempre le azioni definite.

Le variabili non vengono verificate automaticamente per i valori prima delle azioni. Ad esempio, Prop 1 contiene un valore "something" e evar 1 è vuoto. Se impostate Prop 1 su uguar 1, entrambi i valori saranno vuoti. Se occorre evitare questa aggiunta di una condizione per verificare la presenza di un valore.

## Processing Rule Actions {#section_E2285C9D008442C7BF136E52A9A4CC06}

Le azioni impostano le variabili di pagina, eliminate le variabili di pagina o attivano gli eventi. Le azioni possono anche concatenare valori da visualizzare in un report.

For example, you might want to display `category:product` by concatenating two variables.
