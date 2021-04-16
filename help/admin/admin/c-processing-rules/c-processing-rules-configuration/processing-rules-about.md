---
description: Le regole di elaborazione ti consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono a condizioni definite, è possibile impostare ed eliminare i valori e impostare gli eventi.
subtopic: Processing rules
title: Funzionamento delle regole di elaborazione
feature: Strumenti di amministrazione
uuid: 19c31f94-c8d8-47b1-97fa-29ed98c94e87
exl-id: 9d2d9f2d-1e16-486f-9191-2c43776374da
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 2%

---

# Funzionamento delle regole di elaborazione

Le regole di elaborazione ti consentono di apportare modifiche ai dati in base a condizioni definite. Quando gli attributi o i valori corrispondono a condizioni definite, è possibile impostare ed eliminare i valori e impostare gli eventi.

Le regole di elaborazione vengono applicate ai dati durante la raccolta e vengono applicate a tutti i dati che provengono dalle librerie AppMeasurement e dall’API di inserimento dati. Le regole di elaborazione si applicano anche alle origini dati complete e di registro. Queste origini contengono dati che rappresentano un *`hit`* o un&#39;azione eseguita da un utente. Le regole di elaborazione non si applicano ad altre origini dati.

## Concetti importanti {#section_EB138775E7C64C74B0D1D3213F7A823C}

La tabella seguente contiene concetti chiave che è necessario comprendere quando si utilizzano le regole di elaborazione:

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
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Copiare le regole di elaborazione in un'altra suite di rapporti </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate nell’ordine elencato. </p> </td> 
   <td colname="col2"> <p>Se un’azione modifica un valore, le condizioni successive utilizzano il nuovo valore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate immediatamente alla suite di rapporti dopo il salvataggio. </p> </td> 
   <td colname="col2"> <p>Le modifiche apportate alle regole di elaborazione dovrebbero essere visibili nella suite di rapporti entro pochi minuti dal salvataggio. Durante il test delle regole di elaborazione, ti consigliamo di configurare <a href="/help/admin/admin/realtime/t-realtime-admin.md"> rapporti in tempo reale</a> nella suite di rapporti di prova in modo da visualizzare rapidamente i risultati di una regola di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione sono l'unico modo per accedere alle variabili di dati di contesto. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiare una variabile di dati di contesto in un eVar  </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Le regole di elaborazione vengono applicate prima delle regole VISTA e Marketing Channel. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md"> Ordine di elaborazione </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli hit non possono essere esclusi. </p> </td> 
   <td colname="col2"> <p>Puoi utilizzare le regole VISTA per escludere gli hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impossibile modificare la stringa di prodotto, il referente e l'agente utente. </p> </td> 
   <td colname="col2"> <p>Il referente e l'agente utente sono di sola lettura. La stringa di prodotto non è disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gli attributi e le classificazioni dei dispositivi mobili non sono disponibili. </p> </td> 
   <td colname="col2"> <p>La ricerca per dispositivi mobili viene eseguita prima delle regole di elaborazione, ma gli attributi non sono disponibili nelle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I parametri della stringa di query non possono essere letti oltre i primi 255 caratteri di un URL se si esegue JavaScript AppMeasurement H.25.2 o versioni precedenti. JavaScript AppMeasurement H.25.3 e versioni successive forniscono l’URL completo, inclusi tutti i parametri delle stringhe query alle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Effettua l’aggiornamento a H.25.3 o versioni successive, oppure leggi i parametri della stringa di query da URL lunghi lato client e archivia i valori nelle variabili di dati contestuali. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I valori della stringa di query devono essere codificati in Unicode o UTF-8 per essere letti dalle regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Questo potrebbe influenzare i caratteri multibyte passati utilizzando stringhe di query. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Hai un limite a 150 regole con 30 condizioni per ciascuna suite di rapporti. </p> </td> 
   <td colname="col2"> <p>I limiti delle regole di elaborazione si riferiscono a suite di rapporti, non a società. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È necessario impostare le regole di elaborazione per recuperare le variabili dei dati di contesto prima dell’invio dei dati. </p> </td> 
   <td colname="col2"> <p>Le regole di elaborazione vengono applicate quando vengono inviate le chiamate al server. I valori memorizzati nelle variabili di dati di contesto vengono scartati se non vengono copiati utilizzando le regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I confronti di valori nell’interfaccia utente distinguono tra maiuscole e minuscole. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Pulizia dei valori in un rapporto  </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I nomi delle variabili di dati di contesto possono contenere solo caratteri alfanumerici, caratteri di sottolineatura e punti. Eventuali caratteri aggiuntivi vengono eliminati. </p> </td> 
   <td colname="col2"> <p>Ad esempio, la variabile di dati di contesto <code> login_page-home</code> diventa automaticamente <code> login_pagehome</code>. Tutti i dati inviati alla variabile <code> login_page-home</code> sono allocati sotto <code> login_pagehome</code>. </p> <p>Le variabili di dati di contesto che contengono caratteri non supportati non possono essere aggiunte nell’interfaccia delle Regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caret (^) è un carattere speciale nel sistema di regole di elaborazione. </p> </td> 
   <td colname="col2"> <p>Per far corrispondere un singolo carattere di accento circonflesso, utilizza due caratteri di accento circonflesso (^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Condizioni della regola di elaborazione {#section_387390EEE9BA4DA98698522A84326DB4}

Le condizioni controllano le variabili di pagina per un valore corrispondente o se è presente un valore. È possibile aggiungere più condizioni e selezionare se tutte le condizioni devono essere soddisfatte.

Puoi creare una regola senza condizioni per eseguire sempre azioni definite.

Prima dell’esecuzione delle azioni, le variabili non vengono controllate automaticamente per i valori. Ad esempio, Prop1 contiene un valore di &quot;qualcosa&quot; e eVar1 è vuoto. Se si imposta Prop1 su uguale a eVar1, entrambi i valori saranno vuoti. Se devi evitarlo, aggiungi una condizione per verificare la presenza di un valore.

## Azioni regola di elaborazione {#section_E2285C9D008442C7BF136E52A9A4CC06}

Le azioni impostano le variabili di pagina, eliminano le variabili di pagina o attivano gli eventi. Le azioni possono anche concatenare valori da visualizzare in un rapporto.

Ad esempio, è possibile visualizzare `category:product` concatenando due variabili.
