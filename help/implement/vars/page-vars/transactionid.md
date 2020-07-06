---
title: transactionID
description: Utilizzate questa variabile per collegare insieme dati online e offline.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 1%

---


# transactionID

La `transactionID` variabile identifica in modo univoco una transazione in modo che l’hit possa collegarsi ai dati caricati tramite Origini dati. Questa variabile è utile nei casi in cui si desidera utilizzare dati provenienti da altri canali e collegarla ai dati raccolti con AppMeasurement.

>[!NOTE]
>
>Prima di usare questa variabile, accertatevi che [!UICONTROL Transaction ID Storage] sia abilitata in una suite di rapporti. Per ulteriori informazioni, consulta Impostazioni [account](/help/admin/admin/general-acct-settings-admin.md) generali nella guida utente per l&#39;amministratore.

Quando si imposta `transactionID` un hit, Adobe crea uno &quot;snapshot&quot; di tutte le variabili Analytics  impostate o persistenti in quel momento. I dati caricati tramite Origini dati con un ID transazione corrispondente sono legati in modo permanente a tali valori variabili.

Per impostazione predefinita, Adobe ricorda tutti i valori ID transazione (collegati e non collegati) per un massimo di 90 giorni. Se il processo di interazione offline supera i 90 giorni, contatta l&#39;Assistenza clienti per richiedere la proroga di questo limite.

## ID transazione in  lancio Adobe Experience Platform

Puoi impostare l&#39;ID transazione sia durante la configurazione dell&#39;estensione Analytics  (variabili globali), sia in base a regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Transaction ID] sezione.

Puoi impostare l&#39;ID transazione su qualsiasi valore di stringa, compresi gli elementi di dati.

## s.transactionID in AppMeasurement e Launch, editor di codice personalizzato

La `s.transactionID` variabile è una stringa contenente un identificatore univoco per una transazione. I valori validi includono caratteri alfanumerici di lunghezza massima di 100 byte. Il valore predefinito è una stringa vuota.

```js
s.transactionID = "ABC123";
```

Se disponi di più ID transazione per un hit, puoi delimitare ciascuno con una virgola. Più ID transazione sono ancora soggetti al limite di 100 byte.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>Se integrate più canali offline utilizzando questa variabile, accertatevi che i diversi canali non si sovrappongano agli ID transazione. Ad esempio, se hai un valore ID transazione call center di `1234` e un valore ID transazione lead di vendita di `1234`, possono creare conflitti e causare risultati imprevisti. Assicurati che gli ID transazione contengano formati univoci per canale offline e distinguili, se necessario. Ad esempio, imposta l&#39;ID transazione call center su `call_1234` `lead_1234` e l&#39;ID transazione lead di vendita sia in Origini dati che in AppMeasurement.
