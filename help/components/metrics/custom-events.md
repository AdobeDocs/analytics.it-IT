---
title: Eventi personalizzati
description: Il numero di hit in cui esiste un evento personalizzato.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 1%

---

# Eventi personalizzati

*Questa pagina di aiuto descrive il funzionamento degli eventi personalizzati come metriche. Per informazioni sul funzionamento degli eventi personalizzati come variabili di implementazione, vedi [Panoramica degli eventi](/help/implement/vars/page-vars/events/events-overview.md) nella guida utente Implementa .*

Le metriche degli eventi personalizzati mostrano il numero di hit in cui è stato impostato un dato evento personalizzato in una richiesta di immagine. Queste metriche sono vitali per molte implementazioni, in quanto forniscono informazioni dettagliate sugli eventi specifici per ogni organizzazione.

## Calcolo di questa metrica

Gli eventi personalizzati vengono calcolati in modo diverso a seconda del tipo. Puoi controllare il tipo di un evento in [Eventi di successo](../../admin/admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

* **Eventi contatore**: L’impostazione predefinita dell’evento. La maggior parte degli eventi sono eventi contatore. Conta il numero di hit in cui l’evento personalizzato corrispondente è `event1` - `event1000` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile.
* **Eventi numerici**: Somma il valore numerico assegnato all&#39;evento nel `events` variabile.
* **Eventi valuta**: Applica la conversione di valuta in base al tasso di cambio di quel giorno, quindi somma il valore numerico assegnato a ogni hit nel `events` variabile.

Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Contatta l’account manager della tua organizzazione se non sei sicuro di quanti eventi personalizzati sono disponibili.

L’Adobe consiglia vivamente di registrare il modo in cui si utilizza ogni evento nell’organizzazione [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
