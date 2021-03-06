---
description: Utilizzare il connettore dati Dynamic Signal VoiceStorm con Adobe Analytics.
title: Utilizzo dell'integrazione
uuid: c902a868-20a7-42df-8a79-8e154608f299
translation-type: tm+mt
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: tm+mt
source-wordcount: '428'
ht-degree: 2%

---


# Utilizzo dell&#39;integrazione{#using-the-integration}

Una volta implementata, puoi iniziare a utilizzare le funzionalità aggiuntive offerte da questa integrazione.

**Nota**: Possono essere necessarie 24-48 ore per iniziare a visualizzare alcuni dei dati del segnale dinamico nei rapporti di Adobe Analytics.

Le azioni seguenti producono un valore aggiunto da questa integrazione in Adobe Analytics.

## Visualizzazione delle metriche del traffico e della conversione per Dimension di segnale dinamici{#viewing-traffic-and-conversion-metrics-by-dynamic-signal-dimensions}

Esempio di report in Adobe Analytics.

Questa integrazione fornisce nuove dimensioni che diventano disponibili come rapporti di Adobe Analytics. Il rapporto seguente è un esempio di analisi sia delle visite che di una metrica di conversione (Registrazioni) suddivisa per Titolo articolo.

![](assets/examplereport.png)

## Segmentazione per Dimension di segnale dinamici{#segmenting-by-dynamic-signal-dimensions}

Esempi di segmenti basati sulle dimensioni del segnale dinamico.

Una caratteristica principale di questa integrazione è la capacità di creare segmenti Adobe Analytics basati sulle dimensioni di reporting integrate. Ad esempio, puoi creare un segmento che include solo le visite provenienti da una specifica community VoiceStorm. Potresti chiamarlo &quot;Visite guidate da SuperFans&quot;. Questa definizione del segmento potrebbe avere un aspetto simile al seguente.

![](assets/segment1.png)

![](assets/segment2.png)

## Dimension di reporting integrati{#integrated-reporting-dimensions}

Elenca le dimensioni di reporting del segnale dinamico incluse in questa integrazione.

| Dimensione | Descrizione |
|---|---|
| Tipo di canale | Il social network (o piattaforma di blog) in cui l&#39;utente ha condiviso un post della community. Gli utenti possono condividere un post su più canali. I clic e altre attività sono segmentati per canale. Questo campo visualizza Facebook, Twitter, ecc. per vedere quale tipo di canale sta guidando l’attività. |
| ID articolo | L’ID articolo identifica in modo univoco ogni elemento di contenuto nella community del segnale dinamico. |
| Tipo di origine | Questo campo indica se il post è stato creato da un &quot;Membro&quot; o dal &quot;Marchio&quot;. In entrambi i casi il contenuto può essere creato manualmente nell’applicazione o importato da un feed esterno. |
| Nome utente | Utente che ha condiviso un post sui propri social network, generando click-through al sito. |
| ID sorgente | L&#39;ID sorgente identifica in modo univoco il creatore (o l&#39;autore) del post condiviso. Spesso si tratta di un membro specifico o di un feed esterno. |
| ID utente | L’ID utente identifica in modo univoco un utente (ad es. un membro) nella community del segnale dinamico. In questo caso, l&#39;utente è il condivisore che ha condiviso il post sui propri social network. |
| Nome origine | L&#39;origine è il creatore (o autore) del post condiviso. Nella maggior parte dei casi, si tratta di un membro della comunità o di un feed esterno. |
| Titolo articolo | Il titolo del post condiviso che ha generato fa clic sul sito. |
| Nome community | Nome della community di Dynamic Signal. |

