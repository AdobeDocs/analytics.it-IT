---
description: Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire  Adobe Analytics.
keywords: Dynamic Tag Management;global variables;server variable;evar;props;dynamic variable prefix;dynamic variable
solution: Experience Cloud,Analytics
title: Variabili globali
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: a4542164031fc9f181dfdc471a1d54b5056b1223
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 26%

---


# Variabili globali

Descrizioni dei campi e informazioni sulle variabili quando si utilizza Gestione tag dinamica per distribuire  Adobe Analytics.

Queste variabili vengono attivate su tutti i beacon delle regole di caricamento della pagina. Puoi ottenere lo stesso effetto utilizzando una [regola di caricamento pagina](/help/implement/other/dtm/c-rules/t-rules-page-conditions.md) impostata per essere attivata su tutte le pagine. These variables might not fire in [Direct-Call](/help/implement/other/dtm/c-rules/t-rules-direct-conditions.md) and [Event-Based](/help/implement/other/dtm/c-rules/t-rules-event-conditions.md) rules.

## Variabili globali - Descrizioni dei campi {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL  *`Property`*]** > ![](assets/settings_gear.png) **[!UICONTROL Edit Tool]** > **[!UICONTROL Global Variables]**

| Elemento | Descrizione |
|--- |--- |
| Server | La variabile predefinita popola la dimensione Server in  Adobe Analytics. Vedere [Server](../../../vars/page-vars/server.md). |
| eVar | [variabili](../../../vars/page-vars/evar.md) eVar vengono utilizzate per la creazione di rapporti di conversione personalizzati. |
| Proprietà | [Le variabili](../../../vars/page-vars/prop.md) prop vengono utilizzate per creare rapporti sul traffico personalizzati. |
| Prefisso variabile dinamico | Prefisso speciale all&#39;inizio del valore. Il prefisso predefinito è &quot;D=&quot;. Consultate Variabili []dinamiche (../../../vars/page-vars/dynamic-variables.md) |
