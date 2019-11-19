---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# propN

Le variabili di proprietà (`prop`) vengono utilizzate per creare rapporti personalizzati all'interno del modulo Traffico.

<!-- 

propN.xml

 -->

La variabile props può essere utilizzata come contatori (per contare il numero di volte che una visualizzazione di pagina viene inviata), per i report dei percorsi o nei rapporti di correlazione.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | c1-c75 | Traffico personalizzato | "" |

**Sintassi e valori possibili**

```js
s.propN="value"
```

Non esistono limitazioni sulle [!UICONTROL property] variabili al di fuori delle limitazioni standard.

**Esempi**

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Impostazioni di configurazione**

Contatta l’Assistenza clienti Adobe per visualizzare le metriche Visita, Visitatore e Percorso per `prop` le variabili.
