---
title: Stato
description: Popolare il "Rapporto sullo stato del visitatore" in Reports and Analytics.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---

# stato

>[!IMPORTANT]
>
>Questa variabile è ritirata e non è una dimensione disponibile in Analysis Workspace. Utilizza invece la dimensione &quot;Stati Uniti&quot;, che AppMeasurement raccoglie automaticamente in base alla posizione del visitatore.

Nelle versioni precedenti di Adobe Analytics, la `state` veniva utilizzata quando i visitatori compilavano le informazioni di spedizione sui siti di vendita al dettaglio. Funzionalmente identico a una proprietà, ma non disponibile in Analysis Workspace.

## Stato utilizzando l’estensione Adobe Analytics

Puoi impostare lo stato sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL State] sezione .

È possibile impostare lo stato su qualsiasi valore di stringa o elemento dati.

## s.state in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.state` è una stringa che in genere contiene lo stato o la provincia del visitatore. I nomi completi dello stato o i codici a due lettere sono entrambi validi. Ha un valore massimo di 50 byte; i valori più lunghi vengono troncati. Il valore predefinito è una stringa vuota.

```js
s.state = "Utah";
```
