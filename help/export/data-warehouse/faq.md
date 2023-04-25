---
title: Domande frequenti su Data Warehouse
description: Domande frequenti per la Data Warehouse.
feature: Data Warehouse
exl-id: 51c3ba17-a8b2-4030-9521-355ebbbfcd0d
source-git-commit: 78cfb1f3c4d45fc983982a8da11b66f2b2c9ecbc
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 14%

---

# Domande frequenti su Data Warehouse

Domande frequenti per la Data Warehouse.

## Quando uso l’elenco a discesa granularità durante la creazione di una richiesta, in quale formato è possibile prevedere le date?

Quando applichi la granularità in una richiesta di Data Warehouse, la colonna &quot;Data&quot; viene aggiunta al rapporto. A seconda della granularità selezionata, il formato della data cambia.

| Granularità | Formato | Esempio |
| --- | --- | --- |
| Oraria | `mmmm d, yyyy` Ora `H` | 1 gennaio, 20XX, ora 0 |
| Giornaliero | `mmmm d, yyyy` | 1 gennaio 2020 |
| Settimanale | Settimana `w, yyyy` | Settimana 1, 20XX |
| Mensile | `mmmm yyyy` | 20 gennaio |
| Trimestrale | `q` Trimestre `yyyy` | 1° trimestre 20XX |
| Annuale | `yyyy` | 20XX |

## Come funzionano i segmenti come dimensioni nella Data Warehouse?

Quando utilizzi un segmento come dimensione nella Data Warehouse, il rapporto restituisce una colonna contenente `"0"` o `"1"`:

* **`"0"`**: L’elemento dimensionale non soddisfaceva i criteri del segmento.
* **`"1"`**: L’elemento dimensionale soddisfa i criteri del segmento.
