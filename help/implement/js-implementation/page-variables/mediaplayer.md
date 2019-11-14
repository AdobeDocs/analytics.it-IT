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


# mediaPlayer

Questa variabile specifica il lettore utilizzato per utilizzare un elemento video o multimediale.

<!-- 

mediaPlayer.xml

 -->

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | pev3 | Riproduttori video | Nessuno |

**Sintassi e valori** possibili {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Metodo autoTrack:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Metodo di tracciamento manuale:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Esempi** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Insidie, domande e suggerimenti**{#section_0020E031338F4A4880B9AC5B9A85BEF5}

È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando s.Media.autoTrack = true.

