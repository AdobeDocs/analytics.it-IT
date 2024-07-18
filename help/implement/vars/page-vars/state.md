---
title: state
description: (Ritirato) Compilava il "Rapporto sullo stato del visitatore", che non è più disponibile.
feature: Variables
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 82%

---

# state

>[!IMPORTANT]
>
>Questa variabile è ritirata e non è una dimensione disponibile in Analysis Workspace. Utilizza invece la dimensione [Stati USA](/help/components/dimensions/us-states.md), che AppMeasurement raccoglie automaticamente in base alla posizione del visitatore.

Nelle versioni precedenti di Adobe Analytics, la variabile `state` veniva utilizzata quando i visitatori compilavano i dati di spedizione sui siti di vendita al dettaglio. È funzionalmente identica a una variablie prop, ma non è disponibile in Analysis Workspace.

## Stato tramite l’estensione Adobe Analytics

Puoi impostare lo stato sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL State].

È possibile impostare lo stato su qualsiasi valore di stringa o elemento dati.

## s.state in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.state` è una stringa che in genere contiene lo stato o la provincia del visitatore. Il nome completo dello stato o il suo codice di due lettere sono entrambi valori validi. Può avere un valore massimo di 50 byte; i valori più lunghi vengono troncati. Il valore predefinito è una stringa vuota.

```js
s.state = "Utah";
```
