---
description: nulle
seo-description: nulle
seo-title: Windows Silverlight, NET, IIS, XBOX
solution: Analytics
subtopic: Note sulla versione
title: Windows Silverlight, NET, IIS, XBOX
topic: Sviluppatore e implementazione
uuid: 15c20bca-4886-4d57-9957-fe99743851ea
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Windows Silverlight, NET, IIS, XBOX{#windows-silverlight-net-iis-xbox}

>[!IMPORTANT]
>
>Questi SDK sono scaduti e non sono più supportati o distribuiti da Adobe.

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivate la registrazione di debug.

## Versione 1.4.2 {#section_2B70F52C4D214A43844CCEC6B45037F0}

Release Date: **August 2014**

* Rimosso il supporto per l' [!DNL Microsoft Silverlight Analytics Framework]. Adobe non supporta più o distribuisce l' [!DNL Microsoft Silverlight Analytics Framework] integrazione per [!DNL AppMeasurement].

* Modifiche interne per supportare le funzionalità in arrivo.

## Versione 1.4.1 {#section_9134F77804BF472291DA7243FAC89C2B}

Release Date: **March 2013**

* È stata corretta un’eccezione per il richiamo predefinito [!DNL Silverlight] all’esterno del contesto di un browser e la proprietà SSL correttamente esposta nel [!DNL Microsoft Silverlight Analytics Framework] componente.

## Versione 1.4 {#section_2F4ADA4628EC43B480177C3DDB3D1CFA}

Release Date: **February 2013**

* È stato aggiunto il supporto per l’invio di URL superiori a 255 byte per supportare l’espansione del campo URL pagina nei server di raccolta dati Adobe. Gli URL di pagina di lunghezza superiore a 255 byte vengono suddivisi, con i primi 255 byte visualizzati nel `g=` parametro, con i rimanenti byte che vengono visualizzati successivamente nella stringa di query nel parametro di `-g=` query. In questo modo si evita che gli URL lunghi abbiano la precedenza rispetto ad altri dati nel caso di troncamento del browser, ma si possono comunque acquisire URL lunghi.

* È stato aggiunto un nuovo metodo di identificazione fallback del visitatore. Consulta [Identificazione di visitatori](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_identifying_unique_visitors.html)univoci.
* È stato aggiunto un nuovo `abort` flag che può essere impostato all'interno `doPlugins`. Impostando questo flag su true, la [!DNL AppMeasurement] libreria non continua con quella chiamata di tracciamento. Il flag abort viene reimpostato con ogni chiamata di tracciamento, quindi se è necessario interrompere anche una chiamata di tracciamento successiva, il flag dovrà essere nuovamente inserito all’interno `doPlugins`.

   ```js
   s.doPlugins = function(s) { 
        s.campaign = s.getQueryParam("cid"); 
        if ((!s.campaign) && (!s.events)) { 
             s.abort = true; 
        } 
   };
   ```

   Questo consente di centralizzare la logica utilizzata per identificare l'attività che non si desidera tracciare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.

## Versione 1.3.8 {#section_03089199E2DE4199B32F6821DDAED7BD}

Release Date: **September 2012**

* È stato risolto un problema che poteva impedire l'invio dell'evento di completamento del video quando si utilizzava un `media.monitor` metodo personalizzato per tenere traccia dell'evento di chiusura del supporto:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Versione 1.3.7 {#section_32AA8AE0CED4495496D25BF9246AE8AB}

Release Date: **April 2012**

* È stato aggiunto supporto per [!DNL XBOX].

## Versione 1.3.6 {#section_9F2738FA31CD48C4877AB92281EC67A9}

Release Date: **February 2012**

* [!DNL iOS] Telefono 7: È stato risolto un problema che impediva l'applicazione corretta di offlineThrottleDelay.
* Aggiunta di marca temporale alle variabili utilizzate con le chiamate di tracciamento della luce (trackLight).

## Versione 1.3.5 {#section_28BBDE7D187547A4AACCA60E5154DCD2}

Release Date: **January 2012**

* È stato aggiornato il tracciamento video con un nuovo metodo per tenere traccia delle visualizzazioni video complete. Consultate [Misurazione dei video in Adobe Analytics](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/video/index.html).

## Versione 1.3.4 {#section_43788EE6B57E4B2DBEED68BE6954D9CA}

* Nuovo supporto e build per la piattaforma [!DNL iOS] Phone, compreso il tracciamento offline.
* Supporto per il delegato doRequest per ignorare il modo in cui le richieste vengono inviate per i dati di tracciamento.
* Supporto per contextData che supporta le regole di elaborazione lato server (solo v15).
* Supporto per chiamate server di luce (attualmente in versione beta).
* Supporto per l'assegnazione di un valore diverso da 1 a un evento contatore nell'elenco degli eventi.
* Supporto per un nuovo metodo di tracciamento dei video mediante eVar di conversione ed eventi (attualmente in versione beta).

