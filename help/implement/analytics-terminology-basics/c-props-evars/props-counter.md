---
description: Un contatore memorizza (e talvolta visualizza) il numero di volte in cui si è verificato un particolare evento o processo.
keywords: Analytics Implementation;props;s.prop;custom traffic;counters
title: Utilizzo di prop come contatori
topic: Developer and implementation
uuid: ab83bd7e-10d9-49f9-b9e7-c50397e95c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Utilizzo di prop come contatori

Un contatore memorizza (e talvolta visualizza) il numero di volte in cui si è verificato un particolare evento o processo.

È possibile utilizzare un prop per calcolare il numero di volte in cui si verifica un evento. Ad esempio, è necessario monitorare l'utilizzo di Real Player rispetto a Windows Media Player sul sito. Ogni pagina contiene [!UICONTROL Code to Paste], in cui è possibile vedere [!UICONTROL s.prop] le variabili. Utilizzare [!UICONTROL s.prop] 1 per tenere traccia dei giocatori. Per la pagina A, immettete un valore in [!UICONTROL s.prop]1 per rappresentare Real Player.

```js
s.prop1="RealPlayer"
```

A pagina B, immettete un valore simile in [!UICONTROL s.prop]1 per Windows Media Player, come illustrato di seguito.

```js
s.prop1="WindowsMP"
```

> [!NOTE] Adobe offre fino a 75 [!UICONTROL s.prop] variabili da usare.

Man mano che i visitatori accedono al tuo sito e visitano le pagine che contengono Real Player o Windows Media Player, [!DNL Analytics] è possibile segmentare gli utenti in base alle pagine visitate. Il [!UICONTROL Custom Traffic] rapporto mostra quindi il numero di visite a ogni pagina.

> [!NOTE] È possibile personalizzare il nome del [!UICONTROL Custom Traffic] rapporto. Ad esempio, il [!UICONTROL Custom Traffic] rapporto può essere rinominato in "Player Types Report".

