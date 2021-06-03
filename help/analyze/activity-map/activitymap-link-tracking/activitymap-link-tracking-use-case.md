---
description: Puoi distinguere i collegamenti personalizzando l’ID collegamento utilizzando la variabile s_objectID, personalizzando la regione e personalizzando il file del modulo ActivityMap di AppMeasurement.
title: Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e area geografica
uuid: f2da0cda-a33b-4a12-8d99-1f58386d6d30
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 43fe4eb9-08fe-4e20-bc02-3f712c3dec1d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 8%

---

# Differenziare i collegamenti che fanno riferimento allo stesso ID collegamento e area geografica

Puoi distinguere i collegamenti personalizzando l’ID collegamento utilizzando la variabile s_objectID, personalizzando la regione e personalizzando il file del modulo ActivityMap di AppMeasurement .

Ad esempio, supponiamo che tu disponga di più collegamenti &quot;Acquista&quot; identificati da Activity Map con lo stesso ID collegamento e l’area geografica:

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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td>
   <td colname="col2">
     <br/>
     <br/>
    Acquista<br/>
     <br/>
     <br/>
    Acquista<br/>
     <br/>
     <br/>
    Acquista<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    pannello consigli<br/>
     <br/>
     <br/>
    pannello consigli<br/>
     <br/>
     <br/>
    pannello consigli<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

Come personalizzare la pagina web e i tag per differenziare i valori di questi collegamenti? Sono disponibili tre opzioni: Puoi personalizzare l’ID collegamento, l’area geografica o il file del modulo ActivityMap di AppMeasurement.

## Personalizzare l’ID collegamento utilizzando s_objectID {#section_01B0D463397B4837B2D46F087A6E5937}

Creando un ID oggetto univoco, `s_objectID`, per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il tracciamento di Activity Map oppure utilizzare Activity Map per creare rapporti su un tipo o una posizione di collegamento, anziché sull’URL del collegamento. Fai clic [qui](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) per ulteriori informazioni sulla variabile `s_objectID`.

>[!IMPORTANT]
>
>Tenere presente che è necessario un punto e virgola finale (`;`) quando si utilizza `s_objectID` in Activity Map.
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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product1';"&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product2';"&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt; </code><br/>
    <code>&nbsp;&lt;div&gt; </code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;onClick="s_objectID='Product3';"&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Product1<br/>
     <br/>
     <br/>
    Product2<br/>
     <br/>
     <br/>
    Product3<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    pannello consigli<br/>
     <br/>
     <br/>
    pannello consigli<br/>
     <br/>
     <br/>
    pannello consigli<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizzare la regione {#section_6B1EF302573B445DBAF44176D0A12DB9}

Puoi personalizzare la regione assicurandoti che ogni collegamento &quot;Acquista&quot; abbia la propria area geografica definita. Per farlo, aggiungi un parametro `"id"` a uno dei principali tag di ancoraggio &quot;Acquista&quot;.

>[!NOTE]
>Non sei strettamente limitato al parametro `"id"` come identificatore di area. Puoi anche impostare un identificatore personalizzato utilizzando la variabile JavaScript `"s.ActivityMap.regionIDAttribute"`.
>
>
><table id="table_250DB52A869C466B942517BABA1C287B">
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
    <code>&lt;div&nbsp;id="recommendation&nbsp;panel"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;a"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product1.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;b"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product2.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;div&nbsp;id="region&nbsp;c"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&lt;a&nbsp;href="product3.html"&gt;Buy&lt;/a&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;/div&gt;</code><br/>
    <code>&lt;/div&gt;</code>
   </td> 
   <td colname="col2">
     <br/>
     <br/>
    Acquista<br/>
     <br/>
     <br/>
    Acquista<br/>
     <br/>
     <br/>
    Acquista<br/>
     <br/>
     <br/>
   </td> 
   <td colname="col3">
     <br/>
     <br/>
    regione a<br/>
     <br/>
     <br/>
    regione b<br/>
     <br/>
     <br/>
    regione c<br/>
     <br/>
     <br/>
   </td>
  </tr>
 </tbody>
</table>

## Personalizzare il file del modulo ActivityMap di AppMeasurement {#section_B933BB9F944E4D5389002908A5A881F8}

>[!CAUTION]
Verifica che il codice modificato funzioni correttamente. Adobe non è responsabile del funzionamento del codice modificato.

Di seguito sono riportati un paio di esempi di funzioni di collegamento/area geografica **generiche** che è possibile includere (in formato modificato) nel file AppMeasurement.js.

```
s.ActivityMap.link = function(ele, linkName) {
  if (linkName) {
    return linkName;
  }
  if (ele) {
    if (ele.tagName == 'A' && ele.href) {
      return ele.href;
    }
  }
}
```

Il `linkName` viene passato durante le chiamate a `s.tl()`.

```
s.ActivityMap.region = function(ele) {
  var className,
  classNames = {
    'header': 1,
    'navbar': 1,
    'left-content': 1,
    'main-content': 1,
    'footer': 1,
  }; 
  while ((ele && (ele = ele.parentNode))) {
    if ((className=ele.className) && classNames[className]) {
      return className;
    }
  }
  return "BODY";
}
```
