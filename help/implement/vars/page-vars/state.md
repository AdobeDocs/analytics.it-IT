---
title: state
description: Popolare il “Rapporto sullo stato del visitatore” in Reports and Analytics.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 100%

---

# state

>[!IMPORTANT]
>
>Questa variabile è ritirata e non è una dimensione disponibile in Analysis Workspace. Al suo posto, utilizza invece la dimensione “Stati USA”, che AppMeasurement raccoglie automaticamente in base alla posizione del visitatore.

Nelle versioni precedenti di Adobe Analytics, la variabile `state` veniva utilizzata quando i visitatori compilavano i dati di spedizione sui siti di vendita al dettaglio. È funzionalmente identica a una variablie prop, ma non è disponibile in Analysis Workspace.

## Stato tramite l’estensione Adobe Analytics

Puoi impostare lo stato sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL State].

È possibile impostare lo stato su qualsiasi valore di stringa o elemento dati.

## s.state in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.state` è una stringa che in genere contiene lo stato o la provincia del visitatore. Il nome completo dello stato o il suo codice di due lettere sono entrambi valori validi. Può avere un valore massimo di 50 byte; i valori più lunghi vengono troncati. Il valore predefinito è una stringa vuota.

```js
s.state = "Utah";
```
