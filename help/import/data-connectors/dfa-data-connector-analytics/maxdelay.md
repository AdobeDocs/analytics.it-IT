---
title: maxDelay
description: Determinate la quantità massima di tempo in cui AppMeasurement attende una risposta dal DFA prima di inviare una richiesta di immagine.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 1%

---


# maxDelay

La `s.maxDelay` variabile viene utilizzata nel connettore dati DFA per determinare il periodo di timeout durante il contatto con l’host del DFA. Se Adobe non riceve una risposta dai server del DFA entro il periodo specificato impostato in questa variabile, la connessione viene interrotta e i dati vengono elaborati normalmente. Includete questa variabile nell’implementazione se avete a che fare con il tempo di risposta del DFAE su ogni pagina. Adobe consiglia di provare questo valore per determinare il periodo di timeout ottimale.

Questa variabile viene utilizzata solo nelle implementazioni che utilizzano il connettore dati DFA. Anche con le implementazioni che utilizzano il DFA, questa variabile è facoltativa.

## Ritardo massimo  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.maxDelay nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.maxDelay` variabile è un numero intero che rappresenta il numero di millisecondi che AppMeasurement attende una risposta da parte del DFA. Se AppMeasurement non riceve una risposta dal DFA nel tempo, viene inviata ad Adobe una richiesta di immagine senza dati DFA.

```js
s.maxDelay = 750;
```

## Proprietà

* Aumentando il tempo di attesa si raccolgono più dati DFA, ma aumenta anche il rischio di perdere  dati hit Analytics. La perdita  dati hit Analytics si verifica quando l&#39;utente si allontana dalla pagina durante il `s.maxDelay` periodo.
* La riduzione del tempo di attesa riduce il rischio di perdere  dati hit Analytics, ma può ridurre la quantità di dati DFA inviati con i dati hit.
* La perdita dei dati di integrazione DFAE avviene quando il `s.maxDelay` periodo non è sufficiente per consentire all’ospitante del DFAE di rispondere.

>[!NOTE]
>
>Adobe non ha il controllo sui tempi di risposta del DFAE. Se riscontri problemi coerenti anche dopo aver aumentato il periodo di ritardo massimo a un intervallo di tempo ragionevole, consulta l’amministratore di account DFA della tua organizzazione.
