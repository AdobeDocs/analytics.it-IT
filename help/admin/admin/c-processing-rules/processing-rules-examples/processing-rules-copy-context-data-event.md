---
description: Le regole di elaborazione possono attivare gli eventi in base alle variabili Dati di contesto.
seo-description: Le regole di elaborazione possono attivare gli eventi in base alle variabili Dati di contesto.
seo-title: Impostare un evento utilizzando una variabile di dati di contesto
solution: Analytics
subtopic: Regole di elaborazione
title: Impostare un evento utilizzando una variabile di dati di contesto
topic: Strumenti di amministrazione
uuid: 4 a 6018 eb -03 e 2-4 ec 8-874 b-e 48 bf 716 e 103
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Impostare un evento utilizzando una variabile di dati di contesto

Le regole di elaborazione possono attivare gli eventi in base alle variabili Dati di contesto.

Le variabili di dati di contesto sono specificate in appmeasurement nel seguente formato:

```
 s.contextData['search_term']
```

[!UICONTROL Context Variables] L'elenco contiene tutte le variabili inviate alla suite di rapporti nei precedenti 30 giorni. If you know the context data variable name but have not sent it into the current report suite, you can add a value by typing the variable name and clicking **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

The following rule definition expands on the [Copy a Context Data Variable to an eVar](../../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7) rule to also set an event on every hit that contains a specific context data variable:

| Set di regole | Valore |
|---|---|
| Condizione | Se sono impostati i dati contestualì search_ term ' |
| Azione | Impostazione delle ricerche dell'evento |

Ad esempio:

![](assets/processing_rule_set_event.png)

See [Context Data Variables](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables) in Implementation Help.
