---
description: Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e di colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.
title: Formattare le intestazioni di visualizzazione
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---

# Formattare le intestazioni di visualizzazione

Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e di colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.

1. Crea una richiesta su [!UICONTROL Request Wizard: Step 1].
1. Fai clic su **[!UICONTROL Next]** (Usa modello di attribuzione non predefinito).
1. Il giorno [!UICONTROL Request Wizard: Step 2] aggiungere dimensioni e metriche alla richiesta, come desiderato.
1. Fai clic su **[!UICONTROL Format Options]** (Usa modello di attribuzione non predefinito).
1. Configurare [!UICONTROL Display] opzioni:

   | Elemento | Descrizione |
   |--- |--- |
   | Nome rapporto | Visualizza il nome del tipo di report selezionato dalla struttura nella Richiesta guidata: Passaggio 1 (ad esempio, [!DNL Traffic Report]) o il nome digitato nel [!DNL Name this Request] campo. |
   | Filtri Parametri | Visualizza i filtri dimensione, ad esempio un filtro di ricerca. |
   | Segmento | Visualizza il parametro del segmento. |
   | Data Recency | Visualizza i parametri di aggiornamento dei dati. Ad esempio: Data Recency: Visualizzazioni pagina (1,5 ore fa), Uscite (30 minuti fa) Vedi [Opzioni](/help/analyze/report-builder/options.md) per informazioni sull’elaborazione dati corrente. |

   Per quanto riguarda l&#39;ordine di visualizzazione, se [!UICONTROL Row Label] la griglia (nel passaggio 2) contiene un elemento, che viene visualizzato per primo nella richiesta. In caso contrario, il sistema utilizza il primo elemento presente nel [!UICONTROL Column Label] griglia. Se non esistono elementi di riga o colonna, il primo elemento nella [!UICONTROL Metrics] viene visualizzata la griglia.

   **Visualizza intestazioni di riga e colonna:** Aggiunge una riga e una colonna per visualizzare questi elementi.

   Nella versione 3.11, era possibile visualizzare un’intestazione per ogni elemento. Nella versione 4 vengono visualizzati tutti questi elementi o nessuno di essi. Se hai creato una richiesta nella versione 3.11 e la apri nella versione 4.x, nel passaggio 2 Report Builder ti chiede di aggiornare l’intervallo di una cella per gli elementi senza intestazione.

   **Cambia intestazioni in filtri automatici Excel:** Disponibile solo se vengono visualizzate le intestazioni di riga e di colonna. Questa impostazione crea un filtro automatico Excel e lo aggiunge ai risultati restituiti dal generatore di report di dati per questa richiesta.

   >[!NOTE]
   >
   >Excel supporta un solo filtro automatico per foglio di lavoro. Se si crea un nuovo filtro automatico in un foglio di lavoro in cui esiste già un filtro automatico, non verrà visualizzato alcun avviso che avvisa che il filtro automatico esistente verrà sostituito.

   **Esegui struttura automatica:** Trasforma la data restituita da Report Builder da una vista a elenco a una vista a struttura.

   **Denomina questa richiesta:** Consente di digitare un nome definito dall&#39;utente per la richiesta o di utilizzare il nome predefinito selezionato al passaggio 1. Questo nome viene visualizzato come [!UICONTROL Report] nome in [!UICONTROL Request Manager]. Consulta [Assegnare un nome a una richiesta](/help/analyze/report-builder/layout/name-a-request.md).

1. Fai clic su **[!UICONTROL OK]** (Usa modello di attribuzione non predefinito).
