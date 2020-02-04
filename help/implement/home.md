---
title: Implementazione di Adobe Analytics
description: Implementa Adobe Analytics sul tuo sito, proprietà o applicazione.
translation-type: tm+mt
source-git-commit: 8a090574a6822a76366343ad5c657280bf7475eb

---


# Implementazione di Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Per inviare dati ai server di raccolta dati di Adobe, Adobe richiede del codice sul sito o l&#39;app. I passaggi seguenti indicano il funzionamento di un&#39;implementazione tipica.

1. Quando un visitatore accede al sito, viene inviata una richiesta al server Web.
2. Il server Web del sito invia le informazioni sul codice della pagina e la pagina viene visualizzata nel browser.
3. Viene caricata la pagina e viene eseguito il codice JavaScript di Analytics.
Il codice JavaScript invia una richiesta di immagine ai server di raccolta dati Adobe. I dati di pagina definiti nell’implementazione vengono inviati come parte di una stringa di query in questa richiesta di immagine.

4. Adobe restituisce un’immagine in pixel trasparente.
5. I server Adobe memorizzano i dati raccolti in una suite *di* rapporti.
6. I dati della suite di rapporti popolano i rapporti a cui puoi accedere in un browser Web.

   L&#39;esecuzione del codice JavaScript avviene rapidamente e non influisce in modo rilevante sui tempi di caricamento delle pagine. Questo approccio consente di contare le pagine visualizzate quando un visitatore fa clic **[!UICONTROL Reload]**o**[!UICONTROL Back]** per raggiungere una pagina, perché JavaScript viene eseguito anche quando la pagina viene recuperata dalla cache.

Adobe Analytics richiede il codice all&#39;interno del sito Web, dell&#39;app mobile o di altre applicazioni per inviare dati ai server di raccolta dati. Esistono diversi metodi per implementare questo codice, a seconda della piattaforma e delle esigenze aziendali.

* **Adobe Experience Platform Launch**: Metodo standard e consigliato per implementare Adobe Analytics. Inserisci un tag loader in ciascuna pagina e utilizza l’interfaccia di Launch per determinare come viene definita ogni variabile.
* **Gestione** tag dinamica: Il predecessore di Launch. DTM offre un’interfaccia simile per implementare Analytics, ma non viene più aggiornato e non offre flessibilità. Adobe consiglia di implementare Adobe Analytics tramite Launch.
* **JavaScript** legacy: Metodo manuale storico per l’implementazione di Adobe Analytics. Consente di specificare le variabili e le impostazioni utilizzate in un’implementazione e può essere utile per le implementazioni di Launch basate su regole con codice personalizzato.
* **SDK** per dispositivi mobili: Librerie dedicate per inviare facilmente i dati ad Adobe dall&#39;app mobile.

## Articoli chiave di implementazione di Analytics

* [Adobe Debugger](validate/debugger.md)
* [Creare una proprietà in Experience Platform Launch](launch/create-analytics-property.md)
* [Aggiornamenti AppMeasurement](appmeasurement-updates.md)

## Altre guide utente di Analytics

[Guide utente di Analytics](/help/landing/home.md)

## Risorse chiave per Analytics

* [Contattare l’Assistenza clienti](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Forum di Analytics](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Risorse di Adobe Analytics](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
