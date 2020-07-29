---
title: Analisi dei dati interessati dagli eventi
description: Comprendere in che modo i dati influenzati da un evento contribuiscono alla qualità generale dei dati.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 3%

---


# Analisi dei dati interessati dagli eventi

A volte un evento può avere un impatto sulla qualità dei dati nell&#39;organizzazione. Gli esempi includono:

* Un bot che invia dati esterni, come milioni di dollari in entrate
* L&#39;organizzazione ha inviato un aggiornamento al sito Web che ha avuto un impatto negativo sull&#39;implementazione  Analytics
* Altri aspetti che influiscono sulla qualità o completezza dei dati

Se si è verificato un problema di qualità dei dati nel sito, potrebbe essere utile escluderlo dai rapporti per evitare di prendere decisioni aziendali al riguardo. Utilizzare queste sezioni per misurare l&#39;impatto dell&#39;evento sui dati e determinare come si desidera procedere.

## Determinare la causa di un evento

Se non sei sicuro del motivo per cui visualizzi un picco o un rilascio di dati, consulta [Risoluzione dei problemi relativi a picchi/perdite di dati](spikes-drops.md).

## Analizzare ed escludere i dati mediante la segmentazione

 Adobe Analytics offre un modo semplice e affidabile di focalizzare o escludere i dati mediante la segmentazione. Puoi utilizzare le dimensioni dell&#39;intervallo di date all&#39;interno dei segmenti per filtrare o rendere attive quelle date specifiche. See [Exclude specific dates in analysis](segments.md).

## Confronto di un evento con intervalli di date precedenti

Per saperne di più sull&#39;impatto che un evento ha avuto sui dati nel tempo, è possibile utilizzare il confronto delle date in  Analysis Workspace. Questa funzione consente di confrontare i dati giorno per giorno, settimana per settimana o mese per mese per vedere il confronto con gli intervalli precedenti. È quindi possibile utilizzare questo confronto per determinare l&#39;effetto di un evento sulle tendenze. Consultate [Confrontare le date interessate da un evento con gli intervalli](compare-dates.md)precedenti.

## Derivare dati utilizzando metriche calcolate

Dopo aver creato segmenti e utilizzato il confronto delle date, puoi combinare entrambi questi concetti per correggere i dati con tendenze utilizzando metriche calcolate. Includi i segmenti all’interno di una metrica calcolata, quindi moltiplica i giorni interessati per l’offset rilevato durante il confronto delle date. See [Derive data impacted by events](calcmetrics.md).

## Comunicare l’impatto agli utenti nell’organizzazione

Una volta preparato il modo in cui intendete gestire un evento, potete [comunicare con gli utenti dell&#39;organizzazione](communicate.md).  Adobe offre diverse aree all’interno  Analytics in cui è possibile inserire del testo per comunicare agli utenti cosa è accaduto e quali componenti possono utilizzare.

## Video

Questo video illustra i passaggi descritti qui sopra.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Escludere i dati utilizzando la segmentazione
* **2:55**: Confronto di un evento con gli intervalli precedenti
* **8:42**: Derivare dati utilizzando metriche calcolate
* **11:46**: Comunicare l’impatto agli utenti
