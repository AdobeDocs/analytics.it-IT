---
title: Analisi dei dati interessati dagli eventi
description: Comprendere in che modo i dati influenzati da un evento contribuiscono alla qualità generale dei dati.
translation-type: tm+mt
source-git-commit: 65f5fad547558cc9dc481f0eca72873815c9d13a

---


# Analisi dei dati interessati dagli eventi

A volte un evento può avere un impatto sulla qualità dei dati nell&#39;organizzazione. Gli esempi includono:

* Un bot che invia dati esterni, come milioni di dollari in entrate
* L&#39;organizzazione ha inviato un aggiornamento al sito Web che ha avuto un impatto negativo sull&#39;implementazione di Analytics
* Altri aspetti che influiscono sulla qualità o completezza dei dati

Se il sito ha riscontrato problemi di qualità dei dati, problemi di implementazione o altri difetti nei dati, potrebbe essere utile escluderlo dal reporting per evitare di prendere decisioni su dati parziali. Utilizzare queste sezioni per misurare l&#39;impatto dell&#39;evento sui dati e determinare come si desidera procedere.

## Analizzare ed escludere i dati mediante la segmentazione

Adobe Analytics offre un modo semplice e affidabile di focalizzare o escludere i dati mediante la segmentazione. Puoi utilizzare le dimensioni dell&#39;intervallo di date all&#39;interno dei segmenti per filtrare o rendere attive quelle date specifiche. Consulta [Escludere date specifiche nell&#39;analisi](/help/components/c-segmentation/use-cases/exclude-date-range.md) nella guida utente Components (Componenti).

## Confronto di un evento con intervalli di date precedenti

Per saperne di più sull’impatto che un evento ha avuto sui dati nel tempo, puoi utilizzare il confronto delle date in Analysis Workspace. Questa funzione consente di confrontare i dati giorno per giorno, settimana per settimana o mese per mese per vedere il confronto con gli intervalli precedenti. È quindi possibile utilizzare questo confronto per determinare l&#39;effetto di un evento sulle tendenze. Consultate [Confrontare le date interessate da un evento con gli intervalli](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) precedenti nella guida utente Analisi.

## Derivare dati utilizzando metriche calcolate

Dopo aver creato segmenti e utilizzato il confronto delle date, puoi combinare entrambi questi concetti per correggere i dati con tendenze utilizzando metriche calcolate. Includi i segmenti all’interno di una metrica calcolata, quindi moltiplica i giorni interessati per l’offset rilevato durante il confronto delle date. Consulta [Derive data impression by events](/help/components/c-calcmetrics/cm-events.md) (derivare i dati influenzati dagli eventi) nella guida utente Components (Componenti).

## Comunicare l’impatto agli utenti nell’organizzazione

Una volta preparato il modo in cui intendete gestire un evento, potete [comunicare con gli utenti dell&#39;organizzazione](event/event-communicate.md). Adobe offre diverse aree all’interno di Analytics in cui è possibile inserire del testo per comunicare agli utenti cosa è accaduto e quali componenti possono utilizzare.

## Video

Questo video illustra i passaggi descritti qui sopra.

>[!VIDEO](https://video.tv.adobe.com/v/33316?quality=12)

* **0:27**: Escludere i dati utilizzando la segmentazione
* **2:55**: Confronto di un evento con gli intervalli precedenti
* **8:42**: Derivare dati utilizzando metriche calcolate
* **11:46**: Comunicare l’impatto agli utenti
