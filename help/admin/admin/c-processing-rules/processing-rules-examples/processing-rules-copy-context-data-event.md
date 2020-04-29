---
description: Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.
subtopic: Processing rules
title: Impostare un evento utilizzando una variabile di dati di contesto
topic: Admin tools
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
translation-type: tm+mt
source-git-commit: 327fdfd6a6d6bfe1c7bae9825fc8812b5ac7d095

---


# Impostare un evento utilizzando una variabile di dati di contesto

Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.

Le variabili di dati di contesto sono specificate in AppMeasurement nel seguente formato:

```
 s.contextData['search_term']
```

L&#39; [!UICONTROL Context Variables] elenco contiene tutte le variabili che sono state inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato nella suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La seguente definizione di regola si espande su [Copia una variabile di dati di contesto in una regola eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) per impostare anche un evento per ogni hit che contiene una specifica variabile di dati di contesto:

| Set di regole | Valore |
|---|---|
| Condizione | Se i dati contestuali &#39;search_term&#39; sono impostati |
| Azione | Impostate l&#39;evento &#39;Searches&#39; |

Ad esempio:

![](assets/processing_rule_set_event.png)

Consulta Variabili [di dati di](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) contesto nella guida all&#39;implementazione.
