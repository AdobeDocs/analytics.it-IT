---
title: Ricerche dinamiche
description: Scopri cosa sono le ricerche dinamiche e come abilitarle. Include gestori, attributi mobili e tipi di sistemi operativi.
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# Ricerche dinamiche

Le ricerche dinamiche consentono di ricevere file di ricerca aggiuntivi nel feed di dati, altrimenti non disponibili. Questa impostazione consente di inviare le seguenti tabelle di ricerca con ciascun file di feed dati:

* **Nome gestore**: fornisce contesto aggiuntivo per `carrier` colonna. Il nome del file incluso è `carrier.tsv`.
* **Attributi mobili**: fornisce contesto aggiuntivo per `mobile_id` , incluse tutte le funzioni tracciate per ciascun dispositivo mobile. Il nome del file incluso è `mobile_attributes.tsv`.
* **Tipo di sistema operativo**: fornisce un contesto alternativo per `os` colonna. Entrambi `operating_systems.tsv` e `operating_system_type.tsv` utilizzare il `os` come chiave, ma solo `operating_system_type.tsv` è una ricerca dinamica.

## Abilita ricerche dinamiche

Se desideri ricevere i file di ricerca menzionati, devi soddisfare tutti i seguenti prerequisiti:

* La colonna chiave deve essere inclusa nel feed di dati.
   * Per `carrier.tsv`, è necessario includere `carrier`.
   * Per `mobile_attributes.tsv`, è necessario includere `mobile_id`.
   * Per `operating_system_type.tsv`, è necessario includere `os`.
* Le colonne seguenti devono essere **escluso**. Se una di queste colonne è inclusa nel feed di dati, allora il `mobile_attributes.tsv` la ricerca dinamica non è inclusa.
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

Una volta che il feed di dati soddisfa i requisiti di inclusione ed esclusione delle colonne, contatta l’Assistenza clienti con l’ID del feed di dati e richiedi per abilitare le ricerche dinamiche.

## Riferimento intestazione ricerca

Le intestazioni di colonna per questi file di ricerca non cambiano nel tempo, pertanto le intestazioni non vengono incluse in ciascun file di feed dati. Utilizza queste intestazioni di colonna come riferimento o scarica le rispettive `.tsv` file.

+++**Nome gestore**
Scarica [carrier_headers.tsv](assets/carrier_headers.tsv) o fai riferimento alle intestazioni di seguito.

`carrier`
`Carrier Name`
+++

+++**Attributi mobili**
Scarica [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) o fai riferimento alle intestazioni di seguito.

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
Scarica [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) o fai riferimento alle intestazioni di seguito.

`os`
`Operating System Type`
+++
