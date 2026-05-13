---
title: Tipo di connessione
description: Come il visitatore si connette a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
TQID: https://experienceleague.adobe.com/5kdDrW5vGzc4EKpLOF4VWzXish439t-aGp6q-XcK3Fs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 236
ht-degree: 4%

---

# Tipo di connessione

Il &#39;Tipo di connessione&#39; [dimensione](overview.md) mostra come il visitatore si è connesso a Internet. Questa dimensione è utile per determinare come i visitatori si connettono a Internet per navigare nel sito. Puoi utilizzarlo per ottimizzare il contenuto del sito in base alla velocità di connessione dei visitatori.

## Popolare questa dimensione con i dati

Questa dimensione utilizza una combinazione della stringa di query [`ct`](/help/implement/validate/query-parameters.md) e della logica lato server di Adobe. Adobe utilizza le seguenti regole per determinarne il valore:

1. Se la stringa di query `ct` è uguale a `"modem"`, impostare l&#39;elemento dimensione su `"Modem"`. AppMeasurement raccoglie questi dati solo su browser Internet Explorer non supportati, rendendo questo elemento dimensione non comune.
1. Controlla l’indirizzo IP dell’hit e fai riferimento a una tabella di ricerca interna ad Adobe. Se l&#39;indirizzo IP proviene da un gestore di telefonia mobile, impostare la dimensione su `"Mobile Carrier"`.
1. Se la stringa di query `ct` è uguale a `"lan"`, impostare l&#39;elemento dimensione su `"LAN/Wifi"`.
1. Se l&#39;hit proviene da un&#39;origine dati [Origine dati](/help/import/data-sources/overview.md) o è altrimenti considerato un tipo speciale di hit, impostare l&#39;elemento dimensione su `"Not specified"`.
1. Se nessuna delle regole precedenti è soddisfatta, il valore predefinito è `"LAN/Wifi"`.

## Elementi dimensionali

Gli elementi di Dimension includono `LAN/Wifi`, `Mobile Carrier`, `Modem` e `Not Specified`.

* **`LAN/Wifi`**: il visitatore si è connesso a Internet tramite una rete fissa o un hotspot Wi-Fi.
* **`Mobile Carrier`**: il visitatore si è connesso a Internet tramite un gestore di telefonia mobile.
* **`Modem`**: il visitatore si è connesso a Internet tramite un modem su un browser Internet Explorer non supportato.
* **`Not Specified`**: tipo di connessione non disponibile per l&#39;hit.
