---
title: transactionID
description: Utilizza questa variabile per collegare dati online e offline.
feature: Variables
exl-id: 525e90d8-99a7-4f4f-9bce-1395bf72fd8f
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 17%

---

# transactionID

Il `transactionID` la variabile identifica in modo univoco una transazione in modo che l’hit possa legarsi ai dati caricati tramite Origini dati. Questa variabile è utile nei casi in cui desideri utilizzare dati provenienti da altri canali e collegarla ai dati raccolti con AppMeasurement.

>[!NOTE]
>
>Assicurati che [!UICONTROL Transaction ID Storage] è abilitato in una suite di rapporti prima di utilizzare questa variabile. Consulta [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) per ulteriori informazioni, consulta la guida utente dell’amministratore.

Quando si imposta `transactionID` in un hit, Adobe crea un’istantanea di tutte le variabili di Analytics impostate o mantenute in quel momento. I dati caricati tramite Origini dati con un ID transazione corrispondente sono legati in modo permanente a tali valori di variabile.

Per impostazione predefinita, Adobe ricorda tutti i valori ID transazione (collegati e non collegati) per un massimo di 90 . Se il processo di interazione offline dura più di 90 giorni, contatta l’Assistenza clienti per richiedere l’estensione di questo limite.

## ID transazione tramite Web SDK

L’ID transazione è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `commerce.order.transactionID`.

## ID transazione tramite l’estensione Adobe Analytics

Puoi impostare l’ID transazione sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Transaction ID].

Puoi impostare l’ID transazione su qualsiasi valore stringa, inclusi gli elementi dati.

## s.transactionID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.transactionID` variabile è una stringa contenente un identificatore univoco per una transazione. I valori validi includono caratteri alfanumerici fino a 100 byte. Il valore predefinito è una stringa vuota.

```js
s.transactionID = "ABC123";
```

Se disponi di più ID transazione per un hit, puoi delimitarli con una virgola. Gli ID di più transazioni sono ancora soggetti al limite di 100 byte.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>Se integri più canali offline utilizzando questa variabile, assicurati che i diversi canali non si sovrappongano agli ID transazione. Ad esempio, se il valore ID transazione del call center è `1234` e un valore ID transazione cliente potenziale di `1234`, possono creare conflitti e causare risultati imprevisti. Assicurati che gli ID transazione contengano formati univoci per canale offline e, se necessario, differenziali. Ad esempio, imposta l’ID transazione del call center su `call_1234` e l&#39;ID transazione del lead di vendita `lead_1234` in Origini dati e AppMeasurement.
