---
description: Il primo passaggio durante la creazione di una richiesta in Report Builder.
title: 'Richieste di dati: Creazione guidata richieste passaggio 1'
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
TQID: https://experienceleague.adobe.com/87MzdxBePRZKBttF3P6XhuDq5hR6XpEWaLdrYDMu-5Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 392
ht-degree: 3%

---

# Richieste di dati: Creazione guidata richieste passaggio 1

{{legacy-arb}}

Nella maschera Creazione guidata richieste: passaggio 1 selezionare la suite di rapporti, il tipo di rapporto, i segmenti e le date di configurazione.

![Schermata che mostra la Richiesta guidata: Modulo passaggio 1.](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: elenco delle suite di rapporti disponibili in base alle credenziali di accesso. Vedi [Seleziona suite di rapporti](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Selettore intervallo**: consente di selezionare un ID suite di rapporti da una cella in Excel. Vedi [Seleziona suite di rapporti](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segmento**: i segmenti sono sottoinsiemi di dati personalizzati o dati filtrati dalle regole create. I segmenti si basano su hit, visite e visitatori. Per ulteriori informazioni sui segmenti, consulta la [Guida alla segmentazione di Analytics](/help/components/segmentation/seg-home.md).

   Ad esempio, puoi eseguire [!UICONTROL Pages Report] e quindi applicare un segmento Nuovo visitatore.

1. **Consenti sostituzione elenco di pubblicazione**: gli elenchi di pubblicazione erano una funzionalità di Reports &amp; Analytics, che è stata [terminata](https://new.express.adobe.com/webpage/WFCyq7w8kijmB?).

1. **Tipo di report**: specifica il report di base che si desidera eseguire nella richiesta di dati. Puoi eseguire un rapporto per richiesta e tale rapporto può avere dimensioni uno-a-molti e metriche uno-a-molti. Le metriche e le dimensioni per un tipo di report sono visualizzate nell&#39;interfaccia [!UICONTROL Request Wizard; Step 2]. Consulta [Selezionare i tipi di report](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).

1. **Intervalli di date**: definisce l&#39;intervallo di tempo coperto dalla richiesta. Sono disponibili diversi tipi di periodi di tempo per le richieste, ad esempio predefiniti, fissi e continui. Il numero massimo di periodi è 366. Puoi anche scegliere un intervallo di date specificato da una cella e salvare gli intervalli di date come modelli da utilizzare in un secondo momento.  Vedi [Configurazione delle date dei report](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Applica granularità**: specifica il livello di dettaglio basato sul tempo incluso nel report. Vedi [Granularità](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md).

## Risoluzione dei problemi

Talvolta la Creazione guidata richieste viene visualizzata fuori schermo, in particolare per gli utenti che passano da una configurazione all&#39;altra del monitor. Ad esempio, è possibile utilizzare un alloggiamento di espansione sul posto di lavoro e lo schermo del notebook a casa. Se si fa di nuovo clic su &#39;Crea&#39; mentre è già aperta una procedura guidata di richiesta, viene visualizzato il seguente errore:

&quot;Prima di avviarne uno nuovo, devi prima completare il processo di creazione guidata delle richieste.&quot;

Per risolvere il problema, è possibile tornare alla Creazione guidata richieste sullo schermo.

1. Apri Microsoft Excel e accedi a Report Builder.
2. Fare clic su [!UICONTROL Create] per aprire la Creazione guidata richieste fuori schermo.
3. Premere `[Alt]` + `[Space]`.
4. Premere `[M]`.
5. Premere uno dei tasti di direzione.
6. Spostare il mouse, che collega la procedura guidata di richiesta al cursore
7. Fare clic con il mouse per rilasciare la procedura guidata di richiesta sullo schermo.
