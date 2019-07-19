---
description: nulle
seo-description: nulle
seo-title: Windows Silverlight, NET, IIS, XBOX
solution: Analytics
subtopic: Note sulla versione
title: Windows Silverlight, NET, IIS, XBOX
topic: Sviluppatore e implementazione
uuid: 15 c 20 bca -4886-4 d 57-9957-fe 99743851 ea
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>Questi SDK sono diventati obsoleti e non sono più supportati o distribuiti da Adobe.

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivare la registrazione di debug.

## Version 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Release Date: **August 2014**

* Removed support for the [!DNL Microsoft Silverlight Analytics Framework]. Adobe is no longer supporting or distributing the [!DNL Microsoft Silverlight Analytics Framework] integration for [!DNL AppMeasurement].

* Modifiche interne per supportare funzionalità imminenti.

## Version 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Release Date: **March 2013**

* Fixed exception with getting default referrer in [!DNL Silverlight] outside of a browser context and properly exposed SSL property in the [!DNL Microsoft Silverlight Analytics Framework] component.

## Version 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Release Date: **February 2013**

* È stato aggiunto il supporto per l'invio di URL superiori a 255 byte per supportare l'espansione del campo URL pagina nei server di raccolta dati Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Questo consente di evitare che gli URL lunghi abbiano precedenza rispetto ad altri dati nel caso del troncamento del browser, ma consentano comunque l'acquisizione di URL lunghi.

* Aggiunto un nuovo metodo di identificazione del visitatore. See [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors).
* Added a new `abort` flag that can be set inside `doPlugins`. Setting this flag to true causes the [!DNL AppMeasurement] library to not continue with that tracking call. The abort flag is reset with every tracking call, so if a subsequent tracking call also needs to be aborted the flag will need to be set again inside `doPlugins`.

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   Questo consente di centralizzare la logica utilizzata per identificare l'attività che non desideri tracciare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.

## Version 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

Release Date: **September 2012**

* Fixed an issue that might cause the video complete event to not be sent when using a custom `media.monitor` method that tracks the media close event:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Version 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

Release Date: **April 2012**

* È stato aggiunto supporto per [!DNL XBOX].

## Version 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

Release Date: **February 2012**

* [!DNL iOS] Telefono 7: Risolto un problema che impediva la corretta applicazione di offlinethrottledelay.
* Aggiunto il timestamp alle variabili utilizzate con chiamate di tracciamento chiaro (tracklight).

## Version 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

Release Date: **January 2012**

* Aggiornamento del monitoraggio video con un nuovo metodo per tenere traccia delle visualizzazioni video complete. See [Measuring Video in Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html).

## Version 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* New support and build for [!DNL iOS] Phone platform including offline tracking.
* Supporto per il delegato dorequest per ignorare il modo in cui vengono inviate le richieste per il tracciamento dei dati.
* Supporto per contextdata che fornisce regole di elaborazione lato server (solo v 15).
* Supporto per chiamate server chiaro (attualmente nella versione beta).
* Supporto per l'assegnazione di un valore diverso da 1 a un evento contatore nell'elenco degli eventi.
* Supporto per il nuovo metodo di tracciamento video utilizzando evar ed eventi di conversione (attualmente in versione beta).

