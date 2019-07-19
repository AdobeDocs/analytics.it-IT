---
description: Note sulla versione cumulative per Flash. Le app Flash che utilizzano actionscript possono essere misurate sul desktop e sul Web.
seo-description: Note sulla versione cumulative per Flash. Le app Flash che utilizzano actionscript possono essere misurate sul desktop e sul Web.
seo-title: Flash-Flex
solution: Analytics
subtopic: Note sulla versione
title: Flash-Flex
topic: Sviluppatore e implementazione
uuid: 2 ee 7 fb 92-9 b 62-44 d 4-bd 93-6 dff 26764 b 7 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Flash-Flex{#flash-flex}

Note sulla versione cumulative per Flash. Le app Flash che utilizzano actionscript possono essere misurate sul desktop e sul Web.

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivare la registrazione di debug.

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## April 20, 2017 {#section_8521EC2B68E24203A0F1B14A9D2652D2}

**Versione 4.0.3 **

* Inclusione di Visitor API 1.6.1.

## August 18, 2016 {#section_D72EF20672174249B864997905D7552A}

** 4.0.2 - Aggiornamento**

Inclusione di Visitor API 1.6.0.

## May 19, 2016 {#section_061305CFC1E040E69E3CDF4078C17AE4}

** 4.0.1 - Aggiornamento**

Inclusione di Visitor API 1.5.6

## April 21, 2016 {#section_6EFC6DBEB9E1460DB344A8278F9FC696}

Adobe has released a [security update APSB16-13](https://helpx.adobe.com/security/products/analytics/apsb16-13.html) for the [!DNL AppMeasurement] for Flash library. Questo aggiornamento risolve un’importante vulnerabilità nella libreria, applicabile solo quando `debugTracking` viene abilitato e che avrebbe potuto portare a [attacchi XSS basati su DOM](https://www.owasp.org/index.php/DOM_Based_XSS).

>[!IMPORTANT]
>
>This issue affects [!DNL AppMeasurement] for Flash only when `debugTracking` has been enabled ( `debugTracking` is disabled in the default configuration). **Se interessato, consigliamo di disabilitare`debugTracking`immediatamente.** Di seguito vi sono alcuni esempi di codice:

```
public var s:AppMeasurement; 
s = new AppMeasurement(); 
s.debugTracking = false; // set to false or remove line 
                         // for default "disabled” behavior 
```

Le versioni interessate sono [!DNL AppMeasurement] per Flash versione 4.0 e versioni precedenti su tutte le piattaforme.

>[!NOTE]
>
>Due to security reasons, we will no longer be distributing an AS2 version of [!DNL AppMeasurement] for Flash. Continueremo a supportare la raccolta di dati dai progetti basati su AS2 esistenti. Tuttavia, consigliamo fortemente ai clienti di aggiornare le implementazioni a AS3 e di aggiungere le funzioni di sicurezza di [!DNL AppMeasurement] per Flash più recenti.

[!DNL AppMeasurement] per i clienti Flash interessati da questo problema devono ricreare i progetti con la libreria aggiornata disponibile per il download dalla [!DNL Analytics] console [Altro…](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN -121780)

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

Versione 4.0 - Aggiornamento:

* Inclusione di Visitor API 1.5.3.

## September 17, 2015 {#section_319911C0F080452981F8C8BEA2880463}

Versione 4.0 - Aggiornamento:

* Inclusione di API visitatore 1.5.2.

## August 20, 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

Versione 4.0 - Aggiornamento:

* Inclusione di API visitatore 1.5.1.

## June 18, 2015 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

Versione 4.0 - Aggiornamento

* Inclusione di Visitor API 1.5.
* Utilizzate il metodo Visitor API 1.5 + getcustomerids per raccogliere ID cliente e stato autenticato e inviarli con le richieste di raccolta dati (AN -102131)

## May 21, 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

Versione 3.9.2 - Aggiornamento:

* Inclusione di Visitor API 1.4

## February 19, 2015 {#section_95ADF1725CE7415D956944A28182E69B}

Versione 3.9.2:

* Inclusione di Visitor API 1.3.5.
* Changed to not perform automatic referrer tracking after first tracking call, so the 2nd, 3rd, etc., tracking call (usually link tracking) will not double count the referrer when *`s.referrer`* was manually set before the first tracking call. (AN-92647)
* Removal of deprecated [!UICONTROL Heartbeat] video tracking embedded in the Media module. The supported [!UICONTROL Heartbeat] video tracking has been moved to a separate Video [!DNL Analytics] library.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

Versione 3.9.1:

* Added cookie support testing to Flash (k = Y/N query-string variable) and pf=1 to query-string when cookie support test is possible (browser with [!DNL JavaScript] access).
* Supporto per nuove funzioni nel servizio ID visitatore 1.3.2.

## August 21, 2014 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

Versione 3.9:

* Sono state aggiunte variabili di latitudine e longitudine.
* Supporto per nuove funzioni nel servizio ID visitatore 1.3.1.

## Version 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

Data di rilascio: **19 giugno 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Supporto per nuove funzioni nel servizio ID visitatore 1.3.

## Version 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

Data di rilascio:**17 aprile 2014**

* Support for the [Marketing Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Version 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

Release Date: **March 13, 2014**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Version 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

Data di rilascio:**6 febbraio 2014**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Version 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

Data di rilascio: **14 novembre 2013**

* Multiple bug fixes to [!UICONTROL Heartbeat] video tracking.

## Version 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

Data di rilascio: **17 ottobre 2013**

* Support for [heartbeat video tracking](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* VisitorAPI.swc was included to support [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).
* Supporto rilasciato per Flash Player 9 con actionscript 3. La versione minima di Flash Player per actionscript 3 è 10.

## Version 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

Release Date: **September 18, 2013**

* Modifiche interne per supportare una prossima versione beta.

## Version 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

Release Date: **August 15, 2013**

* È stata disattivata la coda di richieste non riuscite quando il tracciamento offline è disabilitato.

## Version 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

Data di rilascio:**21 febbraio 2013**

* È stato risolto un problema relativo alla codifica/decodifica URL in actionscript 2.

## Version 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

Release Date: **January 31, 2013**

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

## Version 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

Data di rilascio: **8 novembre 2012**

* Internal updates for [!DNL Audience Manager] integration.

## Version 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

Data di rilascio: **22 ottobre 2012**

* Changed ActionScript 3 builds to ignore any setting of `s.charSet` because we always use UTF-8

## Version 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Release Date: **September 13, 2012**
**Important change to variable binding**: In version 3.5, an option to disable variable binding was added for customers who need to start and end literal string values with curly braces. Il binding della variabile con parentesi graffe viene utilizzato principalmente per la configurazione di lettori video OSMF utilizzando i tag XML:

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

A new attribute, called `autoBind`, is available to override the default behavior in XML tags:

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

Setting `autoBind` to `false` causes the value to be considered a literal string and variable binding is not used. When this attribute is not set to `false` the behavior in XML tags remains the same.

**Impatto sul codice actionscript**

Though not commonly used, this syntax is also available to bind [!DNL AppMeasurement] variables in your ActionScript code. If you are unsure whether or not you are using variable binding, search your code for [!DNL AppMeasurement] variable values that start and end with curly braces. Ad esempio:

```
s.eVar1 = "{source}";
```

If you are using variable binding, you should change this code to use the new `bindVariable` method:

```
s.bindVariable("eVar1","source");
```

Optionally, instead of changing each location, you can revert to the pre-version 3.5 behavior by setting `autoBindVariablesByValue` to true:

```
s.autoBindVariablesByValue = true;
```

**Correzioni aggiuntive:**

* Fixed an issue that might cause the video complete event to not be sent when using a custom `media.monitor` method that tracks the media close event:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Version 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

Data di rilascio:**19 luglio 2012**

* Added a master-only meta policy, see [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## Version 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

Data di rilascio: **21 giugno 2012**

* Modificato per utilizzare sempre UTF -8 nelle build AS 3. In questo modo si evitano problemi con le stringhe per alcune lingue multibyte.

## Version 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

Data di rilascio:**26 aprile 2012**

Misurazione video: È stata aggiunta la gestione di offset completo non coerente segnalata dall'API Brightcove Player. Ora se l'offset è indicato come zero, in fase di completamento utilizzeremo la lunghezza come offset. Questo risolve problemi con il nuovo metodo di tracciamento completato con un valore di offset.

## Version 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

Release Date: **January 19, 2012**

* Aggiornamento del monitoraggio video con un nuovo metodo per tenere traccia delle visualizzazioni video complete.

## Version 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

Release Date: **September 8, 2011**

* Prop enabled to contain a literal zero value "0". Precedentemente, i prop con valore zero letterale non venivano inviati.

## Version 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

Release Date: **May 2011**

* In OSMF, sono stati risolti dei problemi durante l'utilizzo dei plug-in proxy durante il tracciamento dei lettori video OSMF. This fix enabled OSMF proxyelements to be track when the element they are prois not being track.
* È stato risolto un problema che causava un errore di misurazione del video in Flash Player 9.0.16.

