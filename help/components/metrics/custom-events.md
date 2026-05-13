---
title: Eventi personalizzati
description: Il numero di hit in cui esiste un evento personalizzato.
feature: Metrics
exl-id: 9ae3ff53-8634-466a-a9f6-786c1e62c2fa
TQID: https://experienceleague.adobe.com/1D8ONiUuG3T6DqM7HygbBbf0Y4ja5ej1Hfy8-hKo0yg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 4%

---

# Eventi personalizzati

*Questa pagina della Guida descrive il funzionamento degli eventi personalizzati come metrica. Per informazioni sul funzionamento degli eventi personalizzati come variabile di implementazione, vedere [Panoramica eventi](/help/implement/vars/page-vars/events/events-overview.md) nella guida utente Implementa.*

Le [metriche](overview.md) dell&#39;evento personalizzato mostrano il numero di hit in cui un dato evento personalizzato è stato impostato in una richiesta di immagine. Queste metriche sono vitali per molte implementazioni, in quanto forniscono insight agli eventi specifici di ogni organizzazione.

## Come è calcolata questa metrica

Gli eventi personalizzati vengono calcolati in modo diverso a seconda del tipo. Puoi controllare il tipo di evento in [Eventi di successo](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/c-success-events/success-event.md) nelle impostazioni della suite di rapporti.

* **Eventi contatore**: impostazione predefinita dell&#39;evento. La maggior parte degli eventi sono eventi contatore. Conta il numero di hit in cui l&#39;evento personalizzato corrispondente `event1` - `event1000` esiste nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md).
* **Eventi numerici**: somma il valore numerico assegnato all&#39;evento nella variabile `events`.
* **Eventi di valuta**: applica la conversione della valuta al tasso di cambio di quel giorno, quindi somma il valore numerico assegnato a ogni hit nella variabile `events`.

Il numero di eventi disponibili dipende dal contratto Analytics della tua organizzazione. La maggior parte delle organizzazioni con contratti non legacy dispone di 1000 eventi personalizzati. Se non sai quanti eventi personalizzati sono disponibili, contatta il tuo Adobe Account Team.

Adobe consiglia vivamente di registrare le modalità di utilizzo di ogni evento nel [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) dell&#39;organizzazione.
