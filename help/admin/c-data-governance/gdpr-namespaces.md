---
description: A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.
seo-description: A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.
seo-title: Namespace
title: Namespace
uuid: cab 61844-3209-4980-b 14 c -6859 de 777606
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Namespace

A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.

La stringa namespace viene usata per identificare i campi in cui si desidera eseguire le ricerche quando si fornisce un ID come parte di una richiesta RGPD. Quando una richiesta RGPD viene inviata, la richiesta includerà una sezione JSON che specifica gli ID della persona interessata da usare nella richiesta. È possibile includere più ID come parte di una singola richiesta per una persona interessata. La sezione JSON include:

* Un campo “namespace” contenente la stringa namespace.
* Un campo “type” che per la maggior parte delle richieste di Adobe Analytics contiene il valore “analytics”.
* Un campo “value” contenente l’ID che Analytics deve cercare nelle variabili namespace associate di ciascuna suite di rapporti.

Per altre informazioni fai riferimento alla [documentazione relativa all’API RGPD per Experience Cloud](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md).

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

It is also acceptable to use `“namespaceId”: 10` instead of or in addition to `“namespace”: “AAID”` and you may see some other Adobe products use that form.

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

## Cookie servizio identità

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

Il valore deve essere specificato come numero decimale a 38 cifre. Se si richiama questo numero dalle due colonne mcvisid\_ high/low o post\_ msvisid\_ high/low da un feed dati o da Data Warehouse, è necessario zero pad ciascuno dei due numeri a 19 cifre e quindi concatenarli con il valore alto.

It is also acceptable to use: `“namespaceId”: 4` instead of or in addition to `“namespace”: “ECID”` and you may see some other Adobe products use that form.

>[!NOTE]
>
>L'Experience Cloud ID (ECID) era precedentemente noto come Marketing Cloud ID (MCID) e continua a essere utilizzato con tale nome in alcune documentazione esistenti.
>
>Questi ID sono gli unici ID supportati da Analytics che utilizzano un valore "type" diverso da "analytics".

Se il formato della porzione di valore di uno qualsiasi di questi cookie ID non segue il formato descritto per quell’ID, allora la richiesta RGPD non riuscirà, con messaggio errore “Valore non formattato correttamente”.

Nella maggior parte dei casi questi ID cookie vengono raccolti usando il nuovo [JavaScript per la privacy](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), che fornirà automaticamente tutte le coppie chiave/valore pertinenti per questi ID JSON.

Questo codice JavaScript compila il JSON con altre coppie chiave/valore oltre a quelle elencate in precedenza (namespace, tipo, valore), ma i campi elencati sopra sono quelli più importanti per l'elaborazione del RGPD in Analytics e gli unici campi da specificare se si raccolgono gli ID in altri modi.

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

Per gli ID nelle variabili di conversione e traffico personalizzate (proprietà e eVars), devi assegnare alla variabile l'etichetta ID-DEVICE o ID-PERSON e quindi il tuo nome namespace a quel tipo di ID. Vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7).

Puoi anche vedere i namespace definiti in precedenza per altre variabili o suite di rapporti e riutilizzare una di queste, in modo che lo stesso namespace possa essere facilmente usato per tutte le suite di rapporti che contengono quel tipo di ID. È anche possibile assegnare lo stesso namespace a più variabili all’interno della suite di rapporti. Ad esempio, alcuni clienti memorizzano un ID CRM in una variabile di traffico e in una variabile di conversione (può trovarsi in una sola pagina o in entrambe le pagine a seconda dei casi) e possono assegnare il namespace “ID CRM” a entrambe le variabili.

>[!NOTE]
>
>Non puoi usare il nome descrittivo di una variabile (il nome visualizzato nell'interfaccia utente di reporting) o il numero della variabile (ad esempio evar 12) quando si specifica lo spazio nomi all'API GDPR, a meno che non si tratti dello spazio dei nomi specificato durante l'applicazione dell'etichetta ID-DEVICE o ID-PERSON a questa variabile. L’uso di un namespace invece di un nome descrittivo consente allo stesso blocco di identità dell’utente di specificare la variabile corretta per suite di rapporti multiple in questi casi:

* l’ID si trova in eVars diversi in alcune suite di rapporti oppure
* i nomi descrittivi non corrispondono (come nel caso in cui il nome descrittivo sia stato localizzato per una suite di rapporti specifica)

Per altre informazioni vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7).
