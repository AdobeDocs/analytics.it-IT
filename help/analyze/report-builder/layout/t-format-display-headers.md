---
description: Puoi assegnare un nome al rapporto e configurare come visualizzare le intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.
seo-description: Puoi assegnare un nome al rapporto e configurare come visualizzare le intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.
seo-title: Formattazione delle intestazioni di visualizzazione
solution: Analytics
title: Formattazione delle intestazioni di visualizzazione
topic: Generatore di report
uuid: cd 0 e 167 b -9463-43 fd -87 b 2-724 d 1 c 79 de 68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Formattazione delle intestazioni di visualizzazione

Puoi assegnare un nome al rapporto e configurare come visualizzare le intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.

1. Create a request on the [!UICONTROL Request Wizard: Step 1].
1. Fai clic su **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. Fai clic su **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | Elemento | Descrizione |
   |--- |--- |
   | Nome rapporto | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | Parametri filtri | Visualizza i filtri dimensionali, ad esempio un filtro di ricerca. |
   | Segmento | Visualizza il parametro segmento. |
   | Recency dati | Visualizza i parametri di aggiornamento dei dati. For example:    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **Visualizza intestazioni riga e colonna:** Aggiunge una riga e una colonna per visualizzare questi elementi.

   Nella versione 3.11, è possibile visualizzare un'intestazione per ogni elemento. La versione 4 visualizza tutti questi elementi o nessuno di essi. Se avete creato una richiesta nella versione 3.11 e la avete aperta nella versione 4. x, il generatore di report richiede al passaggio 2 di aggiornare l'intervallo per gli elementi per i quali manca un'intestazione.

   **Cambia intestazioni in filtri automatici Excel:** Disponibile solo se sono visualizzate intestazioni di riga e colonna. Questa impostazione crea un filtro automatico Excel e lo aggiunge al generatore di report di dati per la richiesta.

   >[!NOTE]
   >
   >Excel supporta un solo filtro automatico per foglio di lavoro. Se create un nuovo filtro automatico in un foglio di lavoro in cui esiste già un filtro automatico, Excel non fornisce un messaggio di avviso per la sostituzione del filtro automatico esistente.

   **Esegui struttura automatica:** Trasforma la data restituita dal generatore di report da una visualizzazione a elenco a una vista ad albero.

   **Denominate questa richiesta:** Consente di digitare un nome definito dall'utente per la richiesta, oppure di utilizzare il nome predefinito selezionato al Passaggio 1. This name appears as the [!UICONTROL Report] name in the [!UICONTROL Request Manager]. See [Name a Request](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D).

1. Fai clic su **[!UICONTROL OK]**.
