---
description: Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a proprietà ed eVar.
seo-description: Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a proprietà ed eVar.
seo-title: Copiare una variabile di dati di contesto in una eVar
solution: Analytics
subtopic: Regole di elaborazione
title: Copiare una variabile di dati di contesto in una eVar
topic: Strumenti di amministrazione
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Copiare una variabile di dati di contesto in una eVar

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a proprietà ed eVar.

Le variabili di dati di contesto sono specificate in AppMeasurement nel seguente formato:

```
 s.contextData['search_term']
```

L' [!UICONTROL Context Variables] elenco contiene tutte le variabili che sono state inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato nella suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La seguente definizione di regola popola un'eVar per ogni hit che contiene una specifica variabile di dati di contesto:

| Set di regole | Valore |
|---|---|
| Condizione | Se i dati contestuali 'search_term' sono impostati |
| Azione | Sovrascrivi il valore di eVar3 in 'search_term' |

Ad esempio:

![](assets/set-context-data.png)

Consulta Variabili [di dati di](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) contesto nella guida all'implementazione.
