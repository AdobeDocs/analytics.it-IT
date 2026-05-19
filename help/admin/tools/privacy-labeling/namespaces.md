---
description: A ogni ID che desideri poter cercare viene assegnato uno spazio dei nomi, una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui viene utilizzato in tutte le suite di rapporti.
title: Spazi dei nomi
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
TQID: https://experienceleague.adobe.com/f9Pqs889VWpF4jyxX2GDBVdLyrDqWpHAkcHmDUizoGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 942
ht-degree: 56%

---

# Spazi dei nomi

A ogni ID che desideri poter cercare viene assegnato uno spazio dei nomi, una stringa personalizzata che identifica l’ID in qualsiasi variabile in cui viene utilizzato in tutte le suite di rapporti.

La stringa dello spazio dei nomi viene usata per identificare i campi in cui si desidera eseguire le ricerche quando si fornisce un ID come parte di una richiesta di Privacy dei dati. Quando una richiesta di Privacy dei dati viene inviata, la richiesta includerà una sezione JSON che specifica gli ID dell’interessato da utilizzare per la richiesta. È possibile includere più ID come parte di una singola richiesta per un interessato. Il JSON include:

* Campo &quot;namespace&quot; contenente la stringa namespace.
* Un campo &quot;type&quot; che per la maggior parte delle richieste di Adobe Analytics contiene il valore &quot;analytics&quot;.
* Un campo &quot;value&quot; contenente l’ID che Analytics deve cercare nelle variabili dello spazio dei nomi associate da ciascuna suite di rapporti.

Per ulteriori informazioni e un [elenco degli spazi dei nomi di identità standard](https://experienceleague.adobe.com/it/docs/experience-platform/privacy/api/appendix#standard-namespaces), consulta la [documentazione dell&#39;API per la Privacy dei dati aziendali di CX](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it). Vedi [Creare un processo di accesso/eliminazione](https://experienceleague.adobe.com/it/docs/experience-platform/privacy/api/privacy-jobs#access-delete) per una richiesta di esempio.

## ID cookie

Cookie di monitoraggio Analytics Legacy, noto anche come ID Adobe Analytics (AAID):

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

Il valore deve essere specificato come due numeri esadecimali separati da un trattino. Tutte le cifre esadecimali che sono caratteri alfabetici devono essere specificate utilizzando lettere maiuscole. I valori esadecimali non devono avere zeri iniziali (si noti la differenza rispetto allo stesso valore specificato nel modulo obsoleto, in cui sono richiesti gli zeri iniziali).

È consentito usare `"namespaceId": 10` al posto o in aggiunta di `"namespace": "AAID"` e potresti riscontrare che altri prodotti Adobe usano quel modulo.

## Cookie di tracciamento legacy di Analytics: modulo obsoleto

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Il valore deve essere specificato come due numeri esadecimali a 16 cifre o come due numeri decimali a 19 cifre. I numeri devono essere separati da un trattino, un carattere di sottolineatura o due punti. Gli zeri iniziali devono essere aggiunti qualora le due serie non fossero composte da un numero di cifre sufficienti.

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

Questo codice JavaScript compila il JSON con altre coppie chiave/valore oltre a quelle elencate in precedenza (namespace, type, value), ma i campi elencati sopra sono quelli più importanti per l’elaborazione Privacy dei dati in Analytics e gli unici campi da specificare se si raccolgono gli ID in altri modi.

## ID visitatore personalizzato

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

Lo spazio dei nomi è predefinito anche per l’ID visitatore personalizzato.

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

Per gli ID nelle variabili di conversione e traffico personalizzate (Prop ed eVar), devi assegnare alla variabile l’etichetta ID-DEVICE o ID-PERSON e quindi, a quel tipo di ID, il nome del tuo spazio dei nomi. Vedi [Fornire uno spazio dei nomi quando si applicano a una variabile etichette come ID-DEVICE o ID-PERSON.](/help/admin/tools/privacy-labeling/labels.md)

Puoi anche visualizzare gli spazi dei nomi definiti in precedenza per altre variabili o suite di rapporti e riutilizzarne uno, in modo che lo stesso spazio dei nomi possa essere facilmente utilizzato per tutte le suite di rapporti che memorizzano tale tipo di ID. È anche possibile assegnare lo stesso spazio dei nomi a più variabili all’interno della suite di rapporti. Ad esempio, alcuni clienti memorizzano un ID del sistema di gestione delle relazioni con i clienti in una variabile di traffico e una variabile di conversione (a seconda della pagina, a volte si trova in una delle due variabili, oppure in entrambe) e possono assegnare il namespace &quot;CRM ID&quot; a entrambe le variabili.

>[!TIP]
>
>Per specificare lo spazio dei nomi nell’API Privacy dei dati, evita di usare il nome descrittivo di una variabile (il nome visualizzato nell’interfaccia utente di reporting) o il numero della variabile (ad esempio eVar12), a meno che non si tratti anche dello spazio dei nomi specificato durante l’applicazione dell’etichetta ID-DEVICE o ID-PERSON a tale variabile. Quando si utilizza uno spazio dei nomi invece di un nome descrittivo, con uno stesso blocco di identità dell’utente è possibile specificare la variabile corretta per più suite di rapporti. Per esempio, se l’ID si trova in eVars diversi di alcune delle suite di rapporti, o se i nomi descrittivi non corrispondono (come quando il nome descrittivo è stato localizzato per una specifica suite di rapporti).

>[!CAUTION]
>
>Gli spazi dei nomi `visitorId` e `customVisitorId` sono riservati per identificare il cookie di tracciamento legacy di Analytics e l&#39;ID visitatore del cliente Analytics. Non utilizzare questi spazi dei nomi per le variabili di traffico o conversione personalizzate.

Per altre informazioni vedi [Fornire uno spazio dei nomi quando si applicano a una variabile etichette come ID-DEVICE o ID-PERSON.](/help/admin/tools/privacy-labeling/labels.md)
