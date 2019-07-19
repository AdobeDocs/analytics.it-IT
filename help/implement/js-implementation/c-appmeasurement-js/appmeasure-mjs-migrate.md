---
description: La tabella seguente contiene un elenco delle attività da eseguire per migrare l'implementazione.
keywords: Implementazione di Analytics; appmeasurement; migrare; migrazione; javascript
seo-description: La tabella seguente contiene un elenco delle attività da eseguire per migrare l'implementazione.
seo-title: Migrazione ad appmeasurement per javascript
solution: Analytics
subtopic: Javascript appmeasurement
title: Migrazione ad appmeasurement per javascript
topic: Sviluppatore e implementazione
uuid: 5 be 345 a 8-5 a 95-4176-a 2 e 6-97139 b 9 b 46 ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Migrazione ad appmeasurement per javascript

La tabella seguente contiene un elenco delle attività da eseguire per migrare l'implementazione.

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) Verificate la compatibilità con i plug-in

Dove: s\_ code. js

Alcuni plug-in non sono più supportati. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) Scarica la nuova appmeasurement

Dove: Admin &gt; Code Manager

Il file ZIP di download contiene un file appmeasurement. js minito e file Javascript per i moduli Media e Integra.

![](assets/step3_icon.png) Copia la personalizzazione s\_ code. js a `AppMeasurement.js`.

Dove: s\_ code. js e appmeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (Facoltativo) Aggiorna i plug-in

Dove: Appmeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (Facoltativo) Aggiorna i moduli e integra i moduli

Dove: Appmeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Implementare un nuovo javascript

Dove: Il vostro sito Web

Il nuovo file javascript può essere distribuito in base alla procedura standard. Il codice della pagina esistente è compatibile con questa versione.