---
title: Ora del giorno
description: L’ora numerica del giorno, indipendentemente dal giorno.
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
TQID: https://experienceleague.adobe.com/cktusukSxy7fHIIUi-7MSmx8Gl9FlUObfmJGS3VC3Jw
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '413'
ht-degree: 6%
---
# Ora del giorno

La dimensione &#39;Ora del giorno&#39; [dimensione](overview.md) riporta l&#39;ora numerica di un dato giorno come elemento dimensione. Ad esempio, se un rapporto si estende dal 1° gennaio al 7 gennaio, la prima ora di ogni giorno si raggruppa nello stesso elemento dimensionale. Questo rapporto è utile se desideri un rapporto suddiviso per ora del giorno relativa, ma non vuoi ore statiche come elementi dimensionali. È particolarmente utile come dimensione nei rapporti pianificati, in quanto questa dimensione viene aggregata all’intervallo di date selezionato.

Questa dimensione si basa sul fuso orario della suite di rapporti e non su quello locale del visitatore. Ad esempio, se la suite di rapporti è in tempo di montagna e un visitatore in California visita il tuo sito alle 00:00 ora del Pacifico, gli hit vengono raggruppati sotto l’elemento dimensione `11:00 AM`. Se desideri una dimensione che registri l&#39;ora del visitatore locale, Adobe consiglia di utilizzare il plug-in [getTimeParting](/help/implement/vars/plugins/gettimeparting.md).

## Popolare questa dimensione con i dati

Questa dimensione deriva dalla marca temporale di ciascun hit; non esiste una variabile da impostare. Come indicato sopra, l’ora riflette il fuso orario della suite di rapporti anziché quello locale del visitatore.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal timestamp dell’hit) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal timestamp dell’hit) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono `12:00 AM` - `11:00 PM`, che rappresenta l&#39;ora del giorno in cui si è verificato l&#39;hit (arrotondato per difetto). Ad esempio, se un hit è stato generato alle 15:58, viene raggruppato sotto l&#39;elemento dimensionale `3:00 PM`.

## Ora legale

L&#39;ora legale è una pratica in cui gli orologi sono impostati un&#39;ora avanti in primavera e un&#39;ora indietro in autunno. Se il fuso orario di una suite di rapporti utilizza l’ora legale, Adobe regola i dati di conseguenza per tale ora.

* **Quando inizia l&#39;ora legale**: in marzo, nei rapporti viene in genere visualizzato un intervallo di un&#39;ora nei dati in cui inizia l&#39;ora legale. L’ora non esiste, quindi non fa parte della raccolta dati. Tieni presente che una piccola quantità di dati può comunque arrivare a quest’ora. I server di raccolta dati di Adobe impiegano diversi secondi (fino a un minuto) per prendere in considerazione le regolazioni dell’ora legale.
* **Al termine dell&#39;ora legale**: in novembre, nei report viene in genere visualizzata un&#39;ora a doppia sovrapposizione in cui termina l&#39;ora legale. L’ora si è verificata due volte, quindi entrambe le ore sono aggregate nei rapporti.
