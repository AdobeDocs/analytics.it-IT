---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 11%

---

# visitorID

Adobe utilizza diversi metodi per identificare i visitatori sul sito. La variabile `visitorID` sostituisce tutti gli altri metodi di identificazione dei visitatori.

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questa variabile. Utilizza invece il [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## ID visitatore tramite l’estensione Adobe Analytics

[!UICONTROL Visitor ID] è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Visitor ID].

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. Non impostare questo campo su un valore statico.

## s.visitorID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.visitorID` è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evita di usare trattini, spazi, trattini bassi o simboli in questa variabile.

>[!WARNING]
>
>Se imposti la variabile `visitorID` in una visita, i dati risulteranno in due visitatori univoci distinti.

```js
s.visitorID = "abc123";
```

>[!CAUTION]
>
>Un’implementazione non valida degli ID visitatore personalizzati può portare a dati errati e prestazioni di reporting scadenti. Se questa variabile contiene un valore predefinito (ad esempio `"0"` o `"NULL"`), Adobe considera questi risultati come se fossero lo stesso visitatore. Questa situazione genera dati errati, con un numero basso di visitatori e segmenti a livello di visitatore che non funzionano come previsto. Gli ID visitatore personalizzati implementati in modo non corretto introducono anche un carico pesante sui server di elaborazione, aumentando la [latenza](/help/technotes/latency.md) e riducendo le prestazioni del rapporto.

## ID visitatore che utilizza il Web SDK

Adobe Experience Platform Edge Network consente di fornire più identificatori utilizzando la [Identity Map](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap) di XDM. Ogni identità in Identity Map ha uno spazio dei nomi diverso. È possibile specificare quale spazio dei nomi utilizzare per l&#39;ID visitatore come parte della [configurazione dello stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics). Una volta configurato, quando invii un evento con un valore specificato per questo spazio dei nomi, verrà utilizzato automaticamente come ID visitatore in Analytics.
