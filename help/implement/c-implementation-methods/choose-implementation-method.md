---
description: Esistono diversi modi per implementare Adobe Analytics.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; javascript
seo-description: Esistono diversi modi per implementare Adobe Analytics.
seo-title: Scegliere un metodo di implementazione
solution: Analytics
title: Scegliere un metodo di implementazione
topic: Sviluppatore e implementazione
uuid: 20 d 3317 f -7 c 63-4421-93 e 0-fff 60 dbd 9 f 87
translation-type: tm+mt
source-git-commit: b1e69abd65f171b804e7f56031e594890bbd27bb

---


# Scegliere un metodo di implementazione

Esistono diversi modi per implementare Adobe Analytics.

* [!UICONTROL Adobe Experience Platform Launch] (Consigliato)
* [!UICONTROL Dynamic Tag Management]
* JavaScript

## [!UICONTROL Adobe Experience Platform Launch] {#section_AEEA6AFE2C8D4182BC778F08EA171DC8}

[!UICONTROL Experience Platform Launch] è la prossima generazione di funzionalità di gestione di tag e SDK per dispositivi mobili di Adobe. [!UICONTROL Experience Platform Launch] ti consente di distribuire e gestire semplicemente tutte le integrazioni di analisi, marketing e pubblicità necessarie per sviluppare esperienze cliente rilevanti.

[!UICONTROL Experience Platform Launch] permette a chiunque di generare e mantenere le proprie integrazioni , chiamate “estensioni”. [!DNL Experience Platform Launch] These extensions are available to web and mobile [!UICONTROL Experience Platform Launch] customers in an app-store experience, so customers can quickly install, configure, and deploy their integrations.

For more information, see [Getting Started with Experience Platform Launch](https://docs.adobelaunch.com/getting-started).

## [!UICONTROL Dynamic Tag Management] {#section_22E3F3F928894A6A8D77E6953E6CA51C}

[!UICONTROL Dynamic Tag Management] automatizza gran parte dei dettagli necessari [!DNL Analytics]per l'implementazione. Enter the required information in a form-based interface, and [!DNL Dynamic Tag Management] generates the code you need to add to your pages.
È utile avere familiarità con javascript e comprendere la terminologia di base di Analytics, come

* What an [eVar](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) is and how it works
* When to use a [custom event](../../implement/analytics-terminology-basics/c-props-evars/event-custom.md#concept_CDA3C98C85B24A71B4B5C71F24BF918F)

For information about getting access to Dynamic Tag Management and getting up and running, see [Getting Started](https://marketing.adobe.com/resources/help/en_US/dtm/get_started.html) in the Dynamic Tag Management Product Documentation.

For more information, see [Implementing Analytics with Dynamic Tag Management](../../implement/c-implement-with-dtm/dtm-implementation-overview.md).

## JavaScript {#section_55429940D5094B9BB513E526F224D1B4}

Il metodo di implementazione javascript richiede di configurare manualmente i codici javascript sulle pagine. Molte di queste operazioni possono essere semplificate se utilizzate i metodi di implementazione della piattaforma Geometeience Platform o della gestione tag dinamica. Tuttavia, alcuni utenti potrebbero richiedere il metodo javascript.

L'implementazione javascript richiede:

* Avanzate competenze javascript
* Conoscenza approfondita dei concetti e della terminologia di Analytics

For more information, see [Implementing Analytics Using JavaScript](../../implement/js-implementation/javascript-implementation-overview.md).
