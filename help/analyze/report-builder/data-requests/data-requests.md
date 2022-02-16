---
description: Il primo passaggio durante la creazione di una richiesta in Report Builder.
title: 'Richieste di dati: Creazione guidata richieste passaggio 1'
feature: Report Builder
role: User, Admin
exl-id: 698662a8-8b6b-4338-a315-b41cf6a9424e
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 2%

---

# Richieste di dati: Creazione guidata richieste passaggio 1

Nella Creazione guidata richieste: Modulo del passaggio 1: seleziona la suite di rapporti, il tipo di rapporto, i segmenti e configura le date.

![](assets/rw1_overview.png)

1. **[!UICONTROL Report Suite]**: Elenco delle suite di rapporti disponibili in base alle credenziali di accesso. Vedi [Seleziona suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Selettore intervallo**: Consente di selezionare un ID suite di rapporti da una cella in Excel. Vedi [Seleziona suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).

1. **Segmento**: I segmenti sono sottoinsiemi personalizzati di dati o dati filtrati dalle regole create dall’utente. I segmenti si basano su hit, visite e visitatori. Consulta la sezione [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html) per ulteriori informazioni sui segmenti.

   Ad esempio, puoi eseguire un [!UICONTROL Pages Report], quindi applica un segmento First Time Visits (Visite per la prima volta).

1. **Consenti sostituzione elenco di pubblicazione**: Quando pianifichi un rapporto, puoi scegliere una lista di pubblicazione da utilizzare per la distribuzione. Gli elenchi di pubblicazione sono impostati in **[!UICONTROL Analytics]** > **[!UICONTROL Admin tools]**. La suite di rapporti per questa richiesta viene sostituita dall’ID suite di rapporti assegnato a ciascun destinatario nell’elenco di pubblicazione. Vedi [Consenti sostituzioni elenco di pubblicazione](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md).

1. **Tipo di rapporto**: Specifica il report di base che si desidera eseguire nella richiesta di dati. Puoi eseguire un rapporto per richiesta, con dimensioni da uno a molti e metriche da uno a molti. Le metriche e le dimensioni di un tipo di rapporto vengono visualizzate sul [!UICONTROL Request Wizard; Step 2] interfaccia. Vedi [Seleziona tipi di rapporti](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).

1. **Intervalli di date**: Definisce l’intervallo di tempo coperto dalla richiesta. Sono disponibili diversi tipi di periodi di tempo di richiesta, ad esempio preimpostati, fissi e continui. Il numero massimo di periodi è 366. È inoltre possibile scegliere un intervallo di date specificato da una cella e salvare gli intervalli di date come modelli da utilizzare successivamente.  Vedi [Configurazione delle date dei rapporti](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md)

1. **Applica granularità**: Specifica il livello di dettaglio basato sul tempo incluso nel report. Vedi [Granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).

## Risoluzione dei problemi

A volte la procedura guidata di richiesta appare fuori schermo, specialmente per gli utenti che si spostano tra le impostazioni di monitoraggio. Ad esempio, si utilizza una docking station al lavoro e lo schermo del portatile a casa. Se fai di nuovo clic su &quot;Crea&quot; mentre è già aperta una richiesta guidata, ottieni il seguente errore:

&quot;È innanzitutto necessario completare il processo di richiesta guidata prima di avviarne uno nuovo.&quot;

Lo spostamento della procedura guidata di richiesta sullo schermo risolve questo problema.

1. Apri Microsoft Excel e accedi al Report Builder.
2. Fai clic su [!UICONTROL Create], che apre la procedura guidata di richiesta fuori schermo.
3. Press `[Alt]` + `[Space]`.
4. Press `[M]`.
5. Premere uno dei tasti freccia.
6. Sposta il mouse, che allega la procedura guidata di richiesta al cursore
7. Fai clic sul mouse per rilasciare la procedura guidata di richiesta sullo schermo.
