---
description: Ottiene il tempo di caricamento della pagina in decimi di secondo e consente di memorizzare il valore in un prop, eVar e/o un evento numerico.
keywords: Analytics Implementation
solution: Analytics
title: getLoadTime
topic: Developer and implementation
uuid: 5d26a69b-cbde-4be1-bac1-5ee8a4e55ca3
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# getLoadTime

Ottiene il tempo di caricamento della pagina in decimi di secondo e consente di memorizzare il valore in un prop, eVar e/o un evento numerico.

Per utilizzare questo plug-in, inserire il codice della funzione, quindi chiamare la funzione due volte nel [!DNL s_code.js] file. Una volta all'inizio del file, quindi di nuovo nella `doPlugins` sezione. Questo plug-in non è intenzionalmente definito come metodo dell'oggetto s. In questo modo si sarebbe aggiunto al tempo di caricamento calcolato della pagina.

> [!NOTE] Le istruzioni seguenti richiedono di modificare il codice di raccolta dei dati sul sito. Questo può influenzare la raccolta di dati sul sito e dovrebbe essere eseguito solo da uno sviluppatore con esperienza di utilizzo e implementazione [!DNL Analytics].

## Codice plug-in e implementazione {#section_968AC379C3004C359A85AFED5A48D5AE}

**Aggiungere la funzione**

Aggiungete la seguente definizione della `s_getLoadTime` funzione nella sezione "NON ALTERARE NULLA SOTTO QUESTA LINEA", [!DNL s_code.js]ovunque prima:

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Eseguire la chiamata della funzione iniziale**

Aggiungi una chiamata all'inizio `s_getLoadTime()` di [!DNL s_code.js], all'esterno di qualsiasi funzione.

**Eseguire la chiamata della funzione finale**

Aggiungere un'altra chiamata `s_getLoadTime()` `s_doPlugins()` alla funzione, salvando il valore restituito in una prop, eVar e/o un evento numerico.

Esempio di utilizzo 1 - Risparmiate il tempo di caricamento della pagina in prop10 e eVar20:

```js
s.eVar20=s.prop10=s_getLoadTime();
```

Esempio di utilizzo 2 - Salvare il tempo di caricamento della pagina in un evento numerico 99:

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(Facoltativo) Supporto aggiuntivo per browser meno recenti**

Per supportare browser meno recenti che non forniscono la proprietà [window.performance.time](https://www.html5rocks.com/en/tutorials/webperformance/basics/) , includete la seguente riga nella sezione HEAD dell'HTML della pagina vicino all'inizio e prima di richiamare .js, .css o altri file:

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

