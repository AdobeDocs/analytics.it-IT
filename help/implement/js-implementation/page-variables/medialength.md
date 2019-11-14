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


# mediaLength

La variabile specifica la lunghezza totale del contenuto multimediale riprodotto.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
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
   <td> Nessuna dimensione massima per l'intera richiesta pev3 - la dimensione è limitata al limite di lunghezza URL del browser. </td> 
   <td> pev3 </td> 
   <td> Tempo trascorso sul video; <p>Segmenti video visualizzati </p> </td> 
   <td> Nessuno </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi e valori** possibili {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**Metodo autoTrack:**

Se si utilizza [!UICONTROL s.Media.autoTrack], la [!UICONTROL mediaLength] variabile non deve essere implementata in modo esplicito. Viene determinato automaticamente da AppMeasurement per il codice JavaScript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Esempi** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Insidie, domande e suggerimenti**{#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando [!UICONTROL s.Media.autoTrack] = true.
* Se non esegui il tracciamento tramite [!UICONTROL autoTrack], accertati di impostare la lunghezza in secondi.

