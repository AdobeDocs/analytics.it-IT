---
title: Implementare Adobe Analytics con AppMeasurement per JavaScript
description: Scopri come implementare Adobe Analytics utilizzando JavaScript senza un sistema di gestione dei tag.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
TQID: https://experienceleague.adobe.com/QScNJBw6-Xn-gQCJBBxVT6melUpnyy6VIKrzvnDzJyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 209
ht-degree: 15%

---

# Implementare Adobe Analytics con AppMeasurement per JavaScript

AppMeasurement per JavaScript è sempre stato un metodo comune per implementare Adobe Analytics. Tuttavia, con la crescente popolarità dei sistemi Tag Management, si consiglia di utilizzare [tag in Adobe Experience Platform](../launch/overview.md).

Panoramica ad alto livello dei compiti di implementazione:

![Come implementare Adobe Analytivs con AppMeasurement per JavaScript, come descritto in questa sezione.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Attività</b></th><th style="width:20%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td><td>Assicurati di aver <b>definito una suite di rapporti</b></td><td><a href="../../admin/tools/manage-rs/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td><td><b>Scarica il codice JavaScript richiesto per AppMeasurement</b> da Code Manager. Decomprimi il file.</td><td><a href="../../admin/tools/code-manager-admin.md">Gestione codici</a></td>
</tr>

<tr>
<td>3</td><td><b>Aggiungi <code>AppMeasurement.js</code> al file modello del tuo sito Web</b>. Il codice contiene le librerie necessarie per inviare dati ad Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Definire le variabili di configurazione in <code>AppMeasurement.js</code></b>. Quando viene creata un'istanza dell'oggetto Analytics, queste variabili verificano che le impostazioni di raccolta dati siano corrette.

```JavaScript
// Instantiate the Analytics tracking object with report suite ID
var s_account = "examplersid";
var s=s_gi(s_account);
 
// Make sure data is sent to the correct tracking server
s.trackingServer = "example.data.adobedc.net";
```

</td><td><a href="../vars/config-vars/configuration-variables.md">Variabili di configurazione</a></td>
</tr>

<tr>
<td>5</td><td><b>Definisci le variabili a livello di pagina nel codice di pagina del sito</b>. Queste variabili determinano dimensioni e metriche specifiche inviate ad Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variabili di pagina</a></td>
</tr>

<tr>
<td>6</td><td><b>Invia i dati ad Adobe utilizzando il metodo <code>t()</code></b>, quando sono definite tutte le variabili di pagina.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t(), metodo</a></td>
</tr>

<tr>
<td>7</td><td><b>Estendi e convalida l'implementazione</b> prima di eseguirne il push in produzione.</b></td><td></td>
</tr>

</table>

## Risorse aggiuntive

- [Panoramica di variabili, funzioni, metodi e plug-in](../vars/overview.md)
