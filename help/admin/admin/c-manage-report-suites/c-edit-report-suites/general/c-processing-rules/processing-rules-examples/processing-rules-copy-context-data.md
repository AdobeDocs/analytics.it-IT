---
description: Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a prop e eVar.
subtopic: Processing rules
title: Copiare una variabile di dati di contesto in una eVar
feature: Admin Tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 100%

---

# Copiare una variabile di dati di contesto in una eVar

Le regole di elaborazione vengono utilizzate per spostare i valori dalle variabili di dati di contesto a prop e eVar. Senza regole di elaborazione, le variabili dei dati di contesto sono prive di significato e non compilano alcun rapporto in Analytics.

L’elenco [!UICONTROL Context Variables] contiene tutte le variabili inviate alla suite di rapporti nei 30 giorni precedenti. Se conosci il nome della variabile di dati contestuali ma non lo hai inviato alla suite di rapporti corrente, puoi aggiungere un valore digitando il nome della variabile e facendo clic su **[!UICONTROL Add variable name context data]**:

![Aggiungi](assets/add-context-variable.png)

L’esempio seguente prende la variabile di dati di contesto `search_term` e inserisce il suo valore in `eVar3`:

![Imposta](assets/set-context-data.png)

L’esempio precedente funziona benissimo quando sono presenti solo poche eVar da compilare. Se nell’organizzazione sono presenti centinaia di variabili di dati di contesto che necessitano di una propria eVar, puoi utilizzare le istruzioni condizionali. Decine di istruzioni condizionali possono rientrare in un’unica regola di elaborazione, consentendo all’organizzazione di compilare tutte le eVar in una suite di rapporti senza incorrere nel limite di 150 regole di elaborazione.

L’esempio seguente compila `prop7` con la variabile di dati di contesto `testhierarchy`, ma solo se `testhierarchy` è impostato:

![Condizionale](assets/add-conditional.png)

Per ulteriori informazioni sull’implementazione delle variabili di dati di contesto, consulta [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) nella guida utente per l’implementazione.
