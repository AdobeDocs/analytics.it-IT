---
title: Canale di primo contatto
description: Il primo canale di marketing entro la scadenza del coinvolgimento del visitatore.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
TQID: https://experienceleague.adobe.com/1XBUjwxlZXmhXJtQZgpv9yU5Fwhns-bb9Q7BcP5S30Q
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 7%
---
# Canale di primo contatto

La [dimensione](overview.md) del &#39;canale di primo contatto&#39; segnala il primo canale di marketing con cui un visitatore corrisponde durante il periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita). Questa dimensione è utile per comprendere quali canali di marketing indirizzano il traffico iniziale verso il sito, consentendoti di concentrare le attività di marketing nelle aree più efficaci.

## Popolare questa dimensione con i dati

Questa dimensione viene derivata dalle regole di elaborazione del canale di marketing. Fa riferimento direttamente ai nomi di canale definiti in [Marketing Channel Manager](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md). Ogni hit scorre attraverso le regole di elaborazione del canale di marketing della suite di rapporti in ordine numerico fino a quando non trova una corrispondenza che lega il canale di marketing all’hit. Nessuna variabile da impostare.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dalle regole di elaborazione del canale di marketing) |
| **Campo Web SDK / XDM** | Nessuno (derivato dalle regole di elaborazione del canale di marketing) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Configurabile |

Il canale di primo contatto persiste con il visitatore finché non visita il sito per un periodo più lungo del periodo di coinvolgimento del visitatore (30 giorni per impostazione predefinita).

Per impostare questa dimensione su un valore specifico, sono necessari i seguenti passaggi:

* Imposta l’elemento dimensionale desiderato come canale nel Gestore dei canali di marketing, in Impostazioni della suite di rapporti.
* Imposta una regola di elaborazione del canale di marketing contenente i criteri desiderati per l’hit.
* L&#39;hit del visitatore per il sito deve corrispondere ai criteri descritti nella regola di elaborazione del canale di marketing. _e_ deve essere il primo valore del canale di marketing a farlo nel periodo di coinvolgimento del visitatore.

Se un hit successivo corrisponde ai criteri di un canale di marketing diverso, questa dimensione non viene sovrascritta con il nuovo canale di marketing.

## Elementi dimensionali

Gli elementi Dimension includono un nome di canale nel Marketing Channel Manager. Per impostazione predefinita, i valori includono `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Nel Marketing Channel Manager puoi aggiungere o eliminare canali che influiscono sui valori di questa dimensione.
