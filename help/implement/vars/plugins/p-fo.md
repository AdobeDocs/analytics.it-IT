---
title: p_fo (solo pagina prima)
description: Assicurarsi che alcune routine vengano attivate una sola volta per pagina.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---


# Plug-in Adobe: p_fo (solo pagina prima)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `p_fo` plug-in è un&#39;utility che verifica l&#39;esistenza di un oggetto JavaScript specifico. Se l&#39;oggetto non esiste, il plug-in crea l&#39;oggetto e restituisce `true`. Se l&#39;oggetto JavaScript esiste già sulla pagina, restituisce `false`. Questo plug-in è utile per eseguire il codice esattamente una volta su una pagina. Molti altri plug-in dipendono da questo codice per funzionare. Questo plug-in non è necessario se non si è preoccupati del numero di volte in cui il codice viene eseguito su una pagina o se non si utilizzano plug-in dipendenti.

## Installare il plug-in utilizzando l&#39;estensione Lancio del Adobe Experience Platform 

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Initialize p_for
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v2.0 */
s.p_fo=function(on){var s=this;s.__fo||(s.__fo={});if(s.__fo[on])return!1;s.__fo[on]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `p_fo` metodo utilizza i seguenti argomenti:

* **on** (obbligatorio, stringa): Il nome dell&#39;oggetto JavaScript creato dal plug-in se l&#39;oggetto non esiste ancora nella pagina.

Se l&#39;oggetto non esiste ancora, questo metodo restituisce `true` e crea l&#39;oggetto. Se l&#39;oggetto esiste già, questo metodo restituisce `false`.

## Chiamate di esempio

### Esempio n. 1

Il codice seguente controllerà l&#39;esistenza dell&#39;oggetto &quot;myobject&quot; nella pagina.  Se l&#39;oggetto &quot;myobject&quot; non esiste, il codice creerà l&#39;oggetto &quot;myobject&quot; e restituirà il valore true.  Di conseguenza, verrà eseguito il codice all&#39;interno dell&#39;istruzione condizionale (ad es. Console.log(&#39;hello&#39;);).

D&#39;altro canto, se l&#39;oggetto &quot;myobject&quot; esiste già quando viene effettuata la chiamata p_fo, la funzione p_fo restituirà il valore di false e, di conseguenza, l&#39;istruzione condizionale sarà considerata false.  In questo caso, il codice all&#39;interno dell&#39;istruzione condizionale non verrà eseguito.

```javascript
if(s.p_fo("myobject"))
{
  console.log("hello");
}
```

**NOTA:** Ogni volta che un nuovo oggetto pagina/DOM viene caricato (o la pagina corrente viene ricaricata), l&#39;oggetto specificato nell&#39;argomento on non esisterà più e quindi il plug-in p_for restituirà nuovamente true la prima volta che viene eseguito al termine del caricamento della pagina.

## Cronologia versioni

### 2.0

* Rilascio punto (ricompilato, dimensioni del codice più piccole).
* Tipo di valore restituito modificato da numero intero a booleano

### 1.0

* Versione iniziale.
