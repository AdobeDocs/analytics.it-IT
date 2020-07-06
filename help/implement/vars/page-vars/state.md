---
title: Stato
description: Compila il "Rapporto sullo stato del visitatore" in Reporting e  Analytics.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 1%

---


# state

>[!IMPORTANT]
>
>Questa variabile viene ritirata e non è disponibile in  Analysis Workspace. Utilizzate invece la dimensione &quot;Stati Uniti&quot;, che AppMeasurement raccoglie automaticamente in base alla posizione del visitatore.

Nelle versioni precedenti di Adobe  Analytics, la `state` variabile era utilizzata quando i visitatori compilavano le informazioni di spedizione sui siti di vendita al dettaglio. Funzionalmente identico a un prop, ma non disponibile in  Analysis Workspace.

## Stato  lancio Adobe Experience Platform

Potete impostare lo stato sia durante la configurazione dell&#39;estensione Analytics  (variabili globali), sia in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe  Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL State] sezione.

È possibile impostare state su qualsiasi valore di stringa o elemento dati.

## s.state in AppMeasurement e Launch editor di codice personalizzato

La `s.state` variabile è una stringa che in genere contiene lo stato o la provincia del visitatore. I nomi completi o i codici a due lettere sono entrambi validi. Ha un valore massimo di 50 byte; i valori più lunghi vengono troncati. Il valore predefinito è una stringa vuota.

```js
s.state = "Utah";
```
