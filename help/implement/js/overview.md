---
title: Implementazione di Adobe Analytics con AppMeasurement per JavaScript
description: Scopri come implementare Adobe Analytics utilizzando JavaScript senza un sistema di gestione dei tag.
feature: Implementation Basics
source-git-commit: 93e16a538d6dc05c9cbf0703664aa5320f45b731
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 9%

---

# Implementazione di Adobe Analytics con AppMeasurement per JavaScript

AppMeasurement per JavaScript è stato storicamente un metodo comune per implementare Adobe Analytics. Tuttavia, con la crescente popolarità di Tag Management Systems, utilizzando [tag in Adobe Experience Platform](../launch/overview.md) è consigliato.

Panoramica di alto livello delle attività di implementazione:

![Panoramica sull’implementazione di Adobe Analytics con AppMeasurement](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th><b>Attività</b></th><th><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td><td>Assicurati di avere <b>definizione di una suite di rapporti</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td><td><b>Scarica il codice JavaScript richiesto per AppMeasurement</b> da Code Manager. Decomprimi il file.</td><td><a href="../../admin/admin/code-manager-admin.md">Gestione codici</a></td>
</tr>

<tr>
<td>3</td><td><b>Aggiungi <code>AppMeasurement.js</code> al file modello del sito web</b>. Il codice contiene le librerie necessarie per inviare dati ad Adobe.

```html
<head>
  <script src="AppMeasurement.js"></script>
  …
</head>
```

</td><td></td>
</tr>

<tr>
<td>4</td><td><b>Definisci le variabili di configurazione in <code>AppMeasurement.js</code></b>. Quando viene creata un'istanza dell'oggetto Analytics, queste variabili si accertano che le impostazioni di raccolta dati siano corrette.

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
<td>5</td><td><b>Definire le variabili a livello di pagina nel codice della pagina del sito</b>. Queste variabili determinano la dimensione specifica e le metriche inviate ad Adobe.

```js
s.pageName = "Example page";
s.eVar1 = "Example eVar";
s.events = "event1";
```

</td><td><a href="../vars/page-vars/page-variables.md">Variabili di pagina</a></td>
</tr>

<tr>
<td>6</td><td><b>Invia i dati ad Adobe utilizzando <code>t()</code> metodo</b>, quando sono definite tutte le variabili di pagina.

```js
s.t();
```

</td><td><a href="../vars/functions/t-method.md">t(), metodo</a></td>
</tr>

<tr>
<td>7</td><td><b>Estendi e convalida l’implementazione</b> prima di spingerlo verso la produzione.</b></td><td></td>
</tr>

</table>

## Risorse aggiuntive

- [Panoramica di variabili, funzioni, metodi e plug-in](../vars/overview.md)
