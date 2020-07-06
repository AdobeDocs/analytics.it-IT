---
title: zip
description: Compilare manualmente la dimensione "Codice ZIP" se le impostazioni della suite di rapporti lo consentono.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 1%

---


# zip

La `zip` variabile consente di compilare manualmente la dimensione &quot;Codice ZIP&quot; se è consentita dalle impostazioni [!UICONTROL Zip Option] della suite di rapporti. Nelle versioni precedenti di Adobe  Analytics, questa variabile poteva essere impostata solo manualmente, in genere quando si immettevano informazioni sulla spedizione in un sito Web dedicato alla vendita. I miglioramenti ad Adobe  Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Accertatevi che le impostazioni della suite di rapporti [!UICONTROL Zip Option] in siano impostate sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL geo zip] viene sempre utilizzata. Per ulteriori informazioni, consulta Impostazioni [account](/help/admin/admin/general-acct-settings-admin.md) generali nella guida utente per l&#39;amministratore.

## ZIP in  lancio Adobe Experience Platform

È possibile impostare lo Zip Code sia durante la configurazione dell&#39;estensione  Analytics (variabili globali) sia in base a regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Zip] sezione.

È possibile impostare CAP su qualsiasi valore di stringa, compresi gli elementi di dati.

## s.zip nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.zip` variabile è una stringa che in genere contiene un CAP, ma può contenere qualsiasi valore desiderato fino a 50 byte di lunghezza.

```js
s.zip = "84043";
```
