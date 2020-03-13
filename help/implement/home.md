---
title: Implementazione di Adobe Analytics
description: Implementa Adobe Analytics sul tuo sito, proprietà o applicazione.
translation-type: ht
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Implementazione di Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Per inviare dati ai propri server di raccolta dati, Adobe richiede codice sul sito o nell’app. I seguenti passaggi indicano il funzionamento di un’implementazione tipica.

1. Quando un visitatore accede al tuo sito, viene inviata una richiesta al server web.
2. Il server web del sito invia le informazioni sul codice della pagina e la pagina viene visualizzata nel browser.
3. La pagina viene caricata e viene eseguito il codice JavaScript di Analytics.
Il codice JavaScript invia una richiesta di immagine ai server di raccolta dati Adobe. In questa richiesta di immagine, i dati di pagina definiti nell’implementazione vengono inviati come parte di una stringa di query.

4. Adobe restituisce un’immagine trasparente in pixel.
5. I server Adobe memorizzano i dati raccolti in una *suite di report*.
6. I dati della suite di report popolano i rapporti a cui potrai poi accedere in un browser web.

   L’esecuzione del codice JavaScript avviene rapidamente e non influisce in modo rilevante sui tempi di caricamento delle pagine. Questo approccio consente di contare le pagine visualizzate quando un visitatore fa clic su **[!UICONTROL Reload]** o **[!UICONTROL Back]** per raggiungere una pagina, perché JavaScript viene eseguito anche durante il recupero della pagina dalla cache.

Per poter inviare dati ai server di raccolta dati, Adobe Analytics richiede il codice all’interno del sito web, dell’app mobile o di altre applicazioni. Esistono diversi metodi per implementare questo codice, a seconda della piattaforma e delle esigenze aziendali.

* **Adobe Experience Platform Launch:** metodo standardizzato e consigliato per l’implementazione di Adobe Analytics. Inserisci un tag loader in ciascuna pagina e utilizza l’interfaccia di Launch per determinare come viene definita ogni variabile.
* **Dynamic Tag Management:** predecessore di Launch. DTM offre un’interfaccia simile per implementare Analytics, ma non viene più aggiornato e non offre flessibilità. Adobe consiglia di implementare Adobe Analytics tramite Launch.
* **JavaScript legacy:** metodo manuale che veniva utilizzato per implementare Adobe Analytics. Consente di specificare le variabili e le impostazioni utilizzate in un’implementazione e può essere utile per le implementazioni di Launch basate su regole con codice personalizzato.
* **SDK per dispositivi mobili**: librerie dedicate per inviare facilmente i dati ad Adobe dall’app mobile.

## Articoli chiave di implementazione di Analytics

* [Adobe Debugger](validate/debugger.md)
* [Creare una proprietà in Experience Platform Launch](launch/create-analytics-property.md)
* [Aggiornamenti AppMeasurement](appmeasurement-updates.md)

## Altre guide utente di Analytics

[Guide utente di Analytics](/help/landing/home.md)

## Risorse chiave per Analytics

* [Contattare l’Assistenza clienti](https://helpx.adobe.com/it/contact/enterprise-support.ec.html)
* [Forum di Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Risorse di Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
