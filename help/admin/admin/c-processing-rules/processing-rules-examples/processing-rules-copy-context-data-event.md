---
description: Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.
seo-description: Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.
seo-title: Impostare un evento utilizzando una variabile di dati di contesto
solution: Analytics
subtopic: Regole di elaborazione
title: Impostare un evento utilizzando una variabile di dati di contesto
topic: Strumenti di amministrazione
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Impostare un evento utilizzando una variabile di dati di contesto

Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.

Le variabili di dati di contesto sono specificate in AppMeasurement nel seguente formato:

```
 s.contextData['search_term']
```

L' [!UICONTROL Context Variables] elenco contiene tutte le variabili che sono state inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato nella suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La seguente definizione di regola si espande su [Copia una variabile di dati di contesto in una regola eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) per impostare anche un evento per ogni hit che contiene una specifica variabile di dati di contesto:

| Set di regole | Valore |
|---|---|
| Condizione | Se i dati contestuali 'search_term' sono impostati |
| Azione | Impostate l'evento 'Searches' |

Ad esempio:

![](assets/processing_rule_set_event.png)

Consulta Variabili [di dati di](https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html) contesto nella guida all'implementazione.
