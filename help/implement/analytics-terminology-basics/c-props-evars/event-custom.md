---
description: Gli eventi personalizzati consentono di definire il tipo di successo da monitorare.
keywords: Implementazione di Analytics; Evento personalizzato
seo-description: Gli eventi personalizzati consentono di definire il tipo di successo da monitorare.
seo-title: Che cos'è un evento personalizzato?
solution: Analytics
title: Che cos'è un evento personalizzato?
topic: Sviluppatore e implementazione
uuid: 8 e 78 ba 04-9 b 4 c -4566-980 c-c 24 dd 9 d 82236
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# Che cos'è un evento personalizzato?

Gli eventi personalizzati consentono di definire il tipo di successo da monitorare.

Although similar to [!UICONTROL predefined] events, [!UICONTROL custom] events let you define your own success metric. For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. By using a [!UICONTROL custom] event, you can track the number of visitors who register for your newsletter. [!UICONTROL Custom] seguono la sintassi standard mostrata di seguito.

```js
s.events="event3"
```

The code above shows how to assign an event to the _events_ variable. If you do not modify the event name in the interface, _event3_ would display in the interface.

By default, success events are configured as _counter_ events. Gli eventi contatore conteggio quante volte viene impostato un evento di successo. Alcuni eventi di successo richiedono l'aumento di un evento da parte di un importo personalizzato. These events can be set either as _numeric_ events or _currency_ events. Puoi modificare il tipo di evento in Admin Console.
