---
title: ' cleanStr'
description: Rimuovere o sostituire tutti i caratteri non necessari da una stringa.
translation-type: tm+mt
source-git-commit: e08f3e168a779f9678a109d7f533761629cd38f3

---


# Plug-in Adobe: cleanStr

> [!IMPORTANT] Questo plug-in è fornito da Adobe Consulting come servizio di cortesia per trarre maggior valore dall&#39;utilizzo di Adobe Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `cleanStr` plug-in rimuove o sostituisce tutti i caratteri non necessari da una stringa, inclusi i caratteri tag HTML, gli spazi bianchi, le schede e i ritorni a capo/riga. Sostituisce anche le virgolette singole (`‘` e `’`) singole (`'`) dritte. Adobe consiglia di utilizzare questo plug-in se desiderate rimuovere caratteri non necessari dai valori delle variabili e la funzione &quot;Testo pulito&quot; di Launch non soddisfa le vostre esigenze di implementazione. Questo plug-in non è necessario se i dati raccolti non contengono caratteri superflui o se la funzione &quot;Testo pulito&quot; di Launch è sufficiente.

## Installare il plug-in utilizzando l&#39;estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Per qualsiasi regola di avvio in cui desiderate utilizzare il plug-in, aggiungete un’azione con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Initialize addProductEvar
1. Salvataggio e pubblicazione delle modifiche alla regola

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche all&#39;estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata l&#39;istanza dell&#39;oggetto di tracciamento di Analytics (tramite `s_gi`). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: cleanStr v1.0 */
function cleanStr(str){if("string"===typeof str){str=str.replace(/<\/?[^>]+(>|$)/g,"");str=str.trim(); str=str.replace(/[\u2018\u2019\u201A]/g,"'");str=str.replace(/\t+/g,"");for(str=str.replace(/[\n\r]/g," ");-1<str.indexOf("  ");)str=str.replace(/\s\s/g," ");return str}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `cleanStr` metodo utilizza i seguenti argomenti:

* **`str`**(obbligatorio, stringa): Il valore che si desidera eliminare la codifica HTML, gli spazi bianchi, le schede o altri caratteri non necessari.

Il metodo restituisce il valore dell&#39; `str` argomento e tutti i caratteri non necessari vengono rimossi.

## Esempi

### Esempio n. 1

Si supponga quanto segue (dove i punti rappresentano spazi e le frecce rappresentano caratteri di tabulazione)

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

Quando si esegue il codice seguente...

```js
s.eVar1 = cleanStr(s.eVar1)
```

...eVar1 verrà impostato su &quot;this is a messystring&quot; (questa è una stringa di messaggio) (tutti gli spazi aggiuntivi e tutti i caratteri di tabulazione rimossi)

### Esempio n. 2

Se viene mostrato...

```js
s.eVar1 = "»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

...e viene eseguito il codice seguente...

```js
cleanStr(s.eVar1)
```

...il valore finale di s.eVar1 sarà ancora:

```js
"»∙∙this∙∙is∙a∙∙»∙messy»string∙∙∙∙"
```

L&#39;esecuzione del plug-in da sola (senza assegnare il valore restituito a una variabile) non comporta in realtà la &quot;reimpostazione&quot; della variabile passata attraverso l&#39;argomento str.

## Cronologia versioni

### 1.0 (15 aprile 2018)

* Versione iniziale.
