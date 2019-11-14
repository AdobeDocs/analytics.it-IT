---
description: Gli eventi personalizzati consentono di definire il tipo di successo da monitorare.
keywords: Analytics Implementation;custom event
solution: Analytics
title: L'evento personalizzato
topic: Developer and implementation
uuid: 8e78ba04-9b4c-4566-980c-c24dd9d82236
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# L'evento personalizzato

Gli eventi personalizzati consentono di definire il tipo di successo da monitorare.

Anche se simili agli [!UICONTROL predefined] eventi, [!UICONTROL custom] gli eventi consentono di definire la metrica di successo. Ad esempio, se disponete di una newsletter, l’evento di successo potrebbe essere _Registrazione_. Chiaramente, _Registrazione_ non fa parte degli [!UICONTROL predefined] eventi. Utilizzando un [!UICONTROL custom] evento, potete tenere traccia del numero di visitatori che si sono registrati per la newsletter. [!UICONTROL Custom] gli eventi seguono la sintassi standard mostrata di seguito.

```js
s.events="event3"
```

Il codice riportato sopra mostra come assegnare un evento alla variabile _eventi_ . Se non modificate il nome dell'evento nell'interfaccia, _event3_ viene visualizzato nell'interfaccia.

Per impostazione predefinita, gli eventi di successo sono configurati come eventi _contatore_ . Gli eventi contatore contano il numero di volte in cui un evento di successo è impostato. Alcuni usi di eventi di successo richiedono che un evento venga incrementato di un importo personalizzato. Questi eventi possono essere impostati come eventi _numerici_ o eventi di _valuta_ . Puoi cambiare il tipo di evento in Admin Console.
