---
description: A ogni ID che si desidera cercare viene assegnato uno spazio dei nomi, ovvero una stringa personalizzata che identifica tale ID in qualsiasi variabile in cui viene utilizzato in tutte le suite di rapporti.
title: Namespace
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Namespace

A ogni ID che si desidera cercare viene assegnato uno spazio dei nomi, ovvero una stringa personalizzata che identifica tale ID in qualsiasi variabile in cui viene utilizzato in tutte le suite di rapporti.

La stringa namespace viene usata per identificare i campi in cui si desidera eseguire le ricerche quando si fornisce un ID come parte di una richiesta di Privacy dei dati. Quando una richiesta di Privacy dei dati viene inviata, la richiesta includerà una sezione JSON che specifica gli ID della persona interessata da usare nella richiesta. Più ID possono essere inclusi come parte di una singola richiesta per un soggetto dati. JSON include:

* Un campo &quot;namespace&quot; contenente la stringa dello spazio nomi.
* Un campo &quot;tipo&quot; che per la maggior parte delle richieste di Adobe Analytics contiene il valore &quot;analytics&quot;.
* Un campo &quot;value&quot; contenente l&#39;ID che Analytics deve cercare nelle variabili dello spazio nomi associate da ciascuna suite di rapporti.

Per altre informazioni fai riferimento alla [documentazione relativa all’API Privacy dei dati](https://www.adobe.io/apis/experienceplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/technical_overview/privacy_service_overview/privacy_service_overview.md) per Experience Cloud.

## ID cookie

Cookie di monitoraggio Analytics Legacy, noto anche come ID Adobe Analytics (AAID):

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

Il valore deve essere specificato come due numeri esadecimali separati da un trattino. Tutte le cifre esadecimali che sono caratteri alfabetici devono essere specificate utilizzando il maiuscolo. I valori esadecimali non devono avere zeri iniziali (notare la differenza rispetto allo stesso valore specificato nel modulo obsoleto, dove sono richiesti gli zeri iniziali).

È consentito usare `"namespaceId": 10` al posto o in aggiunta di `"namespace": "AAID"` e potresti riscontrare che altri prodotti Adobe usano quel modulo.

## Cookie di monitoraggio di Analytics Legacy: forma obsoleta

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Forma obsoleta:

Il valore deve essere specificato come due numeri esadecimali di 16 cifre o come due numeri decimali di 19 cifre. I numeri devono essere separati da un trattino, un carattere di sottolineatura o due punti. Gli zeri iniziali devono essere aggiunti qualora le due serie non fossero composte da un numero di cifre sufficienti.

## Cookie del servizio Identity

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

Il valore deve essere specificato come numero decimale a 38 cifre. Se stai estraendo questo numero dalle due colonne mcvisid\_high/low o post\_msvisid\_high/low da un feed di dati o da un rapporto di Data Warehouse, è necessario azzerare ognuno dei due numeri a 19 cifre e poi concatenarli prima con il valore alto.

È consentito usare `"namespaceId": 4` al posto o in aggiunta di `"namespace": "ECID"` e potresti riscontrare che altri prodotti Adobe usano quel modulo.

>[!NOTE] Experience Cloud ID (ECID) era noto in precedenza come Marketing Cloud ID (MCID) e viene indicato ancora con quel nome in alcune documentazioni esistenti.
>
>Questi ID sono gli unici ID supportati da Analytics che utilizzano un valore di “type” diverso da “analytics”.

Se il formato della porzione di valore di uno qualsiasi di questi cookie ID non segue il formato descritto per quell’ID, allora la richiesta di Privacy dei dati non riuscirà, con messaggio errore “Valore non formattato correttamente”.

Nella maggior parte dei casi questi ID cookie vengono raccolti usando il nuovo [JavaScript per la privacy](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm), che fornirà automaticamente tutte le coppie chiave/valore pertinenti per questi ID JSON.

Questo codice JavaScript compila il JSON con altre coppie chiave/valore oltre a quelle elencate in precedenza (namespace, tipo, valore), ma i campi elencati sopra sono quelli più importanti per l’elaborazione Privacy dei dati in Analytics e gli unici campi da specificare se si raccolgono gli ID in altri modi.

## ID visitatore personalizzato

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

Lo spazio dei nomi è anche predefinito per l’ID visitatore personalizzato.

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

Per gli ID nelle variabili di conversione e traffico personalizzate (proprietà ed eVar), devi assegnare alla variabile l’etichetta ID-DEVICE o ID-PERSON e quindi il tuo nome namespace a quel tipo di ID. Vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile.](gdpr-labels.md)

Puoi anche visualizzare i namespace precedentemente definiti per altre variabili o suite di rapporti e riutilizzare uno di questi, in modo che lo stesso namespace possa essere facilmente utilizzato per tutte le suite di rapporti che memorizzano quel tipo di ID. È anche possibile assegnare lo stesso namespace a più variabili all’interno della suite di rapporti. Ad esempio, alcuni clienti memorizzano un ID CRM in una variabile di traffico e una variabile di conversione (a seconda della pagina, a volte si trova in una o nell&#39;altra o in entrambe), e possono assegnare lo spazio dei nomi &quot;ID CRM&quot; a entrambe le variabili.

>[!TIP] Evita di usare il nome descrittivo di una variabile (il nome visualizzato nell’interfaccia utente della reportistica) o il numero della variabile (ad esempio eVar12) quando si specifica il namespace nell’API Privacy dei dati, a meno che non si tratti anche del namespace specificato durante l’applicazione dell’etichetta ID-DEVICE o ID-PERSON a questa variabile. L’uso di un namespace invece di un nome descrittivo consente allo stesso blocco di identità dell’utente di specificare la variabile corretta per suite di rapporti multiple. Per esempio, se l’ID si trova in eVars diversi di alcune delle suite di rapporti, o se i nomi descrittivi non corrispondono (come quando il nome descrittivo è stato localizzato per una specifica suite di rapporti).

>[!CAUTION] I namespace “visitorId” e “customVisitorId” sono riservati per identificare il cookie di tracciamento legacy di Analytics e l’ID visitatore del cliente Analytics. Non utilizzare questi namespace per le variabili di traffico o conversione personalizzate.

Per altre informazioni vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile.](/help/admin/c-data-governance/gdpr-labels.md)
