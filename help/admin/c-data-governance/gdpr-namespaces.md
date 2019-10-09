---
description: A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.
seo-description: A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.
seo-title: Namespace
title: Namespace
uuid: CAB61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Namespace

A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.

La stringa dello spazio dei nomi viene utilizzata per identificare i campi per i quali si desidera eseguire la ricerca quando si fornisce un ID come parte di una richiesta di privacy dei dati. Quando viene inviata una richiesta per la privacy dei dati, la richiesta includerà una sezione JSON che specifica gli ID degli interessati da utilizzare per la richiesta. È possibile includere più ID come parte di una singola richiesta per una persona interessata. La sezione JSON include:

* Un campo “namespace” contenente la stringa namespace.
* Un campo “type” che per la maggior parte delle richieste di Adobe Analytics contiene il valore “analytics”.
* Un campo “value” contenente l’ID che Analytics deve cercare nelle variabili namespace associate di ciascuna suite di rapporti.

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## ID cookie

Cookie di monitoraggio Analytics Legacy, noto anche come ID Adobe Analytics (AAID):

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

Questo valore deve essere specificato come due numeri esadecimali separati da un trattino. Tutte le cifre esadecimali che sono caratteri alfabetici devono essere specificate con caratteri maiuscoli. I valori esadecimali non dovrebbero avere zeri iniziali (notare la differenza rispetto allo stesso valore specificato nella forma obsoleta, dove sono richiesti gli zeri iniziali).

È inoltre possibile utilizzare il modulo `“namespaceId”: 10` al posto di o in aggiunta `“namespace”: “AAID”` e potrebbe essere utilizzato da altri prodotti Adobe.

## Cookie di monitoraggio di Analytics Legacy: forma obsoleta

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Forma obsoleta:

Questo valore deve essere specificato come due numeri esadecimali a 16 cifre oppure due numeri decimali a 19 cifre separati da un trattino. I numeri devono essere separati da un trattino, un trattino basso o due punti. Gli zeri iniziali devono essere aggiunti qualora le due serie non fossero composte da un numero di cifre sufficienti.

## Cookie del servizio identità

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

Il valore deve essere specificato come numero decimale a 38 cifre. Se si sta estraendo questo numero dalle due colonne mcvisid\_high/low o post\_msvisid\_high/low da un feed di dati o da un report Data Warehouse, è necessario azzerare ogni due numeri a 19 cifre e quindi concatenarli prima con il valore alto.

È inoltre accettabile utilizzare: al `“namespaceId”: 4` posto o in aggiunta a `“namespace”: “ECID”` e potrebbe essere visualizzato l'utilizzo di tale modulo da parte di altri prodotti Adobe.

>[!NOTE]
>
>L’Experience Cloud ID (ECID) era precedentemente noto come Marketing Cloud ID (MCID) ed è ancora indicato da tale nome in alcuni documenti esistenti.
>
>Questi ID sono gli unici ID supportati da Analytics che utilizzano un valore "type" diverso da "analytics".

Se il formato della parte del valore di uno di questi cookie ID non segue il formato descritto per tale ID, la richiesta di privacy dei dati non riuscirà, con un errore di tipo "Valore non formattato correttamente".

Nella maggior parte dei casi questi ID cookie vengono raccolti usando il nuovo [JavaScript per la privacy](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), che fornirà automaticamente tutte le coppie chiave/valore pertinenti per questi ID JSON.

Questo codice JavaScript popola il JSON con altre coppie chiave/valore oltre a quelle elencate sopra (spazio dei nomi, tipo, valore), ma i campi elencati sopra sono i più importanti per l'elaborazione della privacy dei dati di Analytics e gli unici da fornire se raccogliete gli ID in un altro modo.

## ID visitatore personalizzato

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

Anche il namespace è predefinito per l'ID visitatore personalizzato.

## ID nelle variabili personalizzate

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

Per gli ID in variabili di traffico o conversione personalizzate (proprietà o eVar), etichettate la variabile con un’etichetta ID-DEVICE o ID-PERSON, quindi assegnate il vostro nome dello spazio nomi a quel tipo di ID. Vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile.](gdpr-labels.md)

Puoi anche vedere i namespace definiti in precedenza per altre variabili o suite di rapporti e riutilizzare una di queste, in modo che lo stesso namespace possa essere facilmente usato per tutte le suite di rapporti che contengono quel tipo di ID. È anche possibile assegnare lo stesso namespace a più variabili all’interno della suite di rapporti. Ad esempio, alcuni clienti memorizzano un ID CRM in una variabile di traffico e in una variabile di conversione (può trovarsi in una sola pagina o in entrambe le pagine a seconda dei casi) e possono assegnare il namespace “ID CRM” a entrambe le variabili.

> [!TIP] Evitare di utilizzare il nome descrittivo di una variabile (il nome visualizzato nell'interfaccia utente di reporting) o il numero della variabile (come eVar12) quando si specifica lo spazio dei nomi nell'API Data Privacy, a meno che non si tratti dello spazio dei nomi specificato quando si applica l'etichetta ID-DEVICE o ID-PERSON. L'utilizzo di uno spazio dei nomi invece di un nome descrittivo consente allo stesso blocco di identità utente di specificare la variabile corretta per più suite di rapporti. Ad esempio, se l’ID si trova in eVar diverse in alcune suite di rapporti o se i nomi descrittivi non corrispondono (ad esempio se il nome descrittivo è stato localizzato per una suite di rapporti specifica).

> [!CAUTION] Gli spazi dei nomi "visitorId" e "customVisitorId" sono riservati per identificare il cookie di tracciamento legacy di Analytics e l’ID visitatore del cliente Analytics. Non utilizzare questi spazi dei nomi per le variabili di traffico o conversione personalizzate.

Per altre informazioni vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile.](/help/admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)
