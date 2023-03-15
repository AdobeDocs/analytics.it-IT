---
title: linkLeaveQueryString
description: Consente di mantenere le stringhe di query nelle dimensioni di tracciamento dei collegamenti.
feature: Variables
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 10%

---

# linkLeaveQueryString

Per impostazione predefinita, AppMeasurement elimina le stringhe di query dagli URL di tracciamento dei collegamenti. Utilizza il `linkLeaveQueryString` variabile per mantenere le stringhe di query nelle dimensioni di tracciamento dei collegamenti.

Per alcuni collegamenti di uscita e di download, la parte importante dell’URL può trovarsi nella stringa di query. Ad esempio, un collegamento per il download come `https://example.com/download.asp?filename=myfile.exe` contiene informazioni importanti sul collegamento nella stringa query.

Se le informazioni di tracciamento dei collegamenti non sono presenti negli URL del sito, l’utilizzo di questa variabile non è necessario. La rimozione di stringhe di query dagli URL di tracciamento dei collegamenti consente di limitare il numero di valori univoci contenuti nella dimensione.

Abilitazione `linkLeaveQueryString` si applica a tutte le dimensioni di tracciamento dei collegamenti (inclusi collegamenti personalizzati, di uscita e di download).

>[!TIP]
>
>Questa variabile non influisce sulle dimensioni che non rientrano nel tracciamento dei collegamenti. Ha effetto solo sui collegamenti personalizzati, sui collegamenti di uscita e sui collegamenti di download.

## Gestire le stringhe di query di collegamento tramite Web SDK

Le stringhe di query non vengono rimosse dal campo XDM `web.webInteraction.URL`. Se desideri rimuovere le stringhe di query da questo campo XDM, puoi modificarlo utilizzando `onBeforeEventSend`.

## Mantieni i parametri URL tramite l’estensione Adobe Analytics

[!UICONTROL Keep URL Parameters] è una casella di controllo sotto [!UICONTROL Link Tracking] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
4. Espandi [!UICONTROL Link Tracking] Pannello a soffietto, che mostra [!UICONTROL Keep URL Parameters] casella di controllo.

Seleziona questa casella se desideri includere le stringhe di query nelle dimensioni di tracciamento dei collegamenti.

## s.linkLeaveQueryString in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkLeaveQueryString` è di tipo booleano. Il valore predefinito è `false`.

* Se questa variabile è impostata su `true`, le stringhe di query vengono mantenute negli URL di tracciamento dei collegamenti.
* Se questa variabile è impostata su `false` o non definito, le stringhe di query vengono rimosse dagli URL di tracciamento dei collegamenti.

```js
s.linkLeaveQueryString = true;
```

## Esempio

Fai attenzione quando imposti questa variabile su true, in quanto può influire sui filtri di tracciamento dei collegamenti come [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md), e [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Considera l’esempio seguente come se fosse attivo `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
