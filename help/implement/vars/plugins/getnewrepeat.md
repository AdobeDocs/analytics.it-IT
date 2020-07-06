---
title: getNewRepeat
description: Consente di tenere traccia dell’attività dei visitatori nuovi e ripetuti.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '805'
ht-degree: 0%

---


# Plug-in Adobe: getNewRepeat

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getNewRepeat` plug-in consente di determinare se un visitatore del sito è un nuovo visitatore o un altro visitatore entro un numero desiderato di giorni. Adobe consiglia di utilizzare questo plug-in se desiderate identificare i visitatori come &quot;nuovi&quot; utilizzando un numero personalizzato di giorni. Questo plug-in non è necessario se le dimensioni Nuovo/Ripeti visitatore in  Analysis Workspace soddisfano le esigenze aziendali.

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
   * Tipo azione: Initialize getNewRepeat
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
/* Adobe Consulting Plugin: getNewRepeat v2.1 */
s.getNewRepeat=function(d){d=d?d:30;var s=this,p="s_nr"+d,b=new Date,e=s.c_r(p),f=e.split("-"),c=b.getTime();b.setTime(c+864E5*d); if(""===e||18E4>c-f[0]&&"New"===f[1])return s.c_w(p,c+"-New",b),"New";s.c_w(p,c+"-Repeat",b);return"Repeat"};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getNewRepeat` metodo utilizza i seguenti argomenti:

* **`d`** (numero intero, facoltativo): Il numero minimo di giorni necessari tra le visite per ripristinare i visitatori `"New"`. Se questo argomento non è impostato, per impostazione predefinita è 30 giorni.

Questo metodo restituisce il valore di `"New"` se il cookie impostato dal plug-in non esiste o è scaduto. Restituisce il valore di `"Repeat"` se il cookie impostato dal plug-in esiste e la quantità di tempo dall&#39;hit corrente e l&#39;ora impostata nel cookie è maggiore di 30 minuti. Questo metodo restituisce lo stesso valore per un’intera visita.

Questo plug-in utilizza un cookie denominato `"s_nr[LENGTH]"` dove `[LENGTH]` è uguale all&#39; `d` argomento. Il cookie contiene una marca temporale Unix che rappresenta l’ora corrente e lo stato corrente del visitatore (`"New"` o `"Repeat"`).

## Chiamate di esempio

### Esempio n. 1

Il codice seguente imposta s.eVar1 uguale al valore di &quot;New&quot; per i nuovi visitatori e continuerà a impostare s.eVar1 uguale al valore di &quot;New&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat();
```

### Esempio n. 2

Se il visitatore ritorna al sito in qualsiasi momento da 31 minuti a 30 giorni dall&#39;ultima chiamata a s.getNewRepeat(), il codice seguente imposta s.eVar1 uguale al valore di &quot;Repeat&quot; e continuerà a impostare s.eVar1 uguale al valore di &quot;Repeat&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat();
```

### Esempio n. 3

Se il visitatore non è stato sul sito per almeno 30 giorni dall&#39;ultima chiamata a s.getNewRepeat(), il codice seguente imposta s.eVar1 uguale al valore di &quot;New&quot; e continuerà a impostare s.eVar1 uguale al valore di &quot;New&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat();
```

### Esempio n. 4

Se il visitatore ritorna al sito in qualsiasi momento da 31 minuti a 365 giorni (ossia 1 anno) dall&#39;ultima chiamata a s.getNewRepeat(), il codice seguente imposta s.eVar1 uguale al valore &quot;Repeat&quot; e continuerà a impostare s.eVar1 uguale al valore &quot;Repeat&quot; (con ogni nuova chiamata) per tutto il resto del visitatore Visita al sito.

```js
s.eVar1=s.getNewRepeat(365);
```

### Esempio n. 5

Se il visitatore non è stato sul sito per almeno 365 giorni (ovvero 1 anno) dall&#39;ultima chiamata a s.getNewRepeat(), il codice seguente imposta s.eVar1 uguale al valore &quot;New&quot; e continuerà a impostare s.eVar1 uguale al valore &quot;New&quot; (con ogni nuova chiamata) per tutto il resto della visita del visitatore al sito.

```js
s.eVar1=s.getNewRepeat(365);
```

## Cronologia versioni

### 2.1 (30 settembre 2019)

* Ridisposizione della logica JavaScript per ridurre le dimensioni del plug-in

### 2.0 (16 aprile 2018)

* Ricompilato con dimensioni del codice più piccole
* È stata rimossa la possibilità di assegnare un nome al cookie per memorizzare le informazioni sulla visita. Il plug-in ora assegna un nome dinamico al cookie in base al valore passato nell&#39; `d` argomento.
