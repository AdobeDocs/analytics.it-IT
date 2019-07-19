---
description: Il codice di Analytics crea un oggetto immagine, un'immagine non visibile che non viene visualizzata sulla pagina.
keywords: Implementazione di Analytics
seo-description: Il codice di Analytics crea un oggetto immagine, un'immagine non visibile che non viene visualizzata sulla pagina.
seo-title: Inserimento del codice Analytics nel tag head
solution: Analytics
title: Inserimento del codice Analytics nel tag head
topic: Sviluppatore e implementazione
uuid: e 8 f 91 d 3 c-cb 72-454 d -9 bd 4-ff 54 d 83 d 981 f
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Inserimento del codice Analytics nel tag head

Il codice di Analytics crea un oggetto immagine, un'immagine non visibile che non viene visualizzata sulla pagina.

>[!NOTE]
>
>Questa sezione si applica solo all'implementazione s_ code. js legacy. [Appmeasurement per javascript 1.0](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) supporta la distribuzione della libreria e del codice della pagina nel `<head>` tag.

In precedenza, una pratica di implementazione comune era quella di inserire il codice javascript di Analytics tra i <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> e </head> tag. Inserendo il codice tra questi tag, è stato impedito che l'immagine da 1 x 1 pixel restituita dalla richiesta che invii dati nei server Adobe comprometta in qualsiasi modo il layout della pagina. L'inserimento del codice nella intestazione del documento indica che il codice è visualizzato prima nel codice. Questo consente di eseguire prima, il che consente di contare le visualizzazioni di pagina per il caricamento parziale di una pagina.

Alcuni elementi del codice richiedono l'esistenza dell'oggetto body. Poiché i browser Web eseguono il codice nell'ordine in cui ricevono il codice, se il codice javascript di Analytics si trova nella intestazione del documento, viene eseguito prima dell'oggetto body. As a result, your implementation does not collect [!UICONTROL ClickMap] data, and automatic tracking of file downloads or [!UICONTROL exit] links are not available. Inoltre, non riceverete dati sui tipi di connessione o i dati della pagina principale dei visitatori. Putting the code in the document head works, but the result is a very limited version of Analytics, and users may wonder why certain reports and tools, including [!UICONTROL ClickMap], aren't recording data.

Il codice di Analytics può essere posizionato ovunque all'interno dei tag BODY (<BODY></BODY>) di una pagina HTML ben formata. Adobe consiglia di posizionare il codice in un file globale incluso nella parte superiore della pagina (all'interno del tag body HTML). Il codice può essere posizionato in qualsiasi punto della pagina, ad eccezione di quanto indicato di seguito:

* Se inserita all'interno di una tabella, pubblicate il codice solo all'interno della variabile <td></td> tag. Ad esempio, non inserire il codice tra un'apertura <tr> e un'apertura <td> tag.
* Il codice che imposta le variabili deve verificarsi dopo il riferimento al file s_ code. js.
* Make certain that the [!UICONTROL report suite ID]s in the *`s_account`* variable in the s_code.js file are set correctly. Questa variabile viene generalmente impostata correttamente quando si scarica codice da Code Manager per una particolare suite di rapporti, o come fornito da un consulente tecnico Adobe.

Se desiderate integrare Analytics con Target, il file javascript include il file in fondo alla pagina. L'esempio seguente mostra il posizionamento corretto del codice Analytics:

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

