---
title: Giorni dall’ultima visita
description: Il numero di giorni tra l’hit corrente e l’ultima volta che hanno visitato.
feature: Dimensions
exl-id: 8063bdc6-516a-4dd0-a4ca-ded739e8d406
TQID: https://experienceleague.adobe.com/VOkdvehFSgp1xBEq49W5FIphzHi8ZCbrsoMnI7rgQMs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 13%
---
# Giorni dall’ultima visita

La [dimensione](overview.md) &quot;Giorni dall&#39;ultima visita&quot; misura il tempo trascorso tra l&#39;hit corrente del visitatore e la visita precedente (se presente). Questa dimensione ti aiuta a comprendere il comportamento dei visitatori dopo la visita al tuo sito. Gli esempi includono:

* Con quale frequenza gli utenti visitano nuovamente il sito?
* In che modo la frequenza di ritorno è correlata alla conversione? Visita frequente o occasionale degli acquirenti?
* Gli utenti che fanno clic sulle campagne tornano spesso?

I visitatori nuovi non sono inclusi in questa dimensione.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server dalla cronologia delle visite del visitatore. Non esiste una variabile da impostare; funziona automaticamente per tutte le implementazioni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono il numero di giorni tra l’ultima visita di un visitatore e l’hit corrente. Ogni numero di giorni è un elemento dimensione separato, con `"Same day"` che si verifica quando l’ultima visita di un visitatore e l’hit corrente si sono verificati nello stesso giorno.
