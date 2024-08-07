---
title: Eventi personalizzati
description: Il numero di hit in cui esiste un evento personalizzato.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Eventi personalizzati

*Questa pagina della Guida descrive il funzionamento degli eventi personalizzati come metrica. Per informazioni sul funzionamento degli eventi personalizzati come variabile di implementazione, vedere [Panoramica eventi](/help/implement/vars/page-vars/events/events-overview.md) nella guida utente Implementa.*

Le [metriche](overview.md) dell&#39;evento personalizzato mostrano il numero di hit in cui un dato evento personalizzato è stato impostato in una richiesta di immagine. Queste metriche sono fondamentali per molte implementazioni, in quanto forniscono informazioni approfondite sugli eventi specifici di ogni organizzazione.

## Come è calcolata questa metrica

Gli eventi personalizzati vengono calcolati in modo diverso a seconda del tipo. Puoi controllare il tipo di evento in [Eventi di successo](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

* **Eventi contatore**: impostazione predefinita dell&#39;evento. La maggior parte degli eventi sono eventi contatore. Conta il numero di hit in cui l&#39;evento personalizzato corrispondente `event1` - `event1000` esiste nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventi numerici**: somma il valore numerico assegnato all&#39;evento nella variabile `events`.
* **Eventi di valuta**: applica la conversione della valuta al tasso di cambio di quel giorno, quindi somma il valore numerico assegnato a ogni hit nella variabile `events`.

Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Se non sai quanti eventi personalizzati sono disponibili, contatta il tuo account team di Adobi.

L&#39;Adobe consiglia vivamente di registrare le modalità di utilizzo di ogni evento nel [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) dell&#39;organizzazione.
