---
title: Analizzare i dati interessati dagli eventi
description: Scopri in che modo i dati interessati da un evento contribuiscono alla qualità complessiva dei dati.
exl-id: 8d81a432-42d6-4f5d-b66a-bb3af7fc4857
feature: Event
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Analizzare i dati interessati dagli eventi

A volte un evento può influire sulla qualità dei dati all’interno dell’organizzazione. Gli esempi includono:

* Un bot che invia dati aberranti, ad esempio milioni di dollari di ricavi
* La tua organizzazione ha inviato al sito web un aggiornamento che ha avuto un impatto negativo sull’implementazione di Analytics
* Altri problemi che influiscono sulla qualità o la completezza dei dati

Se nel tuo sito si sono verificati problemi di qualità dei dati, puoi escluderlo dai rapporti per evitare di prendere decisioni commerciali al riguardo. Utilizza queste sezioni per misurare l’impatto dell’evento sui dati e determinare come procedere.

## Determinare la causa di un evento

Se non sei sicuro del motivo per cui visualizzi un picco o un calo nei dati, consulta [Risoluzione dei problemi relativi a picchi/perdite nei dati](spikes-drops.md).

## Analizzare ed escludere dati utilizzando la segmentazione

Adobe Analytics offre un modo semplice e affidabile di concentrarsi o escludere i dati utilizzando la segmentazione. Puoi utilizzare dimensioni di intervallo di date all’interno di segmenti per filtrare o evidenziare tali date specifiche. Vedi [Escludere date specifiche nell&#39;analisi](segments.md).

## Confrontare un evento con intervalli di date precedenti

Per ulteriori informazioni sull’impatto di un evento sui dati nel tempo, puoi utilizzare il confronto delle date in Analysis Workspace. Questa funzione consente di confrontare i dati giorno per giorno, settimana per settimana o mese per mese per vedere come si confrontano con gli intervalli precedenti. Puoi quindi utilizzare questo confronto per determinare in che misura un evento influisce sulle tendenze. Vedi [Confrontare le date interessate da un evento con intervalli precedenti](compare-dates.md).

## Derivare dati utilizzando metriche calcolate

Dopo aver creato i segmenti e aver utilizzato il confronto delle date, puoi combinare entrambi questi concetti per correggere i dati con tendenze utilizzando metriche calcolate. Includi i segmenti all’interno di una metrica calcolata, quindi moltiplica i giorni interessati per l’offset rilevato durante il confronto delle date. Vedi [Derivazione dei dati interessati dagli eventi](calcmetrics.md).

## Comunicare l’impatto sugli utenti dell’organizzazione

Una volta preparati a gestire un evento, puoi [comunicare con gli utenti della tua organizzazione](communicate.md). Adobe offre diverse aree all’interno di Analytics in cui puoi inserire del testo per comunicare agli utenti cosa è successo e quali componenti possono utilizzare.

## Video

>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analizzare e comunicare le varianti dei tuoi dati](https://video.tv.adobe.com/v/33316?quality=12&learn=on){target="_blank"} per vedere un video dimostrativo.

* **0:27**: escludi dati tramite segmentazione
* **2:55**: confrontare un evento con intervalli precedenti
* **8:42**: derivare dati utilizzando metriche calcolate
* **11:46**: comunicare l&#39;impatto agli utenti

>[!ENDSHADEBOX]


