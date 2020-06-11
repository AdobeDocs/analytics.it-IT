---
title: Ultimo canale touch
description: Il canale di marketing più recente entro la scadenza del coinvolgimento del visitatore.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# Ultimo canale touch

La dimensione &quot;Ultimo canale di contatto&quot; indica il canale di marketing più recente con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (per impostazione predefinita, 30 giorni). Questa dimensione è importante per comprendere quali canali di marketing veicolano il traffico verso il sito e quindi le conversioni, consentendo di concentrare le attività di marketing nelle aree più efficaci.

## Compilare questa dimensione con i dati

Questa dimensione fa direttamente riferimento ai nomi dei canali definiti nel gestore [dei canali di](/help/admin/admin/marketing-channels-admin.md)marketing.

Ogni hit inviato ai server di raccolta dati Adobe viene eseguito tramite le regole di elaborazione del canale Marketing della suite di rapporti. Ripete ogni regola in ordine numerico finché non trova una corrispondenza, in cui il canale di marketing si collega all’hit. L’ultimo canale di tocco persiste con il visitatore fino a quando non visita il sito per un periodo superiore al periodo di coinvolgimento del visitatore (per impostazione predefinita, 30 giorni).

Per impostare questa dimensione su un valore specifico, sono necessari i passaggi seguenti:

* Impostate il valore di dimensione desiderato come canale nel gestore canali di marketing in Impostazioni suite di rapporti.
* Impostate una regola di elaborazione del canale di marketing che contenga i criteri desiderati per l’hit.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri indicati nella regola di elaborazione del canale di marketing.

## Valori dimensione

I valori delle dimensioni includono qualsiasi nome di canale nel gestore canali di marketing. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`e `"Referring domains"`. Puoi aggiungere o eliminare canali in Marketing Channel Manager, che influiscono sui valori di questa dimensione.
