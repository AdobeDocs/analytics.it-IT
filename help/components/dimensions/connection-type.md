---
title: Tipo di connessione
description: Come il visitatore si connette a Internet.
feature: Dimensions
exl-id: 149b2353-6128-4e0c-a73a-bc5a37c66b52
source-git-commit: ac3748826d9907cc68076ad39e865f39ea903cf2
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 2%

---

# Tipo di connessione

La dimensione &quot;Tipo di connessione&quot; mostra il modo in cui il visitatore si è connesso a Internet. Questa dimensione è utile per determinare in che modo i visitatori si connettono a Internet per sfogliare il sito. Puoi utilizzarlo per ottimizzare il contenuto del sito in base alla velocità di connessione dei visitatori.

## Popolare questa dimensione con i dati

Questa dimensione utilizza una combinazione di [`ct` stringa di interrogazione](/help/implement/validate/query-parameters.md) e logica lato server di Adobe. Adobe utilizza le regole seguenti per determinarne il valore:

1. Se la `ct` stringa query uguale a `"modem"`, imposta l’elemento dimensionale su `"Modem"`. AppMeasurement raccoglie questi dati solo su browser Internet Explorer non supportati, rendendo questo elemento dimensionale poco comune.
1. Controlla l&#39;indirizzo IP dell&#39;hit e fai riferimento a una tabella di ricerca interna all&#39;Adobe. Se l’indirizzo IP proviene da un gestore di telefonia mobile, imposta l’elemento dimensionale su `"Mobile Carrier"`.
1. Se la `ct` stringa query uguale a `"lan"`, imposta l’elemento dimensionale su `"LAN/Wifi"`.
1. Se l&#39;hit proviene da un [Origine dati](/help/import/data-sources/overview.md) oppure è considerato un tipo speciale di hit, imposta l’elemento della dimensione su `"Not specified"`.
1. Se nessuna delle regole di cui sopra è soddisfatta, utilizza il valore predefinito di `"LAN/Wifi"`.

## Elementi dimensionali

Gli elementi del Dimension includono `LAN/Wifi`, `Mobile Carrier`, `Modem`e `Not Specified`.

* **`LAN/Wifi`**: Il visitatore si è connesso a Internet tramite un hotspot telefonico o wifi.
* **`Mobile Carrier`**: Il visitatore si è connesso a Internet tramite un gestore di telefonia mobile.
* **`Modem`**: Il visitatore si è connesso a Internet tramite un modem su un browser Internet Explorer non supportato.
* **`Not Specified`**: L&#39;hit non aveva un tipo di connessione.
