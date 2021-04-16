---
description: Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.
subtopic: Processing rules
title: Impostare un evento utilizzando una variabile di dati di contesto
feature: Strumenti di amministrazione
uuid: 4a6018eb-03e2-4ec8-874b-e48bf716e103
exl-id: f0af0e23-c08a-4f82-85b4-25064eeaa3c6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 14%

---

# Impostare un evento utilizzando una variabile di dati di contesto

Le regole di elaborazione possono attivare eventi in base a variabili di dati contestuali.

Le variabili di dati contestuali sono specificate in AppMeasurement nel seguente formato:

```
 s.contextData['search_term']
```

L’elenco [!UICONTROL Context Variables] contiene tutte le variabili inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato nella suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic su **[!UICONTROL Add variable name context data]**:

![](assets/add-context-variable.png)

La seguente definizione di regola si espande su [Copia una variabile di dati di contesto in una regola eVar](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md) per impostare anche un evento su ogni hit che contiene una variabile di dati di contesto specifica:

| Set di regole | Valore |
|---|---|
| Condizione | Se i dati contestuali &quot;search_term&quot; sono impostati |
| Azione | Imposta le &#39;ricerche&#39; dell&#39;evento |

Ad esempio:

![](assets/processing_rule_set_event.png)

Consulta [Variabili di dati di contesto](https://docs.adobe.com/content/help/en/analytics/implementation/vars/page-vars/contextdata.html) nella Guida all&#39;implementazione.
