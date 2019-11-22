---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# resolution

La variabile indica la risoluzione del monitor del visitatore che visualizza la pagina Web.


<!-- 

resolution.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

> [!NOTE] Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio | Report interessati |
|---|---|---|---|
| s | WxH | 1680x1050 | Traffico &gt; Tecnologia &gt; Risoluzione monitor |

