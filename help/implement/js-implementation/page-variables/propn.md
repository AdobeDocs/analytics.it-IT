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


# propN

Le variabili di proprietà ( [!UICONTROL prop]) vengono utilizzate per creare rapporti personalizzati all'interno del [!UICONTROL Traffic Module].

<!-- 

propN.xml

 -->

La variabile props può essere utilizzata come contatori (per contare il numero di volte che una visualizzazione di pagina viene inviata), per i report dei percorsi o nei rapporti di correlazione.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | c1-c75 | Traffico personalizzato | "" |

**Sintassi e valori** possibili {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

Non esistono limitazioni sulle [!UICONTROL property] variabili al di fuori delle limitazioni standard.

**Esempi** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Impostazioni** di configurazione {#section_25FDEB6ECA8242A2A44EE540C083078A}

Contatta l'Assistenza clienti Adobe per visualizzare [!UICONTROL Visit], [!UICONTROL Visitor]e [!UICONTROL Path] le metriche per [!UICONTROL prop] le variabili.
