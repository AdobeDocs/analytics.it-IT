---
title: Stato identificato
description: Flag che determina il riconoscimento dal grafico del dispositivo.
exl-id: 8c6e9003-96f8-460f-a490-203f67be6337
source-git-commit: 1a58c3e87f5918c91b891faa6027f5ad8b6024b9
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 3%

---

# Stato identificato

La dimensione &quot;Stato identificato&quot; è specifica per le suite di rapporti virtuali [Cross-Device Analytics](../cda/overview.md). Indica se gli hit vengono identificati (uniti) o meno dal sistema al momento dell&#39;esecuzione del rapporto. Questa dimensione è utile per comprendere come CDA unisce o comprime correttamente i dati.

## Popolare questa dimensione con i dati

Se hai [Cross-Device Analytics](../cda/overview.md) configurato per una suite di rapporti virtuale, questa dimensione funziona automaticamente.

## Elementi Dimension

Gli elementi del Dimension includono `"Identified"` e `"Unidentified"`.

* **`"Identified"`**: L&#39;hit è mappato a una persona.
* **`"Unidentified"`**: L&#39;hit non è mappato a una persona e non può essere mappato con alcun metodo di attribuzione.
