---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# maxDelay

La variabile s.maxDelay è utilizzata principalmente nelle integrazioni DFA di Genesis per determinare il periodo di timeout durante il contatto con l’host del DFA. Se Adobe non riceve una risposta dai server DFA entro il periodo specificato impostato nella variabile, la connessione viene interrotta e i dati vengono elaborati normalmente. Implementa questa variabile se hai a che fare con il tempo di risposta del DFAE su ogni pagina. È consigliabile sperimentare con questo valore per determinare il periodo di timeout ottimale.

<!-- 

maxDelay.xml

 -->

**Esempio**

```
s.maxDelay="750";
```

**Proprietà**

* Questa variabile è una metrica di evento opzionale compilata tramite JavaScript implementato sul sito.
* Se l’ospitante del DFA non risponde entro il tempo specificato, l’evento designato per Timeout viene eseguito (assegnato tramite la procedura guidata di integrazione di Genesis).
* Questa variabile può contenere solo un valore numerico.
* Il tempo specificato viene misurato in millisecondi.
* Aumentando il tempo di attesa si raccolgono più dati DFA, ma aumenta anche il rischio di perdere i dati hit di Analytics.

   La perdita dei dati di hit di Analytics si verifica quando l'utente si allontana dalla pagina durante il *`s.maxDelay`* periodo.

* Una riduzione del tempo di attesa ridurrà il rischio di perdita dei dati hit di Analytics, ma potrebbe ridurre la quantità di dati DFA inviati con i dati hit.

   La perdita dei dati di integrazione DFAE si verificherebbe quando il *`s.maxDelay`* periodo non contiene il tempo sufficiente per consentire all’ospitante del DFAE di rispondere.

> [!NOTE] Adobe non ha il controllo sui tempi di risposta del DFAE. Se riscontri problemi coerenti anche dopo aver aumentato il periodo di ritardo massimo a un intervallo di tempo ragionevole, consulta l’amministratore di account DFA della tua organizzazione.
