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


# mediaSession

Questa variabile specifica i segmenti di una risorsa video o multimediale utilizzata.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 byte </td> 
   <td> pev3 </td> 
   <td>  Tempo trascorso sul video <p>Segmenti video visualizzati </p> </td> 
   <td> Nessuno </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi e valori** possibili {#section_9A63266633C4427CB4A6549E4D887B85}

**Metodo autoTrack:**

Se si utilizza [!UICONTROL s.Media.autoTrack], *`mediaName`* non è necessario implementarlo esplicitamente. Sarà determinato automaticamente da AppMeasurement per il codice JavaScript.

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

**Esempi** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

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
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Insidie, domande e suggerimenti**{#section_1BCEB037AB724B6EBE87420BD3604B88}

È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando [!UICONTROL s.Media.autoTrack] = true.
