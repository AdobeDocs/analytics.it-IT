---
title: Stato identificato
description: Flag che determina il riconoscimento dal grafico del dispositivo.
feature: Dimensions
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 3%

---

# Stato identificato

La dimensione &quot;Stato identificato&quot; è specifica per [Analisi multidispositivo](../cda/overview.md) suite di rapporti virtuali. Indica se gli hit vengono identificati (uniti) o meno dal sistema al momento dell&#39;esecuzione del rapporto. Questa dimensione è utile per comprendere come CDA unisce o comprime correttamente i dati.

## Popolare questa dimensione con i dati

Fino a quando [Analisi multidispositivo](../cda/overview.md) configurata per una suite di rapporti virtuale, questa dimensione funziona come non disponibile.

## Elementi Dimension

Gli elementi del Dimension includono `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: L&#39;hit è mappato a una persona.
* **`"Unidentified"`**: L&#39;hit non è mappato a una persona e non può essere mappato con alcun metodo di attribuzione.
