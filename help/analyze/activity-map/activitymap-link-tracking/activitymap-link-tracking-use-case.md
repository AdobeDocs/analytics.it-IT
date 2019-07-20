---
description: Puoi distinguere i collegamenti personalizzando l'ID del collegamento utilizzando la variabile s_ objectid personalizzando l'area e personalizzando il file del modulo activmeasurement appmeasurement.
seo-description: Puoi distinguere i collegamenti personalizzando l'ID del collegamento utilizzando la variabile s_ objectid personalizzando l'area e personalizzando il file del modulo activmeasurement appmeasurement.
seo-title: Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e regione
solution: Analytics
title: Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e regione
topic: Activity map
uuid: f 2 da 0 cda-a 33 b -4 a 12-8 d 99-1 f 58386 d 6 d 30
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e regione

Puoi distinguere i collegamenti personalizzando l'ID del collegamento utilizzando la variabile s_ objectid personalizzando l'area e personalizzando il file del modulo activmeasurement appmeasurement.

Ad esempio, supponiamo che tu abbia più collegamenti "Buy" identificati da Activity Map con lo stesso ID collegamento e regione:

<table id="table_3020E2C0175D455C84E794CF51BE5A93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Esempio di codice </th> 
   <th colname="col2" class="entry"> ID collegamento </th> 
   <th colname="col3" class="entry"> Area geografica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code>&lt; div id = "pannello raccomandazione" &gt; 
 &lt; div &gt; 
 &lt; a href = "product1.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a href = "product2.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a href = "product3.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Acquista <p> </p> <p> </p> <p>Acquista </p> <p> </p> <p> </p> <p>Acquista </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>recommendation panel <p> </p> <p> </p> <p>recommendation panel </p> <p> </p> <p> </p> <p>recommendation panel </p> </td> 
  </tr> 
 </tbody> 
</table>

Come è possibile personalizzare la pagina Web e i tag per differenziare i valori di questi collegamenti? Sono disponibili tre opzioni: Puoi personalizzare l'ID collegamento, oppure personalizzare l'area o personalizzare il file modulo activitymap appmeasurement.

## Customize the Link ID Using s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Creando un ID oggetto univoco per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il tracciamento delle Activity Map oppure utilizzare Activity Map per generare rapporti su un tipo di collegamento o su una posizione, piuttosto che sull'URL del collegamento. Click [here](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) for more information on the s_objectID variable.

>[!IMPORTANT]
>
>È necessario un punto e virgola finale (;) quando si utilizza s_ objectid nella Activity Map.

<table id="table_9439A5F320304E439A19842CF3EBA456"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> Esempio di codice </th> 
   <th colname="col2" class="entry"> ID collegamento </th> 
   <th colname="col3" class="entry"> Area geografica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>&lt; div id = "pannello raccomandazione" &gt; 
 &lt; div &gt; 
 &lt; a onclick = "s_ objectid ='Product 1 '; " href = "product1.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a onclick = "s_ objectid ='Product 2 '; " href = "product2.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div &gt; 
 &lt; a onclick = "s_ objectid ='Product 3 '; " href = "product3.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Prodotto 2 </p> <p> </p> <p> </p> <p>Prodotto 3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>pannello raccomandazione </p> <p> </p> <p> </p> <p>pannello raccomandazione </p> <p> </p> <p> </p> <p>pannello raccomandazione </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customize the Region {#section_6B1EF302573B445DBAF44176D0A12DB9}

Potete personalizzare l'area accertandovi che ogni collegamento «acquista» abbia la propria regione definita. A questo scopo, aggiungete un parametro "id" a uno degli elementi principali di ciascun tag di ancoraggio "Buy".

>[!NOTE]
>
>Non sei rigorosamente limitato al parametro «id» come identificatore di regione. Puoi anche impostare un identificatore personalizzato utilizzando la variabile javascript "s. activitymap. regionidattribute".

<table id="table_250DB52A869C466B942517BABA1C287B"> 
 <thead> 
  <tr> 
   <th colname="col02" class="entry"> Esempio di codice </th> 
   <th colname="col2" class="entry"> ID collegamento </th> 
   <th colname="col3" class="entry"> Area geografica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col02"> 
    <code>&lt; div id = "pannello raccomandazione" &gt; 
 &lt; div id = "region a" &gt; 
 &lt; a href = "product1.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div id = "region b" &gt; 
 &lt; a href = "product2.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; 
 &lt; div id = "region c" &gt; 
 &lt; a href = "product3.html" &gt; Acquista &lt;/a &gt; 
 &lt;/div &gt; </code>
  </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Acquista </p> <p> </p> <p> </p> <p>Acquista </p> <p> </p> <p> </p> <p>Acquista </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>regione a <p> </p> <p> </p> <p>regione b </p> <p> </p> <p> </p> <p>regione c </p> </td> 
  </tr> 
 </tbody> 
</table>

## Customize the AppMeasurement ActivityMap Module file {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Accertatevi di verificare il codice modificato per assicurare che funzioni correttamente. Adobe non è responsabile del funzionamento del codice modificato.

Di seguito sono riportati alcuni esempi di** funzioni collegamento/regione generico che potresti includere (nel modulo modificato) nel file appmeasurement. js.

```
s.ActivityMap.link = function(ele,linkName){ 
if(linkName){ 
return linkName; 
} 
if(ele){ 
if(ele.tagName == 'A' && ele.href){ 
return ele.href; 
} 
} 
} 
```

Il linkname viene passato durante le chiamate a s. tl.

```
s.ActivityMap.region = function(ele){ 
var className, 
classNames = { 
'header': 1, 
'navbar': 1, 
'left-content': 1, 
'main-content': 1, 
'footer': 1, 
}; 
  while( (ele && (ele = ele.parentNode))){ 
if( (className=ele.className) && classNames[className]){ 
return className; 
} 
} 
return "BODY"; 
} 
```

