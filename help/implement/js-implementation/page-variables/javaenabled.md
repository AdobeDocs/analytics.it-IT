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



# javaEnabled

La variabile indica se Java è abilitato nel browser.


<!-- 

javaEnabled.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell'esecuzione di doPlugins.

> [!NOTE] Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio | Report interessati |
|---|---|---|---|
| v | Y o N | Y | Traffico &gt; Tecnologia &gt; Java |
