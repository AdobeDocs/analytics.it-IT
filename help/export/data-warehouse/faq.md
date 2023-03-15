---
title: Domande frequenti su Data Warehouse
description: Domande frequenti per la Data Warehouse.
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 14%

---

# Domande frequenti su Data Warehouse

Domande frequenti per la Data Warehouse.

## Quando utilizzo il menu a discesa di granularità durante la creazione di una richiesta, in quale formato posso aspettarmi che si trovino le date?

Quando si applica la granularità in una richiesta Data Warehouse, la colonna &quot;Data&quot; viene aggiunta al rapporto. A seconda della granularità selezionata, il formato della data cambia.

| Granularità | Formato | Esempio |
| --- | --- | --- |
| Oraria | `mmmm d, yyyy` Ora `H` | 1 gennaio, 20XX, Ora 0 |
| Giornaliero | `mmmm d, yyyy` | 1 gennaio 20XX |
| Settimanale | Settimana `w, yyyy` | Settimana 1, 20XX |
| Mensile | `mmmm yyyy` | Gennaio 20XX |
| Trimestrale | `q` Trimestre `yyyy` | 1° trimestre 20XX |
| Annuale | `yyyy` | 20XX |

## Come funzionano i segmenti come dimensioni in Data Warehouse?

Quando utilizzi un segmento come dimensione in Data Warehouse, il rapporto restituisce una colonna contenente `"0"` o `"1"`:

* **`"0"`**: l’elemento dimensionale non soddisfa i criteri del segmento.
* **`"1"`**: l’elemento dimensione ha soddisfatto i criteri del segmento.
