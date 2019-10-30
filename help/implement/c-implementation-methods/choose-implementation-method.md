---
description: Esistono diversi modi per implementare Adobe Analytics.
keywords: Implementazione di Analytics;metodo di implementazione;gestione tag dinamica;dtm;javascript
seo-description: Esistono diversi modi per implementare Adobe Analytics.
seo-title: Scegliere un metodo di implementazione
solution: Analytics
title: Scegliere un metodo di implementazione
topic: Sviluppatore e implementazione
uuid: 20d3317f-7c63-4421-93e0-fff60dbd9f87
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Scegliere un metodo di implementazione

Esistono diversi modi per implementare Adobe Analytics.

* [!UICONTROL Adobe Experience Platform Launch] (consigliato)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] è la nuova generazione di funzionalità di gestione di tag per siti Web e SDK per dispositivi mobili di Adobe. [!UICONTROL Experience Platform Launch] offre un modo semplice per implementare e gestire tutte le integrazioni di analisi, marketing e pubblicità necessarie per fornire esperienze cliente rilevanti.

[!UICONTROL Experience Platform Launch] permette a chiunque di generare e mantenere le proprie integrazioni , chiamate “estensioni”. [!DNL Experience Platform Launch] These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

Per ulteriori informazioni, consulta [Guida introduttiva al lancio](https://docs.adobelaunch.com/getting-started)della piattaforma Experience.

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] automatizza gran parte del lavoro di dettaglio richiesto per l'implementazione [!DNL Analytics]. Immettere le informazioni richieste in un'interfaccia basata su modulo e [!DNL Dynamic Tag Management] generare il codice da aggiungere alle pagine.
È utile avere familiarità con JavaScript e comprendere la terminologia di base di Analytics, ad esempio

* Che cos'è una [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) e come funziona
* Quando utilizzare un evento [personalizzato](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

Per informazioni su come ottenere l’accesso a Gestione tag dinamica e come iniziare a utilizzare, consulta la [Guida introduttiva](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) nella Documentazione prodotto Gestione tag dinamica.

Per ulteriori informazioni, consulta [Implementazione di Analytics con Gestione](../../implement/c-implement-with-dtm/dtm-implementation-overview.md)tag dinamica.

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

Il metodo di implementazione JavaScript richiede la configurazione manuale dei codici JavaScript sulle pagine. Gran parte di questo sforzo può essere semplificato se utilizzi i metodi di implementazione di Experience Platform Launch o Gestione tag dinamica. Tuttavia, alcuni utenti potrebbero richiedere il metodo JavaScript.

L'implementazione JavaScript richiede:

* Forti competenze JavaScript
* Comprensione dei concetti e della terminologia di Analytics

Per ulteriori informazioni, consultate [Implementazione di Analytics tramite JavaScript](../../implement/js-implementation/javascript-implementation-overview.md).
