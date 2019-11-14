---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---



# javascriptVersion

La variabile indica la versione di JavaScript supportata dal browser.

<!-- 

javascriptVersion.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

> [!NOTE] Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Traffic &gt; Technology &gt; Versione JavaScript |

La versione H.10 e successiva del file JavaScript rileva accuratamente fino alla versione 1.7 (la versione più elevata al momento del rilascio di H.10). Versioni precedenti del file JavaScript rilevate solo fino alla versione 1.3
