---
title: p_fo (solo pagina prima)
description: Assicurati che alcune routine si attivino una sola volta per pagina.
feature: Appmeasurement Implementation
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 7%

---

# Plug-in Adobe: p_fo (solo pagina prima)

{{plug-in}}

Il plug-in `p_fo` è un&#39;utility che verifica l&#39;esistenza di un oggetto JavaScript specifico. Se l&#39;oggetto non esiste, il plug-in crea l&#39;oggetto e restituisce `true`. Se l&#39;oggetto JavaScript esiste già nella pagina, restituisce `false`. Questo plug-in è utile per eseguire il codice esattamente una volta su una pagina. Diversi altri plug-in si basano su questo codice per funzionare. Questo plug-in non è necessario se non sei preoccupato del numero di volte in cui il codice viene eseguito su una pagina o se non utilizzi plug-in dipendenti.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fare clic su **[!UICONTROL Tags]** a sinistra, quindi fare clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi sulla scheda **[!UICONTROL Catalog]**
1. Individuare e installare l&#39;estensione **[!UICONTROL Common Web SDK Plugins]**.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi sull&#39;elemento dati desiderato.
1. Imposta il nome dell’elemento dati desiderato con la seguente configurazione:
   * Estensione: Common Web SDK Plugins
   * Elemento dati: `p_fo`
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare manualmente il plug-in implementando Web SDK

Questo plug-in non è ancora supportato per l&#39;utilizzo in un&#39;implementazione manuale del Web SDK.

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
   * Tipo azione: inizializza p_fo
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

Copiare e incollare il codice seguente in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta Adobe a risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `p_fo` utilizza i seguenti argomenti:

* **on** (obbligatorio, stringa): nome dell&#39;oggetto JavaScript creato dal plug-in, se l&#39;oggetto non esiste ancora nella pagina.

Se l&#39;oggetto non esiste ancora, questa funzione restituisce `true` e crea l&#39;oggetto. Se l&#39;oggetto esiste già, questa funzione restituisce `false`.

## Esempio di chiamate

### Esempio di #1

Il codice seguente verifica l&#39;esistenza dell&#39;oggetto &quot;myobject&quot; all&#39;interno della pagina.  Se l&#39;oggetto &quot;myobject&quot; non esiste, il codice creerà l&#39;oggetto &quot;myobject&quot; e restituirà il valore true.  Di conseguenza, verrà eseguito il codice all’interno dell’istruzione condizionale (ovvero Console.log(&#39;hello&#39;);).

D&#39;altra parte, se l&#39;oggetto &quot;myobject&quot; esiste già quando viene effettuata la chiamata p_fo, la funzione p_fo restituirà il valore false e, pertanto, l&#39;istruzione condizionale sarà considerata false.  In questo caso, il codice all’interno dell’istruzione condizionale non verrà eseguito.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTA:** ogni volta che un nuovo oggetto pagina/DOM viene caricato (o la pagina corrente viene ricaricata), l&#39;oggetto specificato nell&#39;argomento on non esiste più e pertanto il plug-in p_fo restituisce nuovamente true la prima volta che viene eseguito dopo il completamento del caricamento della pagina.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.0

* Versione a punti (ricompilata, con codice di dimensioni inferiori).
* Tipo di valore restituito cambiato da intero a booleano

### 1,0

* Versione iniziale.
