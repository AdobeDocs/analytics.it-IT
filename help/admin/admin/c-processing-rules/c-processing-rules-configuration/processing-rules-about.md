---
description: Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono a condizioni definite, i valori possono essere impostati ed eliminati e gli eventi possono essere impostati.
seo-description: Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono a condizioni definite, i valori possono essere impostati ed eliminati e gli eventi possono essere impostati.
seo-title: Funzionamento delle regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Funzionamento delle regole di elaborazione
topic: Strumenti di amministrazione
uuid: 19c31f94-c8d8-47b1-97fa-29ed98c94e87
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Funzionamento delle regole di elaborazione

Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono a condizioni definite, i valori possono essere impostati ed eliminati e gli eventi possono essere impostati.

Le regole di elaborazione vengono applicate ai dati durante la raccolta e a tutti i dati che arrivano tramite le librerie AppMeasurement e tramite l'API di inserimento dati. Le regole di elaborazione si applicano anche alle origini dati complete e log. Queste origini contengono dati che rappresentano un'azione *`hit`* o un'azione eseguita da un utente. Le regole di elaborazione non si applicano ad altre origini dati.

## Concetti importanti {#section_EB138775E7C64C74B0D1D3213F7A823C}

La tabella seguente contiene i concetti chiave che è necessario comprendere quando si utilizzano le regole di elaborazione:

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Concetto </p> </th> 
   <th colname="col2" class="entry"> <p>Dettagli </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Le regole si applicano a una singola suite di rapporti. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md" type="task" format="dita" scope="local"> Copiare le regole di elaborazione in un'altra suite di rapporti </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate nell'ordine indicato. </p> </td> 
   <td colname="col2"> <p>Se un'azione modifica un valore, le condizioni successive utilizzano il nuovo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate immediatamente alla suite di rapporti dopo il salvataggio. </p> </td> 
   <td colname="col2"> <p>Le modifiche apportate alle regole di elaborazione devono essere visibili nella suite di rapporti entro pochi minuti dal salvataggio. Durante il test delle regole di elaborazione, consigliamo di configurare rapporti <a href="/help/admin/admin/realtime/t-realtime-admin.md" format="dita" scope="local"></a> in tempo reale nella suite di rapporti di prova in modo da visualizzare rapidamente i risultati di una regola di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione sono l'unico modo per accedere alle variabili di dati di contesto. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md" format="dita" scope="local"> Copiare una variabile di dati di contesto in una eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate prima delle regole VISTA e Marketing Channel. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md" type="concept" format="dita" scope="local"> Ordine di elaborazione </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli hit non possono essere esclusi. </p> </td> 
   <td colname="col2"> <p>Potete utilizzare le regole VISTA per escludere gli hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impossibile modificare la stringa prodotto, il referente e l'agente utente. </p> </td> 
   <td colname="col2"> <p>Il referente e l'agente utente sono di sola lettura. La stringa prodotto non è disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Attributi e classificazioni del dispositivo mobile non disponibili. </p> </td> 
   <td colname="col2"> <p>La ricerca del dispositivo mobile viene eseguita prima delle regole di elaborazione, ma gli attributi non sono disponibili nelle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I parametri delle stringhe di query non possono essere letti oltre i primi 255 caratteri di un URL se si esegue JavaScript AppMeasurement H.25.2 o versioni precedenti. JavaScript AppMeasurement H.25.3 e versioni successive forniscono l’URL completo, inclusi tutti i parametri della stringa di query per le regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Aggiornamento a H.25.3 o versione successiva oppure lettura dei parametri di stringa di query da URL lunghi sul lato client e memorizzazione dei valori nelle variabili di dati contestuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I valori delle stringhe di query devono essere codificati in Unicode o UTF-8 per essere letti dalle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Ciò potrebbe interessare i caratteri multibyte passati utilizzando stringhe di query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hai un limite di 150 regole con 30 condizioni per ciascuna suite di rapporti. </p> </td> 
   <td colname="col2"> <p>I limiti delle regole di elaborazione sono per suite di rapporti, non per società. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione devono essere configurate per recuperare le variabili dei dati di contesto prima dell'invio dei dati. </p> </td> 
   <td colname="col2"> <p>Le regole di elaborazione vengono applicate quando vengono inviate chiamate al server. I valori memorizzati nelle variabili di dati di contesto vengono scartati se non vengono copiati utilizzando le regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I confronti di valori nell’interfaccia utente non fanno distinzione tra maiuscole e minuscole. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md" type="concept" format="dita" scope="local"> Pulizia dei valori in un report </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I nomi delle variabili di dati di contesto possono contenere solo caratteri alfanumerici, caratteri di sottolineatura e punti. Eventuali caratteri aggiuntivi vengono rimossi. </p> </td> 
   <td colname="col2"> <p>Ad esempio, la variabile di dati contestuali <code> login_page-home</code> diventa <code> login_pagehome</code>automaticamente. Tutti i dati inviati alla <code> login_page-home</code> variabile sono assegnati in <code> login_pagehome</code>. </p> <p>Le variabili di dati di contesto contenenti caratteri non supportati non possono essere aggiunte nell'interfaccia Regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caret (^) è un carattere speciale nel sistema di regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Per far corrispondere un singolo carattere di inserimento, utilizzate due caratteri di inserimento (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Condizioni regola di elaborazione {#section_387390EEE9BA4DA98698522A84326DB4}

Le condizioni controllano le variabili di pagina per un valore corrispondente o se è presente un valore. È possibile aggiungere più condizioni e selezionare se tutte le condizioni devono essere soddisfatte.

È possibile creare una regola senza condizioni per eseguire sempre azioni definite.

Prima dell'esecuzione delle azioni, le variabili non vengono verificate automaticamente per i valori. Ad esempio, Prop1 contiene il valore "qualcosa" e eVar1 è vuoto. Se impostate Prop1 su uguale a eVar1, entrambi i valori saranno vuoti. Per evitare questa situazione, aggiungere una condizione per verificare la presenza di un valore.

## Azioni regole di elaborazione {#section_E2285C9D008442C7BF136E52A9A4CC06}

Le azioni impostano variabili di pagina, eliminano variabili di pagina o attivano eventi. Le azioni possono anche concatenare valori da visualizzare in un report.

Ad esempio, potrebbe essere utile visualizzare `category:product` concatenando due variabili.
