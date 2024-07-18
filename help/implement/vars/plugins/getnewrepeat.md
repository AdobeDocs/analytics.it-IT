---
title: getNewRepeat
description: Tracciare l’attività dei visitatori nuovi rispetto a quelli ripetuti.
feature: Variables
exl-id: 8f64e176-1926-4cb1-bfae-09d7e2c015ae
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 7%

---

# Plug-in di Adobe: getNewRepeat

{{plug-in}}

Il plug-in `getNewRepeat` consente di determinare se un visitatore del sito è un nuovo visitatore o un visitatore ripetuto entro un numero desiderato di giorni. L’Adobe consiglia di utilizzare questo plug-in se desideri identificare i visitatori come &quot;nuovi&quot; utilizzando un numero di giorni personalizzato. Questo plug-in non è necessario se le dimensioni Visitatore nuovo/ripetuto in Analysis Workspace soddisfano le esigenze della tua organizzazione.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fare clic su **[!UICONTROL Tags]** a sinistra, quindi fare clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi sulla scheda **[!UICONTROL Catalog]**
1. Individuare e installare l&#39;estensione **[!UICONTROL Common Web SDK Plugins]**.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi sull&#39;elemento dati desiderato.
1. Imposta il nome dell’elemento dati desiderato con la seguente configurazione:
   * Estensione: Common Web SDK Plugins
   * Elemento dati: `getNewRepeat`
1. Imposta il parametro `daysBeforeReset` a destra.
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare manualmente il plug-in implementando Web SDK

Questo plug-in non è ancora supportato per l’utilizzo in un’implementazione manuale dell’SDK per web.

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
   * Tipo azione: inizializzare getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v3.0 (Requires AppMeasurement) */
function getNewRepeat(d){var a=d;if("-v"===a)return{plugin:"getNewRepeat",version:"3.0"};var d=function(){if("undefined"!==typeof window.s_c_il)for(var c=0,b;c<window.s_c_il.length;c++)if(b=window.s_c_il[c],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof d&&(d.contextData.getNewRepeat="3.0");window.cookieWrite=window.cookieWrite||function(c,b,f){if("string"===typeof c){var h=window.location.hostname,a=window.location.hostname.split(".").length-1;if(h&&!/^[0-9.]+$/.test(h)){a=2<a?a:2;var e=h.lastIndexOf(".");if(0<=e){for(;0<=e&&1<a;)e=h.lastIndexOf(".",e-1),a--;e=0<e?h.substring(e):h}}g=e;b="undefined"!==typeof b?""+b:"";if(f||""===b)if(""===b&&(f=-60),"number"===typeof f){var d=new Date;d.setTime(d.getTime()+6E4*f)}else d=f;return c&&(document.cookie=encodeURIComponent(c)+"="+encodeURIComponent(b)+"; path=/;"+(f?" expires="+d.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(c)===b:!1}};window.cookieRead=window.cookieRead||function(c){if("string"===typeof c)c=encodeURIComponent(c);else return"";var b=" "+document.cookie,a=b.indexOf(" "+c+"="),d=0>a?a:b.indexOf(";",a);return(c=0>a?"":decodeURIComponent(b.substring(a+2+c.length,0>d?b.length:d)))?c:""};a=a?a:30;d="s_nr"+a;var k=new Date,m=cookieRead(d),n=m.split("-"),l=k.getTime();k.setTime(l+864E5*a);if(""===m||18E5>l-n[0]&&"New"===n[1])return cookieWrite(d,l+"-New",k),"New";cookieWrite(d,l+"-Repeat",k);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `getNewRepeat` utilizza i seguenti argomenti:

* **`d`** (numero intero, facoltativo): il numero minimo di giorni necessari tra le visite che reimposta i visitatori su `"New"`. Se questo argomento non è impostato, il valore predefinito è 30 giorni.

Questa funzione restituisce il valore di `"New"` se il cookie impostato dal plug-in non esiste o è scaduto. Restituisce il valore di `"Repeat"` se il cookie impostato dal plug-in esiste e il tempo trascorso dall&#39;hit corrente e dal cookie è superiore a 30 minuti. Questa funzione restituisce lo stesso valore per un’intera visita.

Questo plug-in utilizza un cookie denominato `"s_nr[LENGTH]"` in cui `[LENGTH]` è uguale all&#39;argomento `d`. Il cookie contiene una marca temporale Unix che rappresenta l&#39;ora corrente e lo stato corrente del visitatore (`"New"` o `"Repeat"`).

## Esempi

```js
// Sets eVar1 to "New" if it is the visitor's first visit to the site, or they have not visited in at least 30 days. Otherwise, sets eVar1 to "Repeat".
s.eVar1 = getNewRepeat();

// Sets eVar2 to "New" if it is the visitor's first visit to the site, or they have not visited in at least a year (365 days). Otherwise, sets eVar2 to "Repeat".
s.eVar2 = getNewRepeat(365);
```

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.1 (30 settembre 2019)

* Ridisposizione della logica JavaScript per ridurre le dimensioni del plug-in

### 2.0 (16 aprile 2018)

* Ricompilato con dimensioni del codice inferiori
* È stata rimossa la possibilità di denominare il cookie per memorizzare le informazioni sulla visita. Il plug-in ora assegna al cookie un nome dinamico in base al valore passato nell&#39;argomento `d`.
