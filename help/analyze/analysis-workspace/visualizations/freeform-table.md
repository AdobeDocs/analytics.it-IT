---
title: Tabella a forma libera
description: Informazioni sulle tabelle a forma libera e sul generatore di tabelle a forma libera
translation-type: tm+mt
source-git-commit: ce06a5ca2caeb266c729947c76e93c611502e6d9

---


# Tabella a forma libera

In Analysis Workspace, una tabella a forma libera non è solo una tabella di dati, ma anche una visualizzazione interattiva. Puoi trascinare una combinazione di [componenti](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html) nelle righe e nelle colonne per creare una tabella personalizzata per l’analisi. Man mano che ciascun componente viene eliminato, la tabella viene aggiornata immediatamente per consentire un&#39;analisi rapida.

È possibile personalizzare la tabella in diversi modi:

* **Righe**
   * Prima dell&#39;impaginazione è possibile visualizzare fino a 400 righe ciascuna riga di quota. È possibile inserire più righe in un singolo schermo regolando la densità [di](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html)visualizzazione del progetto.
   * Le righe possono essere suddivise per componenti aggiuntivi. Per suddividere più righe alla volta, è sufficiente selezionare più righe e quindi trascinare il componente successivo sopra le righe selezionate. Ulteriori informazioni sulle [suddivisioni](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html).
   * Le righe possono essere [filtrate](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/pagination-filtering-sorting.html) per visualizzare un set ridotto di elementi. Ulteriori impostazioni sono disponibili in Impostazioni [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/table-settings.html)riga.

* **Colonne**
   * I componenti possono essere impilati all’interno di colonne per creare metriche segmentate, analisi interscheda e altro ancora.
   * La vista di ogni colonna può essere regolata sotto le impostazioni [della](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html)colonna.
   * Sono disponibili diverse azioni tramite il menu di scelta rapida [accessibile](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html). Il menu fornisce azioni diverse a seconda se si fa clic sull&#39;intestazione della tabella, sulle righe o sulle colonne.

## Generatore tabella a forma libera

Se prima preferite aggiungere diversi componenti alla tabella, quindi eseguire il rendering dei dati, potete attivare il Generatore di tabelle a forma libera. Con il generatore abilitato, puoi trascinare e rilasciare dimensioni, suddivisioni, metriche e segmenti per creare tabelle che rispondano a domande più complesse. I dati non verranno aggiornati al volo, ma verranno aggiornati dopo aver fatto clic **[!UICONTROL Build]**.

Generatore di tabelle è un’opzione che consente di risparmiare tempo quando si ha una domanda complessa da porre ai dati e si ha un’idea della tabella da creare per rispondere alla domanda. Altri vantaggi del generatore di tabelle includono la possibilità di:

* Disporre la tabella nel formato esatto desiderato, senza dover attendere il rendering di ogni azione.
* È possibile eseguire rapidamente fino a 4 livelli di analisi approfondite.
* Definire le impostazioni Riga e Suddivisione per ogni riga e colonna di tabella.
* **[!UICONTROL Breakdown by Position]**per ogni livello della tabella per impostazione predefinita (nelle tabelle a forma libera tradizionali, l’impostazione predefinita è**[!UICONTROL Breakdown by Item]**.)
* Ordinare manualmente le righe statiche nella tabella. Ad esempio, per visualizzare le righe delle metriche in un determinato ordine.
* Visualizzare in anteprima il formato della tabella prima di eseguire il rendering dei dati reali.

Guardate il Generatore di tabelle a forma libera in azione [qui](https://youtu.be/GUMWiJAmMGI).

## Esporta dati tabella a forma libera

I dati contenuti in una tabella a forma libera possono essere copiati da Analysis Workspace in alcuni modi:

* Fare clic con il pulsante destro del mouse sull&#39;intestazione della tabella e selezionare **[!UICONTROL Copy to Clipboard]**. Verrà esportata la tabella completa (visibile).
* Evidenziare celle specifiche nella tabella, fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Copy to Clipboard]**oppure utilizzare il tasto di scelta rapida Ctrl + C.
* **[!UICONTROL Project > Download CSV]**. In questo modo tutte le tabelle visibili nel progetto verranno esportate come CSV.
