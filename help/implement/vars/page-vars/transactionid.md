---
title: transactionID
description: Utilizza questa variabile per collegare insieme dati online e offline.
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 0%

---

# transactionID

La variabile `transactionID` identifica in modo univoco una transazione in modo che l&#39;hit possa collegarsi ai dati caricati tramite Origini dati. Questa variabile è utile nei casi in cui desideri utilizzare dati provenienti da altri canali e collegarla ai dati raccolti con AppMeasurement.

>[!NOTE]
>
>Assicurati che [!UICONTROL Transaction ID Storage] sia abilitato in una suite di rapporti prima di utilizzare questa variabile. Per ulteriori informazioni, consulta [Impostazioni generali dell’account](/help/admin/admin/general-acct-settings-admin.md) nella guida utente Admin .

Quando si imposta `transactionID` su un hit, Adobe acquisisce uno &quot;snapshot&quot; di tutte le variabili Analytics impostate o persistenti in quel momento. I dati caricati tramite Origini dati con un ID transazione corrispondente sono legati in modo permanente a tali valori variabili.

Per impostazione predefinita, Adobe ricorda tutti i valori ID transazione (collegati e non collegati) per un massimo di 90 giorni. Se il processo di interazione offline supera i 90 giorni, contatta l’Assistenza clienti per estendere questo limite.

## ID transazione tramite tag in Adobe Experience Platform

Puoi impostare l’ID transazione sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base alle regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Transaction ID] .

Puoi impostare l’ID transazione su qualsiasi valore stringa, inclusi gli elementi dati.

## s.transactionID in AppMeasurement e nell’editor di codice personalizzato

La variabile `s.transactionID` è una stringa contenente un identificatore univoco per una transazione. I valori validi includono caratteri alfanumerici di lunghezza massima di 100 byte. Il valore predefinito è una stringa vuota.

```js
s.transactionID = "ABC123";
```

Se disponi di più ID transazione per un risultato, puoi delimitare ciascuno con una virgola. Più ID transazione sono ancora soggetti al limite di 100 byte.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>Se integri più canali offline utilizzando questa variabile, assicurati che i diversi canali non si sovrappongano agli ID transazione. Ad esempio, se disponi di un valore ID transazione del call center `1234` e di un valore ID transazione lead di vendita `1234`, possono creare conflitti e causare risultati imprevisti. Assicurati che gli ID transazione contengano formati univoci per canale offline e differenziali se necessario. Ad esempio, imposta l&#39;ID transazione del call center su `call_1234` e l&#39;ID transazione lead di vendita `lead_1234` sia in Origini dati che in AppMeasurement.
