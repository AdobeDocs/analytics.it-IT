---
title: Implementazione di Adobe Analytics
description: Implementa Adobe Analytics sul tuo sito, proprietà o applicazione.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '900'
ht-degree: 38%

---

# Implementazione di Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Per inviare dati ai propri server di raccolta dati, Adobe richiede codice sul sito o nell’app. I seguenti passaggi indicano il funzionamento di un’implementazione tipica.

1. Quando un visitatore accede al tuo sito, viene inviata una richiesta al server web.
2. Il server web del sito invia le informazioni sul codice della pagina e la pagina viene visualizzata nel browser.
3. La pagina viene caricata e viene eseguito il codice JavaScript di Analytics.
Il codice JavaScript invia una richiesta di immagine ai server di raccolta dati Adobe. In questa richiesta di immagine, i dati di pagina definiti nell’implementazione vengono inviati come parte di una stringa di query.

4. Adobe restituisce un’immagine trasparente in pixel.
5. I server di Adobe memorizzano i dati raccolti in una o più *suite di rapporti*.
6. I dati della suite di report popolano i rapporti a cui potrai poi accedere in un browser web.

L’esecuzione del codice JavaScript avviene rapidamente e non influisce in modo rilevante sui tempi di caricamento delle pagine. Questo approccio consente di contare le pagine visualizzate quando un visitatore fa clic su **[!UICONTROL Reload]** o **[!UICONTROL Back]** per raggiungere una pagina, perché JavaScript viene eseguito anche durante il recupero della pagina dalla cache.

Per poter inviare dati ai server di raccolta dati, Adobe Analytics richiede il codice all’interno del sito web, dell’app mobile o di altre applicazioni. Esistono diversi metodi per implementare questo codice, a seconda della piattaforma e delle esigenze aziendali.

## Metodi di implementazione del sito web

Per **sito web**, sono disponibili i seguenti metodi di implementazione:

* **Estensione Web SDK**: metodo standardizzato e consigliato per l’implementazione di Adobe Analytics per i nuovi clienti. Installare **Estensione Adobe Experience Platform Web SDK** nella raccolta dati di Adobe Experience Platform **Tag**, utilizza un tag loader in ogni pagina e invia dati a Adobe Experience Platform **Rete Edge** in un formato adatto alla tua organizzazione. La rete Edge inoltra i dati in arrivo ad Adobe Analytics nel formato corretto.
  ![Estensione Web SDK](./assets/websdk-extension-implementation.png)
Consulta [Implementare Adobe Analytics utilizzando l’estensione Adobe Experience Platform Web SDK](./aep-edge/overview.md) per ulteriori informazioni.

* **SDK per web**: se non desideri utilizzare la raccolta dati di Adobe Experience Platform, puoi caricare manualmente le librerie SDK web sul tuo sito. Fai riferimento alla libreria SDK web (`alloy.js`) su ogni pagina e invia le chiamate di tracciamento desiderate al Adobe Experience Platform **Rete Edge** in un formato adatto alla tua organizzazione. La rete Edge inoltra i dati in arrivo ad Adobe Analytics nel formato corretto.
  ![SDK per web](./assets/websdk-implementation.png)
Consulta [Implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK](./aep-edge/overview.md) per ulteriori informazioni.


* **Estensione Analytics**: installa **Estensione Adobe Analytics** nella raccolta dati di Adobe Experience Platform **Tag**. Inserisci un tag loader in ciascuna pagina e utilizza l’estensione Adobe Analytics per determinare come viene definita ogni variabile. Utilizza questo metodo di implementazione se desideri la comodità dei tag, ma non utilizzare l’infrastruttura di rete Edge.
  ![Estensione Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulta [Implementare Adobe Analytics utilizzando l’estensione Analytics](launch/overview.md) per ulteriori informazioni.

* **JavaScript legacy:** metodo manuale che veniva utilizzato per implementare Adobe Analytics. Fai riferimento alla libreria di AppMeasurement (`AppMeasurement.js`) in ogni pagina e quindi delle variabili di struttura e delle impostazioni utilizzate in un’implementazione.
  ![JavaScript legacy](./assets/appmeasurement-implementation.png)
Questo metodo di implementazione può essere utile per le implementazioni che utilizzano codice personalizzato ed è ancora consigliato quando utilizzi (desideri):

   * [dati Activity Map](../analyze/activity-map/activity-map.md),

     >[!INFO]
     >
     >È supportato l’utilizzo dell’SDK per web più recente, Activity Map. Consulta [Abilita Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) per ulteriori informazioni.

   * [misurazione di flussi multimediali](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=it),

   * [API livestream o trigger livestream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/getting_started.md),

   * [Tracciamento pagina AMP](./other/amp.md)

  Consulta [Implementare Adobe Analytics con AppMeasurement per JavaScript](js/overview.md) per ulteriori informazioni.

Il seguente flusso di decisione può essere utile per selezionare un metodo di implementazione:

![Albero decisionale](./assets/decision-tree.png)


>[!TIP]
>
>Contatta l’Adobe per consigli e best practice sull’implementazione da scegliere in base alla situazione corrente.

## Metodi di implementazione delle app mobili

Per **app mobile**, sono disponibili i seguenti metodi di implementazione:

* **Estensione Mobile SDK**: metodo standardizzato e consigliato per l’implementazione di Adobe Analytics nell’app mobile. Utilizza librerie dedicate per inviare facilmente i dati ad Adobe dall’app mobile. Installare **Estensione Adobe Experience Platform Mobile SDK** nella raccolta dati di Adobe Experience Platform **Tag** e implementa il codice corretto nell’app per importare librerie, registrare estensioni e caricare la configurazione di tag. I dati vengono inviati a Adobe Experience Platform **Rete Edge** in un formato adatto alla tua organizzazione. Experience Edge inoltra i dati in arrivo ad Adobe Analytics nel formato corretto.
  ![Estensione Mobile SDK](./assets/mobilesdk-extension.png)

  Consulta [Implementare Adobe Analytics utilizzando l’SDK di Adobe Experience Platform Mobile](../implement/aep-edge/mobile-sdk/overview.md) per ulteriori informazioni.

* **Estensione Analytics**: installa **Estensione Adobe Analytics** nella raccolta dati di Adobe Experience Platform **Tag**, e implementa il codice corretto nell’applicazione per importare librerie, registrare le estensioni e caricare la configurazione di tag. Utilizza l’estensione Analytics per determinare come viene definita ogni variabile. Utilizza questo metodo di implementazione se desideri la comodità della raccolta dati di Adobe Experience Platform, ma non utilizzare l’infrastruttura di rete Edge di Experience Platform di Adobe.
  ![Estensione Analytics](./assets/mobilesdk-analytics-extension.png)

  Consulta [Implementare Adobe Analytics utilizzando l’estensione Analytics](../implement/aep-edge/mobile-sdk/overview.md) per ulteriori informazioni.


>[!CAUTION]
>
>Il supporto per gli SDK della versione 4 per dispositivi mobili è terminato il 31 agosto 2021. Per ulteriori informazioni, consulta le domande frequenti relative alla [versione 4 degli SDK per dispositivi mobili](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/).

## Articoli chiave di implementazione di Analytics

* [Prendere in consegna un’implementazione Adobe Analytics esistente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creare una proprietà tag in Experience Platform](launch/create-analytics-property.md)
* [Aggiornamenti AppMeasurement](appmeasurement-updates.md)

## Altre guide utente di Analytics

[Guide utente di Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=it)

## Risorse chiave per Analytics

* [Contattare l’Assistenza clienti](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=it#support)
* [Forum di Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Risorse di Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
