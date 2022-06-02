---
title: Implementazione di Adobe Analytics
description: Implementa Adobe Analytics sul tuo sito, proprietà o applicazione.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: dd94330c660aee8c588b00f7d63e6879003cb958
workflow-type: ht
source-wordcount: '372'
ht-degree: 100%

---

# Implementazione di Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Ecco una panoramica video di Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

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

* **Tag di Adobe Experience Platform**: metodo standardizzato e consigliato per l’implementazione di Adobe Analytics. Inserisci un tag loader in ciascuna pagina e utilizza l’interfaccia di Data Collection per determinare come viene definita ogni variabile.
* **JavaScript legacy:** metodo manuale che veniva utilizzato per implementare Adobe Analytics. Consente di specificare le variabili e le impostazioni utilizzate in un’implementazione e può essere utile per le implementazioni basate su regole con codice personalizzato.
* **SDK per dispositivi mobili:** librerie dedicate per inviare facilmente i dati ad Adobe dall’app mobile.

## Articoli chiave di implementazione di Analytics

* [Prendere in consegna un’implementazione Adobe Analytics esistente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creare una proprietà tag in Experience Platform](launch/create-analytics-property.md)
* [Aggiornamenti AppMeasurement](appmeasurement-updates.md)

## Altre guide utente di Analytics

[Guide utente di Analytics](https://experienceleague.adobe.com/docs/analytics.html?lang=it)

## Risorse chiave per Analytics

* [Contattare l’Assistenza clienti](https://experienceleague.adobe.com/?support-solution=Analytics&amp;lang=it#support)
* [Forum di Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Risorse di Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://experienceleague.adobe.com/?lang=it#home)
