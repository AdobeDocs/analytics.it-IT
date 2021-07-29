---
title: maxDelay
description: Determina la quantità massima di tempo che AppMeasurement attende una risposta da DFA prima di inviare una richiesta di immagine.
exl-id: 154f7e34-39e7-4390-ae36-d4fbc998787f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# maxDelay

La variabile `s.maxDelay` viene utilizzata nel connettore dati DFA per determinare il periodo di timeout durante il contatto con l’host DFA. Se Adobe non riceve una risposta dai server DFA entro il periodo specificato impostato in questa variabile, la connessione viene interrotta e i dati vengono elaborati normalmente. Includi questa variabile nell’implementazione se sei interessato al tempo di risposta del DFA su ogni pagina. Adobe consiglia di provare questo valore per determinare il periodo di timeout ottimale.

Questa variabile viene utilizzata solo nelle implementazioni che utilizzano il connettore dati DFA. Anche con le implementazioni che utilizzano DFA, questa variabile è facoltativa.

## Ritardo massimo tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.maxDelay in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.maxDelay` è un numero intero che rappresenta il numero di millisecondi che AppMeasurement attende una risposta da DFA. Se AppMeasurement non riceve una risposta da DFA in tempo, viene inviata ad Adobe una richiesta di immagine senza dati DFA.

```js
s.maxDelay = 750;
```

## Proprietà

* L’aumento del tempo di attesa raccoglie più dati DFA, ma aumenta anche il rischio di perdere i dati hit di Analytics. La perdita dei dati hit di Analytics si verifica quando l’utente si allontana dalla pagina durante il periodo `s.maxDelay` .
* La riduzione del tempo di attesa riduce il rischio di perdita dei dati hit di Analytics, ma può ridurre la quantità di dati DFA inviati con i dati hit.
* La perdita di dati di integrazione DFA si verifica quando il `s.maxDelay` periodo non è sufficiente per consentire all’host DFA di rispondere.

>[!NOTE]
>
>L’Adobe non ha il controllo del tempo di risposta del DFA. Se noti problemi coerenti anche dopo aver aumentato il periodo di ritardo massimo a un intervallo di tempo ragionevole, consulta l’amministratore dell’account DFA della tua organizzazione.
