---
description: Il codice di Analytics crea un oggetto immagine, un'immagine non visibile che non viene visualizzata sulla pagina.
keywords: Implementazione di Analytics
seo-description: Il codice di Analytics crea un oggetto immagine, un'immagine non visibile che non viene visualizzata sulla pagina.
seo-title: Inserimento del codice Analytics nel tag head
solution: Analytics
title: Inserimento del codice Analytics nel tag head
topic: Sviluppatore e implementazione
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Inserimento del codice Analytics nel tag head

Il codice di Analytics crea un oggetto immagine, un'immagine non visibile che non viene visualizzata sulla pagina.

>[!NOTE]
>
> Questa sezione si applica solo all'implementazione s_code.js legacy. [AppMeasurement per JavaScript 1.0](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) supporta la distribuzione della libreria e del codice della pagina nel `<head>` tag.

In precedenza, una pratica comune di implementazione consisteva nell'inserire il codice JavaScript di Analytics tra <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> e </head> tag. Posizionando il codice tra questi tag, si evita che l'immagine da 1 x 1 pixel restituita dalla richiesta che inviava dati ai server Adobe influenzi in alcun modo il layout di pagina. Se si inserisce del codice nell'intestazione del documento, il codice viene visualizzato prima nel codice. Questo consente di eseguire prima, contando in modo più efficace le visualizzazioni di pagina per i caricamenti parziali delle pagine.

Alcuni elementi del codice richiedono l'esistenza dell'oggetto body. Poiché i browser Web eseguono il codice nell'ordine in cui lo ricevono, se il codice JavaScript di Analytics si trova nell'intestazione del documento, viene eseguito prima che l'oggetto body esista. Di conseguenza, l'implementazione non raccoglie [!UICONTROL ClickMap] dati e il tracciamento automatico dei download o [!UICONTROL exit] dei collegamenti dei file non è disponibile. Inoltre, non vengono ricevuti i dati relativi al tipo di connessione né i dati della home page del visitatore. L'inserimento del codice nell'intestazione del documento funziona, ma il risultato è una versione molto limitata di Analytics, e gli utenti potrebbero chiedersi perché alcuni report e strumenti, inclusi [!UICONTROL ClickMap]i dati, non stiano registrando.

Il codice di Analytics può essere inserito ovunque all'interno dei tag BODY (<BODY></BODY>) di una pagina HTML ben formata. Adobe consiglia di inserire il codice in un file di inclusione globale nella parte superiore della pagina (all’interno del tag HTML body). Il codice può essere inserito in qualsiasi punto della pagina, fatta eccezione per quanto segue:

* Se inserito in una tabella, il codice viene inserito solo all'interno della tabella <td></td> tag. Ad esempio, non inserite il codice tra un'apertura <tr> tag e apertura <td> tag .
* Il codice che imposta le variabili deve verificarsi dopo il riferimento al file s_code.js.
* Verificate che gli [!UICONTROL report suite ID]s nella *`s_account`* variabile nel file s_code.js siano impostati correttamente. Questa variabile viene generalmente impostata correttamente quando si scarica il codice dal Gestore dei codici per una determinata suite di rapporti, o come fornito da un consulente tecnico Adobe.

Se desiderate integrare Analytics con Target, il file di inclusione JavaScript deve essere posizionato in fondo alla pagina. L'esempio seguente mostra la corretta posizione del codice Analytics:

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3.
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

