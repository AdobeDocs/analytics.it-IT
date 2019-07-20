---
description: Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili Dati contestuali a prop ed evar.
seo-description: Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili Dati contestuali a prop ed evar.
seo-title: Copiare una variabile di dati di contesto in una evar
solution: Analytics
subtopic: Regole di elaborazione
title: Copiare una variabile di dati di contesto in una evar
topic: Strumenti di amministrazione
uuid: 1 beaec 4 c -71 e 9-49 ce-b 154-78408 cc 532 a 3
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Copiare una variabile di dati di contesto in una evar

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili Dati contestuali a prop ed evar.

Le variabili di dati di contesto sono specificate in appmeasurement nel seguente formato:

```
 s.contextData['search_term']
```

[!UICONTROL Context Variables] L'elenco contiene tutte le variabili inviate alla suite di rapporti nei precedenti 30 giorni. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La seguente definizione regola compila un evar su ogni hit contenente una variabile di dati di contesto specifica:

| Set di regole | Valore |
|---|---|
| Condizione | Se sono impostati i dati contestualì search_ term ' |
| Azione | Valore sovrascritto da evar 3 a'search_ term ' |

Ad esempio:

![](assets/set-context-data.png)

See [Context Data Variables](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) in Implementation Help.
