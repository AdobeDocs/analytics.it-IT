---
description: Tabella di ricerca per determinare il tipo di hit in base all’evento della pagina.
keywords: page;event;page_event;post_page_event
title: Ricerca eventi pagina
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
TQID: 'https://experienceleague.adobe.com/VaSk-h0AVXNcL-YoxuFu2XJwzING-08-GX2Pgt6dj4s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 226
ht-degree: 4%

---

# Ricerca eventi pagina

Tabella di ricerca per determinare il tipo di un hit in base al valore `page_event`. Come indicato nel [Riferimento colonna dati](datafeeds-reference.md), le colonne `page_event` e `post_page_event` sono tinyint unsigned.

* Consulta [`t()`](/help/implement/vars/functions/t-method.md) per informazioni sull&#39;implementazione delle chiamate di visualizzazione pagina per AppMeasurement e Web SDK.
* Consulta [`tl()`](/help/implement/vars/functions/tl-method.md) per informazioni sull&#39;implementazione delle chiamate di tracciamento dei collegamenti per AppMeasurement e Web SDK.
* Consulta [Implementare Adobe Analytics con Adobe Experience Platform Edge Network](/help/implement/aep-edge/overview.md) per capire come Adobe Analytics traduce i payload XDM in tipi di eventi di pagina.

| Valore `page_event` | Valore `post_page_event` | Descrizione |
| --- | --- | --- |
| `0` | `0` | Tutte le chiamate standard di visualizzazione pagina. È il valore predefinito per la maggior parte degli hit. |
| `10` | `100` | Collegamenti personalizzati. Imposta il tipo di collegamento su `o` (AppMeasurement) o `xdm.web.webInteraction.type` su `other` (Web SDK o Mobile SDK). |
| `11` | `101` | Collegamenti di download. Imposta il tipo di collegamento su `d` (AppMeasurement) o `xdm.web.webInteraction.type` su `download` (Web SDK o Mobile SDK). |
| `12` | `102` | Collegamenti di uscita. Imposta il tipo di collegamento su `e` (AppMeasurement) o `xdm.web.webInteraction.type` su `exit` (Web SDK o Mobile SDK). |
| `31` | `76` | Avvio file multimediale |
| `32` | `77` | Aggiornamenti dei contenuti multimediali (senza altra elaborazione variabile) |
| `33` | `78` | Aggiornamenti multimediali (con altra elaborazione variabile) |
| `40` | `80` | Sondaggio |
| `50` | `50` | Avvio contenuti multimediali in streaming |
| `51` | `51` | Chiusura di contenuti multimediali in streaming |
| `52` | `52` | Scrubbing di contenuti multimediali in streaming |
| `53` | `53` | I contenuti multimediali in streaming mantengono |
| `54` | `54` | Inizio annuncio contenuti multimediali in streaming |
| `55` | `55` | Chiusura annuncio multimediale in streaming |
| `56` | `56` | Scrubbing di annunci multimediali in streaming |
| `60` | `60` | Avvio file multimediale Primetime |
| `61` | `61` | Chiusura file multimediali Primetime |
| `62` | `62` | Scrubbing dei contenuti multimediali di Primetime |
| `63` | `63` | File multimediali Primetime keep alive |
| `64` | `64` | Avvio annuncio multimediale Primetime |
| `65` | `65` | Chiusura annuncio multimediale Primetime |
| `66` | `66` | Scrubbing di annunci multimediali di Primetime |
| `70` | `70` | Include i dati delle attività di Target |
