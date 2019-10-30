---
description: La tabella seguente contiene un elenco delle attività da eseguire per migrare l’implementazione.
keywords: Implementazione di Analytics;app measurement;migrate;migrazione;javascript
seo-description: La tabella seguente contiene un elenco delle attività da eseguire per migrare l’implementazione.
seo-title: Migrazione ad AppMeasurement per JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrazione ad AppMeasurement per JavaScript
topic: Sviluppatore e implementazione
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Migrazione ad AppMeasurement per JavaScript

La tabella seguente contiene un elenco delle attività da eseguire per migrare l’implementazione.

> [!NOTE] È consigliabile eseguire la migrazione al servizio [](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) identità al momento della migrazione a [!DNL AppMeasurement] JavaScript.

![](assets/step1_icon.png) Verifica compatibilità plug-in

Dove: s\_code.js

Alcuni plug-in non sono più supportati. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) Scarica la nuova AppMeasurement

Dove: Amministratore &gt; Code Manager

Il file zip di download contiene un file AppMeasurement.js minificato e file Javascript per i moduli Media e Integrate.

![](assets/step3_icon.png) Copiate la personalizzazione s\_code.js in `AppMeasurement.js`.

Dove: s\_code.js e AppMeasurement.js

Sposta tutto il codice visualizzato prima della `DO NOT ALTER ANYTHING BELOW THIS LINE` sezione in s\_code.js all'inizio di AppMeasurement.js.

![](assets/step4_icon.png) (Facoltativo) Aggiornamento dei plug-in

Dove: AppMeasurement.js

Se utilizzate il plug-in getQueryParam, aggiornate queste chiamate per utilizzare la nuova utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (Facoltativo) Aggiornare i moduli Media e Integrare

Dove: AppMeasurement.js

Se utilizzate uno di questi moduli, copiate e incollate il codice da AppMeasurement\_Module\_Media.js e/o AppMeasurement\_Module\_Integrate.js e incollatelo subito prima del file `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Implementare un nuovo JavaScript

Dove: Il sito Web

Il nuovo file JavaScript può essere distribuito in base al processo standard. Il codice di pagina esistente è compatibile con questa versione.