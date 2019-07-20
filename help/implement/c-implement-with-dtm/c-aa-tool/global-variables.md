---
description: Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.
keywords: Gestione tag dinamica; variabili globali; server variabile; evar; prop; prefisso variabile dinamica; variabile dinamica
seo-description: Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.
seo-title: Variabili globali
solution: Marketing Cloud, Analytics, Gestione tag dinamica
title: Variabili globali
uuid: d 759320 a -96 ee -4073-b 5 fd -5257 b 7033003
translation-type: tm+mt
source-git-commit: 3489f00bd7dddefda0420fc361056416f6f10d3f

---


# Variabili globali

Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire Adobe Analytics.

Queste variabili attivano tutti i beacon delle regole di caricamento pagina. You can accomplish the same effect by using a [Page-Load rule](../../../implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md#task_69B41CB230EE4530A755D91233F73706) set to fire on all pages. These variables might not fire in [Direct-Call](../../../implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md#task_85EB8F01775A402BA53B8298F0AADA09) and [Event-Based](../../../implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md#task_A122DE72110F4579A91F9D96D92D39FC) rules.

## Global Variables - Field Descriptions {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]**&gt;![](assets/settings_gear.png)**[!UICONTROL Edit Tool]**&gt;**[!UICONTROL Global Variables]**

| Elemento | Descrizione |
|--- |--- |
| Server | La variabile predefinito compila la dimensione Server in Adobe Analytics. See [Page Variables](/help/implement/js-implementation/c-variables/page-variables.md) |
| Evar | [Le variabili](/help/implement/js-implementation/c-variables/page-variables.md) evar vengono utilizzate per creare rapporti di conversione personalizzati. |
| Proprietà | [Le variabili prop](/help/implement/js-implementation/c-variables/page-variables.md) vengono utilizzate per creare rapporti sul traffico personalizzati. |
| Prefisso variabile dinamica | Un prefisso speciale all'inizio del valore. Il prefisso predefinito è "D =". See [Dynamic Variables](/help/implement/js-implementation/c-variables/dynvars-overview.md) |
