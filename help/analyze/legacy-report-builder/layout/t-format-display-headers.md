---
description: Scopri come denominare il rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e di colonna.
title: Formattare le intestazioni di visualizzazione
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 2%

---

# Formattare le intestazioni di visualizzazione

{{legacy-arb}}

Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e di colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.

1. Crea una richiesta su [!UICONTROL Request Wizard: Step 1].
1. Fai clic su **[!UICONTROL Next]**.
1. Nel modulo [!UICONTROL Request Wizard: Step 2], aggiungi i dati di dimensioni e metriche alla richiesta, come desiderato.
1. Fai clic su **[!UICONTROL Format Options]**.
1. Configurare le opzioni [!UICONTROL Display]:

   | Elemento | Descrizione |
   |--- |--- |
   | Nome report | Visualizza il nome del tipo di report selezionato dalla struttura nella Richiesta guidata: Passaggio 1 (ad esempio, [!DNL Traffic Report]) oppure il nome digitato nel campo [!DNL Name this Request]. |
   | Filtri Parametri | Visualizza i filtri dimensione, ad esempio un filtro di ricerca. |
   | Segmento | Visualizza il parametro del segmento. |
   | Data Recency | Visualizza i parametri di aggiornamento dei dati. Ad esempio:    Data Recency: Visualizzazioni pagina (1,5 ore fa), Uscite (30 minuti fa) Per informazioni sull&#39;elaborazione dei dati correnti, consulta [Opzioni](/help/analyze/legacy-report-builder/options.md). |

   Per quanto riguarda l&#39;ordine di visualizzazione, se la griglia [!UICONTROL Row Label] (nel passaggio 2) contiene un elemento, verrà visualizzata per prima nella richiesta. In caso contrario, verrà utilizzato il primo elemento presente nella griglia [!UICONTROL Column Label]. Se non esistono elementi riga o colonna, verrà visualizzato il primo elemento nella griglia [!UICONTROL Metrics].

   **Visualizza intestazioni di riga e colonna:** Aggiunge una riga e una colonna per visualizzare questi elementi.

   Nella versione 3.11, era possibile visualizzare un’intestazione per ogni elemento. Nella versione 4 vengono visualizzati tutti questi elementi o nessuno di essi. Se hai creato una richiesta nella versione 3.11 e la apri nella versione 4.x, nel passaggio 2 il Report Builder ti chiede di aggiornare l’intervallo di una cella per gli elementi per i quali manca un’intestazione.

   **Filtri automatici intestazioni in Excel:** Disponibile solo se vengono visualizzate le intestazioni di riga e di colonna. Questa impostazione crea un filtro automatico di Excel e lo aggiunge al Report Builder di dati restituito per questa richiesta.

   >[!NOTE]
   >
   >Excel supporta un solo filtro automatico per foglio di lavoro. Se si crea un nuovo filtro automatico in un foglio di lavoro in cui esiste già un filtro automatico, non verrà visualizzato alcun avviso che avvisa che il filtro automatico esistente verrà sostituito.

   **Esegui struttura automatica:** trasforma la data restituita dal Report Builder da una visualizzazione elenco a una visualizzazione struttura.

   **Denomina questa richiesta:** Consente di digitare un nome definito dall&#39;utente per la richiesta o di utilizzare il nome predefinito selezionato al passaggio 1. Questo nome viene visualizzato come nome [!UICONTROL Report] in [!UICONTROL Request Manager]. Vedi [Denomina una richiesta](/help/analyze/legacy-report-builder/layout/name-a-request.md).

1. Fai clic su **[!UICONTROL OK]**.
