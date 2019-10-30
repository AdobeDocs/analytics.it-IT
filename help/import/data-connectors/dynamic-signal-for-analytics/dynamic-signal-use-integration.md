---
description: nulle
seo-description: nulle
seo-title: Utilizzo dell'integrazione
solution: Analytics
title: Utilizzo dell'integrazione
uuid: c902a868-20a7-42df-8a79-8e154608f299
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Utilizzo dell'integrazione{#using-the-integration}

Una volta implementata, potete iniziare a utilizzare le funzionalità aggiuntive offerte da questa integrazione.

**Nota**: Potrebbero essere necessarie 24-48 ore per iniziare a visualizzare alcuni dei dati del segnale dinamico nel reporting di Adobe Analytics.

Le azioni seguenti producono un valore aggiunto da questa integrazione in Adobe Analytics.

## Visualizzazione delle metriche di traffico e conversione per dimensioni del segnale dinamico{#viewing-traffic-and-conversion-metrics-by-dynamic-signal-dimensions}

Esempio di report in Adobe Analytics.

Questa integrazione fornisce nuove dimensioni che diventano disponibili come rapporti di Adobe Analytics. Il rapporto seguente è un esempio di analisi sia delle visite che di una metrica di conversione (Registrazioni) che è stata suddivisa per Titolo articolo.

![](assets/examplereport.png)

## Segmentazione per dimensioni del segnale dinamico{#segmenting-by-dynamic-signal-dimensions}

Esempi di segmenti basati sulle dimensioni del segnale dinamico.

Una caratteristica principale di questa integrazione è la capacità di creare segmenti Adobe Analytics basati sulle dimensioni di reporting integrate. Ad esempio, puoi creare un segmento che include solo Visite provenienti da una specifica community VoiceStorm. Potete chiamare questo "Visite guidate da SuperFans". Questa definizione del segmento potrebbe essere simile a quella riportata di seguito.

![](assets/segment1.png)

![](assets/segment2.png)

## Dimensioni di reporting integrate{#integrated-reporting-dimensions}

Elenca le dimensioni di reporting del segnale dinamico incluse con questa integrazione.

| Dimensione | Descrizione |
|---|---|
| Tipo canale | Il social network (o piattaforma di blog) in cui l'utente ha condiviso un post della community. Gli utenti possono condividere un post su più canali. I clic e altre attività sono segmentati per canale. Questo campo visualizza Facebook, Twitter, ecc. per vedere quale tipo di canale sta guidando l'attività. |
| ID articolo | L'ID articolo identifica in modo univoco ogni elemento di contenuto nella community del segnale dinamico. |
| Tipo origine | Questo campo indica se il post è stato creato da un "membro" o dal "marchio". In entrambi i casi, il contenuto può essere creato manualmente nell’applicazione o importato da un feed esterno. |
| Nome utente | Utente che ha condiviso un post sui propri social network, generando click-through al sito. |
| ID origine | L'ID origine identifica in modo univoco l'autore (o l'autore) del post condiviso. Questo è spesso un membro specifico o un feed esterno. |
| ID utente | L'ID utente identifica in modo univoco un utente (ad es. un membro) nella comunità di segnali dinamici. In questo caso, l'utente è il condivisore che ha condiviso il post sui propri social network. |
| Nome origine | L'origine è il creatore (o autore) del post condiviso. Nella maggior parte dei casi, si tratta di un membro della comunità o di un feed esterno. |
| Titolo articolo | Il titolo del post condiviso che ha generato fa clic di nuovo sul sito. |
| Nome community | Nome della community di segnali dinamici. |

