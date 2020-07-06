---
title: getPreviousValue
description: Ottenere l'ultimo valore passato in una variabile.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%

---


# Plug-in Adobe: getPreviousValue

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getPreviousValue` plug-in consente di impostare una variabile su un valore impostato su un hit precedente. Questo plug-in non è necessario se l’implementazione contiene tutti i valori desiderati nell’hit corrente.

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
   * Tipo azione: Inizializza getPreviousValue
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
/* Adobe Consulting Plugin: getPreviousValue v2.0 */
s.getPreviousValue=function(v,c){var s=this,d;c=c||"s_gpv";var b=new Date;b.setTime(b.getTime()+18E5);s.c_r(c)&&(d=s.c_r(c)); v?s.c_w(c,v,b):s.c_w(c,d,b);return d};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getPreviousValue` metodo utilizza i seguenti argomenti:

* **`v`** (stringa, obbligatorio): Variabile con il valore che si desidera passare alla richiesta immagine successiva. Una variabile comune utilizzata è `s.pageName` per recuperare il valore della pagina precedente.
* **`c`** (stringa, facoltativo): Nome del cookie che memorizza il valore.  Se questo argomento non è impostato, per impostazione predefinita viene impostato su `"s_gpv"`.

Quando si chiama questo metodo, restituisce il valore stringa contenuto nel cookie. Il plug-in quindi ripristina la scadenza del cookie e gli assegna il valore della variabile dall&#39; `v` argomento. Il cookie scade dopo 30 minuti di inattività.

## Chiamate di esempio

### Esempio n. 1

Codice seguente...

```js
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

* Primo imposta s.prop7 come valore passato in s.pageName nella richiesta di immagine precedente (ovvero il valore memorizzato nel cookie &quot;gpv_Page&quot;)
* Il codice reimposta il cookie &quot;gpv_Page&quot;, facendolo corrispondere al valore corrente di s.pageName
* Se s.pageName non è impostato al momento dell&#39;esecuzione del codice, il codice reimposterà la scadenza per il valore corrente del cookie

### Esempio n. 2

Il codice seguente imposta s.prop7 come ultimo valore passato in s.pageName, ma solo se event1 è contenuto anche all&#39;interno di s.events, come determinato dal plug-in in inList, al momento della chiamata.

```js
if(s.inList(s.events,"event1")) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Esempio n. 3

Il codice seguente imposta s.prop7 come ultimo valore passato in s.pageName ma solo se s.pageName è attualmente impostato sulla pagina allo stesso tempo.

```js
if(s.pageName) s.prop7=s.getPreviousValue(s.pageName,"gpv_Page");
```

### Esempio n. 4

Il codice seguente imposta s.eVar10 uguale al valore passato in s.eVar1 nella richiesta di immagine precedente.   Il precedente valore eVar1 sarebbe stato contenuto nel cookie &quot;s_gpv&quot;.  Il codice imposta quindi il cookie &quot;s_gpv&quot; uguale al valore corrente di s.eVar1.

```js
s.eVar10 = s.getPreviousValue(s.eVar1)
```

## Improbabile

Se la variabile associata all&#39;argomento v è impostata su un nuovo valore e il plug-in getPreviousValue viene eseguito MA una chiamata server Analytics  NON viene inviata contemporaneamente, il nuovo valore dell&#39;argomento v sarà comunque considerato il &quot;valore precedente&quot; al successivo avvio del plug-in.
Ad esempio, si supponga che il codice seguente venga eseguito sulla prima pagina della visita:

```js
s.pageName="home"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Questo codice genera una chiamata server in cui l’argomento pageName è uguale a &quot;home&quot; e l’argomento p7 (prop7) non è impostato.  Tuttavia, la chiamata a s.getPreviousValue memorizzerebbe il valore di s.pageName (ovvero &quot;home&quot;) nel cookie specificato nella chiamata (ovvero il cookie &quot;gpv_Page&quot;).
Ora, si supponga che subito dopo, sulla stessa pagina, venga eseguito il seguente codice (per qualsiasi motivo):

```js
s.pageName="happy value"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
```

Poiché la funzione s.t() non viene eseguita in questo blocco di codice, non verrà creata un&#39;altra richiesta di immagine.  Tuttavia, quando il codice della funzione s.getPreviousValue() viene eseguito questa volta, s.prop7 verrà impostato come il valore precedente di s.pageName (cioè &quot;home&quot;) e quindi memorizzerà il nuovo valore di s.pageName (ovvero &quot;Happy value&quot;) nel cookie &quot;gpv_Page&quot;.
Supponiamo che il visitatore passi a un&#39;altra pagina e che il seguente codice venga eseguito su questa pagina:

```js
s.pageName="page 2"
s.prop7=s.getPreviousValue(s.pageName,"gpv_Page")
s.t();
```

Quando viene eseguita la funzione di chiamata s.t(), viene creata una richiesta di immagine in cui s.pageName=&quot;page 2&quot; e s.prop7 è uguale a &quot;Happy value&quot;, che era il valore di s.pageName quando è stata effettuata l’ultima chiamata a getPreviousValue.   Il valore s.prop7 di &quot;home&quot; non è mai stato incluso in alcuna richiesta di immagine reale, anche se &quot;home&quot; era il primo valore passato in s.pageName.

## Cronologia versioni

### v2.0 (7 ottobre 2019)

* Rilascio punto (riscrittura logica completa).
