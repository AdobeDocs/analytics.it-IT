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


# colorDepth

La variabile viene utilizzata per mostrare il numero di bit utilizzati per visualizzare il colore su ogni pixel dello schermo.


<!-- 

colordepth.xml

 -->

Ad esempio, 32 rappresenta 32 bit di colore sullo schermo. Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

> [!NOTE] Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in `props/eVars`, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio | Report interessati |
|---|---|---|---|
| c | 8,16 e 32 | 32 | Traffic &gt; Technology &gt; Monitor Colour Depth |
