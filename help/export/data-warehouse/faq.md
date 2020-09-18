---
title: Domande frequenti su Data Warehouse
description: Domande frequenti per la Data Warehouse.
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 9%

---


# Domande frequenti su Data Warehouse

Domande frequenti per la Data Warehouse.

## Quando si utilizza il menu a discesa di granularità durante la creazione di una richiesta, in quale formato è possibile specificare le date?

Quando si applica la granularità in una richiesta di Data Warehouse, al rapporto viene aggiunta la colonna &quot;Data&quot;. A seconda della granularità selezionata, cambia il formato della data.

| Granularity (Granularità) | Formato | Esempio |
| --- | --- | --- |
| Oraria | `mmmm d, yyyy` Ora `H` | 1 gennaio, 20XX, ora 0 |
| Giornaliero | `mmmm d, yyyy` | 1 gennaio, 20 XX |
| Settimanale | Settimana `w, yyyy` | Settimana 1, 20XX |
| Mensile | `mmmm yyyy` | 20 gennaio |
| Trimestrale | `q` Trimestre `yyyy` | 1° trimestre 20XX |
| Annuale | `yyyy` | 20XX |

## Come funzionano i segmenti come dimensioni nella Data Warehouse?

Quando utilizzi un segmento come dimensione nella Data Warehouse, il rapporto restituisce una colonna contenente `"0"` o `"1"`:

* **`"0"`**: L&#39;elemento dimensione non soddisfa i criteri del segmento.
* **`"1"`**: L&#39;elemento dimensione soddisfa i criteri del segmento.
