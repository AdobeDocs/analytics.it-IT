---
description: Come implementare Analytics negli articoli istantanei di Facebook.
keywords: Implementazione di Analytics;incorpora;variabile personalizzata;evento personalizzato;tracciamento dei visitatori;limitazioni
seo-description: Come implementare Analytics negli articoli istantanei di Facebook.
seo-title: Articoli istantanei Facebook
solution: Analytics
title: Articoli istantanei Facebook
topic: Sviluppatore e implementazione
uuid: 04b6366b-7c52-4dae-b2dd-bb6b78fd409c
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Articoli istantanei Facebook

Come implementare Analytics negli articoli istantanei di Facebook.

Facebook Instant Articles è un nuovo metodo che consente agli editori di creare articoli interattivi veloci su Facebook. Gli articoli istantanei possono caricare il contenuto fino a 10 volte più rapidamente del Web per dispositivi mobili.

Adobe Analytics può essere incorporato negli articoli Facebook istantanei per monitorare il comportamento dei visitatori mentre interagiscono con il contenuto. Poiché il contenuto dell'editore si trova nell'app Facebook e non nei siti Web dell'editore, l'approccio basato sui tag è leggermente diverso dall'implementazione standard di Analytics.

## Passaggio 1: Incorpora una pagina HTML di Analytics {#section_0DF847F8BA624CF8A239C10003A39E59}

Quando create il contenuto Facebook Instant Article, potete incorporare il contenuto HTML di analisi all'interno di un iFrame. Ad esempio:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## Passaggio 2: Modificare il codice HTML di Analytics {#section_76707B51D63A47FF833C2D3FFF8412B4}

Il codice HTML di esempio riportato di seguito può essere utilizzato per acquisire le statistiche dagli articoli istantanei. Questo file è in genere ospitato su uno dei server Web della tua azienda. Ogni volta che viene caricato un articolo istantaneo, il file viene caricato in un iframe come descritto nel passaggio uno, che attiva l'invio dei dati di analisi ad Adobe.

```
<html> 
    <head> 
        <title>Facebook Stats</title> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/VisitorAPI.js"></script> 
        <script language="javaScript" type="text/javascript" src="https://[your-domain-here]/js/AppMeasurement.js"></script> 
    </head> 
    <body> 
        <script> 
            //Standard Variable Configuration 
   var v_orgId = "[your-marketing-cloud-org-id]@AdobeOrg"; 
   var s_account = "[your-report-suite-id]"; 
   var s_trackingServer = "[your-tracking-server]"; 
   var s_visitorNamespace = "[your-namespace]"; 
     
   //Instantiation 
   var visitor = Visitor.getInstance(v_orgId); 
   visitor.trackingServer = s_trackingServer; 
     
   var s = s_gi(s_account); 
   s.account = s_account; 
   s.trackingServer = s_trackingServer; 
   s.visitorNamespace = s_visitorNamespace; 
   s.visitor = visitor; 
     
   //Custom Variables 
   s.pageName = s.Util.getQueryParam("pageName"); 
   s.prop10 = "Facebook Instant Article"; 
       
   //Page View Image Request Call 
   s.t(); 
        </script> 
    </body> 
</html> 
```

**Per modificare questo HTML di esempio per la vostra implementazione specifica**

1. Si consiglia di ospitare le ultime copie delle versioni non modificate di VisitorAPI.js e AppMeasurement.js in una directory comune sui server Web della società.

   Se necessario, questi file possono essere scaricati anche da Code Manager (Gestione codici) nell'interfaccia utente di Analytics.

1. Includi le variabili di configurazione standard di implementazione di Analytics:

   1. L’ID organizzazione Experience Cloud.
   1. ID suite di rapporti in cui verrà catturato il traffico degli articoli istantanei di Facebook.
   1. Il dominio del server di tracciamento della società.
   1. La variabile dello spazio dei nomi del visitatore. **** Nota: Molti di questi valori si trovano all'interno dell'implementazione standard di Analytics. Se necessario, l'Assistenza clienti o Adobe Consulting possono contribuire a fornire i valori appropriati.

1. [Impostare il tracciamento](/help/implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B)personalizzato delle variabili e degli eventi.
1. Includere la sintassi della richiesta di immagini della visualizzazione pagina `( s.t())`.

## Passaggio 3: Impostazione del tracciamento personalizzato delle variabili e degli eventi {#section_932C41BD21154C25B99389299BDF3E0B}

Le variabili e gli eventi personalizzati possono essere tracciati all'interno dell'HTML di analisi tramite diversi approcci. Il primo approccio consiste nell’includere la logica JavaScript nella configurazione personalizzata, in modo simile a quello che si potrebbe fare con un’implementazione standard di Analytics. Ad esempio, per impostare il valore di una prop, utilizzate semplicemente la stessa sintassi utilizzata in un'implementazione normale:

```
s.prop10 = "Facebook Instant Article";
```

Potete inoltre inviare dinamicamente le variabili all’iframe utilizzando i parametri della stringa di query nell’ `src` attributo iframe. Ad esempio:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

Tali parametri di stringa di query possono essere successivamente impostati nella sezione delle variabili personalizzate del codice JavaScript HTML di analisi utilizzando la `Util.getQueryParam` funzione all'interno della [!DNL AppMeasurement] libreria predefinita, come segue:

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## Tracciamento visitatori {#section_60F0C77659534949831E85B5FD9AE81E}

Fintanto che la pagina HTML di Analytics è ospitata sul server Web, Adobe può supportare l'informativa sulla privacy esistente in tutti gli articoli istantanei di Facebook. Ciò significa che se un utente finale ha rinunciato al tracciamento sul sito principale, verrà escluso anche il tracciamento su tutti gli articoli Instant di Facebook, senza richiedere passaggi aggiuntivi. L'utilizzo di questa pagina di utilità significa anche che il servizio identità (ID visitatore) è supportato in modo da poter integrare le metriche e le variabili acquisite negli articoli istantanei di Facebook con il resto di Experience Cloud. (Un esempio è relativo all'utilizzo di pubblicità mirata [!DNL Adobe Audience Manager]).

## Limitazioni di tracciamento {#section_1EE1BB069A3148DB9446371AFE196567}

Ci sono poche questioni da considerare con questo approccio. Eventuali valori DOM solitamente accessibili solo tramite JavaScript nell'articolo istantaneo di Facebook (come referrer) non saranno recuperabili nell'iframe per il tracciamento. Tuttavia, i report tecnologici standard come browser, dispositivo, dimensione dello schermo o risoluzione dovrebbero funzionare normalmente. Inoltre, pageURL può essere ottenuto facendo riferimento [!DNL document.referrer] alla pagina dell'utility.

## Cosa succede dopo? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] è entusiasta di collaborare con Facebook e i nostri editori per offrire agli editori sul web mobile funzionalità di analisi leader del settore in un'esperienza utente estremamente rapida. Ci impegniamo a creare la migliore soluzione a lungo termine per rispondere alle esigenze di analisi in evoluzione dei nostri clienti.

Il progetto Facebook Instant Article si sta muovendo rapidamente e i cambiamenti stanno avvenendo sempre di più, quindi rivedete spesso con noi per gli aggiornamenti. Con l'ulteriore miglioramento delle integrazioni e con l'adozione di articoli Instant su Facebook da parte di altri editori, ci aspettiamo dei cambiamenti.

In caso di domande o problemi, rivolgiti al tuo consulente Adobe o all'Assistenza clienti.
