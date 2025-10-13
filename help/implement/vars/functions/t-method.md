---
title: t
description: Invia ad Adobe una chiamata di tracciamento per la visualizzazione della pagina.
feature: Appmeasurement Implementation
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 14%

---

# t()

Il metodo `t()` è un importante componente di base di Adobe Analytics. Prende tutte le variabili Analytics definite sulla pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe.

Ad esempio, considera il seguente codice JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

L&#39;esecuzione del metodo `t()` accetta tutte le variabili di Analytics definite e formula un URL basato su tali variabili. Alcune variabili di Analytics determinano l’URL dell’immagine, mentre altre variabili determinano i valori dei parametri della stringa di query.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

Adobe riceve la richiesta di immagine, quindi analizza l’intestazione della richiesta, l’URL e i parametri della stringa di query. I server di raccolta dati restituiscono quindi un’immagine trasparente 1x1 pixel, visualizzata in modo invisibile sul sito.

## Inviare un evento tramite l’estensione Web SDK

Utilizza un’azione per configurare l’invio di dati evento XDM ad Adobe. Lo stream di dati riceve tali dati, applica eventuali mappature configurate e inoltra tali dati ad Adobe Analytics, se si tratta di un servizio aggiunto a tale stream di dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. In [!UICONTROL Actions], fare clic sull&#39;azione desiderata o sull&#39;icona **&#39;+&#39;** per aggiungere un&#39;azione.
1. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Action Type] su **[!UICONTROL Send event]**.

## Inviare un evento manualmente implementando il Web SDK

Utilizza il comando `sendEvent` per inviare dati ad Adobe. Lo stream di dati riceve tali dati, applica eventuali mappature configurate e inoltra tali dati ad Adobe Analytics, se si tratta di un servizio aggiunto a tale stream di dati.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Per ulteriori informazioni, vedere [`sendEvent`](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/sendevent/overview) nella documentazione di Web SDK.

## Chiamata di tracciamento per la visualizzazione pagina tramite l’estensione Adobe Analytics

L’estensione Adobe Analytics in Adobe Experience Platform Data Collection dispone di una posizione dedicata per impostare una chiamata di tracciamento per la visualizzazione della pagina.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. In [!UICONTROL Actions], fare clic sull&#39;azione desiderata o sull&#39;icona **&#39;+&#39;** per aggiungere un&#39;azione.
1. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su **[!UICONTROL Adobe Analytics]** e [!UICONTROL Action Type] su **[!UICONTROL Send Beacon]**.
1. Fare clic sul pulsante di opzione `s.t()`.

## Metodo s.t() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare il metodo `s.t()` quando si desidera inviare una chiamata di tracciamento ad Adobe.

```js
s.t();
```

Facoltativamente, è possibile utilizzare un oggetto come argomento per sostituire i valori delle variabili. Per ulteriori informazioni, vedere [sostituzioni variabili](../../js/overrides.md).

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement utilizzavano diverse righe di codice per chiamare questa funzione. Il codice aggiuntivo storicamente adattato soluzioni alternative per diversi browser. La standardizzazione e le best practice nei browser moderni non richiedono più questo blocco di codice. Al momento è necessaria solo la chiamata al metodo `s.t()`.
