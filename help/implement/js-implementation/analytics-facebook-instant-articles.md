---
description: Come implementare Analytics negli articoli Instant Instant di Facebook.
keywords: Implementazione di Analytics; embed; custom variable; evento personalizzato; tracciamento dei visitatori; tracciamento; limitazioni
seo-description: Come implementare Analytics negli articoli Instant Instant di Facebook.
seo-title: Articoli istantanei Facebook
solution: Analytics
title: Articoli istantanei Facebook
topic: Sviluppatore e implementazione
uuid: 04 b 6366 b -7 c 52-4 dae-b 2 dd-bb 6 b 78 fd 409 c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Articoli istantanei Facebook

Come implementare Analytics negli articoli Instant Instant di Facebook.

Gli articoli Instant Instant di Facebook rappresentano un nuovo metodo per gli editori di creare articoli veloci e interattivi su Facebook. Gli articoli istantanei possono caricare contenuti fino a 10 volte più veloci rispetto al Web per dispositivi mobili.

Adobe Analytics può essere incorporato negli articoli Instant Instant di Facebook per monitorare il comportamento dei visitatori quando interagiscono con il contenuto. Poiché il contenuto editore è all'interno dell'app Facebook e non nei siti Web dell'editore, l'approccio sui tag è leggermente diverso da un'implementazione standard di Analytics.

## Passaggio 1: Embed an Analytics HTML page {#section_0DF847F8BA624CF8A239C10003A39E59}

Quando create il contenuto Articolo istantaneo di Facebook, potete incorporare il contenuto HTML di analisi all'interno di un iframe. Ad esempio:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html" height="0"></iframe>
```

## Passaggio 2: Modify your Analytics HTML {#section_76707B51D63A47FF833C2D3FFF8412B4}

L'HTML di esempio di seguito può essere utilizzato per acquisire le statistiche dagli articoli istantanei. In genere questo file viene ospitato su uno dei server Web della vostra azienda. Ogni volta che un articolo istantaneo viene caricato, carica il file in un iframe come descritto al punto uno, che attiva l'invio dei dati di analisi ad Adobe.

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

**Per modificare questo esempio di HTML per l'implementazione specifica**

1. Si consiglia di ospitare le copie più recenti delle versioni non modificate di visitorapi. js e appmeasurement. js su una directory comune sui server Web della società.

   Questi file possono essere scaricati anche dall'interno di Code Manager (Gestione codici), se necessario.

1. Include le variabili di configurazione standard di implementazione di Analytics:

   1. L'ID organizzazione Experience Cloud.
   1. L'ID suite di rapporti in cui verrà acquisito il traffico Articolo Instant Facebook.
   1. Dominio server di tracciamento della tua azienda.
   1. La variabile namespace del visitatore. **Nota:** Molti di questi valori sono disponibili nell'implementazione standard di Analytics. L'Assistenza clienti o Adobe Consulting può fornire assistenza per fornire i valori corretti, se necessario.

1. [Imposta la variabile personalizzata e il tracciamento eventi](../../implement/js-implementation/analytics-facebook-instant-articles.md#section_932C41BD21154C25B99389299BDF3E0B).
1. Include the page view image request syntax `( s.t())`.

## Passaggio 3: Set custom variable and event tracking {#section_932C41BD21154C25B99389299BDF3E0B}

Le variabili e gli eventi personalizzati possono essere tracciati nel codice HTML di analisi tramite approcci diversi. Il primo approccio consiste nel includere logica javascript nella configurazione personalizzata, simile a quanto faresti con un'implementazione standard di Analytics. Ad esempio, per impostare il valore di un prop, usa semplicemente la stessa sintassi da usare in una normale implementazione:

```
s.prop10 = "Facebook Instant Article";
```

You can also dynamically send variables to the iframe by leveraging query string parameters in the iframe `src` attribute. Ad esempio:

```
<iframe class="no-margin" src="https://[your-domain-here]/analytics.html?prop1=dynamic%20article%20title&eVar1=facebook%20page%20name&pageName=your%20page%20name%20here&cmpId=your%20campaignID%20here" height="0"></iframe>
```

Those query string parameters can subsequently be set in the custom variables section of your analytics HTML JavaScript by using the `Util.getQueryParam` function within the default [!DNL AppMeasurement] library, as follows:

```
s.pageName = s.Util.getQueryParam("pageName"); 
s.campaign = s.Util.getQueryParam("cmpId"); 
s.eVar1 = s.Util.getQueryParam("eVar1"); 
s.prop1 = s.Util.getQueryParam("prop1"); 
```

## Visitor Tracking {#section_60F0C77659534949831E85B5FD9AE81E}

Fintanto che la pagina HTML di Analytics è ospitata sul server Web, Adobe può supportare l'informativa sulla privacy esistente in tutti gli articoli Instant Instant di Facebook. Questo significa che se un utente finale ha rinunciato al tracciamento sul sito principale, anche questi verranno non tracciati in tutti i vostri articoli Instant Instant, senza dover effettuare ulteriori passaggi. Utilizzando questa pagina di utilità, è inoltre supportato il servizio identità (ID visitatore), che consente di integrare le metriche e le variabili acquisite negli articoli Instant Instant con il resto di Experience Cloud. (An example is for targeted advertising using [!DNL Adobe Audience Manager]).

## Tracking Limitations {#section_1EE1BB069A3148DB9446371AFE196567}

Esistono alcuni problemi da tenere presenti con questo approccio. Eventuali valori DOM che sono generalmente accessibili solo tramite javascript nell'articolo Instant Instant (ad esempio, referrer) non saranno recuperabili nell'iframe per il tracciamento. Tuttavia, i rapporti tecnologici standard come browser, dispositivo, dimensione dello schermo o risoluzione dovrebbero funzionare normalmente. Moreover, the pageURL can be obtained by referencing [!DNL document.referrer] from your utility page.

## What's Next? {#section_A170A10E2A3642A784DF720195DA8B38}

[!DNL Adobe Analytics] è entusiasta di collaborare con Facebook e i nostri editori per portare le funzionalità di analisi leader del settore agli editori sul Web mobile in un'esperienza utente veloce. Ci impegniamo a creare la soluzione term-term più lunga per rispondere all'analisi in evoluzione necessaria ai nostri clienti.

Il progetto Articolo istantaneo Facebook si sta spostando rapidamente e le modifiche si verificano continuamente; quindi, per aggiornamenti, consultate frequenti con noi. Si aspettano modifiche man mano che miglioriamo ulteriormente le integrazioni e quando più editori adottano gli articoli Instant Instant in futuro.

In caso di domande o problemi, rivolgetevi al consulente Adobe o all'Assistenza clienti.
