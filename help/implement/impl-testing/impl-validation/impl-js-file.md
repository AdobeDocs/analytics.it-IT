---
description: Verificare che la pagina contenga un riferimento corretto al file .JS. È possibile specificare il percorso relativo al documento corrente oppure utilizzare un nome di percorso assoluto.
keywords: Analytics Implementation
solution: Analytics
title: File JavaScript JS
topic: Developer and implementation
uuid: 6e83223f-2127-41d3-9806-bd085fa2a747
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# File JavaScript JS

Verificare che la pagina contenga un riferimento corretto al file .JS. È possibile specificare il percorso relativo al documento corrente oppure utilizzare un nome di percorso assoluto.

```js
<script language="JavaScript" 
src="https://www.sampleco.com/javascript/includes/s_code.js"></script>
```

Se alcune pagine del sito vengono caricate in un protocollo protetto (https:) e fanno riferimento al file [!DNL AppMeasurement] per JavaScript, assicurarsi che il riferimento al file sia protetto (tramite https:) oppure codificare il riferimento come mostrato di seguito. In questo esempio viene adottato il protocollo della pagina corrente e viene impedito l'avviso che "alcuni elementi non sono protetti".

```js
<script language="JavaScript" 
src="//www.sampleco.com/javascript/includes/s_code.js"></script>
```

Verificate che il [!DNL .JS] file sui server Web disponga delle autorizzazioni impostate correttamente in modo che possa essere scaricato ed eseguito dai visitatori del sito Web. Se nei server di sviluppo viene utilizzato un [!DNL .JS] file diverso, impostare l'attributo "sola lettura" per il [!DNL .JS] file sui server di produzione per evitare la sovrascrittura. Se modificata, accertatevi che le seguenti impostazioni siano impostate correttamente nella parte superiore del [!DNL .JS] file:

```js
/************************** CONFIG SECTION **************************/
/* You may add or alter any code config here.                       */
/* Link Tracking Config */
s.trackDownloadLinks=false /* true for download tracking */
s.trackExternalLinks=false /* true for exit link tracking */
s.trackInlineStats=false /* true for ClickMap support */
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls"
s.linkInternalFilters="javascript:"
s.linkLeaveQueryString=false
s.linkTrackVars="None" 
s.linkTrackEvents="None"
```

Se " *`s_account`*" viene assegnato un valore nella parte superiore del [!DNL .JS] file, accertati che l'ID suite di rapporti (popolato nella [!UICONTROL s_account]variabile) sia corretto. Inoltre, accertatevi che il codice nella pagina non stia impostando la [!UICONTROL Report Suite ID] ( *`s_account`* variabile).

Esaminate la richiesta di immagine e le variabili per garantire che il "metodo fallback" (la terza parte del codice "split" nell’esempio sopra) non crei la richiesta di immagine invece del [!DNL .JS] file. Questo può essere determinato perché il metodo "fallback" crea solo una richiesta di immagine con informazioni minime.
