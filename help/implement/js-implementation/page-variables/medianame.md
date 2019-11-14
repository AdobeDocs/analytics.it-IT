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


# mediaName

Questa variabile specifica il nome del video o dell’elemento multimediale.

<!-- 

mediaName.xml

 -->

È disponibile solo tramite [!UICONTROL Data Insertion API] e [!UICONTROL Full Processing Data Source].

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 64 KB | pev3 | Video; Flusso video successivo; Flusso video precedente; Segmenti Video Visualizzati; Tempo trascorso sul video | Nessuno |

**Sintassi e valori** possibili {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Metodo autoTrack:**

Se si utilizza [!UICONTROL s.Media.autoTrack], la *`mediaName`* variabile non deve essere implementata in modo esplicito. Viene determinato automaticamente da AppMeasurement per il codice JavaScript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Esempi** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Insidie, domande e suggerimenti**{#section_941A445BB52E4063B0F6920E61BB90DE}

* È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando [!UICONTROL s.Media.autoTrack] = true.
* Questa variabile viene memorizzata come variabile mySQL TEXT anziché come VARCHAR(100).
