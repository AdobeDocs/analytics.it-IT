---
title: zip
description: Compilare manualmente la dimensione "Codice postale" se le impostazioni della suite di rapporti lo consentono.
feature: Variables
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 24%

---

# zip

La `zip` consente di compilare manualmente la dimensione &quot;Codice postale&quot; se la variabile [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti lo consentono. Nelle versioni precedenti di Adobe Analytics, questa variabile poteva essere impostata solo manualmente, in genere quando si immettevano informazioni di spedizione su un sito di vendita al dettaglio. I miglioramenti apportati ad Adobe Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Assicurati che [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti è impostato sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL geo zip] viene sempre utilizzato. Vedi [Impostazioni account generali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) nella guida utente di Admin per ulteriori informazioni.

## ZIP utilizzando l’estensione Adobe Analytics

Puoi impostare Zip Code sia durante la configurazione dell’estensione Analytics (variabili globali) sia sotto regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Zip].

Puoi impostare Zip Code su qualsiasi valore di stringa, inclusi gli elementi dati.

## s.zip in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La `s.zip` variabile è una stringa che in genere contiene un codice postale, ma può contenere qualsiasi valore desiderato per una lunghezza massima di 50 byte.

```js
s.zip = "84043";
```
