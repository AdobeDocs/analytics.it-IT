---
title: Dimensioni del ciclo di vita mobile
description: Dimensioni basate sui dati raccolti tramite Mobile SDK.
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
TQID: 'https://experienceleague.adobe.com/VUN8x5eMzIfJ9VGw76v2pWfKWU7b-ct-kI6liwWTObw'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 6fd4400b33fcfc8bc3cd3ffc54fa738fef3441ef
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 4%
---
# Dimensioni del ciclo di vita mobile

>[!BEGINSHADEBOX]

*Questa pagina fa riferimento ai dati tracciati comunemente tramite Adobe Experience Platform Mobile SDK. Per informazioni sul dispositivo mobile tramite l&#39;agente utente, vedere [Dimensioni di ricerca mobile](mobile-dimensions.md). Per le metriche tracciate con Mobile SDK, vedi [Metriche del ciclo di vita mobile](../metrics/lifecycle-metrics.md).*

>[!ENDSHADEBOX]

| Nome dimensione ciclo di vita | Descrizione | Variabile dati contestuali |
| --- | --- | --- |
| **[!UICONTROL First Launch Date]** | Data in cui l&#39;app è stata eseguita per la prima volta dopo l&#39;installazione o la reinstallazione, in formato `M/d/yyyy`. | `a.InstallDate` |
| **[!UICONTROL Device Name (SDK)]** | Il nome del dispositivo raccolto da SDK. | `a.DeviceName` |
| **[!UICONTROL Operating System Version (SDK)]** | Il nome e la versione del sistema operativo raccolti da SDK. | `a.OSVersion` |
| **[!UICONTROL Resolution (SDK)]** | Risoluzione in pixel dello schermo del dispositivo, come larghezza x altezza. | `a.Resolution` |
| **[!UICONTROL Acquisition Source]** | Il referente originale per una campagna di acquisizione app, ad esempio una newsletter o un social network. | `a.referrer.campaign.source` |
| **[!UICONTROL App Id]** | Il nome e la versione dell&#39;app, nel formato `AppName BundleVersion (app version code)`. Ad esempio, `MyAppName 1.1(1)`. | `a.AppID` |
| **[!UICONTROL Acquisition Medium]** | Canale di marketing per una campagna di acquisizione app, ad esempio banner o e-mail. | `a.referrer.campaign.medium` |
| **[!UICONTROL Acquisition Term]** | Parole chiave a pagamento o altri termini associati a una campagna di acquisizione app. | `a.referrer.campaign.term` |
| **[!UICONTROL Acquisition Content]** | Nome o ID del contenuto che ha visualizzato il collegamento di acquisizione dell&#39;app. | `a.referrer.campaign.content` |
| **[!UICONTROL Acquisition Name]** | Nome della campagna di acquisizione app. | `a.referrer.campaign.name` |
| **[!UICONTROL Location (down to 10 km)]** | La latitudine e la longitudine del visitatore, precise al primo decimale. Ad esempio, `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| **[!UICONTROL Location (down to 100 m)]** | La latitudine e la longitudine del visitatore, con precisione alla terza cifra decimale. Ad esempio, `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| **[!UICONTROL Location (down to 1 m)]** | La latitudine e la longitudine del visitatore, con precisione al quinto decimale. Ad esempio, `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| **[!UICONTROL Point of Interest Name]** | Il nome del punto di interesse (POI) in cui si trova il dispositivo. Quando si utilizza l&#39;estensione [Places](https://developer.adobe.com/client-sdks/solution/places/), questo valore corrisponde al nome dell&#39;area Places. | `a.loc.poi` |
| **[!UICONTROL Distance to Point of Interest Center]** | La distanza tra il dispositivo e il centro del punto di interesse in cui si trova il dispositivo. | `a.loc.dist` |
| **[!UICONTROL Launch Number]** | Il numero di volte in cui l’app è stata avviata o portata in primo piano. | `a.Launches` |
| **[!UICONTROL Days Since First Use]** | Il numero di giorni dalla prima esecuzione dell’app. | `a.DaysSinceFirstUse` |
| **[!UICONTROL Action Name]** | Nome dell&#39;azione inviata in una chiamata `trackAction`. | `a.action` |
| **[!UICONTROL Lifetime Value (evar)]** | Il valore del ciclo di vita di un utente, ad esempio acquisti, visualizzazioni di annunci, video completati o condivisioni social nel corso del ciclo di vita. | `a.ltv.amount` |
| **[!UICONTROL Beacon Major]** | L’ID principale del beacon in cui si trova il dispositivo. | `a.beacon.major` |
| **[!UICONTROL Beacon Minor]** | ID secondario del beacon in prossimità del dispositivo. | `a.beacon.minor` |
| **[!UICONTROL Beacon UUID]** | L’UUID del beacon in cui si trova il dispositivo. | `a.beacon.uuid` |
| **[!UICONTROL Beacon Proximity]** | Prossimità del dispositivo al beacon: `0` (sconosciuto), `1` (immediato), `2` (vicino) o `3` (lontano). | `a.beacon.prox` |
| **[!UICONTROL Days Since Last Use]** | Il numero di giorni dall&#39;ultimo utilizzo dell&#39;app. | `a.DaysSinceLastUse` |
| **[!UICONTROL Hour of Day (SDK)]** | L’ora in cui è stata avviata l’app, nel formato 24 ore. Utile per la suddivisione del tempo per determinare le ore di utilizzo di picco. | `a.HourOfDay` |
| **[!UICONTROL Day of Week (SDK)]** | Il giorno della settimana in cui è stata avviata l’app. | `a.DayOfWeek` |
| **[!UICONTROL Point of Interest ID]** | ID del punto di interesse in cui si trova il dispositivo. Quando utilizzi l&#39;estensione [Places](https://developer.adobe.com/client-sdks/solution/places/), questo valore corrisponde all&#39;ID dell&#39;area Places. | `a.loc.poi.id` |

>[!NOTE]
>
>Alcune di queste dimensioni sono compilate da metodi nel legacy Mobile Services SDK (4.x), che non è più supportato. Il SDK Adobe Experience Platform Mobile non li compila automaticamente:
>
>* **Dimensioni di acquisizione** ([!UICONTROL Acquisition Source], [!UICONTROL Medium], [!UICONTROL Term], [!UICONTROL Content] e [!UICONTROL Name]): compilate da Acquisizione da app mobile, che il SDK mobile [non supporta](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/comparison/).
>* Dimensioni **[!UICONTROL Location]e[!UICONTROL Distance to Point of Interest Center]**: compilate dal metodo `trackLocation` 4.x. Il SDK Mobile sostituisce questo metodo con l&#39;estensione [Places](https://developer.adobe.com/client-sdks/solution/places/), che popola [!UICONTROL Point of Interest Name] e [!UICONTROL Point of Interest ID].
>* **[!UICONTROL Lifetime Value (evar)]**: popolato dal metodo `trackLifetimeValueIncrease` 4.x.
>* **Dimensioni beacon** ([!UICONTROL Beacon Major], [!UICONTROL Minor], [!UICONTROL UUID] e [!UICONTROL Proximity]): compilate dal metodo `trackBeacon` 4.x. Per inviare i dati beacon con Mobile SDK, vedi [Tracciamento dei beacon](https://developer.adobe.com/client-sdks/solution/adobe-analytics/track-beacon/).
>
>Per ulteriori informazioni, consulta [Migrazione da Adobe Mobile Library (v4) ad Experience Platform Analytics](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/analytics/).
