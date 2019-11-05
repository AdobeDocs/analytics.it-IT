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
source-git-commit: 4e3e164f5c28290ac280343d95cf5cb1186e09cd

---


# Copiare una variabile di dati di contesto in una eVar

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili dei dati di contesto a prop ed eVar. Senza le regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non popolano alcun report in Analytics.

L' [!UICONTROL Context Variables] elenco contiene tutte le variabili che sono state inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati di contesto ma non lo hai inviato nella suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic **[!UICONTROL Add variable name context data]**:

![Aggiungi](assets/add-context-variable.png)

L'esempio seguente prende la variabile di dati di `search_term` contesto e ne inserisce il valore in `eVar3`:

![Set](assets/set-context-data.png)

L'esempio di cui sopra funziona bene quando ci sono solo poche eVar da compilare. Se nell'organizzazione sono presenti centinaia di variabili di dati di contesto ciascuna delle quali necessita di un'eVar, è possibile utilizzare istruzioni condizionali. Dozzine di istruzioni condizionali possono essere inserite all'interno di una singola regola di elaborazione, consentendo all'organizzazione di compilare tutte le eVar in una suite di rapporti senza eseguire il limite di 150 regole della regola di elaborazione.

L'esempio seguente viene compilato `prop7` con la variabile di dati contestuali `testhierarchy`, ma solo se `testhierarchy` è impostata:

![Condizionale](assets/add-conditional.png)

Per ulteriori informazioni sull'implementazione di variabili di dati di contesto, vedi Variabili [di dati di](/help/implement/js-implementation/c-variables/context-data-variables.md) contesto nella guida per l'utente Implementa.
