---
description: A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.
title: Namespace
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
source-git-commit: 79f650a7168e0cc44194445f3164a3f981e39a91
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 88%

---

# Namespace

A ciascun ID che si desidera cercare viene assegnato uno spazio dei nomi, o namespace, ovvero una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui esso viene usato per tutte le suite di rapporti.

La stringa namespace viene usata per identificare i campi in cui si desidera eseguire le ricerche quando si fornisce un ID come parte di una richiesta di Privacy dei dati. Quando una richiesta di Privacy dei dati viene inviata, la richiesta includerà una sezione JSON che specifica gli ID dell’interessato da utilizzare per la richiesta. È possibile includere più ID come parte di una singola richiesta per un interessato. La sezione JSON include:

* Un campo “namespace” contenente la stringa namespace.
* Un campo “type” che per la maggior parte delle richieste di Adobe Analytics contiene il valore “analytics”.
* Un campo “value” contenente l’ID che Analytics deve cercare nelle variabili namespace associate di ciascuna suite di rapporti.

Consulta la sezione [Experience Cloud di documentazione sull’API della Privacy dei dati](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it) per maggiori dettagli e per [elenco degli spazi dei nomi di identità standard](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/api/appendix#standard-namespaces). Consulta [Creare un processo di accesso/eliminazione](https://experienceleague.adobe.com/en/docs/experience-platform/privacy/api/privacy-jobs#access-delete) per una richiesta di esempio.

## ID cookie

Cookie di monitoraggio Analytics Legacy, noto anche come ID Adobe Analytics (AAID):

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

Questo valore deve essere specificato come due numeri esadecimali separati da un trattino. Tutte le cifre esadecimali che sono caratteri alfabetici devono essere specificate con caratteri maiuscoli. I valori esadecimali non dovrebbero avere zeri iniziali (notare la differenza rispetto allo stesso valore specificato nella forma obsoleta, dove sono richiesti gli zeri iniziali).

È consentito usare `"namespaceId": 10` al posto o in aggiunta di `"namespace": "AAID"` e potresti riscontrare che altri prodotti Adobe usano quel modulo.

## Cookie di tracciamento legacy di Analytics: modulo obsoleto

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Questo valore deve essere specificato come due numeri esadecimali a 16 cifre oppure due numeri decimali a 19 cifre separati da un trattino. I numeri devono essere separati da un trattino, un trattino basso o due punti. Gli zeri iniziali devono essere aggiunti qualora le due serie non fossero composte da un numero di cifre sufficienti.

## Cookie del servizio Identity

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

Il valore deve essere specificato come numero decimale a 38 cifre. Se stai estraendo questo numero dalle due colonne mcvisid\_high/low o post\_msvisid\_high/low da un feed di dati o da un rapporto di Data Warehouse, è necessario azzerare ognuno dei due numeri a 19 cifre e poi concatenarli prima con il valore alto.

È consentito usare `"namespaceId": 4` al posto o in aggiunta di `"namespace": "ECID"` e potresti riscontrare che altri prodotti Adobe usano quel modulo.

>[!NOTE]
>
>Experience Cloud ID (ECID) era noto in precedenza come Marketing Cloud ID (MCID) e viene indicato ancora con quel nome in alcune documentazioni esistenti.
>
>Questi ID sono gli unici ID supportati da Analytics che utilizzano un valore di “type” diverso da “analytics”.

Se il formato della porzione di valore di uno qualsiasi di questi cookie ID non segue il formato descritto per quell’ID, allora la richiesta di Privacy dei dati non riuscirà, con messaggio errore “Valore non formattato correttamente”.

Nella maggior parte dei casi questi ID cookie vengono raccolti usando il nuovo [JavaScript per la privacy](https://developer.adobe.com/experience-platform-apis/references/privacy-service/), che fornirà automaticamente tutte le coppie chiave/valore pertinenti per questi ID JSON.

Questo codice JavaScript compila il JSON con altre coppie chiave/valore oltre a quelle elencate in precedenza (namespace, tipo, valore), ma i campi elencati sopra sono quelli più importanti per l’elaborazione Privacy dei dati in Analytics e gli unici campi da specificare se si raccolgono gli ID in altri modi.

## ID visitatore personalizzato

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

Anche il namespace è predefinito per l&#39;ID visitatore personalizzato.

## ID nelle variabili personalizzate

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

Per gli ID nelle variabili di conversione e traffico personalizzate (proprietà ed eVar), devi assegnare alla variabile l’etichetta ID-DEVICE o ID-PERSON e quindi il tuo nome namespace a quel tipo di ID. Vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile.](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)

Puoi anche vedere i namespace definiti in precedenza per altre variabili o suite di rapporti e riutilizzare una di queste, in modo che lo stesso namespace possa essere facilmente usato per tutte le suite di rapporti che contengono quel tipo di ID. È anche possibile assegnare lo stesso namespace a più variabili all’interno della suite di rapporti. Ad esempio, alcuni clienti memorizzano un ID CRM in una variabile di traffico e in una variabile di conversione (può trovarsi in una sola pagina o in entrambe le pagine a seconda dei casi) e possono assegnare il namespace “ID CRM” a entrambe le variabili.

>[!TIP]
>
>Evita di usare il nome descrittivo di una variabile (il nome visualizzato nell’interfaccia utente di reporting) o il numero della variabile (ad esempio eVar12) quando si specifica il namespace nell’API Privacy dei dati, a meno che non si tratti anche del namespace specificato durante l’applicazione dell’etichetta ID-DEVICE o ID-PERSON a questa variabile. L’uso di un namespace invece di un nome descrittivo consente allo stesso blocco di identità dell’utente di specificare la variabile corretta per suite di rapporti multiple. Per esempio, se l’ID si trova in eVars diversi di alcune delle suite di rapporti, o se i nomi descrittivi non corrispondono (come quando il nome descrittivo è stato localizzato per una specifica suite di rapporti).

>[!CAUTION]
>
>Gli spazi dei nomi `visitorId` e `customVisitorId` sono riservati per identificare il cookie di tracciamento legacy di Analytics e l’ID visitatore del cliente Analytics. Non utilizzare questi spazi dei nomi per le variabili di traffico o conversione personalizzate.

Per altre informazioni vedi [Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile.](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)
