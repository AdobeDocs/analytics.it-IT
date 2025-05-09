---
description: Tabella di ricerca per determinare il tipo di hit in base all’evento della pagina.
keywords: page;event;page_event;post_page_event
title: Ricerca eventi pagina
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
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
