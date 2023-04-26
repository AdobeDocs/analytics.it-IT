---
title: Ricerche dinamiche
description: Scopri cosa sono le ricerche dinamiche e come attivarle. Include i vettori, gli attributi mobili e i tipi di sistemi operativi.
source-git-commit: b6084fc34165ea602fce616e13b3adfcd7bdfdbd
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Ricerche dinamiche

Le ricerche dinamiche consentono di ricevere ulteriori file di ricerca nel feed di dati, altrimenti non sono disponibili. Questa impostazione consente di inviare le seguenti tabelle di ricerca con ciascun file di feed dati:

* **Nome del vettore**: Fornisce contesto aggiuntivo per `carrier` colonna. Il nome file incluso è `carrier.tsv`.
* **Attributi di Mobile**: Fornisce contesto aggiuntivo per `mobile_id` , comprese tutte le funzioni tracciate per ciascun dispositivo mobile. Il nome file incluso è `mobile_attributes.tsv`.
* **Tipo di sistema operativo**: Fornisce un contesto alternativo per `os` colonna. Entrambi `operating_systems.tsv` e `operating_system_type.tsv` utilizza `os` come chiave, ma solo `operating_system_type.tsv` è una ricerca dinamica.

## Abilita ricerche dinamiche

Se desideri ricevere i file di ricerca menzionati, devi soddisfare tutti i seguenti prerequisiti:

* La colonna chiave deve essere inclusa nel feed di dati.
   * Per `carrier.tsv`, devi includere `carrier`.
   * Per `mobile_attributes.tsv`, devi includere `mobile_id`.
   * Per `operating_system_type.tsv`, devi includere `os`.
* Le colonne seguenti devono essere **esclusi**. Se una di queste colonne è inclusa nel feed di dati, le tabelle di ricerca aggiuntive non sono incluse.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Una volta che il feed di dati soddisfa i requisiti di inclusione ed esclusione delle colonne, contatta l’Assistenza clienti con l’ID del feed di dati e richiedi per abilitare le ricerche dinamiche.

## Riferimento intestazione di ricerca

Le intestazioni di colonna per questi file di ricerca non cambiano nel tempo, pertanto le intestazioni non sono incluse in ogni file di feed di dati. Usa queste intestazioni di colonna come riferimento o scarica le rispettive `.tsv` file.

+++**Nome del vettore**
Scarica [carrier_headers.tsv](assets/carrier_headers.tsv) o fare riferimento alle intestazioni sottostanti.

`carrier`
`Carrier Name`
+++

+++**Attributi di Mobile**
Scarica [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) o fare riferimento alle intestazioni sottostanti.

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**Tipo di sistema operativo**
Scarica [operations_system_type_headers.tsv](assets/operating_system_type_headers.tsv) o fare riferimento alle intestazioni sottostanti.

`os`
`Operating System Type`
+++