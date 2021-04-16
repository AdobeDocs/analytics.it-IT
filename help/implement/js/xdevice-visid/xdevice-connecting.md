---
description: L’identificazione tra i visitatori aiuta a collegare i visitatori su più dispositivi. L'identificazione dei visitatori tra i dispositivi utilizza la variabile ID visitatore s.visitorID per associare un utente tra i dispositivi.
keywords: Implementazione di Analytics
subtopic: Visitors
title: Connettere gli utenti tra i dispositivi
topic-fix: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 2%

---

# Connettere gli utenti tra i dispositivi

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Consulta [Analisi multidispositivo](/help/components/cda/overview.md) nella guida utente dei componenti.

L’identificazione tra i visitatori aiuta a collegare i visitatori su più dispositivi. L&#39;identificazione dei visitatori tra dispositivi utilizza la variabile `visitorID` per associare un utente tra dispositivi. La variabile `visitorID` ha la priorità più alta quando identifica i visitatori univoci.

Quando invii un hit con un ID visitatore personalizzato, Adobe verifica la presenza di eventuali profili visitatore con un ID visitatore corrispondente. Se esiste, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.

L’impostazione della variabile `visitorID` viene generalmente impostata dopo l’autenticazione, o dopo che un visitatore esegue altre azioni che consentono di identificarli in modo univoco indipendentemente dal dispositivo utilizzato. Gli identificatori efficaci includono un hash del loro nome utente, indirizzo e-mail o un ID interno che non contiene informazioni personali identificabili.

Dopo che il cliente effettua l’accesso da ciascun dispositivo, tutti sono legati allo stesso profilo utente. Se il visitatore si disconnette in un secondo momento su un dispositivo, continua a appartenere allo stesso profilo visitatore, perché ad Adobe riconosce che il cookie del browser su ciascun dispositivo appartiene allo stesso profilo visitatore. Adobe consiglia di utilizzare la variabile `visitorID` ogni volta che possibile nel caso in cui il cookie del browser venga eliminato.

## Limitazioni

L’utilizzo di ID visitatore personalizzati offre un maggiore controllo sull’identificazione dei visitatori, ma presenta alcune limitazioni.

* **La deduplicazione dei visitatori non è retroattiva**: Se un visitatore accede al sito per la prima volta e quindi si autentica, vengono conteggiati due visitatori unici. Un visitatore univoco conta l&#39;ID di Analytics generico generato automaticamente e un altro conta l&#39;ID visitatore personalizzato al momento dell&#39;accesso. Questa duplicazione di visitatori univoci è presente ogni volta che un visitatore utilizza un nuovo dispositivo o cancella i propri cookie.
* **Incompatibilità con il servizio** Experience Cloud ID: Dall’introduzione dell’identificazione incrociata dei visitatori su più dispositivi, Adobe ha rilasciato modi più potenti e affidabili per tenere traccia dei visitatori su più dispositivi. Questi nuovi metodi di identificazione non sono compatibili con l’override dell’ID visitatore personalizzato. Se prevedi di utilizzare il servizio ID, Cross-Device Analytics (CDA) o Device Co-op, Adobe consiglia vivamente di non utilizzare la variabile `visitorID` .
