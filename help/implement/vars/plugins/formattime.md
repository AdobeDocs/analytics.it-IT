---
title: formatTime
description: Converti un numero di secondi nel suo equivalente in minuti, ore, ecc.
feature: Variables
exl-id: 4b98e7fe-f05b-4346-b284-697268adc1a2
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 6%

---

# Plug-in Adobe: formatTime

{{plug-in}}

Il plug-in `formatTime` consente di richiedere un numero qualsiasi di secondi e di presentarli in un formato a blocchi, arrotondato al valore di benchmark desiderato. L’Adobe consiglia di utilizzare questo plug-in se desideri acquisire un valore di tempo in secondi e convertirlo in un formato bucket (ad esempio minuti, giorni o settimane). Questo plug-in non è necessario se non si desidera inserire valori basati su secondi in un formato con arrotondamento temporale.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l’utilizzo nell’SDK per web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: Initialize formatTime
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Configure tracking using custom code], che mostra il pulsante [!UICONTROL Open Editor].
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiare e incollare il codice seguente in qualsiasi punto del file di AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento di Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: formatTime v2.0 */
function formatTime(ns,tf,bml){var f=ns,d=tf,e=bml;function h(b,d,c,e){if("string"!==typeof d)return!1;if("string"===typeof b)b=b.split(c||",");else if("object"!==typeof b)return!1;c=0;for(a=b.length;c<a;c++)if(1==e&&d===b[c]||d.toLowerCase()===b[c].toLowerCase())return!0;return!1}if(arguments&&"-v"===arguments[0])return{plugin:"formatTime",version:"2.0"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var b=0,c;b<window.s_c_il.length;b++)if(c=window.s_c_il[b],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.formatTime="2.0");if(!("undefined"===typeof f||isNaN(f)||0>Number(f))){b="";if("string"===typeof d&&"d"===d||("string"!==typeof d||!h("h,m,s",d))&&86400<=f){var c=86400;var g="days";b=isNaN(e)?1:c/(e*c)}else"string"===typeof d&&"h"===d||("string"!==typeof d||!h("m,s",d))&&3600<=f?(c=3600,g="hours",b=isNaN(e)?4:c/(e*c)):"string"===typeof d&&"m"===d||("string"!==typeof d||!h("s",d))&&60<=f?(c=60,g="minutes",b=isNaN(e)?2:c/(e*c)):(c=1,g="seconds",b=isNaN(e)?.2:c/e);b=Math.round(f*b/c)/b+" "+g;0===b.indexOf("1 ")&&(b=b.substring(0,b.length-1));return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `formatTime` utilizza i seguenti argomenti:

* **`ns`** (obbligatorio, numero intero): numero di secondi per la conversione o il formato
* **`tf`** (facoltativo, stringa): tipo di formato in cui restituire i secondi; impostazione predefinita: secondi
   * Imposta su `"d"` se vuoi il tempo in giorni (arrotondato al benchmark di 1/4 giorno più vicino per impostazione predefinita)
   * Imposta su `"h"` se desideri il tempo in ore (arrotondato al benchmark di 1/4 ore più vicino per impostazione predefinita)
   * Imposta su `"m"` se vuoi il tempo in minuti (arrotondato al benchmark di 1/2 minuti più vicino per impostazione predefinita)
   * Imposta su `"s"` se desideri il tempo in secondi (arrotondato al benchmark di 5 secondi più vicino per impostazione predefinita)
* **`bml`** (facoltativo, numero): lunghezza dei parametri di riferimento di arrotondamento. Impostazione predefinita dei benchmark elencati nell&#39;argomento `tf`

La funzione restituisce il numero di secondi formattati utilizzando l&#39;unità specificata nell&#39;argomento `tf`. Se l&#39;argomento `tf` non è impostato:

* Qualsiasi valore inferiore a un minuto viene arrotondato al valore di riferimento di 5 secondi più vicino
* Il tempo compreso tra un minuto e un&#39;ora viene arrotondato al valore di riferimento di 1/2 minuto più vicino
* Qualsiasi elemento compreso tra un’ora e un giorno viene arrotondato al valore di riferimento di un quarto d’ora più vicino
* Qualsiasi valore superiore a un giorno viene arrotondato al valore di riferimento del giorno più vicino

## Esempi

```js
// Sets eVar1 to "10.5 hours".
// 38242 seconds equals 10 hours, 37 minutes, and 22 seconds. Since the tf argument is not set, the value returned is the number of seconds converted to the nearest quarter-hour benchmark.
s.eVar1 = formatTime(38242);

// Sets eVar4 to "10.75 hours".
// 38250 seconds equals 10 hours, 37 minutes, and 30 seconds. This value rounds up to the nearest quarter hour.
s.eVar4 = formatTime(38250);

// Sets eVar9 to "637.5 minutes".
s.eVar9 = formatTime(38242, "m");

// Sets eVar14 to "640 minutes".
// The tf argument forces the returned value to minutes, while the bml argument forces the value to the nearest 20-minute increment.
s.eVar14 = formatTime(38242, "m", 20);

// Sets eVar2 to "126 seconds", the closest 2-second benchmark to 125 seconds.
s.eVar2 = formatTime(125, "s", 2);

// Sets eVar7 to "3 minutes", the closest 3-minute benchmark to 125 seconds.
s.eVar7 = formatTime(125, "m", 3);

// Sets eVar55 to "2.4 minutes, the closest 2/5-minute benchmark to 145 seconds.
s.eVar55 = formatTime(145, "m", .4);
```

## Cronologia versioni

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.1 (21 maggio 2018)

* È stato aggiunto l&#39;argomento `bml` per consentire una maggiore flessibilità nell&#39;arrotondamento

### 1.0 (15 aprile 2018)

* Versione iniziale.
