---
title: Implementazione di Adobe Analytics
description: Implementa Adobe Analytics sul tuo sito, proprietà o applicazione.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
source-git-commit: d2c291f7db465034ffadc4a2c1caf9639caf2a1d
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 79%

---

# Implementazione di Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Ecco una panoramica video di Adobe Analytics:

>[!VIDEO](https://video.tv.adobe.com/v/27429/?quality=12)

Per inviare dati ai propri server di raccolta dati, Adobe richiede codice sul sito o nell’app. I seguenti passaggi indicano il funzionamento di un’implementazione tipica.

1. Quando un visitatore accede al tuo sito, viene inviata una richiesta al server web.
2. Il server web del sito invia le informazioni sul codice della pagina e la pagina viene visualizzata nel browser.
3. La pagina viene caricata e viene eseguito il codice JavaScript di Analytics.
4. Il codice JavaScript invia una richiesta di immagine da 1x1 pixel ai server di raccolta dati di Adobe. In questa richiesta di immagine, i dati di pagina definiti nell’implementazione vengono inviati come parte di una stringa di query.
5. I server di raccolta dati di Adobe restituiscono l’immagine richiesta.
6. I server di Adobe analizzano e memorizzano i dati raccolti in una suite di rapporti.
7. I dati della suite di report popolano i rapporti a cui potrai poi accedere in un browser web.


Adobe offre diversi metodi per implementare questo codice, a seconda della piattaforma e delle esigenze della tua organizzazione.

* **Estensione SDK per web**: Il metodo corrente, standardizzato e consigliato per l’implementazione di Adobe Analytics. Installa l’estensione Web SDK in raccolta dati Adobe Experience Platform, utilizza un tag loader in ogni pagina e invia i dati a Adobe Experience Platform Edge in un formato adatto alla tua organizzazione. Experience Edge inoltra i dati in arrivo ad Adobe Analytics nel formato corretto.
* **SDK per web**: Se non desideri utilizzare i tag, puoi caricare manualmente le librerie SDK web sul tuo sito. Fai riferimento alla libreria SDK web in ogni pagina e invia le chiamate di tracciamento desiderate ad Adobe Experience Edge.
* **Estensione Adobe Analytics**: installa l’estensione Adobe Analytics in raccolta dati Adobe Experience Platform. Inserisci un tag loader in ciascuna pagina e utilizza l’estensione Analytics per determinare come viene definita ogni variabile.
* **JavaScript legacy:** metodo manuale che veniva utilizzato per implementare Adobe Analytics. Consente di specificare le variabili e le impostazioni utilizzate in un’implementazione e può essere utile per le implementazioni di basate su regole con codice personalizzato.
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
* [Experience League](https://experienceleague.adobe.com/?lang=it#dashboard/learning)
