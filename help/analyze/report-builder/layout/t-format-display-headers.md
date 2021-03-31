---
description: Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.
title: Formattare le intestazioni di visualizzazione
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 3%

---


# Formattare le intestazioni di visualizzazione

Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.

1. Crea una richiesta sul [!UICONTROL Request Wizard: Step 1].
1. Fai clic su **[!UICONTROL Next]**.
1. Nel modulo [!UICONTROL Request Wizard: Step 2], aggiungi alla richiesta i dati relativi a dimensioni e metriche, come desiderato.
1. Fai clic su **[!UICONTROL Format Options]**.
1. Configura le opzioni [!UICONTROL Display] :

   | Elemento | Descrizione |
   |--- |--- |
   | Nome del rapporto | Visualizza il nome del tipo di report selezionato dalla struttura nella Creazione guidata richieste: Passaggio 1 (ad esempio, [!DNL Traffic Report]) o il nome digitato nel campo [!DNL Name this Request]. |
   | Parametri dei filtri | Visualizza i filtri dimensionali, ad esempio un filtro di ricerca. |
   | Segmento | Visualizza il parametro del segmento. |
   | Data Recency | Visualizza i parametri di aggiornamento dei dati. Ad esempio:    Attualità dei dati: Visualizzazioni di pagina (1.5 ora fa), Uscite (30 minuti fa) Per informazioni sull&#39;elaborazione dati corrente, vedere [Opzioni](/help/analyze/report-builder/options.md) . |

   Per quanto riguarda l&#39;ordine di visualizzazione, se la griglia [!UICONTROL Row Label] (al passaggio 2) contiene un elemento, viene visualizzata per prima nella richiesta. In caso contrario, il sistema utilizza il primo elemento presente nella griglia [!UICONTROL Column Label]. Se non esistono elementi di riga o colonna, viene visualizzato il primo elemento della griglia [!UICONTROL Metrics].

   **Visualizza intestazioni riga e colonna:** aggiunge una riga e una colonna per visualizzare questi elementi.

   Nella versione 3.11, puoi visualizzare un’intestazione per ogni elemento. La versione 4 visualizza tutti questi elementi o nessuno di essi. Se hai creato una richiesta nella versione 3.11 e la apri nella versione 4.x, in Report Builder viene richiesto di aggiornare l’intervallo di una cella per gli elementi per i quali manca un’intestazione al passaggio 2.

   **Cambia intestazioni in filtri automatici Excel:** disponibile solo se sono visualizzate le intestazioni di riga e colonna. Questa impostazione crea un filtro automatico di Excel e lo aggiunge ai resi del generatore di report di dati per questa richiesta.

   >[!NOTE]
   >
   >Excel supporta un solo filtro automatico per foglio di lavoro. Se si crea un nuovo filtro automatico in un foglio di lavoro in cui esiste già un filtro automatico, in Excel non viene visualizzato un messaggio di avviso relativo alla sostituzione del filtro automatico esistente.

   **Esegui struttura automatica:** trasforma la data restituita dal generatore di report da una vista a elenco in una vista ad albero.

   **Denomina questa richiesta:** ti consente di digitare un nome definito dall&#39;utente per la richiesta o di utilizzare il nome predefinito selezionato al passaggio 1. Questo nome viene visualizzato come [!UICONTROL Report] nel [!UICONTROL Request Manager]. Vedere [Denominare una richiesta](/help/analyze/report-builder/layout/name-a-request.md).

1. Fai clic su **[!UICONTROL OK]**.
