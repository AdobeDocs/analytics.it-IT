---
title: Implementare Adobe Analytics con AppMeasurement per JavaScript
description: Scopri come implementare Adobe Analytics utilizzando JavaScript senza un sistema di gestione dei tag.
feature: Implementation Basics
exl-id: 25b9d768-c641-4f6c-a4ae-0d6c238c4776
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 9%

---

# Implementare Adobe Analytics con AppMeasurement per JavaScript

L’AppMeasurement per JavaScript è sempre stato un metodo comune per implementare Adobe Analytics. Tuttavia, con la crescente popolarità dei sistemi Tag Management, si consiglia di utilizzare [tag in Adobe Experience Platform](../launch/overview.md).

Panoramica ad alto livello dei compiti di implementazione:

![Come implementare Adobe Analytivs con AppMeasurement per JavaScript, come descritto in questa sezione.](../assets/appmeasurement-annotated.png)

<table>

<tr>
<th style="width:5%"></th><th style="width:75%"><b>Attività</b></th><th style="width:20%"><b>Ulteriori informazioni</b></th>
</tr>

<tr>
<td>1</td><td>Assicurati di aver <b>definito una suite di rapporti</b></td><td><a href="../../admin/admin/c-manage-report-suites/report-suites-admin.md">Report Suite Manager</a></td>
</tr>

<tr>
<td>2</td><td><b>Scarica il codice JavaScript richiesto per l'AppMeasurement</b> da Code Manager. Decomprimi il file.</td><td><a href="../../admin/admin/code-manager-admin.md">Gestione codici</a></td>
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
<td>5</td><td><b>Definisci le variabili a livello di pagina nel codice di pagina del sito</b>. Queste variabili determinano dimensioni e metriche specifiche inviate a Adobe.

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
