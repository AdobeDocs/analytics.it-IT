---
description: La tabella seguente contiene un elenco delle attività da eseguire per migrare l’implementazione.
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrazione ad AppMeasurement per JavaScript
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Migrazione ad AppMeasurement per JavaScript

La tabella seguente contiene un elenco delle attività da eseguire per migrare l’implementazione.

>[!NOTE]
>
>È consigliabile eseguire la migrazione al servizio [](/help/implement/js-implementation/c-unique-visitors/visid-service.md) identità al momento della migrazione a [!DNL AppMeasurement] JavaScript.

![](assets/step1_icon.png) Verifica compatibilità plug-in

Dove: s\_code.js

Alcuni plug-in non sono più supportati. See [AppMeasurement Plug-in Support](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md) .

![](assets/step2_icon.png) Scarica la nuova AppMeasurement

Dove: Amministratore &gt; Code Manager

Il file zip di download contiene un file AppMeasurement.js minificato e file Javascript per i moduli Media e Integrate.

![](assets/step3_icon.png) Copiate la personalizzazione s\_code.js in `AppMeasurement.js`.

Dove: s\_code.js e AppMeasurement.js

Sposta tutto il codice visualizzato prima della `DO NOT ALTER ANYTHING BELOW THIS LINE` sezione in s\_code.js all'inizio di AppMeasurement.js.

![](assets/step4_icon.png) (Facoltativo) Aggiornamento dei plug-in

Dove: AppMeasurement.js

Se utilizzate il plug-in getQueryParam, aggiornate queste chiamate per utilizzare la nuova utility, [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md).

![](assets/step5_icon.png) (Facoltativo) Aggiornare i moduli Media e Integrare

Dove: AppMeasurement.js

Se utilizzate uno di questi moduli, copiate e incollate il codice da AppMeasurement\_Module\_Media.js e/o AppMeasurement\_Module\_Integrate.js e incollatelo subito prima del file `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Implementare un nuovo JavaScript

Dove: Il sito Web

Il nuovo file JavaScript può essere distribuito in base al processo standard. Il codice di pagina esistente è compatibile con questa versione.
