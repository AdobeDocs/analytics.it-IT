---
title: p_fo (solo pagina prima)
description: Assicurati che alcune routine si attivino una sola volta per pagina.
feature: Variables
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 8%

---

# Plug-in di Adobe: p_fo (solo pagina prima)

{{plug-in}}

La `p_fo` Il plug-in è un&#39;utility che verifica l&#39;esistenza di un oggetto JavaScript specifico. Se l&#39;oggetto non esiste, il plug-in crea l&#39;oggetto e restituisce `true`. Se l&#39;oggetto JavaScript esiste già nella pagina, restituisce `false`. Questo plug-in è utile per eseguire il codice esattamente una volta su una pagina. Diversi altri plug-in si basano su questo codice per funzionare. Questo plug-in non è necessario se non sei preoccupato del numero di volte in cui il codice viene eseguito su una pagina o se non utilizzi plug-in dipendenti.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con l’SDK per web.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic su **[!UICONTROL Tags]** a sinistra, quindi fai clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi fai clic sul pulsante **[!UICONTROL Catalog]** scheda
1. Individua e installa il **[!UICONTROL Common Web SDK Plugins]** estensione.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi fai clic sull’elemento dati desiderato.
1. Imposta il nome dell&#39;elemento dati desiderato con la seguente configurazione:
   * Estensione: Plug-in SDK per web comuni
   * Elemento dati: `p_fo`
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare il plug-in manualmente durante l’implementazione dell’SDK per web

Questo plug-in non è ancora supportato per l&#39;utilizzo in un&#39;implementazione manuale dell&#39;SDK web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza p_fo
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `p_fo` La funzione utilizza i seguenti argomenti:

* **su** (obbligatorio, stringa): Nome dell&#39;oggetto JavaScript creato dal plug-in se l&#39;oggetto non esiste ancora nella pagina.

Se l&#39;oggetto non esiste ancora, questa funzione restituisce `true` e crea l&#39;oggetto. Se l&#39;oggetto esiste già, questa funzione restituisce `false`.

## Chiamate di esempio

### Esempio n. 1

Il codice seguente controllerà l&#39;esistenza dell&#39;oggetto &quot;myobject&quot; all&#39;interno della pagina.  Se l&#39;oggetto &quot;myobject&quot; non esiste, il codice creerà l&#39;oggetto &quot;myobject&quot; e restituirà il valore true.  Di conseguenza, viene eseguito il codice all’interno dell’istruzione condizionale (ad esempio Console.log(&#39;hello&#39;);).

Se invece l&#39;oggetto &quot;myobject&quot; esiste già quando avviene la chiamata p_fo, la funzione p_fo restituirà il valore di false e, quindi, l&#39;istruzione condizionale verrà considerata false.  In questo caso, il codice all’interno dell’istruzione condizionale non verrà eseguito.

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTA:** Ogni volta che viene caricato un nuovo oggetto pagina/DOM (o la pagina corrente viene ricaricata), l’oggetto specificato nell’argomento on non esisterà più e quindi il plug-in p_fo restituirà nuovamente true la prima volta che viene eseguito dopo il termine del caricamento della pagina.

## Cronologia versioni

### 3.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.0

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* Tipo di valore restituito modificato da integer a booleano

### 1.0

* Versione iniziale.
