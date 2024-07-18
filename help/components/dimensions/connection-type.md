---
title: Tipo di connessione
description: Come il visitatore si connette a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 4%

---

# Tipo di connessione

Il &#39;Tipo di connessione&#39; [dimensione](overview.md) mostra come il visitatore si è connesso a Internet. Questa dimensione è utile per determinare come i visitatori si connettono a Internet per navigare nel sito. Puoi utilizzarlo per ottimizzare il contenuto del sito in base alla velocità di connessione dei visitatori.

## Popolare questa dimensione con i dati

Questa dimensione utilizza una combinazione della stringa di query [`ct`](/help/implement/validate/query-parameters.md) e della logica lato server di Adobe. Adobe utilizza le seguenti regole per determinarne il valore:

1. Se la stringa di query `ct` è uguale a `"modem"`, impostare l&#39;elemento dimensione su `"Modem"`. AppMeasurement raccoglie questi dati solo su browser Internet Explorer non supportati, rendendo questo elemento dimensionale non comune.
1. Controlla l’indirizzo IP dell’hit e fai riferimento a una tabella di ricerca interna da Adobe. Se l&#39;indirizzo IP proviene da un gestore di telefonia mobile, impostare la dimensione su `"Mobile Carrier"`.
1. Se la stringa di query `ct` è uguale a `"lan"`, impostare l&#39;elemento dimensione su `"LAN/Wifi"`.
1. Se l&#39;hit proviene da un&#39;origine dati [Origine dati](/help/import/data-sources/overview.md) o è altrimenti considerato un tipo speciale di hit, impostare l&#39;elemento dimensione su `"Not specified"`.
1. Se nessuna delle regole precedenti è soddisfatta, il valore predefinito è `"LAN/Wifi"`.

## Elementi dimensionali

Gli elementi del Dimension includono `LAN/Wifi`, `Mobile Carrier`, `Modem` e `Not Specified`.

* **`LAN/Wifi`**: il visitatore si è connesso a Internet tramite una rete fissa o un hotspot Wi-Fi.
* **`Mobile Carrier`**: il visitatore si è connesso a Internet tramite un gestore di telefonia mobile.
* **`Modem`**: il visitatore si è connesso a Internet tramite un modem su un browser Internet Explorer non supportato.
* **`Not Specified`**: tipo di connessione non disponibile per l&#39;hit.
