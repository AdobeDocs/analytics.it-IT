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


# Media.trackEvents

La variabile identifica gli eventi da inviare con un hit per contenuti multimediali.

<!-- 

media_trackEvents.xml

 -->

È applicabile solo con JavaScript e [!UICONTROL ActionSource].

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackEvents="None" |

**Sintassi e valori** possibili {#section_66A978EF56914BEAAE73359A268A1B4A}

Nomi evento come event1 o purchase.

**Esempi** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**Insidie, domande e suggerimenti**{#section_030B11C64EE84D46A85CA550DB732D28}

Assicurarsi di compilare [!UICONTROL trackVars] gli "eventi" ogni volta che questa variabile viene compilata.
