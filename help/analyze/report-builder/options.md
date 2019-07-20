---
description: Nel pannello Opzioni, potete specificare le impostazioni della data, le impostazioni della latenza (Dati correnti), le informazioni sul registro e configurare gli aggiornamenti.
seo-description: Nel pannello Opzioni, potete specificare le impostazioni della data, le impostazioni della latenza (Dati correnti), le informazioni sul registro e configurare gli aggiornamenti.
seo-title: Opzioni del Generatore di report
solution: Analytics
title: Opzioni del Generatore di report
topic: Generatore di report
uuid: f 2920 dee -4245-4617-a 02 e -03726 dde 2 bb 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Opzioni del Generatore di report

Nel pannello Opzioni, potete specificare le impostazioni della data, le impostazioni della latenza (Dati correnti), le informazioni sul registro e configurare gli aggiornamenti.

1. In the Add-Ins toolbar, click **[!UICONTROL Options]** ![](assets/options_icon.png):

| Elemento | Descrizione |
|--- |--- |
| [!UICONTROL As Of Date] |  |
| Imposta sulla data corrente | Lets you specify or reset the  [!UICONTROL As Of Date] so that report builder uses the current date or asks you which date to use upon refresh. |
| Richiedi di impostare all'aggiornamento | Lets you set the  [!UICONTROL As Of Date] when refreshing a request. |
| [!UICONTROL Data Recency] |  |
| [!UICONTROL Include Current Data] | Lets you view data latency (also known as  [!UICONTROL Data Recency]) down to the minute in reporting, occasionally even before this data has been processed by  Adobe Analytics.<br>Se non utilizzate questa opzione, viene utilizzata la modalità finalizzata (elaborata), che in genere è più [latente](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=data_latency).<br>Questa impostazione si applica a tutte le richieste della cartella di lavoro compatibili con Dati correnti. Se la richiesta non è compatibile, viene applicata la modalità finalizzata.<br>Prendete nota delle situazioni seguenti per utilizzare la [!UICONTROL Include Current Data] modalità:<br>**Opzioni formato**: È possibile specificare se visualizzare queste informazioni ([!UICONTROL Data Recency]) durante [la formattazione delle intestazioni di visualizzazione](../../analyze/report-builder/layout/t-format-display-headers.md).<br>**Suddivisioni**: Non supportato. If the  [!UICONTROL Data Recency] mode is set to the Current Data, and one of the requests contains a break-down element, this request reverts to non-current data mode. Tuttavia, altre richieste continuano a utilizzare la modalità Dati corrente.<br>**Request Manager**: Potete visualizzare una colonna Dati corrente in Richieste di manager, per verificare se l'impostazione è applicata a una richiesta pianificata.<br>**Cartelle di lavoro pianificate**: Questa modalità viene memorizzata durante il processo di pianificazione a livello di cartella di lavoro. If you open a scheduled workbook that is using finalized data, and apply [!UICONTROL Include Current Data], current mode is used thereafter.<br>**Autorizzazioni**: Per gli utenti che non hanno accesso ai dati correnti, questa opzione è nascosta. Quando si attiva questa opzione, se una o più richieste non possono essere applicate, viene emesso un avviso. |
| Disattivazione avvisi di richiesta non compatibile con dati correnti | Displays warnings if the  [!UICONTROL Include Current Data] mode is selected but the data mode cannot be applied to the edited request.  For example, if you set [!UICONTROL Include Current Data], and then edit a request that has a segment selected, a warning is issued. |
| Registrare richieste di generatore di report al file locale (per la risoluzione dei problemi) | Consente di effettuare le richieste a un file locale. Utilizzare questo file di registro per la risoluzione dei problemi. |
| Interpreta valore digitato… | Interpreta un valore digitato in un controllo di filtro come posizione della cella prima di considerare un'espressione filtro.<br>Ad esempio, se create una richiesta di Pagina Primi 10, utilizzando una delle scarpe filtro, la richiesta visualizzerebbe una cella contenente qualcosa di simile a: Filtro: Top 1-10 Page, Page contains Shoes |
| Aggiornamento quando è disponibile una nuova versione | Indica al sistema di inviare una notifica se è disponibile una nuova versione per l'installazione. |
