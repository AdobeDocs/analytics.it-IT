---
title: Implementare Adobe Analytics
description: Implementa Adobe Analytics sul tuo sito, proprietà o applicazione.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/c1TZC9k-mu1n95Oq3jhQOvcBXFwx8oK28plhoNcJDK4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c77ba355-6681-41fe-b719-563d3f507fdbid: c8add8f2-4250-4fd9-9cde-9707036c567did: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: f8a45b24-4be7-4f1b-909b-60d06b483a20id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 197233b18a57ac67d4b56ddd34f296d88dd9c4b2
workflow-type: tm+mt
source-wordcount: 814
ht-degree: 79%

---

# Implementare Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Per poter inviare dati ai server di raccolta dati, Adobe Analytics richiede il codice all’interno del sito web, dell’app mobile o di altre applicazioni. Esistono diversi metodi per implementare questo codice, a seconda della piattaforma e delle esigenze aziendali.

## Metodi di implementazione del sito web

Per il tuo **sito web**, sono disponibili i seguenti metodi di implementazione:

### Lato client

* **Estensione Web SDK**: metodo standardizzato e consigliato per l’implementazione di Adobe Analytics per nuovi clienti. Aggiungi l’**estensione Adobe Experience Platform Web SDK** nei **tag** della raccolta dati di Adobe Experience Platform, quindi inserisci un tag loader in ciascuna pagina. Il tag invia i dati alla **rete Edge** di Adobe Experience Platform, che inoltra tali dati ad Adobe Analytics.
  ![Estensione Web SDK](./assets/websdk-extension-implementation.png)
Consulta [Come implementare Adobe Analytics utilizzando l&#39;estensione Adobe Experience Platform Web SDK.](./aep-edge/overview.md) per ulteriori informazioni.

* **SDK per web**: se non desideri utilizzare la raccolta dati di Adobe Experience Platform, puoi caricare manualmente le librerie SDK web sul tuo sito. Consulta la libreria SDK web (`alloy.js`) su ciascuna pagina e invia le chiamate di tracciamento desiderate alla **rete Edge** di Adobe Experience Platform in un formato adatto alla tua organizzazione. La rete Edge inoltra tali dati ad Adobe Analytics.
  ![Web SDK](./assets/websdk-implementation.png)
Per ulteriori informazioni, vedere [Come implementare Adobe Analytics utilizzando Adobe Experience Platform Web SDK](./aep-edge/overview.md).

* **Estensione Analytics**: aggiungi l’**estensione Adobe Analytics** nei **tag** della raccolta dati di Adobe Experience Platform, quindi inserisci un tag loader in ciascuna pagina. Il tag invia i dati direttamente ad Adobe Analytics. Utilizza questo metodo di implementazione se desideri la comodità dei tag, ma non utilizzare l’infrastruttura di rete Edge.
  ![Estensione Adobe Analytics](./assets/analytics-extension-implementation.png)
Consulta [Come implementare Adobe Analytics utilizzando l&#39;estensione Analytics](launch/overview.md) per ulteriori informazioni.

* **JavaScript legacy:** metodo manuale che veniva utilizzato per implementare Adobe Analytics. Consulta la libreria di AppMeasurement (`AppMeasurement.js`) in ogni pagina, quindi imposta le variabili e le impostazioni in JavaScript.
  ![Come implementare Adobe Analytics utilizzando la versione precedente di JavaScript](./assets/appmeasurement-implementation.png)
Questo metodo di implementazione può essere utile per le implementazioni che utilizzano codice personalizzato ed è ideale per tipi di implementazione non offerti altrove, ad esempio per [pagine AMP](other/amp.md).

Il seguente flusso decisionale può essere utile per selezionare un metodo di implementazione lato client:

![Un albero delle decisioni per la selezione di un metodo di implementazione, come descritto in questa sezione.](./assets/decision-tree.png)


>[!TIP]
>
>Contatta il tuo team Adobe Account per consigli e best practice sull’implementazione da scegliere in base alla situazione corrente.

### Lato server

Per implementare Adobe Analytics lato server, sono disponibili le seguenti opzioni:

* **API Edge Network**: implementi il codice nel server che utilizza l&#39;API Adobe Experience Platform Edge Network per comunicare con Adobe Analytics tramite uno stream di dati.
  ![Implementazione lato server](assets/edge-network-server-api.png)
Per ulteriori informazioni, vedere [Implementare Adobe Analytics utilizzando l&#39;API Edge Network di Adobe Experience Platform](/help/implement/aep-edge/api/overview.md).

* **API di inserimento dati (in blocco)**: si utilizza l’API di inserimento dati (in blocco) di Adobe Analytics per raccogliere i dati lato server direttamente in Adobe Analytics.
  ![API di inserimento dati](assets/analytics-apis.png)
Per ulteriori informazioni, vedere [API di inserimento dati](../import/c-data-insertion-api/c-data-insertion-api.md).

## Metodi di implementazione delle app mobili

Per la tua **app mobile**, sono disponibili i seguenti metodi di implementazione:

* **Estensione Web SDK**: metodo standardizzato e consigliato per l’implementazione di Adobe Analytics nella tua app mobile. Usa le librerie dedicate per inviare facilmente i dati ad Adobe dall’app mobile. Aggiungi l’**estensione Adobe Experience Platform Mobile SDK** nei **tag** della raccolta dati di Adobe Experience Platform, quindi implementa la libreria Mobile SDK nell’app. Puoi utilizzare l’SDK per importare librerie, registrare estensioni e caricare la configurazione di tag. Invia dati alla **Rete Edge** di Adobe Experience Platform; Edge inoltra quindi tali dati ad Adobe Analytics.
  ![Estensione di Mobile SDK](./assets/mobilesdk-extension.png)

  Consulta [Implementare Adobe Analytics utilizzando Mobile SDK di Adobe Experience Platform](../implement/aep-edge/mobile-sdk/overview.md) per ulteriori informazioni.

* **Estensione Analytics**: aggiungi l’**estensione Adobe Analytics** nei **tag** della raccolta dati di Adobe Experience Platform e implementa la libreria di Mobile SDK nella tua app. Puoi utilizzare l’SDK per importare librerie, registrare estensioni e caricare la configurazione di tag. Questo metodo di implementazione invia i dati direttamente ad Adobe Analytics. È consigliabile se desideri la comodità di Raccolta dati di Adobe Experience Platform, ma non vuoi utilizzare l’infrastruttura di rete Edge di Adobe Experience Platform.
  ![Estensione Analytics](./assets/mobilesdk-analytics-extension.png)

  Consulta [Implementare Adobe Analytics utilizzando l’estensione Analytics](../implement/aep-edge/mobile-sdk/overview.md) per ulteriori informazioni.


>[!CAUTION]
>
>Per il supporto delle versioni precedenti degli SDK per dispositivi mobili di Adobe, consulta [Annunci sulla fine del supporto degli SDK](https://developer.adobe.com/client-sdks/resources/sdks-end-of-support/).

## Articoli chiave di implementazione di Analytics

* [Prendere in consegna un’implementazione Adobe Analytics esistente](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Creare una proprietà tag in Experience Platform](launch/create-analytics-property.md)
* [Aggiornamenti AppMeasurement](appmeasurement-updates.md)
* [Tutorial su come configurare Adobe Analytics con Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-analytics.html?lang=it)
* [Tutorial sull’implementazione di Adobe Experience Cloud nelle app per dispositivi mobili](https://experienceleague.adobe.com/docs/platform-learn/implement-mobile-sdk/overview.html?lang=it)


## Risorse chiave per Analytics

* [Contatta l’Assistenza clienti](https://experienceleague.adobe.com/?support-solution=Analytics?lang=it#support)
* [Community di Adobe Analytics su Experience League](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Risorse di Adobe Analytics](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
* [Note sulla versione più recente](../release-notes/latest.md)
