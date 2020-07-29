---
description: 'null'
title: 'Richieste di dati: Creazione guidata richieste passaggio 1'
uuid: 717542c3-e4aa-4e00-b0ca-cadecd219d13
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 5%

---


# Richieste di dati: Creazione guidata richieste passaggio 1

Nella Richiesta guidata: Modulo Passaggio 1: seleziona la suite di rapporti, il tipo di rapporto, i segmenti e le date di configurazione.

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: L&#39;elenco delle suite di rapporti disponibili in base alle credenziali di accesso. Consultate [Selezionare le suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)di rapporti.

1. **Selettore** intervallo: Consente di selezionare un ID suite di rapporti da una cella in Excel. Consultate [Selezionare le suite](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)di rapporti.

1. **Segmento**: I segmenti sono sottoinsiemi personalizzati di dati o dati filtrati dalle regole create dall&#39;utente. I segmenti si basano su hit, visite e visitatori. Per ulteriori informazioni sui segmenti, consulta la [Guida](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html) alla segmentazione di Analytics.

   Ad esempio, puoi eseguire un [!UICONTROL Pages Report], quindi applicare un segmento Prima visita.

1. **Consenti sostituzione** elenco di pubblicazione: Quando pianificate un rapporto, potete scegliere un elenco di pubblicazione da utilizzare per la distribuzione. Gli elenchi di pubblicazione sono impostati in **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. La suite di rapporti per questa richiesta viene sostituita dall&#39;ID suite di rapporti assegnato a ciascun destinatario nell&#39;elenco di pubblicazione. See [Allow Publishing List Overrides](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Tipo** rapporto: Specifica il rapporto di base che si desidera eseguire nella richiesta di dati. Potete eseguire un rapporto per ogni richiesta, che può avere dimensioni uno-a-molti e metriche uno-a-molti. Metriche e dimensioni per un tipo di rapporto vengono visualizzate nell&#39; [!UICONTROL Request Wizard; Step 2] interfaccia. Consultate [Selezionare i tipi](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md)di report.

1. **Intervalli** di date: Definisce l’intervallo di tempo coperto dalla richiesta. Sono disponibili diversi tipi di periodi di tempo di richiesta, ad esempio preimpostati, fissi e in continuo. Il numero massimo di periodi è 366. Puoi anche scegliere un intervallo di date specificato da una cella e salvare gli intervalli di date come modelli da utilizzare successivamente.  Consultate [Configurazione delle date dei rapporti](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Applica granularità**: Specifica il livello di dettaglio basato sul tempo incluso nel rapporto. Consultate [Granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

## Risoluzione dei problemi

A volte la procedura guidata di richiesta appare fuori schermo, in particolare per gli utenti che si spostano tra le diverse impostazioni del monitor. Ad esempio, si utilizza una docking station al lavoro e lo schermo del laptop a casa. Se fate nuovamente clic su &#39;Crea&#39; mentre è già aperta una procedura guidata di richiesta, viene visualizzato il seguente errore:

&quot;Prima di avviare una nuova procedura guidata di richiesta è necessario completare il processo.&quot;

Lo spostamento della procedura guidata di richiesta sullo schermo risolve il problema.

1. Aprite Microsoft Excel ed effettuate l&#39;accesso al Report Builder.
2. Fate clic [!UICONTROL Create]per aprire la procedura guidata di richiesta fuori schermo.
3. Premere `[Alt]` + `[Space]`.
4. Premere `[M]`.
5. Premere uno dei tasti freccia.
6. Sposta il mouse, allegando la procedura guidata di richiesta al cursore
7. Fate clic sul mouse per rilasciare la procedura guidata di richiesta sullo schermo.
