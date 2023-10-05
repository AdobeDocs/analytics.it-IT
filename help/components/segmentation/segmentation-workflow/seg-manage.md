---
description: Il Gestore segmenti offre diversi modi per curare i segmenti, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.
title: Gestire segmenti (Gestore segmenti)
feature: Segmentation
exl-id: be182a55-23cb-415f-a7d0-3c1efeead1a1
source-git-commit: 9a6c2e7c2f83882f6df630f975b0c44e75a2ed7a
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 31%

---

# Gestore segmenti

Il Gestore segmenti offre diversi modi per curare i segmenti, ad esempio condividere, filtrare, assegnare tag, approvare, copiare, eliminare e contrassegnare come preferiti.

Il Gestore segmenti di Analytics mostra tutti i segmenti di tua proprietà e quelli che sono stati condivisi con te. Gli utenti a livello di amministratore possono visualizzare tutti i segmenti dell’organizzazione. Questa panoramica presenta l’interfaccia utente e le funzionalità del Gestore segmenti.

![Gestore segmenti](assets/segments-manager.png)

## Accedere al Gestore segmenti

1. In Adobe Analytics, seleziona la **[!UICONTROL Components]** , quindi seleziona **[!UICONTROL Segments]**.

   Oppure

   In un rapporto esistente, seleziona l’icona Segmenti ![](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) nel menu di navigazione a sinistra, seleziona quindi **[!UICONTROL Manage]**.

## Azioni disponibili nel Gestore segmenti

Nel Gestore segmenti puoi effettuare le seguenti operazioni:

* [Filtrare segmenti](/help/components/segmentation/segmentation-workflow/t-seg-filter.md)

* [Contrassegnare i segmenti come preferiti](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md)

* [Approvare segmenti](/help/components/segmentation/segmentation-workflow/seg-approve.md)

* [Assegnare tag ai segmenti](/help/components/segmentation/segmentation-workflow/seg-tag.md)

* [Condividere segmenti](/help/components/segmentation/segmentation-workflow/t-seg-share.md)

* Esporta un segmento in un file CSV.

* [Copiare segmenti](/help/components/segmentation/segmentation-workflow/seg-copy.md)

* [Eliminare segmenti](/help/components/segmentation/segmentation-workflow/seg-delete.md)

## Configurare le colonne

Puoi configurare le informazioni visualizzate per ciascun segmento nel Gestore segmenti configurando le colonne visualizzate.

Per configurare le colonne visibili nel Gestore segmenti:

1. In Adobe Analytics, seleziona la **[!UICONTROL Components]** , quindi seleziona **[!UICONTROL Segments]**.

1. Nel Gestore segmenti, seleziona la **Personalizza colonne** icona ![Icona Personalizza colonne](assets/customize-columns-icon.png), quindi seleziona le colonne da visualizzare nel Gestore segmenti.

   Sono disponibili le seguenti colonne:

   | Titolo colonna | Descrizione |
   |---|---|
   | Titolo e descrizione | Questi valori vengono forniti nel Generatore di segmenti. Per modificare il titolo e la descrizione, seleziona il collegamento del titolo per aprire il Generatore di segmenti. |
   | Preferiti | Visualizza icone a forma di stella accanto a ciascun segmento, che consentono di contrassegnare i segmenti come preferiti. Per ulteriori informazioni, consulta [Contrassegnare i segmenti come preferiti](/help/components/segmentation/segmentation-workflow/t-seg-favorite.md). |
   | di Report Suite Manager | Questa colonna indica in quale suite di rapporti il segmento è stato salvato l’ultima volta. |
   | Proprietario | Indica il proprietario del segmento. In quanto utente non amministratore, puoi visualizzare solo i segmenti che possiedi o quelli che sono stati condivisi con te. |
   | Tag (non selezionato nel selettore colonna, di conseguenza la colonna non viene visualizzata) | I tag applicati al segmento da te o da altri utenti che lo hanno condiviso con te. |
   | Condiviso con | Elenca singoli utenti o gruppi (solo amministratori) o tutti coloro (solo amministratori) con cui hai condiviso il segmento. <p>Quando un segmento viene condiviso da te o con te, accanto al nome del segmento viene visualizzata un’icona di condivisione.</p> |
   | Data di modifica | Mostra la data dell’ultima modifica apportata al segmento. |
   | Utilizzato in | Mostra quanti componenti il segmento è attualmente utilizzato in. <p>Ad esempio, se il segmento viene utilizzato in 40 progetti e 2 avvisi, il valore di questa colonna viene visualizzato come [!UICONTROL **42 componenti**].</p> <p>Seleziona il valore in questa colonna per visualizzare il raggruppamento della posizione in cui viene utilizzato il segmento (ad esempio, [!UICONTROL **Progetti (40)**], [!UICONTROL **Avvisi (2)**]).</p><p>I segmenti possono essere utilizzati in uno qualsiasi dei seguenti tipi di componenti:</p> <ul><li>Avvisi</li><li>Progetti</li><li>Progetti programmati</li><li>Metriche calcolate</li></ul><p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, tieni presente quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Il [!UICONTROL **Utilizzato in**] non viene visualizzata per impostazione predefinita. [Configurare le colonne](#configure-columns) per visualizzarlo.</li><li>Se non sono presenti dati in questa colonna per un determinato componente, ma è presente un [!UICONTROL **Ultimo utilizzo**] data, il componente potrebbe essere stato utilizzato in un’analisi senza essere stato salvato.</li></ul><p>È possibile utilizzare [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) oltre a queste informazioni, ti aiuteranno a tenere traccia di come i componenti vengono utilizzati nella tua organizzazione e a comprenderne meglio il funzionamento.</p> |
   | Ultimo utilizzo | Mostra la data dell’ultimo utilizzo del segmento in uno dei seguenti tipi di componenti: <ul><li>Avvisi</li><li>Metriche calcolate</li><li>Progetti</li><li>Progetti programmati</li><li>Segmenti</li></ul> <p>Queste informazioni possono essere utili per determinare se un componente è utile per gli utenti dell’organizzazione, dove viene utilizzato e se deve essere eliminato o modificato.</p><p>Quando visualizzi questa colonna, tieni presente quanto segue:</p><ul><li>Queste informazioni non includono l’utilizzo da API, Report Builder o Data Warehouse.</li><li>Per alcuni componenti, questa colonna potrebbe non contenere dati se il componente è stato utilizzato l’ultima volta prima di settembre 2023.</li></ul><p>È possibile utilizzare [Dizionario dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md) oltre a queste informazioni, ti aiuteranno a tenere traccia di come i componenti vengono utilizzati nella tua organizzazione e a comprenderne meglio il funzionamento. |

   {style="table-layout:auto"}

## Video introduttivo {#section_B3C5DA22DC5248DBA17C56E03DA2D4F2}

Questo [video di su Adobe Analytics](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/components/segmentation/segment-management-and-sharing.html) offre una breve panoramica sull’utilizzo del Gestore segmenti.


