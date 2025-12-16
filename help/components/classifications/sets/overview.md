---
title: Panoramica sui set di classificazione
description: Scopri come utilizzare i set di classificazione per gestire i dati di classificazione. Scopri le differenze tra i set di classificazione e le classificazioni legacy.
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 0f80bb314c8e041a98af26734d56ab364c23a49b
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 10%

---

# Panoramica sui set di classificazione

I set di classificazione forniscono un’unica interfaccia per gestire classificazioni e regole. Questo flusso di lavoro combina la creazione di classificazioni in [Impostazioni suite di rapporti](/help/admin/tools/manage-rs/report-suites-admin.md) con la [Importazione classificazioni](/help/components/classifications/sets/manage/set-manager.md). Il risultato è un’unica interfaccia intuitiva per creare e gestire i dati di classificazione.


## Set di classificazione e classificazioni legacy

La differenza principale tra i set di classificazione e le classificazioni legacy è che i set di classificazione combinano tutte le funzionalità in un’unica interfaccia, in cui le classificazioni legacy si basano su tre interfacce.

### Classificazioni legacy

![Classificazione legacy](/help/components/classifications/sets/assets/classifications-legacy.svg)

Nelle classificazioni legacy, le classificazioni ![Schema](/help/assets/icons2/Schema.svg) (come traffico, conversioni, canali di marketing e altro) hanno ciascuna una propria dimensione (chiave ![Chiave](/help/assets/icons2/Key.svg)). Definisci queste classificazioni come parte delle [impostazioni della suite di rapporti](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md).

Le regole ![BidRule](/help/assets/icons/BidRule.svg) vengono definite separatamente nei set di regole come parte dell&#39;interfaccia [Generatore regole di classificazione](/help/components/classifications/crb/classification-rule-builder.md). Nell’interfaccia, associa un set di regole a una o più suite di rapporti.

Utilizza l&#39;[Importazione classificazioni](/help/components/classifications/importer/c-working-with-saint.md) per scaricare un modello ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), importare ![Classificazioni UploadToCloud](/help/assets/icons/UploadToCloud.svg) o esportare ![Scarica](/help/assets/icons/Download.svg) classificazioni da una combinazione di suite di rapporti - chiave (set di dati).



### Set di classificazione

![Set di classificazione](./assets/classifications-sets.svg)

I set di classificazione combinano in un unico set tutte le interfacce di classificazione legacy. Ogni set di classificazione definisce:

* Una o più sottoscrizioni, ovvero la combinazione di una suite di rapporti ![Dati](/help/assets/icons2/Data.svg) e della dimensione ![Chiave](/help/assets/icons2/Key.svg) (chiave), che si desidera classificare. Se desideri classificare i prodotti in base a una SKU di prodotto, puoi definire tutte le suite di rapporti con una dimensione di SKU di prodotto applicabile. Inoltre, non è necessario replicare le classificazioni tra le suite di rapporti, come nell’interfaccia delle classificazioni legacy.
* Elenco di classificazioni ![Schema](/help/assets/icons2/Schema.svg) (schema) per la chiave. Ad esempio, per le classificazioni dei prodotti puoi specificare categoria, colore, dimensione, genere e altro ancora. Dopo aver definito le classificazioni, puoi scaricare un modello ![DocumentFragment](/help/assets/icons/DocumentFragment.svg), caricare ![UploadToCloud](/help/assets/icons/UploadToCloud.svg) dati di classificazione, scaricare ![Scarica](/help/assets/icons/Download.svg) dati di classificazione e altro ancora.
* Una o più regole ![BidRule](/help/assets/icons/BidRule.svg) per supportare le classificazioni.


Per accedere a **[!UICONTROL Classification sets]** dal menu **[!UICONTROL Components]** nell&#39;interfaccia di Adobe Analytics, è necessario essere un amministratore di prodotto o appartenere a un profilo di prodotto contenente l&#39;elemento di autorizzazione [!UICONTROL Report Suite Tools] > [!UICONTROL Classifications]. Le interfacce legacy di gestione delle classificazioni sono disponibili nel menu **[!UICONTROL Admin]**.

I set di classificazione sono costituiti da tre aree funzionali:

* [**[!UICONTROL Classification Sets]**](manage/set-manager.md): per creare, modificare ed eliminare i set di classificazione.
* [**[!UICONTROL Jobs]**](job-manager.md): visualizzazione dello stato dei processi dei set di classificazione.
* [**[!UICONTROL Consolidations]**](consolidations/manage.md): per combinare più set di classificazione in un singolo set di classificazione.


## Flusso di lavoro

Il flusso di lavoro per i set di classificazione in genere prevede i seguenti passaggi:

1. Valuta per quali combinazioni di suite di rapporti e dimensioni desideri creare un set di classificazione. Un esempio è la definizione di un set di classificazione dei prodotti che puoi creare per qualsiasi suite di rapporti per la quale desideri classificare i prodotti con maggiori dettagli. Ad esempio, dettagli come categoria e colore.
1. [Crea un set di classificazione](/help/components/classifications/sets/manage/create.md) con sottoscrizioni per una o più combinazioni di suite di rapporti e dimensioni chiave che identificano i prodotti. Ad esempio:

   | Suite di rapporti | Dimensione chiave |
   |---|---|
   | Suite di rapporti 1 | ID prodotto |
   | Suite di rapporti 2 | SKU prodotto |

1. [Aggiungi le classificazioni](/help/components/classifications/sets/manage/schema.md#add) che hai identificato allo schema del set di classificazione. Ad esempio:

   | Nome classificazione | Nome identità |
   |---|---|
   | Categoria | categoria |
   | Colore | colore |

1. Crea manualmente un file contenente i dati di classificazione. [Utilizza un modello](/help/components/classifications/sets/manage/schema.md#template) per assicurarti di utilizzare il [formato di file supportato](data-files.md#classification-set-file-formats) e le colonne per il file. Quindi aggiungi i dati al file modello.

   In alternativa, è possibile esportare i dati direttamente dal catalogo prodotti nei [formati di file supportati](data-files.md#classification-set-file-formats) con colonne conformi al modello. Ad esempio, un file CSV come:

   ```
   Key,Category,Color
   Adobe Nike Tech Fleece Full-Zip Hoodie - Men's,Men,Black
   Adobe Nike Tech Fleece Full-Zip Hoodie - Women's,Women,Black
   Men's North Face Adobe Jacket,Men,Black
   Nike Air Hybrid 2 Golf Bag,Equipment,Blue
   STITCH&reg; Ultimate Garment Bag,Equipment,Brown
   Adobe Analytics Training Tee - Navy,Men,Navy
   AirPods Pro 2,Electronics,White
   Adobe Analytics Training Tee - Green,Men,Green
   Women's North Face Adobe Jacket,Women,Blue
   Adobe Analytics Training Tee - Grey,Men,Gray
   Adobe Analytics One Million Views - Grey,Equipment,Grey
   Adobe and MGM Tee - White,Women,White
   Adobe and MGM Tee - Charcoal,Women,Charcoal
   ```

   Nel file di dati di classificazione si fa riferimento alla dimensione chiave per ogni suite di rapporti (ad esempio: **[!UICONTROL Product ID]** e **[!UICONTROL Product SKU]**) che utilizza `Key`. E si fa riferimento a ogni classificazione utilizzando **[!UICONTROL Classification Name]** (ad esempio `Category` o `Color`).

1. [Carica](/help/components/classifications/sets/manage/schema.md#upload) il file contenente i dati di classificazione nello schema del set di classificazione.

1. Imposta [regole](manage/rules.md) per classificare automaticamente i dati in arrivo e quelli del passato.

1. [Automatizza](/help/components/classifications/sets/manage/schema.md#automate) il processo di aggiornamenti al catalogo prodotti che desideri visualizzare nei dati di classificazione tramite l&#39;utilizzo di una posizione cloud.

1. [Scarica](/help/components/classifications/sets/manage/schema.md#download) i dati di classificazione per convalidare il contenuto.

1. [Controlla la cronologia dei processi](/help/components/classifications/sets/job-manager.md) per visualizzare i risultati delle azioni (caricamento, download, modello e altro) sulle classificazioni.
1. Se disponi di più set di classificazione simili come risultato di una migrazione dalla funzionalità di classificazione legacy, [consolida](consolidations/manage.md) questi set di classificazione.



## Miglioramenti

L’architettura back-end rilasciata con i set di classificazione contiene diversi miglioramenti:

* Riduzione del tempo di elaborazione (da 72 ore a 24 ore).
* Interfaccia utente riprogettata per gestire le classificazioni.
* Opzione per utilizzare i dati di classificazione in Adobe Experience Platform tramite il connettore di origine di [Adobe Analytics per i dati di classificazione](https://experienceleague.adobe.com/it/docs/experience-platform/sources/connectors/adobe-applications/classifications).

Anche l’architettura back-end rilasciata con i set di classificazione contiene diverse modifiche:

* Quando si utilizza il browser o l&#39;importazione automatica, **[!UICONTROL Overwrite on conflict]** è sempre abilitato.
* Quando si utilizza il browser o l’importazione automatizzata, l’opzione per esportare immediatamente dopo l’importazione non è più supportata. Le esportazioni devono essere avviate separatamente.
* L&#39;endpoint API di Analytics 2.0 `GetDimensions` ora restituisce identificatori stringa per le classificazioni anziché identificatori numerici. È comunque possibile utilizzare gli identificatori numerici, ma si consiglia di utilizzare i nuovi identificatori stringa laddove possibile. Gli identificatori numerici possono essere recuperati utilizzando il parametro `?expansion=hidden` della stringa di query.

>[!IMPORTANT]
>
>Le prestazioni dei set di classificazione dipendono principalmente dal numero di valori chiave univoci che contengono dati. Presta attenzione quando disponi di variabili che contengono un numero elevato di valori univoci. Soprattutto quando combini tali variabili da più suite di rapporti e dimensioni in un unico set di classificazione.

## Limitazioni

* I set di classificazione non supportano ancora le regole. La funzionalità delle regole viene aggiunta all&#39;interfaccia dei set di classificazione prima che la funzionalità [generatore di regole legacy](/help/components/classifications/crb/classification-rule-builder.md) non sia più disponibile.
* Non viene effettuata alcuna migrazione delle configurazioni e delle regole di classificazione legacy ai set di classificazione. Un’utility di migrazione viene aggiunta all’interfaccia dei set di classificazione prima che la funzionalità di classificazione legacy diventi non disponibile.
