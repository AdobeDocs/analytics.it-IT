---
title: Tabella a forma libera
description: Informazioni sulle tabelle a forma libera e sul generatore di tabelle a forma libera
translation-type: ht
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# Tabella a forma libera

In Analysis Workspace, una tabella a forma libera non è semplicemente una tabella di dati, ma è soprattutto una visualizzazione interattiva. Puoi trascinare una combinazione di [componenti](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) nelle righe e nelle colonne per creare una tabella personalizzata per l’analisi. Man mano che ciascun componente viene rilasciato, la tabella viene aggiornata immediatamente in modo da poter eseguire analisi rapide.

Puoi personalizzare la tabella in diversi modi:

* **Righe**
   * Prima dell’impaginazione ogni riga delle dimensioni può visualizzare fino a 400 righe. È possibile inserire più righe in una singola schermata regolando la [densità di visualizzazione](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) del progetto.
   * Le righe possono essere suddivise per componenti aggiuntivi. Per suddividere più righe alla volta, seleziona semplicemente più righe e quindi trascina il componente successivo sopra le righe selezionate. Scopri di più sulle [suddivisioni](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Le righe possono essere [filtrate](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) per visualizzare un set ridotto di elementi. Sono disponibili altre impostazioni in [Impostazioni riga](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html).

* **Colonne**
   * I componenti possono essere impilati all’interno di colonne per creare metriche segmentate, analisi incrociate e altro ancora.
   * La visualizzazione di ogni colonna può essere regolata nelle [impostazioni della colonna](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html).
   * Sono disponibili diverse azioni tramite il [menu di scelta rapida](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). A seconda dell’elemento su cui fai clic (intestazione della tabella, righe o colonne), il menu fornisce azioni diverse.

## Generatore di tabelle a forma libera

Se prima preferisci aggiungere diversi componenti alla tabella e quindi eseguire il rendering dei dati, puoi attivare il Generatore di tabelle a forma libera. Con il generatore abilitato, puoi trascinare e rilasciare più dimensioni, raggruppamenti, metriche e segmenti per creare tabelle che rispondano a esigenze più complesse. I dati non verranno aggiornati istantaneamente, ma solo dopo aver fatto clic su **[!UICONTROL Build]** (Crea).

Il Generatore di tabelle è un’opzione che consente di risparmiare tempo quando hai complesse richieste da estrapolare tramite i dati, e hai chiare idee su come creare la tabella affinché fornisca le giuste risposte alle tue domande. Altri vantaggi del generatore di tabelle includono la possibilità di:

* Disporre la tabella esattamente nel formato desiderato, senza dover attendere i tempi di rendering per ogni azione.
* Esegui rapidamente fino a 4 livelli di raggruppamento.
* Definisci le impostazioni di riga e raggruppamento per ogni riga della tabella e colonna delle dimensioni.
* **[!UICONTROL Breakdown by Position]** (Suddivisione per posizione) per ogni livello della tabella per impostazione predefinita (nelle tabelle a forma libera tradizionali, l’impostazione predefinita è **[!UICONTROL Breakdown by Item]** (Suddivisione per elemento)).
* Ordina manualmente le righe statiche nella tabella. Ad esempio, per visualizzare le righe di metrica in un determinato ordine.
* Visualizza in anteprima il formato della tabella prima di eseguire il rendering dei dati reali.

Osserva il Generatore di tabelle a forma libera in azione [qui](https://youtu.be/GUMWiJAmMGI).

## Esportare i dati dalla tabella a forma libera

I dati contenuti in una tabella a forma libera possono essere copiati da Analysis Workspace in alcuni modi:

* Fai clic con il pulsante destro del mouse su un’intestazione di tabella e seleziona **[!UICONTROL Copy to Clipboard]** (Copia negli Appunti). Verrà esportata la tabella completa (visibile).
* Per evidenziare celle specifiche nella tabella, fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Copy to Clipboard]** (Copia negli Appunti), oppure usa la combinazione di tasti Ctrl + C.
* **[!UICONTROL Project > Download CSV]** (Progetto > scarica CSV). In questo modo tutte le tabelle visibili nel progetto verranno esportate come CSV.
