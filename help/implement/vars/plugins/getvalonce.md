---
title: getValOnce
description: Impedite che una variabile Analytics  venga impostata sullo stesso valore due volte nella riga.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---


# Plug-in Adobe: getValOnce

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `getValOnce` plug-in impedisce che una variabile venga impostata più volte sullo stesso valore. Adobe consiglia di utilizzare questo plug-in quando si desidera deduplicare le occorrenze in cui un visitatore aggiorna una pagina o in altro modo visita una pagina specifica più volte. Questo plug-in non è necessario se non sei preoccupato per la metrica &#39;Occorrenze&#39; in  Analysis Workspace.

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
   * Tipo azione: Inizializza getValOnce
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
/* Adobe Consulting Plugin: getValOnce v2.01 */
s.getValOnce=function(vtc,cn,et,ep){if(vtc&&(cn=cn||"s_gvo",et=et||0,ep="m"===ep?6E4:864E5,vtc!==this.c_r(cn))){var e=new Date;e.setTime(e.getTime()+et*ep);this.c_w(cn,vtc,0===et?0:e);return vtc}return""};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `getValOnce` metodo utilizza i seguenti argomenti:

* **`vtc`** (obbligatorio, stringa): La variabile da verificare e verificare se è stata precedentemente impostata su un valore identico
* **`cn`** (facoltativo, stringa): Nome del cookie che contiene il valore da verificare. Il valore predefinito è `"s_gvo"`
* **`et`** (facoltativo, numero intero): Scadenza del cookie in giorni (o minuti, a seconda dell&#39; `ep` argomento). Il valore predefinito è `0`, che scade alla fine della sessione del browser
* **`ep`** (facoltativo, stringa): Impostate questo argomento solo se è impostato anche l&#39; `et` argomento. Impostate questo argomento su `"m"` se desiderate che l&#39; `et` argomento scada in minuti invece che in giorni. Il valore predefinito è `"d"`, che imposta l&#39; `et` argomento in giorni.

Se l&#39; `vtc` argomento e il valore del cookie corrispondono, questo metodo restituisce una stringa vuota. Se l&#39; `vtc` argomento e il valore del cookie non corrispondono, il metodo restituisce l&#39; `vtc` argomento come una stringa.

## Chiamate di esempio

### Esempio n. 1

Utilizzate questa chiamata per evitare che lo stesso valore venga passato a s.campaign più di una volta alla riga per i 30 giorni successivi:

```js
s.campaign=s.getValOnce(s.campaign,"s_campaign",30);
```

Nella chiamata precedente, il plug-in confronterà prima il valore già contenuto nel cookie s_campaign con il valore proveniente dalla variabile s.campaign corrente.   Se non viene trovata una corrispondenza, il plug-in imposta il cookie s_campaign pari al nuovo valore proveniente da s.campaign e restituisce il nuovo valore.   Questo confronto avverrà per i prossimi trenta giorni

### Esempio n. 2

Utilizzate questa chiamata per evitare che lo stesso valore venga impostato per tutta la sessione:

```js
s.eVar2=s.getValOnce(s.eVar2,"s_ev2",0,"m");
```

Questo codice impedisce che lo stesso valore venga passato in s.eVar2 più di una volta alla riga durante l&#39;intera sessione dell&#39;utente.  Inoltre ignora il valore &quot;m&quot; nel frammento (alla fine della chiamata), dal momento che l’ora di scadenza è impostata su 0.   Il codice memorizza anche il valore di confronto nel cookie s_ev2.

## Cronologia versioni

### 2.01

* È stato risolto un problema relativo alla scrittura dei cookie.

### 2.0

* Rilascio punto (ricompilato, dimensioni del codice più piccole).

### 1.1

* Aggiunta l&#39;opzione per scegliere minuti o giorni per la scadenza tramite il `t` parametro.
* Correzione dell&#39;ambito della `k` variabile utilizzata per limitarla al solo plug-in. Questa modifica impedisce possibili interferenze con altro codice sulla pagina.
