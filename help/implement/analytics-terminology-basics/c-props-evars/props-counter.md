---
description: Un contatore memorizza (e talvolta visualizza) il numero di volte in cui si è verificato un evento o un processo specifico.
keywords: Implementazione di Analytics; prop; s. prop; traffico personalizzato; contatori
seo-description: Un contatore memorizza (e talvolta visualizza) il numero di volte in cui si è verificato un evento o un processo specifico.
seo-title: Utilizzo di prop come contatori
solution: Analytics
title: Utilizzo di prop come contatori
topic: Sviluppatore e implementazione
uuid: ab 83 bd 7 e -10 d 9-49 f 9-b 9 e 7-c 50397 e 95 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizzo di prop come contatori

Un contatore memorizza (e talvolta visualizza) il numero di volte in cui si è verificato un evento o un processo specifico.

Potete utilizzare un prop per calcolare quante volte si verifica un evento. Ad esempio, potete tenere traccia dell'utilizzo di Real Player vs. Windows Media Player sul sito. Each page contains [!UICONTROL Code to Paste], in which you can see [!UICONTROL s.prop] variables. Use [!UICONTROL s.prop] 1 to track the players. For page A, enter a value in [!UICONTROL s.prop]1 to represent Real Player.

```js
s.prop1="RealPlayer"
```

For page B, enter a similar value in [!UICONTROL s.prop]1 for Windows Media Player, as shown below.

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

As visitors come to your site and visit the pages containing the Real Player or Windows Media Player, [!DNL Analytics] is able to segment the users based on which pages they visited. [!UICONTROL Custom Traffic] Il rapporto mostra quindi il numero di visite a ogni pagina.

>[!NOTE]
>
>The name of the [!UICONTROL Custom Traffic] report can be customized. For example, the [!UICONTROL Custom Traffic] report can be renamed to "Player Types Report."

