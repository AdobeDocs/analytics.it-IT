---
description: Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.
keywords: Gestione tag dinamica;variabili globali;variabile server;evar;prop;prefisso variabile dinamica;variabile dinamica
seo-description: Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.
seo-title: Variabili globali
solution: Experience Cloud,Analytics,Gestione tag dinamica
title: Variabili globali
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Variabili globali

Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.

Queste variabili vengono attivate su tutti i beacon delle regole di caricamento della pagina. Potete ottenere lo stesso effetto utilizzando una regola di caricamento [pagina](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) impostata per essere attivata su tutte le pagine. Queste variabili potrebbero non essere attivate nelle regole [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) e [Basate](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) sugli eventi.

## Variabili globali - Descrizioni dei campi {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]**&gt;![](assets/settings_gear.png)**[!UICONTROL Edit Tool]**&gt;**[!UICONTROL Global Variables]**

| Elemento | Descrizione |
|--- |--- |
| Server | La variabile predefinita popola la dimensione Server in Adobe Analytics. Vedere Variabili [di pagina](/help/implement/js-implementation/c-variables/page-variables.md) |
| eVar | [Le variabili](/help/implement/js-implementation/c-variables/page-variables.md) eVar vengono utilizzate per creare rapporti di conversione personalizzati. |
| Proprietà | [Le variabili](/help/implement/js-implementation/c-variables/page-variables.md) prop vengono utilizzate per creare rapporti sul traffico personalizzati. |
| Prefisso variabile dinamico | Prefisso speciale all'inizio del valore. Il prefisso predefinito è "D=". Vedere Variabili [dinamiche](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
