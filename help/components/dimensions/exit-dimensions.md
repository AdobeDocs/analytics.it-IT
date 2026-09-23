---
title: Dimensioni di uscita
description: Elenca le dimensioni di uscita e il relativo utilizzo.
keywords: chiudi pagina, esci dalla sezione del sito, esci dal server, esci da insight personalizzato
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
TQID: https://experienceleague.adobe.com/YRjvhW8OzBlip9ok0-1D4rYSljkccpIAlDkqCQv7nyo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 6%
---
# Dimensioni di uscita

>[!BEGINSHADEBOX]

*Questa pagina della Guida descrive il funzionamento delle uscite come [dimensione](overview.md). Per informazioni sul funzionamento delle uscite come metrica, vedi la metrica [Uscite](../metrics/exits.md).*

>[!ENDSHADEBOX]

Le dimensioni di uscita registrano l’ultimo elemento dimensione e lo applicano retroattivamente a tutti gli hit nella visita. Le dimensioni di uscita sono disponibili per tutte le variabili con percorsi abilitati in [Variabili di traffico](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nelle impostazioni della suite di rapporti.

## Popolare le dimensioni di uscita con i dati

Una determinata dimensione di uscita è basata sulla variabile di traffico associata. Adobe deriva ogni dimensione di uscita dall’ultimo valore visualizzato per tale variabile durante la visita; non esiste una variabile dedicata da impostare. Se la variabile non-exit contiene dati, anche la dimensione di uscita associata contiene dati. Se le variabili di traffico contengono dati, per le dimensioni di uscita non sono necessarie modifiche di implementazione.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dall’ultimo hit del visitatore) |
| **Campo Web SDK / XDM** | Nessuno (derivato dall’ultimo hit del visitatore) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Visita |

## Elementi dimensionali

Poiché le variabili di uscita sono in genere basate su stringhe personalizzate nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. I valori in una determinata dimensione di uscita corrispondono agli elementi dimensionali nella dimensione non di uscita associata. Ad esempio, gli elementi dimensionali nella dimensione &quot;Pagina di uscita&quot; contengono elementi dimensionali simili nella dimensione &quot;Pagina&quot;.
