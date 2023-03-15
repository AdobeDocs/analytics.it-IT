---
title: Tipo di connessione
description: Come il visitatore si connette a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 2%

---

# Tipo di connessione

La dimensione &quot;Tipo di connessione&quot; mostra come il visitatore si è connesso a Internet. Questa dimensione è utile per determinare come i visitatori si connettono a Internet per navigare nel sito. Puoi utilizzarlo per ottimizzare il contenuto del sito in base alla velocità di connessione dei visitatori.

## Popola questa dimensione con i dati

Questa dimensione utilizza una combinazione di [`ct` stringa di query](/help/implement/validate/query-parameters.md) e logica lato server di Adobe. Adobe utilizza le seguenti regole per determinarne il valore:

1. Se il `ct` stringa di query uguale a `"modem"`, imposta l’elemento dimensione su `"Modem"`. AppMeasurement raccoglie questi dati solo su browser Internet Explorer non supportati, rendendo questo elemento dimensionale non comune.
1. Controlla l’indirizzo IP dell’hit e fai riferimento a una tabella di ricerca interna da Adobe. Se l’indirizzo IP proviene da un gestore di telefonia mobile, imposta l’elemento dimensione su `"Mobile Carrier"`.
1. Se il `ct` stringa di query uguale a `"lan"`, imposta l’elemento dimensione su `"LAN/Wifi"`.
1. Se l’hit proviene da un [Origine dati](/help/import/c-data-sources/datasrc-home.md) o è altrimenti considerato un tipo speciale di hit, imposta l’elemento dimensionale su `"Not specified"`.
1. Se nessuna delle regole di cui sopra è soddisfatta, il valore predefinito è `"LAN/Wifi"`.

## Elementi dimensionali

Gli elementi del Dimension includono `LAN/Wifi`, `Mobile Carrier`, `Modem`, e `Not Specified`.

* **`LAN/Wifi`**: il visitatore si è connesso a Internet tramite una rete fissa o un hotspot Wi-Fi.
* **`Mobile Carrier`**: il visitatore si è connesso a Internet tramite un operatore di telefonia mobile.
* **`Modem`**: il visitatore si è connesso a Internet tramite un modem su un browser Internet Explorer non supportato.
* **`Not Specified`**: l’hit non aveva un tipo di connessione.
