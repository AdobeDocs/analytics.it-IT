---
description: L’identificazione dei visitatori cross-device consente di collegare i visitatori tra più dispositivi. L’identificazione dei visitatori cross-device utilizza la variabile ID visitatore, s.visitorID, per associare un utente a più dispositivi.
keywords: Implementazione di Analytics
subtopic: Visitors
title: Connettere gli utenti tra i dispositivi
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Connettere gli utenti tra i dispositivi

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra i dispositivi non è più consigliato. Consulta [Analytics tra dispositivi](/help/components/cda/overview.md) nella guida utente Componenti.

L’identificazione dei visitatori cross-device consente di collegare i visitatori tra più dispositivi. L’identificazione dei visitatori cross-device utilizza `visitorID` per associare un utente tra i dispositivi. Il `visitorID` La variabile ha la priorità più alta quando si identificano i visitatori univoci.

Quando invii un hit con un ID visitatore personalizzato, Adobe controlla tutti i profili di visitatori che hanno un ID visitatore corrispondente. Se ne esiste uno, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.

Impostazione di `visitorID` La variabile viene generalmente impostata dopo l’autenticazione o dopo che un visitatore esegue un’altra azione che ti consente di identificarle in modo univoco indipendentemente dal dispositivo utilizzato. Gli identificatori effettivi includono un hash del loro nome utente, indirizzo e-mail o un ID interno che non contiene informazioni personali identificabili.

Una volta effettuato l’accesso da ogni dispositivo, il cliente è legato allo stesso profilo utente. Se il visitatore successivamente si disconnette da un dispositivo, continua a appartenere allo stesso profilo visitatore perché Adobe riconosce che il cookie del browser su ciascun dispositivo appartiene allo stesso profilo visitatore. L’Adobe consiglia di utilizzare `visitorID` variabile, se possibile, nel caso in cui il cookie del browser venga eliminato.

## Limitazioni

L’utilizzo degli ID visitatore personalizzati offre un maggiore controllo sull’identificazione dei visitatori, ma presenta anche limitazioni.

* **La deduplicazione dei visitatori non è retroattiva**: se un visitatore accede al sito per la prima volta e poi si autentica, vengono conteggiati due visitatori univoci. Un visitatore univoco conta l’ID Analytics generico generato automaticamente, mentre un altro conta l’ID visitatore personalizzato al momento dell’accesso. Questa duplicazione di visitatori univoci è presente ogni volta che un visitatore utilizza un nuovo dispositivo o cancella i suoi cookie.
* **Incompatibilità con il servizio ID Experience Cloud**: dall’introduzione dell’identificazione dei visitatori cross-device, Adobe ha rilasciato modi più potenti e affidabili per monitorare i visitatori tra i dispositivi. Questi nuovi metodi di identificazione non sono compatibili con la sostituzione dell’ID visitatore personalizzato. Se prevedi di utilizzare il servizio ID o Cross-Device Analytics (CDA), l’Adobe consiglia vivamente di non utilizzare `visitorID` variabile.
