---
title: zip
description: Compilare manualmente la dimensione "Codice postale" se le impostazioni della suite di rapporti lo consentono.
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# zip

La `zip` consente di compilare manualmente la dimensione &quot;Codice postale&quot; se la variabile [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti lo consentono. Nelle versioni precedenti di Adobe Analytics, questa variabile poteva essere impostata solo manualmente, in genere quando si immettevano informazioni di spedizione su un sito di vendita al dettaglio. I miglioramenti apportati ad Adobe Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Assicurati che [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti è impostato sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL geo zip] viene sempre utilizzato. Vedi [Impostazioni account generali](/help/admin/admin/general-acct-settings-admin.md) nella guida utente di Admin per ulteriori informazioni.

## ZIP utilizzando i tag in Adobe Experience Platform

Puoi impostare Zip Code sia durante la configurazione dell’estensione Analytics (variabili globali) sia in regole.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Zip] sezione .

Puoi impostare Zip Code su qualsiasi valore di stringa, inclusi gli elementi dati.

## s.zip in AppMeasurement e nell’editor di codice personalizzato

La `s.zip` variabile è una stringa che in genere contiene un codice postale, ma può contenere qualsiasi valore desiderato per una lunghezza massima di 50 byte.

```js
s.zip = "84043";
```
