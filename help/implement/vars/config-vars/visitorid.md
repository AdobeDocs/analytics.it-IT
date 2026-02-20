---
title: visitorID
description: Utilizza un ID visitatore personalizzato.
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 4%

---

# visitorID

Adobe utilizza diversi metodi per [identificare i visitatori](../../id/overview.md) sul tuo sito. **La variabile `visitorID` sostituisce tutti gli altri metodi di identificazione dei visitatori.**

>[!IMPORTANT]
>
>Adobe consiglia di non utilizzare questa variabile. Utilizza invece il [servizio Adobe Experience Cloud Identity](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Utilizzo di `visitorID` in Analytics

Questa variabile è una sostituzione manuale dell’ID visitatore che sostituisce tutte le altre forme di identificazione del visitatore. Per essere conteggiato come un singolo visitatore, ogni hit per una persona deve utilizzare lo stesso valore `visitorID`.

* Gli hit che omettono `visitorID` tornano a un altro metodo di identificazione dei visitatori e vengono trattati come visitatori separati.
* Gli hit che utilizzano più di un valore `visitorID` vengono trattati come visitatori separati.
* Adobe non unisce gli hit che utilizzano ID visitatore diversi.

Consulta [Identificazione dei visitatori in Adobe Analytics](../../id/overview.md) per informazioni dettagliate sulla precedenza di identificazione e sul motivo per cui la combinazione di identificatori può aumentare il numero di visitatori.

>[!WARNING]
>
>Imposta `visitorID` solo se puoi garantire che è impostato su ogni hit per quella persona e che il valore non cambia mai. Impostandola solo su alcuni hit, introducendola in parte durante una visita (ad esempio in caso di autenticazione) o modificandola tra un hit e l’altro, l’attività di un singolo visitatore si divide in più visitatori.

>[!CAUTION]
>
>I valori degli ID visitatore personalizzati non validi possono causare dati errati e prestazioni di reporting scadenti. Se questa variabile contiene un valore predefinito o un valore segnaposto (ad esempio `"0"` o `"NULL"`), Adobe considera questi risultati come se fossero lo stesso visitatore. Questa situazione genera dati errati, con conteggi di visitatori artificialmente bassi e segmenti a livello di visitatore che non funzionano come previsto. Gli ID visitatore personalizzati implementati in modo non corretto possono anche introdurre un carico pesante sui server di elaborazione, aumentando la [latenza](/help/technotes/latency.md) e riducendo le prestazioni del rapporto.

## ID visitatore tramite l’estensione Adobe Analytics

[!UICONTROL Visitor ID] è un campo nel pannello a soffietto [!UICONTROL Cookies] durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Seleziona la proprietà tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi seleziona il pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi il pannello a soffietto [!UICONTROL Cookies], che mostra il campo [!UICONTROL Visitor ID].

Assegna questo campo all’elemento dati contenente l’ID visitatore personalizzato. **Non impostare questo campo su un singolo valore statico per tutti i visitatori.** Utilizza un elemento dati che si risolve per visitatore e rimane costante in tutti gli hit.

## s.visitorID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.visitorID` è una stringa che contiene un identificatore univoco personalizzato per il visitatore. I valori validi includono caratteri alfanumerici fino a 100 byte. Evita di usare trattini, spazi, trattini bassi o simboli in questa variabile.

```js
s.visitorID = "abc123";
```

## ID visitatore che utilizza il Web SDK

Adobe Experience Platform Edge Network consente di fornire più identificatori utilizzando la [Identity Map](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html#using-identitymap) di XDM. Ogni identità in Identity Map ha uno spazio dei nomi diverso. È possibile specificare lo spazio dei nomi da utilizzare per l&#39;ID visitatore come parte della [configurazione dello stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html#analytics). Una volta configurato, questo campo viene utilizzato automaticamente come ID visitatore in Analytics quando invii un evento con un valore specificato per questo spazio dei nomi.
