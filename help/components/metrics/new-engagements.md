---
title: Nuovi coinvolgimenti
description: Il numero di volte in cui è impostato un canale di primo contatto.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 6%

---

# Nuovi coinvolgimenti

La [metrica](overview.md) dei &quot;Nuovi impegni&quot; mostra il numero di volte in cui un visitatore corrisponde a un canale di marketing per la prima volta nel periodo di coinvolgimento del visitatore. Questa metrica è utile quando desideri confrontare per la prima volta qualsiasi dimensione con un visitatore che corrisponde a una regola di elaborazione del canale di marketing.

## Come è calcolata questa metrica

Durante l&#39;elaborazione dei dati, ogni hit viene eseguito tramite [Regole di elaborazione del canale di marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Se un hit corrisponde a una regola di elaborazione del canale di marketing e il visitatore non dispone già di un canale di primo contatto, l’hit è un nuovo coinvolgimento. Se un hit non corrisponde ad alcuna regola di elaborazione del canale di marketing o se il visitatore dispone già di un canale di primo contatto, l’hit non è un nuovo coinvolgimento.

I visitatori possono avere più di un nuovo coinvolgimento se lasciano scadere il periodo di coinvolgimento dei visitatori.
