---
description: L’identificazione dei visitatori tra dispositivi consente di collegare i visitatori tra più dispositivi. L’identificazione dei visitatori su più dispositivi utilizza la variabile ID visitatore, s.visitorID, per associare un utente a più dispositivi.
keywords: Analytics Implementation
subtopic: Visitors
title: Connettere gli utenti tra i dispositivi
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 2%

---


# Connettere gli utenti tra i dispositivi

>[!IMPORTANT]
>
>Questo metodo di identificazione dei visitatori tra dispositivi non è più consigliato. Consultate [Analisi cross-device](/help/components/cda/overview.md) nella guida utente dei componenti.

L’identificazione dei visitatori tra dispositivi consente di collegare i visitatori tra più dispositivi. L&#39;identificazione dei visitatori su più dispositivi utilizza la variabile `visitorID` per associare un utente a più dispositivi. La variabile `visitorID` assume la massima priorità nell&#39;identificare i visitatori univoci.

Quando invii un hit con un ID visitatore personalizzato,  Adobe verifica la presenza di eventuali profili visitatore con un ID visitatore corrispondente. Se ne esiste uno, il profilo visitatore già presente nel sistema viene utilizzato da quel momento in poi e il profilo visitatore precedente non viene più utilizzato.

L&#39;impostazione della variabile `visitorID` viene generalmente impostata dopo l&#39;autenticazione, o dopo che un visitatore esegue altre azioni che consentono di identificarle in modo univoco indipendentemente dal dispositivo utilizzato. Gli identificatori efficaci includono un hash del proprio nome utente, indirizzo e-mail o un ID interno che non contiene alcuna informazione identificabile personalmente.

Dopo che il cliente ha effettuato l&#39;accesso da ciascun dispositivo, tutti i collegamenti sono legati allo stesso profilo utente. Se il visitatore si disconnette successivamente su un dispositivo, continua a appartenere allo stesso profilo visitatore, perché  Adobe riconosce che il cookie del browser su ciascun dispositivo appartiene allo stesso profilo visitatore.  Adobe consiglia di utilizzare la variabile `visitorID` quando possibile nel caso in cui il cookie del browser venga eliminato.

## Limitazioni

L’utilizzo del proprio ID visitatore personalizzato offre maggiore controllo sulle modalità di identificazione dei visitatori, ma presenta anche dei limiti.

* **La deduplicazione dei visitatori non è retroattiva**: Se un visitatore accede al sito per la prima volta, quindi esegue l&#39;autenticazione, vengono contati due visitatori unici. Un singolo conteggio dei visitatori per l’ID Analytics generico generato automaticamente e un altro per l’ID visitatore personalizzato al momento dell’accesso. Questa duplicazione di visitatori univoci è presente ogni volta che un visitatore utilizza un nuovo dispositivo o cancella i cookie.
* **Incompatibilità con il servizio** ID Experience Cloud : Dall&#39;introduzione dell&#39;identificazione dei visitatori su più dispositivi,  Adobe ha reso disponibili metodi più potenti e affidabili per monitorare i visitatori su più dispositivi. Questi nuovi metodi di identificazione non sono compatibili con l’override dell’ID visitatore personalizzato. Se prevedete di utilizzare il servizio ID, l’analisi cross-device (CDA) o Device Co-op,  Adobe consiglia vivamente di non utilizzare la variabile `visitorID`.
