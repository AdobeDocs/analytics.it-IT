---
description: Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Variabili globali
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variabili globali

Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.

Queste variabili vengono attivate su tutti i beacon delle regole di caricamento della pagina. Puoi ottenere lo stesso effetto utilizzando una [regola di caricamento pagina](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md) impostata per essere attivata su tutte le pagine. These variables might not fire in [Direct-Call](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md) and [Event-Based](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md) rules.

## Variabili globali - Descrizioni dei campi {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]**&gt;![](assets/settings_gear.png)**[!UICONTROL Edit Tool]**&gt;**[!UICONTROL Global Variables]**

| Elemento | Descrizione |
|--- |--- |
| Server | La variabile predefinita popola la dimensione Server in Adobe Analytics. Vedere Variabili [di pagina](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVar | [Le variabili](/help/implement/js-implementation/c-variables/page-variables.md) eVar vengono utilizzate per creare rapporti di conversione personalizzati. |
| Proprietà | [Le variabili](/help/implement/js-implementation/c-variables/page-variables.md) prop vengono utilizzate per creare rapporti sul traffico personalizzati. |
| Prefisso variabile dinamico | Prefisso speciale all'inizio del valore. Il prefisso predefinito è "D=". Vedere Variabili [dinamiche](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
