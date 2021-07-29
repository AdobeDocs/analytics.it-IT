---
title: Stato
description: Popolare il "Rapporto sullo stato del visitatore" in Reports and Analytics.
exl-id: a6e3f30b-b5d1-48f8-8961-8e9c6d4d29da
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# stato

>[!IMPORTANT]
>
>Questa variabile è ritirata e non è una dimensione disponibile in Analysis Workspace. Utilizza invece la dimensione &quot;Stati Uniti&quot;, che AppMeasurement raccoglie automaticamente in base alla posizione del visitatore.

Nelle versioni precedenti di Adobe Analytics, la variabile `state` veniva utilizzata quando i visitatori compilavano le informazioni di spedizione sui siti di vendita al dettaglio. Funzionalmente identico a una proprietà, ma non disponibile in Analysis Workspace.

## Utilizzo dei tag in Adobe Experience Platform

Puoi impostare lo stato sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic su un&#39;azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull&#39;icona &quot;+&quot;.
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL State] .

È possibile impostare lo stato su qualsiasi valore di stringa o elemento dati.

## s.state in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.state` è una stringa che in genere contiene lo stato o la provincia del visitatore. I nomi completi dello stato o i codici a due lettere sono entrambi validi. Ha un valore massimo di 50 byte; i valori più lunghi vengono troncati. Il valore predefinito è una stringa vuota.

```js
s.state = "Utah";
```
