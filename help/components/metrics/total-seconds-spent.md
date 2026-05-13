---
title: Totale secondi trascorsi
description: Numero totale aggregato di secondi trascorsi sull’elemento dimensione.
feature: Metrics
exl-id: 02302982-ce8c-44e9-9967-0a4f226f5e9e
TQID: https://experienceleague.adobe.com/FQ5FGTOKnJph7C0jWwbcAHA31yUwz7ewQRPykUD6R0E
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 5%

---

# Totale secondi trascorsi

La [metrica](overview.md) &quot;Totale secondi trascorsi&quot; mostra il numero aggregato di secondi trascorsi da un visitatore su un dato elemento della dimensione. Questa metrica è utile quando si desidera la quantità di tempo trascorso su un dato elemento dimensionale e non si desidera calcolare la media come fanno altre metriche tempo trascorso.

In Report Builder, questa metrica è denominata &quot;Tempo totale trascorso&quot;.

## Come è calcolata questa metrica

Questa metrica utilizza i seguenti passaggi per misurare il calcolo:

1. Per un dato hit, controlla la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Sono conteggiati sia gli hit di visualizzazione pagina che quelli di tracciamento dei collegamenti.
3. La quantità di secondi trascorsi tra i due hit contribuisce all’elemento dimensionale.

Le variabili persistenti, ad esempio [eVar](../dimensions/evar.md), vengono conteggiate in base al totale dei secondi trascorsi. Le variabili di traffico, ad esempio [props](../dimensions/prop.md), includono i secondi trascorsi nelle successive chiamate di tracciamento dei collegamenti.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una successiva richiesta di immagine per misurare il tempo trascorso. Questo concetto si applica anche alle visite consistenti in un singolo hit (un mancato recapito).

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
