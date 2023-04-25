---
title: transactionID
description: Utilizza questa variabile per collegare insieme dati online e offline.
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 14%

---

# transactionID

La `transactionID` identifica in modo univoco una transazione in modo che l&#39;hit possa collegarsi ai dati caricati tramite Origini dati. Questa variabile è utile nei casi in cui desideri utilizzare dati provenienti da altri canali e collegarla ai dati raccolti con AppMeasurement.

>[!NOTE]
>
>Assicurati che [!UICONTROL Transaction ID Storage] è abilitata in una suite di rapporti prima di utilizzare questa variabile. Vedi [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) nella guida utente di Admin per ulteriori informazioni.

Quando si imposta `transactionID` in un hit, Adobe prende uno &quot;snapshot&quot; di tutte le variabili Analytics impostate o persistite in quel momento. I dati caricati tramite Origini dati con un ID transazione corrispondente sono legati in modo permanente a tali valori variabili.

Per impostazione predefinita, Adobe ricorda tutti i valori ID transazione (collegati e non collegati) per un massimo di 90 giorni. Se il processo di interazione offline supera i 90 giorni, contatta l’Assistenza clienti per estendere questo limite.

## ID transazione tramite SDK web

ID transazione: [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `commerce.order.transactionID`.

## ID transazione utilizzando l’estensione Adobe Analytics

Puoi impostare l’ID transazione sia durante la configurazione dell’estensione Analytics (variabili globali) sia in base alle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta la [!UICONTROL Extension] elenco a discesa in Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Transaction ID].

Puoi impostare l’ID transazione su qualsiasi valore stringa, inclusi gli elementi dati.

## s.transactionID in AppMeasurement e nell’editor di codici personalizzati dell’estensione Analytics

La `s.transactionID` è una stringa contenente un identificatore univoco per una transazione. I valori validi includono caratteri alfanumerici di lunghezza massima di 100 byte. Il valore predefinito è una stringa vuota.

```js
s.transactionID = "ABC123";
```

Se disponi di più ID transazione per un risultato, puoi delimitare ciascuno con una virgola. Più ID transazione sono ancora soggetti al limite di 100 byte.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>Se integri più canali offline utilizzando questa variabile, assicurati che i diversi canali non si sovrappongano agli ID transazione. Ad esempio, se disponi di un valore ID transazione call center di `1234` e un valore ID transazione lead di vendita di `1234`, possono creare conflitti e causare risultati imprevisti. Assicurati che gli ID transazione contengano formati univoci per canale offline e differenziali se necessario. Ad esempio, imposta l’ID transazione del call center su `call_1234` e il tuo ID transazione lead di vendita `lead_1234` sia in Origini dati che in AppMeasurement.
