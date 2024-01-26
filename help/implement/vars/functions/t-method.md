---
title: t
description: Invia ad Adobe una chiamata di tracciamento per la visualizzazione della pagina.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 14%

---

# t()

Il `t()` Il metodo è un componente core importante per Adobe Analytics. Prende tutte le variabili di Analytics definite sulla pagina, le compila in una richiesta di immagine e invia tali dati ai server di raccolta dati di Adobe.

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

Esecuzione di `t()` Il metodo accetta tutte le variabili di Analytics definite e formula un URL basato su tali variabili. Alcune variabili di Analytics determinano l’URL dell’immagine, mentre altre variabili determinano i valori dei parametri della stringa di query.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

L’Adobe riceve la richiesta di immagine, quindi analizza l’intestazione della richiesta, l’URL e i parametri della stringa di query. I server di raccolta dati restituiscono quindi un’immagine trasparente 1x1 pixel, visualizzata in modo invisibile sul sito.

## Inviare eventi tramite l’estensione Web SDK

Utilizza un’azione per configurare l’invio di dati evento XDM all’Adobe. Lo stream di dati riceve tali dati, applica eventuali mappature configurate e inoltra tali dati ad Adobe Analytics, se si tratta di un servizio aggiunto a tale stream di dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. Sotto [!UICONTROL Actions], fai clic sull’Azione desiderata o fai clic su **&#39;+&#39;** per aggiungere un&#39;azione.
1. Imposta il [!UICONTROL Extension] elenco a discesa per **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Action Type] a **[!UICONTROL Send event]**.

## Inviare eventi manualmente implementando Web SDK

Utilizza il `sendEvent` comando per inviare dati ad Adobe. Lo stream di dati riceve tali dati, applica eventuali mappature configurate e inoltra tali dati ad Adobe Analytics, se si tratta di un servizio aggiunto a tale stream di dati.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Consulta [Tracciare gli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Chiamata di tracciamento per la visualizzazione pagina tramite l’estensione Adobe Analytics

L’estensione Adobe Analytics in Adobe Experience Platform Data Collection dispone di una posizione dedicata per impostare una chiamata di tracciamento per la visualizzazione della pagina.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
1. Sotto [!UICONTROL Actions], fai clic sull’azione desiderata o fai clic su **&#39;+&#39;** per aggiungere un&#39;azione.
1. Imposta il [!UICONTROL Extension] elenco a discesa per **[!UICONTROL Adobe Analytics]** e [!UICONTROL Action Type] a **[!UICONTROL Send Beacon]**.
1. Fai clic su `s.t()` pulsante di opzione.

## Metodo s.t() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.t()` quando desideri inviare una chiamata di tracciamento ad Adobe.

```js
s.t();
```

Facoltativamente, è possibile utilizzare un oggetto come argomento per sostituire i valori delle variabili. Consulta [sostituzioni variabili](../../js/overrides.md) per ulteriori informazioni.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement utilizzavano diverse righe di codice per chiamare questa funzione. Il codice aggiuntivo storicamente adattato soluzioni alternative per diversi browser. La standardizzazione e le best practice nei browser moderni non richiedono più questo blocco di codice. Solo la chiamata al metodo `s.t()` è necessario ora.
