---
title: zip
description: Compilare manualmente la dimensione "Codice postale" se le impostazioni della suite di rapporti lo consentono.
exl-id: 1acf4bf7-3788-46bd-bcdb-9885c7b93b59
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# zip

La variabile `zip` ti consente di compilare manualmente la dimensione &quot;Codice postale&quot; se lo consente [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti. Nelle versioni precedenti di Adobe Analytics, questa variabile poteva essere impostata solo manualmente, in genere quando si immettevano informazioni di spedizione su un sito di vendita al dettaglio. I miglioramenti apportati ad Adobe Analytics consentono di impostare automaticamente questa variabile utilizzando i dati di geolocalizzazione. Questa variabile non persiste oltre l’hit impostato.

>[!IMPORTANT]
>
>Assicurati che le [!UICONTROL Zip Option] nelle impostazioni della suite di rapporti siano impostate sul valore desiderato. Non è possibile utilizzare questa variabile se [!UICONTROL geo zip] viene sempre utilizzato. Per ulteriori informazioni, consulta [Impostazioni generali dell’account](/help/admin/admin/general-acct-settings-admin.md) nella guida utente Admin .

## ZIP utilizzando i tag in Adobe Experience Platform

Puoi impostare Zip Code sia durante la configurazione dell’estensione Analytics (variabili globali) sia in regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Zip] .

Puoi impostare Zip Code su qualsiasi valore di stringa, inclusi gli elementi dati.

## s.zip in AppMeasurement e nell’editor di codice personalizzato

La variabile `s.zip` è una stringa che in genere contiene un codice postale, ma può contenere qualsiasi valore desiderato fino a 50 byte di lunghezza.

```js
s.zip = "84043";
```
