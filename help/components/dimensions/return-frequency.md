---
title: Frequenza di ritorno
description: Periodo di tempo compreso tra la visita corrente e la visita precedente.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI
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
source-wordcount: '282'
ht-degree: 13%
---
# Frequenza di ritorno

La &#39;Frequenza di ritorno&#39; [dimensione](overview.md) mostra il periodo di tempo che intercorre tra le visite dei visitatori di ritorno. Quando un visitatore ritorna sul sito, Adobe osserva da quanto tempo è avvenuta la visita precedente e memorizza l’hit nell’elemento dimensionale appropriato. Questa dimensione è utile per valutare l’attrattiva del sito web e la sua rilevanza per i visitatori nel tempo. Può anche aiutare a identificare l&#39;impatto dei contenuti e delle promozioni del sito sui visitatori.

>[!TIP]
>
>Questa dimensione non include i visitatori nuovi.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server confrontando la visita corrente con la visita precedente del visitatore. Non esiste una variabile da impostare; funziona automaticamente per tutte le implementazioni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visita |

## Elementi dimensionali

Gli elementi Dimension includono contenitori basati sul tempo, a seconda del tempo trascorso dalla visita precedente.

* Meno di 1 giorno
* 1-3 giorni
* 3-7 giorni
* 7-14 giorni
* Da 14 giorni a 1 mese
* Più di 1 mese

## Gli elementi Dimension vengono visualizzati in contenitori al di fuori dell’intervallo di date del progetto

Quando imposti l’intervallo di date di un progetto, in genere viene visualizzato l’attributo degli elementi dimensionali per le visite al di fuori dell’intervallo di date. Ad esempio, un visitatore accede al tuo sito a luglio e poi ritorna due volte nello stesso giorno di settembre. La dimensione Frequenza di ritorno per il mese di settembre mostrerebbe una visita in &quot;Più di 1 mese&quot; e una visita in &quot;Meno di 1 giorno&quot;.
