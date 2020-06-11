---
title: Eventi personalizzati
description: Il numero di hit in cui esiste un evento personalizzato.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 0%

---


# Eventi personalizzati

*Questa pagina della guida descrive il funzionamento degli eventi personalizzati come una metrica. Per informazioni sul funzionamento degli eventi personalizzati come variabile di implementazione, consultate Panoramica[degli](/help/implement/vars/page-vars/events/events-overview.md)eventi nella guida per l&#39;utente Implementazione.*

Le metriche evento personalizzate mostrano il numero di hit in cui un determinato evento personalizzato è stato impostato in una richiesta di immagine. Queste metriche sono vitali per molte implementazioni, in quanto forniscono informazioni sugli eventi specifici per ogni organizzazione.

## Modalità di calcolo di questa metrica

Gli eventi personalizzati vengono calcolati in modo diverso a seconda del tipo. Potete controllare il tipo di evento in Eventi [di](../../admin/admin/c-success-events/success-event.md) successo nelle impostazioni della suite di rapporti.

* **Eventi** contatore: L&#39;impostazione predefinita dell&#39;evento. La maggior parte degli eventi sono contro-eventi. Conta il numero di hit in cui esiste l’evento personalizzato corrispondente `event1` - `event1000` nella [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile.
* **Eventi** numerici: Somma il valore numerico assegnato all&#39;evento nella `events` variabile.
* **Eventi** valuta: Applica la conversione di valuta in base al tasso di cambio del giorno, quindi somma il valore numerico assegnato a ogni hit nella `events` variabile.

Il numero di eventi disponibili dipende dal contratto Analytics dell&#39;organizzazione. La maggior parte delle organizzazioni per i contratti non legacy dispone di 1000 eventi personalizzati. Contatta il responsabile commerciale dell&#39;azienda se non sei sicuro di quanti eventi personalizzati sono disponibili.

Adobe consiglia vivamente di registrare il modo in cui si utilizza ogni evento nel documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione aziendale.
