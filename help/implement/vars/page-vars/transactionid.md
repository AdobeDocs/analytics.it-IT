---
title: transactionID
description: Utilizza questa variabile per collegare dati online e offline.
feature: Appmeasurement Implementation
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 13%

---

# transactionID

La variabile `transactionID` identifica in modo univoco una transazione in modo che l&#39;hit possa fornire valori di dimensione ai dati caricati tramite [Origini dati ID transazione](/help/import/data-sources/transactionid.md). Questa variabile è utile nei casi in cui desideri compilare i dati del canale offline con i valori raccolti dai dati del canale online.

>[!NOTE]
>
>Prima di utilizzare questa variabile, assicurati che [!UICONTROL Transaction ID Storage] sia abilitato in una suite di rapporti. Per ulteriori informazioni, consulta [Impostazioni account generali](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) nella guida utente dell&#39;amministratore.

Quando imposti `transactionID` su un hit, Adobe crea un&#39;istantanea di tutte le variabili Analytics impostate o mantenute in quel momento. Per l&#39;elenco delle dimensioni incluse nello snapshot, vedere [Origini dati ID transazione](/help/import/data-sources/transactionid.md). Adobe ricorda tutti i valori ID transazione (collegati e non collegati) per un massimo di 25 mesi.

## ID transazione tramite Web SDK

L’ID transazione è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.payments[3].transactionID` o `xdm.commerce.order.payments.transactionID`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.transactionID` o `data.__adobe.analytics.xact`

## ID transazione tramite l’estensione Adobe Analytics

Puoi impostare l’ID transazione sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Transaction ID].

Puoi impostare l’ID transazione su qualsiasi valore stringa, inclusi gli elementi dati.

## s.transactionID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.transactionID` è una stringa contenente un identificatore univoco per una transazione. I valori validi includono caratteri alfanumerici fino a 100 byte. Il valore predefinito è una stringa vuota.

```js
s.transactionID = "ABC123";
```

Se disponi di più ID transazione per un hit, puoi delimitarli con una virgola. Gli ID di più transazioni sono ancora soggetti al limite di 100 byte.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!TIP]
>
>Se integri più canali offline utilizzando questa variabile, assicurati che i diversi canali non si sovrappongano agli ID transazione. Ad esempio, se si dispone di un ID transazione call center di `1234` e di un ID transazione lead di vendita di `1234`, è possibile che si verifichino conflitti e si verifichino risultati imprevisti. Assicurati che gli ID transazione contengano formati univoci per canale offline e, se necessario, differenziali. Ad esempio, imposta l&#39;ID transazione del call center su `call_1234` e l&#39;ID transazione del lead di vendita `lead_1234` sia in Origini dati che in AppMeasurement.
