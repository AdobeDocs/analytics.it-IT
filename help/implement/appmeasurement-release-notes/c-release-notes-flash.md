---
description: Note cumulative sulla versione di Flash. Le app Flash che utilizzano ActionScript possono essere misurate sul desktop e sul Web.
seo-description: Note cumulative sulla versione di Flash. Le app Flash che utilizzano ActionScript possono essere misurate sul desktop e sul Web.
seo-title: Flash-Flex
solution: Analytics
subtopic: Note sulla versione
title: Flash-Flex
topic: Sviluppatore e implementazione
uuid: 2ee7fb92-9b62-44d4-bd93-6dff26764b7f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Flash-Flex{#flash-flex}

Note cumulative sulla versione di Flash. Le app Flash che utilizzano ActionScript possono essere misurate sul desktop e sul Web.

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivate la registrazione di debug.

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

Adobe ha rilasciato un [ aggiornamento sulla sicurezza APSB16-13 ](https://helpx.adobe.com/security/products/analytics/apsb16-13.html) per la libreria [!DNL AppMeasurement] per Flash . Questo aggiornamento risolve un’importante vulnerabilità nella libreria, applicabile solo quando `debugTracking` viene abilitato e che avrebbe potuto portare a [attacchi XSS basati su DOM](https://www.owasp.org/index.php/DOM_Based_XSS).

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

[!DNL AppMeasurement] i clienti Flash interessati da questo problema devono ricreare i progetti con la libreria aggiornata disponibile per il download dalla [!DNL Analytics] console [Altro...](https://help.adobe.com/en_US/Flex/4.0/UsingFlashBuilder/WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7feb.html#WS6f97d7caa66ef6eb1e63e3d11b6c4d0d21-7f88) (AN-121780)

## November 5, 2015 {#section_18C1A1C82EA844E78A1D563E66DE3FCF}

Versione 4.0 - Aggiornamento:

* Inclusione di Visitor API 1.5.3.

## September 17, 2015 {#section_319911C0F080452981F8C8BEA2880463}

Versione 4.0 - Aggiornamento:

* Inclusione di API visitatore 1.5.2.

## August 20, 2015 {#section_1BEA10285E9F4863B89B4B713DBB20DB}

Versione 4.0 - Aggiornamento:

* Inclusione di API visitatore 1.5.1.

## 18 giugno 2015 {#section_2ACB18A1693244D6A49B53F4E17F0C30}

Versione 4.0 - Aggiornamento

* Inclusione di Visitor API 1.5.
* Utilizzare il metodo getCustomerIDs API visitatore 1.5+ per raccogliere gli ID cliente e lo stato di autenticazione e inviarli con richieste di raccolta dati (AN-102131)

## May 21, 2015 {#section_F5EFCC451F13499F9AA53326AE5926F1}

Versione 3.9.2 - Aggiornamento:

* Inclusione di Visitor API 1.4

## February 19, 2015 {#section_95ADF1725CE7415D956944A28182E69B}

Versione 3.9.2:

* Inclusione di Visitor API 1.3.5.
* Changed to not perform automatic referrer tracking after first tracking call, so the 2nd, 3rd, etc., tracking call (usually link tracking) will not double count the referrer when *`s.referrer`* was manually set before the first tracking call. (AN-92647)
* Rimozione del tracciamento [!UICONTROL Heartbeat] video obsoleto incorporato nel modulo File multimediali. Il tracciamento [!UICONTROL Heartbeat] video supportato è stato spostato in una [!DNL Analytics] libreria video separata.

## September 18, 2014 {#section_80939868A2284961BF620851B000294F}

Versione 3.9.1:

* È stato aggiunto il test del supporto dei cookie a Flash (k = Y/N della variabile della stringa di query) e pf=1 alla stringa di query quando è possibile eseguire il test del supporto dei cookie (browser con [!DNL JavaScript] accesso).
* Supporto per le nuove funzioni nel servizio ID visitatore 1.3.2.

## August 21, 2014 {#section_F7CA56E42B6548D3BE5A0D020BCEE97A}

Versione 3.9:

* Sono state aggiunte variabili di latitudine e longitudine.
* Supporto per le nuove funzioni nel servizio ID visitatore 1.3.1.

## Versione 3.8.1 {#section_29A2A0A20D9B43A1B57E5ED299C6EAF3}

Data di rilascio: **19 giugno 2014**

* È stata corretta la gestione dei flag di attesa e di completamento per i campi API del visitatore, come l’ID [!DNL Analytics] visitatore legacy, che causava degli errori.
* Supporto per le nuove funzioni nel servizio ID visitatore 1.3.

## Versione 3.8 {#section_3F75C4D0C9BE470B95838DDB2CDCA79F}

Data di rilascio:**17 aprile 2014**

* Supporto per il servizio [ID visitatori di](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.

## Versione 3.7.3 {#section_1159B2AB56F54903A6FBFB7047AEC1C5}

Release Date: **March 13, 2014**

* Correzioni di bug multiple per il tracciamento [!UICONTROL Heartbeat] video.

## Versione 3.7.2 {#section_D6DCE5FE846A45F1A2CED237E8AAEFE9}

Data di rilascio:**6 febbraio 2014**

* Correzioni di bug multiple per il tracciamento [!UICONTROL Heartbeat] video.

## Versione 3.7.1 {#section_DC79F108AB5E42189A8EC7D87697AE0B}

Data di rilascio: **14 novembre 2013**

* Correzioni di bug multiple per il tracciamento [!UICONTROL Heartbeat] video.

## Versione 3.7 {#section_7239878DCD724FD0B9BC900821A4DA96}

Data di rilascio: **17 ottobre 2013**

* Supporto per il tracciamento [video](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/)heartbeat.
* VisitorAPI.swc è stato incluso per supportare il servizio [ID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#)visitatori.
* È stato eliminato il supporto per Flash Player 9 con ActionScript 3. La versione minima di Flash Player per ActionScript 3 è 10.

## Versione 3.6.2 {#section_57FB21568BDD48F7882F00AD630E6CE8}

Release Date: **September 18, 2013**

* Modifiche interne per supportare una prossima versione beta.

## Versione 3.5.5 {#section_149CAF8AF39741C2B9F6A015F7FB8C61}

Release Date: **August 15, 2013**

* Disabilitata la ricomposizione delle richieste non riuscite quando il tracciamento offline è disattivato.

## Versione 3.5.4 {#section_3429BD7DE2B64110BEE3A3850E58A0F7}

Data di rilascio:**21 febbraio 2013**

* È stato risolto un problema relativo alla codifica/decodifica URL in ActionScript 2.

## Versione 3.5.3 {#section_5192BC1C8BF547D1A5A92863686601DD}

Release Date: **January 31, 2013**

* È stato aggiunto il supporto per l’invio di URL superiori a 255 byte per supportare l’espansione del campo URL pagina nei server di raccolta dati Adobe. Gli URL di pagina di lunghezza superiore a 255 byte vengono suddivisi, con i primi 255 byte visualizzati nel `g=` parametro, con i rimanenti byte che vengono visualizzati successivamente nella stringa di query nel parametro di `-g=` query. In questo modo si evita che gli URL lunghi abbiano la precedenza rispetto ad altri dati nel caso di troncamento del browser, ma si possono comunque acquisire URL lunghi.

* È stato aggiunto un nuovo metodo di identificazione fallback del visitatore. Consulta [Identificazione di visitatori](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)univoci.
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

## Versione 3.5.2 {#section_77727E343EC14B869020358183DAB2DB}

Data di rilascio: **8 novembre 2012**

* Aggiornamenti interni per [!DNL Audience Manager] l'integrazione.

## Versione 3.5.1 {#section_F6345AC9F4994D6F97BBCF399B02BB21}

Data di rilascio: **22 ottobre 2012**

* Sono state modificate le build di ActionScript 3 per ignorare qualsiasi impostazione di `s.charSet` perché UTF-8 viene sempre utilizzato

## Versione 3.5 {#section_7DC183DD46CF42FE85F42E7AB8915D99}

Data di rilascio: 13 **settembre 2012** Modifiche **importanti al binding** variabile: Nella versione 3.5, per i clienti che devono iniziare e terminare i valori letterali di stringa con parentesi graffe è stata aggiunta l’opzione per disabilitare il binding delle variabili. Il binding delle variabili utilizzando le parentesi graffe viene utilizzato principalmente per configurare lettori video OSMF utilizzando i tag XML:

```
<autoTrackMediaName>{media.player.metadata(https://www.corp1.com/,episodeID)}</autoTrackMediaName>
```

È disponibile un nuovo attributo denominato `autoBind`, che consente di ignorare il comportamento predefinito nei tag XML:

```
<autoTrackMediaName autoBind=false>{123}</autoTrackMediaName>
```

L'impostazione `autoBind` a `false` causa della quale il valore viene considerato come una stringa letterale e il binding della variabile non viene utilizzato. Quando questo attributo non è impostato sul comportamento `false` dei tag XML resta lo stesso.

**Impatto sul codice ActionScript**

Sebbene non venga utilizzata comunemente, questa sintassi è disponibile anche per eseguire il binding delle [!DNL AppMeasurement] variabili nel codice ActionScript. Se non si è certi di utilizzare o meno il binding delle variabili, cercare nel codice i valori delle [!DNL AppMeasurement] variabili che iniziano e terminano con le parentesi graffe. Ad esempio:

```
s.eVar1 = "{source}";
```

Se si utilizza il binding delle variabili, è necessario modificare questo codice per utilizzare il nuovo `bindVariable` metodo:

```
s.bindVariable("eVar1","source");
```

Facoltativamente, invece di cambiare ogni posizione, potete ripristinare il comportamento precedente alla versione 3.5 impostando `autoBindVariablesByValue` su true:

```
s.autoBindVariablesByValue = true;
```

**Correzioni Aggiuntive:**

* È stato risolto un problema che poteva impedire l'invio dell'evento di completamento del video quando si utilizzava un `media.monitor` metodo personalizzato per tenere traccia dell'evento di chiusura del supporto:

   ```
   If(media.event==”CLOSE”) { 
   … 
   } 
   ```

## Versione 3.4.9 {#section_5F2566CF954242D0A7205DA0B257DABA}

Data di rilascio:**19 luglio 2012**

* È stato aggiunto un metadati solo principale, vedete [https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html](https://www.adobe.com/devnet/flashplayer/articles/fplayer9_security.html).

## Versione 3.4.8 {#section_7501E04F6A854D50BFF0F287607A796F}

Data di rilascio: **21 giugno 2012**

* Modificato per utilizzare sempre UTF-8 nelle build AS3. In questo modo si evitano problemi con le stringhe per alcune lingue multibyte.

## Versione 3.4.7 {#section_B26A014D13B14878816472E394FBAAA6}

Data di rilascio:**26 aprile 2012**

Misurazione video: È stata aggiunta la gestione dell'offset completo non coerente segnalato dall'API del lettore Brightcove. Ora, se l'offset è indicato come zero, al termine utilizzeremo la lunghezza come offset. Questo risolve problemi con il nuovo metodo di tracciamento che viene completato utilizzando un valore di offset.

## Versione 3.4.6 {#section_273B76A58745486E9715D9F5C2AEC433}

Release Date: **January 19, 2012**

* È stato aggiornato il tracciamento video con un nuovo metodo per tenere traccia delle visualizzazioni video complete.

## Versione 3.4.5 {#section_DEDF0BEF6BF4458CA00896799E5BA67C}

Release Date: **September 8, 2011**

* Proprietà abilitate per contenere un valore zero letterale "0". Precedentemente non venivano inviate proprietà con un valore letterale zero.

## Versione 3.4.3 {#section_6C930AA0E95045BCA9AD4096B63657C9}

Release Date: **May 2011**

* In OSMF, problemi risolti quando si utilizzano i plug-in proxy durante il tracciamento dei lettori video OSMF. Questa correzione ha permesso il tracciamento degli elementi proxy OSMF quando l'elemento che si stanno proxando non viene tracciato.
* È stato risolto un problema che causava un errore durante la misurazione del video in Flash Player 9.0.16.

