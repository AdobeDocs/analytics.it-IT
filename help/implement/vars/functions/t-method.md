---
title: t
description: Invia ad Adobe una chiamata di tracciamento della visualizzazione della pagina.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 15%

---

# t()

La `t()` è un componente di base importante per Adobe Analytics. Prende tutte le variabili Analytics definite nella pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe.

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

Esecuzione del `t()` prende tutte le variabili di Analytics definite e formula un URL basato su tali variabili. Alcune variabili di Analytics determinano l’URL dell’immagine, mentre altre variabili determinano i valori dei parametri della stringa di query.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

Adobe riceve la richiesta di immagine, quindi analizza l’intestazione della richiesta, l’URL e i parametri della stringa di query. I server di raccolta dati restituiscono quindi un’immagine trasparente da 1 pixel x 1, visualizzata in modo invisibile sul sito.

## Invia un evento utilizzando l&#39;estensione SDK per web

Utilizza un’azione per configurare l’invio ad Adobe di dati evento XDM. Il Datastream riceve questi dati, applica eventuali mappature configurate e inoltra tali dati ad Adobe Analytics se si tratta di un servizio aggiunto a tale Datastream.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. Sotto [!UICONTROL Actions], fai clic sull’azione desiderata o sul pulsante **&#39;+&#39;** per aggiungere un’azione.
1. Imposta la [!UICONTROL Extension] elenco a discesa in **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Action Type] a **[!UICONTROL Send event]**.

## Invia l&#39;evento manualmente implementazione dell&#39;SDK per web

Utilizza la `sendEvent` per inviare dati ad Adobe. Il Datastream riceve questi dati, applica eventuali mappature configurate e inoltra tali dati ad Adobe Analytics se si tratta di un servizio aggiunto a tale Datastream.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Vedi [Tracciare gli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) per ulteriori informazioni, consulta la documentazione SDK per web .

## Chiamata di tracciamento della visualizzazione pagina tramite l’estensione Adobe Analytics

L’estensione Adobe Analytics in Adobe Experience Platform Data Collection ha una posizione dedicata impostata come chiamata di tracciamento della visualizzazione della pagina.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. Sotto [!UICONTROL Actions], fai clic sull’azione desiderata o fai clic sul pulsante **&#39;+&#39;** per aggiungere un’azione.
1. Imposta la [!UICONTROL Extension] elenco a discesa in **[!UICONTROL Adobe Analytics]** e [!UICONTROL Action Type] a **[!UICONTROL Send Beacon]**.
1. Fai clic sul pulsante `s.t()` pulsante di scelta.

## s.t() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.t()` quando desideri inviare una chiamata di tracciamento ad Adobe.

```js
s.t();
```

Facoltativamente, è possibile utilizzare un oggetto come argomento per sostituire i valori delle variabili. Vedi [sostituzioni delle variabili](../../js/overrides.md) per ulteriori informazioni.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement utilizzavano diverse righe di codice per chiamare questa funzione. Il codice aggiuntivo sistemato storicamente soluzioni alternative per diversi browser. La standardizzazione e le best practice nei browser moderni non richiedono più questo blocco di codice. Solo la chiamata del metodo `s.t()` È necessario ora.
