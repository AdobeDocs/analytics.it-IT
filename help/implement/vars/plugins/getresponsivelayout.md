---
title: getResponsiveLayout
description: Determinare il layout di un sito Web attualmente visualizzato.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---


# Plug-in Adobe: getResponsiveLayout

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getResponsiveLayout` plug-in consente di tenere traccia della versione del sito Web reattivo basato sul design che un visitatore sta attualmente visualizzando. Adobe consiglia di utilizzare questo plug-in se il sito utilizza una progettazione reattiva e desideri monitorare la versione del sito visualizzato da un visitatore. Questo plug-in non è necessario se il sito non utilizza la progettazione reattiva.

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
   * Tipo azione: Initialize getResponsiveLayout
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
/* Adobe Consulting Plugin: getResponsiveLayout v1.0 */
var getResponsiveLayout=function(ppw,plw,tw){if(!(isNaN(ppw)||isNaN(plw)||isNaN(tw)||plw<ppw||tw<plw)){var b=window.innerWidth|| document.documentElement.clientWidth||document.body.clientWidth;return(ppw<plw&&b<=plw?b<=ppw?"phone portrait layout":"phone landscape layout":b<=plw?"phone layout":b<=tw?"tablet layout":"desktop layout")+":"+b+"x"+(window.innerHeight|| document.documentElement.clientHeight||document.body.clientHeight)}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getResponsiveLayout` metodo utilizza i seguenti argomenti:

* **`ppw`** (obbligatorio, numero intero): Larghezza massima di pixel che una finestra del browser può avere prima che la pagina passi da un layout telefono verticale a un layout telefono orizzontale
* **`plw`** (obbligatorio, numero intero): Larghezza massima di pixel che una finestra del browser può avere prima che la pagina passi da un layout telefono orizzontale a un layout basato su tablet
* **`tw`** (obbligatorio, booleano): Larghezza massima di pixel che una finestra del browser può avere prima che la pagina passi da un layout tablet a un layout basato su desktop

La chiamata di questo metodo restituisce una stringa contenente due parti. La prima parte utilizza uno dei seguenti valori, a seconda della larghezza del browser e degli argomenti precedenti:

* `"phone portrait layout"`
* `"phone landscape layout"`
* `"phone layout"` (per i siti che non dispongono sia di layout verticale che di layout orizzontale)
* `"tablet layout"`
* `"desktop layout"`

La seconda parte della stringa restituita corrisponde alle dimensioni di larghezza e altezza del browser. Ad esempio, `"desktop layout:1243x700"`.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

* Il sito passa dalla modalità verticale del telefono alla modalità orizzontale del telefono quando la larghezza del browser è maggiore di 500 pixel
* Il sito passa dalla modalità orizzontale del telefono alla modalità tablet quando la larghezza del browser è superiore a 700 pixel
* Il sito passa dalla modalità tablet alla modalità desktop quando la larghezza del browser è superiore a 1000 pixel

...il codice seguente imposta eVar10 uguale al layout di progettazione reattivo corrente come esperienza del visitatore, nonché alla larghezza e alle dimensioni del browser

```js
s.eVar10 = getResponsiveLayout(500, 700, 1000);
```

### Esempio n. 2

Se viene mostrato...

* Il sito dispone solo di una modalità telefono, tablet e desktop
* Il sito passa dalla modalità telefono alla modalità tablet quando la larghezza del browser è superiore a 500 pixel
* Il sito passa dalla modalità tablet alla modalità desktop quando la larghezza del browser è superiore a 1.100 pixel

...il codice seguente imposta eVar10 uguale al layout di progettazione reattivo corrente come esperienza del visitatore, nonché alla larghezza e alle dimensioni del browser

```js
s.eVar10 = getResponsiveLayout(500, 500, 1100);
```

## Cronologia versioni

### 1.0 (2 maggio 2018)

* Versione iniziale.
