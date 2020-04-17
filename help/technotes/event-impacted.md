---
title: Analisi dei dati interessati dagli eventi
description: Comprendere in che modo i dati influenzati da un evento contribuiscono alla qualità generale dei dati.
translation-type: tm+mt
source-git-commit: e3360e15de14f594e62b4be6316f8b095091ec1f

---


# Analisi dei dati interessati dagli eventi

A volte un evento può avere un impatto sulla qualità dei dati nell&#39;organizzazione. Gli esempi includono:

* Un bot che invia dati esterni, come milioni di dollari in entrate
* L&#39;organizzazione ha inviato un aggiornamento al sito Web che ha avuto un impatto negativo sull&#39;implementazione di Analytics
* Consente di uscire dalla qualità del server, sia alla fine dell&#39;azienda che alla fine di Adobe

Se il sito ha riscontrato problemi di qualità dei dati, problemi di implementazione o altri difetti nei dati, potrebbe essere utile escluderlo dal reporting per evitare di prendere decisioni su dati parziali. Utilizzare queste sezioni per misurare l&#39;impatto dell&#39;evento sui dati e determinare come si desidera procedere.

## Analizzare ed escludere i dati mediante la segmentazione

Adobe Analytics offre un modo semplice e affidabile di focalizzare o escludere i dati mediante la segmentazione. Puoi utilizzare le dimensioni dell&#39;intervallo di date all&#39;interno dei segmenti per filtrare o rendere attive quelle date specifiche. Consulta [Escludere date specifiche nell&#39;analisi](/help/components/c-segmentation/use-cases/exclude-date-range.md) nella guida utente Components (Componenti).

## Confronto di un evento con intervalli di date precedenti

Per saperne di più sull’impatto che un evento ha avuto sui dati nel tempo, puoi utilizzare il confronto delle date in Analysis Workspace. Questa funzione consente di confrontare i dati giorno per giorno, settimana per settimana o mese per mese per vedere il confronto con gli intervalli precedenti. È quindi possibile utilizzare questo confronto per determinare l&#39;effetto di un evento sulle tendenze. Consultate [Confrontare le date interessate da un evento con gli intervalli](/help/analyze/analysis-workspace/components/calendar-date-ranges/compare-event.md) precedenti nella guida utente Analisi.

## Utilizzo di un evento del calendario in Reporting e analisi

Se utilizzate Reporting e analisi, potete utilizzare un evento [del](/help/components/t-calendar-event.md) calendario per evidenziare i giorni interessati in qualsiasi rapporto con tendenze. Questo metodo non si applica ad Analysis Workspace.

1. Passa a **[!UICONTROL Components]** > **[!UICONTROL Calendar events]**.
2. Inserite il titolo, l’intervallo di date e il testo della nota desiderati.
3. Fai clic su **[!UICONTROL Save]**.

![Evento calendario](assets/exclude_calendar_event.jpg)
