---
description: Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono alle condizioni definite, è possibile impostare ed eliminare i valori e impostare gli eventi.
subtopic: Processing rules
title: Funzionamento delle regole di elaborazione
feature: Processing Rules
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
source-git-commit: 65b3a9001aa062429a870d374af20618c532de35
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 100%

---

# Funzionamento delle regole di elaborazione

Le regole di elaborazione consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono alle condizioni definite, è possibile impostare ed eliminare i valori e impostare gli eventi.

Le regole di elaborazione vengono applicate ai dati durante la raccolta e a tutti i dati che provengono dalle librerie AppMeasurement e dall’API di inserimento dati. Le regole di elaborazione si applicano anche alle origini dati complete e di registro. Queste origini contengono dati che rappresentano un *`hit`* o un’azione eseguita da un utente. Le regole di elaborazione non si applicano ad altre origini dati.

## Concetti importanti {#section_EB138775E7C64C74B0D1D3213F7A823C}

La tabella seguente contiene concetti chiave da considerare quando si utilizzano le regole di elaborazione:

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
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Copiare le regole di elaborazione in un’altra suite di rapporti </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate nell’ordine in cui sono elencate. </p> </td> 
   <td colname="col2"> <p>Se un’azione modifica un valore, le condizioni successive utilizzano il nuovo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate alla suite di rapporti immediatamente dopo il salvataggio. </p> </td> 
   <td colname="col2"> <p>Le modifiche apportate alle regole di elaborazione diventano visibili nella suite di rapporti entro pochi minuti dal salvataggio. Durante il test delle regole di elaborazione, è consigliabile configurare <a href="/help/admin/admin/realtime/t-realtime-admin.md"> rapporti in tempo reale</a> nella suite di rapporti di test, per vedere rapidamente i risultati di una regola di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione rappresentano l’unico modo per poter accedere alle variabili di dati di contesto. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiare una variabile di dati di contesto in una eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate prima delle regole VISTA e del canale di marketing. </p> </td> 
   <td colname="col2"> <p> <a href="/help/technotes/processing-order.md"> Ordine di elaborazione </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli hit non possono essere esclusi. </p> </td> 
   <td colname="col2"> <p>Puoi utilizzare le regole VISTA per escludere gli hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Non è possibile modificare la stringa di prodotto, l’URL di provenienza (referrer) e l’agente utente. </p> </td> 
   <td colname="col2"> <p>Il referrer e l’agente utente sono di sola lettura. La stringa di prodotto non è disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli attributi e le classificazioni dei dispositivi mobili non sono disponibili. </p> </td> 
   <td colname="col2"> <p>La ricerca per dispositivi mobili viene eseguita prima delle regole di elaborazione, ma gli attributi non sono disponibili nelle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I parametri della stringa di query non possono essere letti oltre i primi 255 caratteri di un URL se si esegue JavaScript AppMeasurement H.25.2 o versioni precedenti. JavaScript AppMeasurement H.25.3 e versioni successive forniscono alle regole di elaborazione l’URL completo, inclusi tutti i parametri delle stringhe di query. </p> </td> 
   <td colname="col2"> <p>Effettua l’aggiornamento alla versione H.25.3 o successiva, oppure leggi i parametri della stringa di query da URL lunghi lato client e salvane i valori nelle variabili di dati di contesto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I valori della stringa di query devono essere codificati in Unicode o UTF-8 per essere letti dalle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Questo requisito potrebbe incidere sui caratteri multibyte passati mediante stringhe di query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ogni suite di rapporti può avere un massimo di 150 regole, con un massimo di 30 condizioni ciascuna. </p> </td> 
   <td colname="col2"> <p>I limiti delle regole di elaborazione si riferiscono alle singole suite di rapporti, non all’intera società. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione devono essere impostate in modo da recuperare le variabili dei dati di contesto prima dell’invio dei dati. </p> </td> 
   <td colname="col2"> <p>Le regole di elaborazione vengono applicate al momento dell’invio delle chiamate al server. I valori memorizzati nelle variabili di dati di contesto vengono scartati se non vengono copiati mediante le regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I confronti di valori nell’interfaccia utente non distinguono tra maiuscole e minuscole. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Pulire i valori in un rapporto </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I nomi delle variabili di dati di contesto possono contenere solo caratteri alfanumerici, trattini bassi e punti. Eventuali altri caratteri vengono eliminati. </p> </td> 
   <td colname="col2"> <p>Ad esempio, la variabile di dati di contesto <code> login_page-home</code> diventa automaticamente <code> login_pagehome</code>. Tutti i dati inviati alla variabile <code> login_page-home</code> vengono assegnati a <code> login_pagehome</code>. </p> <p>Le variabili di dati di contesto che contengono caratteri non supportati non possono essere aggiunte nell’interfaccia delle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>L’accento circonflesso o caret (^) è un carattere speciale nel sistema delle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Per indicare un singolo carattere caret, utilizza due caratteri caret (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Condizioni della regola di elaborazione {#section_387390EEE9BA4DA98698522A84326DB4}

Le condizioni verificano la presenza di un valore corrispondente nelle variabili di pagina. È possibile aggiungere più condizioni e selezionare se tutte devono essere soddisfatte.

Puoi creare una regola senza condizioni per eseguire sempre le azioni definite.

Prima dell’esecuzione delle azioni, i valori delle variabili non vengono controllati automaticamente. Ad esempio, Prop1 contiene un valore “something” ed eVar1 è vuoto. Se si imposta Prop1 su uguale a eVar1, entrambi i valori saranno vuoti. Per evitare che questo accada, aggiungi una condizione per verificare la presenza di un valore.

## Azioni delle regole di elaborazione {#section_E2285C9D008442C7BF136E52A9A4CC06}

Le azioni impostano o eliminano le variabili di pagina, oppure attivano gli eventi. Le azioni possono anche concatenare i valori da visualizzare in un rapporto.

Ad esempio, potrebbe essere utile visualizzare `category:product` concatenando due variabili.
