---
description: Puoi distinguere i collegamenti personalizzando l’ID del collegamento utilizzando la variabile s_objectID, personalizzando la regione e personalizzando il file del modulo ActivityMap di AppMeasurement.
title: Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e area geografica
topic: Activity map
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
translation-type: tm+mt
source-git-commit: 370d81bafc523b00a38b0064ad4ca3e6bb655d9f
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 10%

---


# Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e area geografica

Puoi distinguere i collegamenti personalizzando l’ID del collegamento utilizzando la variabile s_objectID, personalizzando la regione e personalizzando il file del modulo ActivityMap di AppMeasurement.

Ad esempio, supponiamo che tu disponga di più collegamenti &quot;Acquista&quot; identificati da  Activity Map con lo stesso ID collegamento e regione:

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p> </p>Buy <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p> </p>pannello di raccomandazione <p> </p> <p> </p> <p>pannello di raccomandazione </p> <p> </p> <p> </p> <p>pannello di raccomandazione </p> </td> 
  </tr> 
 </tbody> 
</table>

In che modo è possibile personalizzare la pagina Web e i tag per differenziare i valori di questi collegamenti? Sono disponibili tre opzioni: Puoi personalizzare l’ID collegamento, la regione o il file del modulo ActivityMap di AppMeasurement.

## Personalizzare l’ID collegamento utilizzando s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Creando un ID oggetto univoco per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il tracciamento  Activity Map oppure utilizzare  Activity Map per creare rapporti su un tipo o una posizione di collegamento, anziché sull’URL del collegamento. Fare clic [qui](https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/page-variables.html) per ulteriori informazioni sulla variabile s_objectID.

>[!IMPORTANT]
>
>Tenere presente che è necessario un punto e virgola finale (;) quando si utilizza s_objectID in  Activity Map.

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt;&nbsp;&nbsp;&nbsp; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p>Product1 <p> </p> <p> </p> <p>Prodotto 2 </p> <p> </p> <p> </p> <p>Prodotto 3 </p> <p> </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p> <p>pannello di raccomandazione </p> <p> </p> <p> </p> <p>pannello di raccomandazione </p> <p> </p> <p> </p> <p>pannello di raccomandazione </p> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personalizzare la regione {#section_6B1EF302573B445DBAF44176D0A12DB9}

Puoi personalizzare l&#39;area facendo in modo che ogni collegamento &quot;acquista&quot; abbia una propria regione definita. A tal fine, aggiungete un parametro &quot;id&quot; a uno dei principali tag di ancoraggio &quot;Buy&quot;.

>[!NOTE]
>
>Non sei strettamente limitato al parametro &quot;id&quot; come identificatore di regione. Potete anche impostare un identificatore personalizzato utilizzando la variabile JavaScript &quot;s.ActivityMap.regionIDAtribute&quot;.

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
    <code>
      &lt;div&nbsp;id="recommendation&nbsp;panel"&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
     &nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt; 
     &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt; 
     &nbsp;&nbsp;&nbsp;&lt;/div&gt; 
    </code> </td> 
   <td colname="col2"> <p> </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> <p> </p> <p> </p> <p>Buy </p> </td> 
   <td colname="col3"> <p> </p> <p> </p> <p> </p>regione a <p> </p> <p> </p> <p>regione B </p> <p> </p> <p> </p> <p>regione c </p> </td> 
  </tr> 
 </tbody> 
</table>

## Personalizzare il file del modulo ActivityMap di AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
>
>Verificate che il codice modificato funzioni correttamente.  Adobe non è responsabile del funzionamento del codice modificato.

Di seguito sono riportati un paio di esempi di funzioni di collegamento/regione*** generiche che è possibile includere (nel modulo modificato) nel file AppMeasurement.js.

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

Il linkName viene passato durante le chiamate a s.tl.

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

