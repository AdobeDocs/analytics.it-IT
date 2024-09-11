---
description: La pagina Metriche calcolate offre diversi modi per curare le metriche, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferite.
title: Gestione metriche calcolate
feature: Calculated Metrics
exl-id: 32430e77-2450-4672-9c21-255e76802a4c
source-git-commit: d8caeb60097fd5d9e5adef35e2a1c0edc42cdaf7
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 8%

---

# Gestione metriche calcolate

La pagina Metriche calcolate offre diversi modi per curare le metriche, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferite.

La pagina Metriche calcolate mostra tutti i segmenti di tua proprietà e che sono stati condivisi con te. Gli utenti a livello di amministratore possono visualizzare tutte le metriche personalizzate all’interno dell’organizzazione.

<!-- add screenshot -->

## Accedere al gestore delle metriche calcolate

1. In Adobe Analytics, selezionare [!UICONTROL **Componenti**] > [!UICONTROL **Metriche calcolate**].

## Azioni disponibili nel gestore delle metriche calcolate

Nel Gestore metriche calcolate puoi effettuare le seguenti operazioni:

* [Filtrare le metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-filter.md)

* [Contrassegnare le metriche calcolate come preferite](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md)

* [Approvare le metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-approving.md)

* [Assegnare tag alle metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-tagging.md)

* [Condividere le metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-sharing.md)

* Esporta una metrica calcolata in un file CSV.

* [Copiare le metriche calcolate](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-copy.md)

* Elimina metriche calcolate

## Configurare le colonne

Puoi configurare le informazioni visualizzate per ogni metrica calcolata nel gestore delle metriche calcolate configurando le colonne visualizzate.

Per configurare le colonne visibili in Gestione metriche calcolate:

1. In Adobe Analytics, selezionare la scheda **[!UICONTROL Components]**, quindi selezionare **[!UICONTROL Calculated metrics]**.

1. In Gestione metriche calcolate, selezionare l&#39;icona **Personalizza colonne** ![Personalizza colonne icona](assets/customize-columns-icon.png), quindi selezionare le colonne da visualizzare in Gestione metriche calcolate.

   Sono disponibili le seguenti colonne:

   | Titolo colonna | Descrizione |
   |---|---|
   | Preferiti | Visualizza icone a forma di stella accanto a ciascuna metrica calcolata, che consentono di contrassegnare le metriche calcolate come preferite. Per ulteriori informazioni, vedere [Contrassegnare le metriche calcolate come preferite](/help/components/c-calcmetrics/c-workflow/cm-workflow/cm-favorite.md). |
   | Titolo e descrizione | Questi valori vengono forniti nel generatore di metriche calcolate. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il generatore di metriche calcolate. |
   | Suite di rapporti | Indica in quale suite di rapporti la metrica è stata salvata l’ultima volta. |
   | Proprietario | Indica il proprietario della metrica personalizzata. In qualità di non amministratore, puoi visualizzare solo le metriche che possiedi o quelle che sono state condivise con te. |
   | Tag | Mostra i tag applicati alla metrica, da te o da altri utenti che hanno condiviso con te la metrica calcolata. |
   | Condiviso con | Elenca singoli utenti o gruppi (solo amministratori) o tutti coloro (solo amministratori) con cui hai condiviso la metrica calcolata. <p>Quando una metrica calcolata viene condivisa, accanto al nome della metrica calcolata viene visualizzata un’icona di condivisione.</p> |
   | Data di modifica | Indica la data dell’ultima modifica apportata alla metrica personalizzata. |
   | Utilizzate in | Mostra dove sono attualmente utilizzate le metriche calcolate e quante volte in ciascuna area. <p>Ad esempio, se la metrica calcolata viene utilizzata in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**]. <p>Selezionare il valore in questa colonna per visualizzare la suddivisione della posizione di utilizzo delle metriche calcolate, ad esempio [!UICONTROL **Progetti (40)**], [!UICONTROL **Avvisi (2)**]. Inoltre, puoi visualizzare l’elenco degli elementi in cui vengono utilizzate le metriche calcolate. Ad esempio, per visualizzare l&#39;elenco dei progetti in cui vengono utilizzati, seleziona il collegamento [!UICONTROL **Progetti (40)**].</p><p>Ciascuna delle seguenti aree mostra il numero di istanze di metriche calcolate utilizzate in quell’area:</p> <ul><li>[!UICONTROL **Progetti**]<p>Contiene le metriche calcolate create [nel generatore di metriche calcolate](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-all-projects) e disponibili per tutti i progetti.</p></li><li>[!UICONTROL **Componenti ad hoc**]<p>Contiene le metriche calcolate create [come metriche calcolate rapide](/help/analyze/analysis-workspace/components/apply-create-metrics.md#create-calculated-metrics-for-a-single-project) e disponibili solo all&#39;interno di un singolo progetto.</p></li><li>[!UICONTROL **Progetti programmati**]</li><li>[!UICONTROL **Scorecard per dispositivi mobili**]</li><li>[!UICONTROL **Annotazioni**]</li><li>[!UICONTROL **Avvisi**]</li><li>[!UICONTROL **Report Builder**]<p>Selezionando questa opzione viene scaricato un file CSV con le seguenti colonne di dati:</p><ul><li>Nome Report Builder</li><li>Ultimo accesso</li><li>ID utente IMS ultimo accesso</li><li>Nome utente ultimo accesso</li></ul></li></ul><p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Queste informazioni sono disponibili solo per gli amministratori di sistema.</li><li>La colonna [!UICONTROL **Usato in**] non viene visualizzata per impostazione predefinita. [Configura le colonne](#configure-columns) per visualizzarlo.</li><li>Queste informazioni non includono l’utilizzo dall’API o da Data Warehouse.</li><li>Se nella colonna non sono presenti dati per un determinato componente ma è presente la data [!UICONTROL **Ultimo utilizzo**], è possibile che il componente sia stato utilizzato in un&#39;analisi senza essere stato salvato.</li><li>Le informazioni sull’utilizzo sono disponibili a partire da settembre 2023.</li></ul><p>Puoi usare il [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell&#39;organizzazione e per comprenderne meglio il funzionamento.</p> |
   | Ultimo utilizzo | Mostra la data in cui la metrica calcolata è stata utilizzata l’ultima volta in una delle seguenti aree: <ul><li>Avvisi</li><li>Metriche calcolate</li><li>Progetti</li><li>Progetti programmati</li></ul> <p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, prendi in considerazione quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Per alcuni componenti, questa colonna potrebbe non contenere dati se il componente è stato utilizzato l’ultima volta prima di settembre 2023.</li><li>Queste informazioni sono disponibili solo per gli amministratori di sistema.</li></ul><p>Puoi usare il [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) insieme a queste informazioni per tenere traccia di come vengono utilizzati i componenti nell&#39;organizzazione e per comprenderne meglio il funzionamento. |

   {style="table-layout:auto"}
