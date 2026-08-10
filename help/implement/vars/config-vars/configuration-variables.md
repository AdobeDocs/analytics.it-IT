---
title: Variabili di configurazione
description: Utilizza le variabili di configurazione per determinare come vengono raccolti i dati.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 381
ht-degree: 3%

---

# Panoramica delle variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono acquisiti ed elaborati nei rapporti. In genere non contengono valori di dimensioni o metriche.

## Impostazione delle variabili di configurazione

Nelle implementazioni che utilizzano l’estensione Web SDK o Analytics, le variabili di configurazione si trovano in genere nelle impostazioni dell’estensione:

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Fare clic sulla scheda [!UICONTROL Extensions], quindi su [!UICONTROL Configure] sotto l&#39;estensione.

Nelle implementazioni di JavaScript che utilizzano `AppMeasurement.js`, le variabili di configurazione vengono in genere impostate nella parte superiore del file JS.

>[!IMPORTANT]
>
>Assicurarsi che tutte le variabili di configurazione siano impostate prima di chiamare un metodo di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evitare di impostare le variabili di configurazione nella funzione [`doPlugins()`](../functions/doplugins.md).

## Variabili di configurazione ritirate

Le seguenti variabili di configurazione vengono ritirate. Sono documentati qui come riferimento se si trovano in un’implementazione legacy.

* **`account`**: determinata la suite di rapporti a cui sono stati inviati i dati. La suite di rapporti è ora gestita tramite la creazione di istanze dell&#39;oggetto di tracciamento (metodo [`s_gi()`](../functions/s-gi.md)). Utilizzare il metodo [`s.sa()`](../functions/sa-method.md) se è necessario modificare la suite di rapporti dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento.
* **`cookieDomain`**: determinato il dominio in cui AppMeasurement imposta i cookie. Le versioni correnti di AppMeasurement rilevano automaticamente il dominio del cookie corretto, rendendo obsoleta questa variabile.
* **`cookieDomainPeriods`**: ha aiutato AppMeasurement a determinare dove memorizzare i cookie quando un dominio conteneva più periodi. Le versioni correnti di AppMeasurement rilevano automaticamente il dominio corretto, rendendo obsoleta questa variabile.
* **`fpCookieDomainPeriods`**: l&#39;equivalente di prima parte di `cookieDomainPeriods`, utilizzato per impostare i cookie nella posizione corretta quando il suffisso di un dominio di prima parte contiene un punto aggiuntivo (ad esempio `example.co.uk`). Le versioni correnti di AppMeasurement rilevano automaticamente il dominio corretto, rendendo obsoleta questa variabile.
* **`trackingServer`**: specificato il dominio utilizzato per inviare dati ad Adobe tramite HTTP. È stato dichiarato obsoleto a favore di una raccolta dati sicura tramite HTTPS. Usa [`trackingServerSecure`](trackingserversecure.md) invece.
* **`trackInlineStats`**: versione precedente di [Activity Map](/help/analyze/activity-map/overview.md) abilitata o disabilitata.
* **`visitorMigrationKey`**: ha portato una chiave utilizzata per migrare i visitatori da cookie di terze parti a cookie di prime parti. È stato ritirato perché le librerie moderne impostano un cookie di fallback di prime parti (`fid`) e si basano sul servizio ID visitatore per l&#39;identità.
* **`visitorMigrationServer`**: specificato il server utilizzato durante la migrazione di cookie di terze parti a cookie di prima parte.
* **`visitorMigrationServerSecure`**: equivalente HTTPS di `visitorMigrationServer`.
* **`visitorNameSpace`**: ha contribuito a determinare il dominio dei cookie di terze parti. È stato ritirato a favore dell&#39;utilizzo della variabile [`trackingServerSecure`](trackingserversecure.md) per le implementazioni che non utilizzano il servizio ID visitatore.
