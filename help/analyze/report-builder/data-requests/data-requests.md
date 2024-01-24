---
description: Il primo passaggio durante la creazione di una richiesta in Report Builder.
title: 'Richieste di dati: Creazione guidata richieste passaggio 1'
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: 244af34b463ea5df55eaca31f3b2df4ada552b5d
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 3%

---

# Richieste di dati: Creazione guidata richieste passaggio 1

Nella maschera Creazione guidata richieste: passaggio 1 selezionare la suite di rapporti, il tipo di rapporto, i segmenti e le date di configurazione.

![Schermata che mostra il modulo Creazione guidata richieste: passaggio 1.](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: elenco delle suite di rapporti disponibili in base alle credenziali di accesso. Consulta [Selezionare suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Selettore intervallo**: consente di selezionare un ID suite di rapporti da una cella in Excel. Consulta [Selezionare suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segmento**: i segmenti sono sottoinsiemi di dati personalizzati o dati filtrati dalle regole create. I segmenti si basano su hit, visite e visitatori. Consulta la [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it) per ulteriori informazioni sui segmenti.

   Ad esempio, è possibile eseguire una [!UICONTROL Pages Report], quindi applica un segmento Nuovo visitatore.

1. **Consenti sostituzione elenco di pubblicazione**: gli elenchi di pubblicazione erano una funzione di Reports &amp; Analytics che ora [fine vita](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?).

1. **Tipo di rapporto**: specifica il rapporto di base da eseguire nella richiesta di dati. Puoi eseguire un rapporto per richiesta e tale rapporto può avere dimensioni uno-a-molti e metriche uno-a-molti. Le metriche e le dimensioni di un tipo di rapporto sono visualizzate nel [!UICONTROL Request Wizard; Step 2] di rete. Consulta [Seleziona tipi di rapporto](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Intervalli di date**: definisce l’intervallo di tempo coperto dalla richiesta. Sono disponibili diversi tipi di periodi di tempo per le richieste, ad esempio predefiniti, fissi e continui. Il numero massimo di periodi è 366. Puoi anche scegliere un intervallo di date specificato da una cella e salvare gli intervalli di date come modelli da utilizzare in un secondo momento.  Consulta [Configurazione delle date dei rapporti](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Applica granularità**: specifica il livello di dettaglio basato sul tempo incluso nel rapporto. Consulta [Granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

## Risoluzione dei problemi

Talvolta la Creazione guidata richieste viene visualizzata fuori schermo, in particolare per gli utenti che passano da una configurazione all&#39;altra del monitor. Ad esempio, è possibile utilizzare un alloggiamento di espansione sul posto di lavoro e lo schermo del notebook a casa. Se si fa di nuovo clic su &#39;Crea&#39; mentre è già aperta una procedura guidata di richiesta, viene visualizzato il seguente errore:

&quot;Prima di avviarne uno nuovo, devi prima completare il processo di creazione guidata delle richieste.&quot;

Per risolvere il problema, è possibile tornare alla Creazione guidata richieste sullo schermo.

1. Apri Microsoft Excel e accedi al Report Builder.
2. Clic [!UICONTROL Create], che apre la procedura guidata di richiesta fuori schermo.
3. Premi `[Alt]` + `[Space]`.
4. Premi `[M]`.
5. Premere uno dei tasti di direzione.
6. Spostare il mouse, che collega la procedura guidata di richiesta al cursore
7. Fare clic con il mouse per rilasciare la procedura guidata di richiesta sullo schermo.
