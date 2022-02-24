---
description: Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.
subtopic: Processing rules
title: Impostare un evento utilizzando una variabile di dati di contesto
feature: Admin Tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '156'
ht-degree: 100%

---

# Impostare un evento utilizzando una variabile di dati di contesto

Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.

Le variabili di dati contestuali sono specificate in AppMeasurement nel seguente formato:

```
 s.contextData['search_term']
```

L’elenco [!UICONTROL Context Variables] contiene tutte le variabili inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati contestuali ma non lo hai inviato alla suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic su **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La seguente definizione di regola si sviluppa su [Copiare una variabile di dati contestuali in un eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) per impostare anche un evento su ogni hit che contiene una variabile di dati contestuali specifica:

| Set di regole | Valore |
|---|---|
| Condizione | Se sono impostati i dati contestuali “search_term” |
| Azione | Imposta le “ricerche” dell’evento |

Esempio:

![](assets/processing_rule_set_event.png)

Consulta [Variabili di dati contestuali](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/contextdata.html?lang=it) nella Guida all’implementazione.
