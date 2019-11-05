---
description: Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.
seo-description: Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.
seo-title: Formattare le intestazioni di visualizzazione
solution: Analytics
title: Formattare le intestazioni di visualizzazione
topic: Generatore di report
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Formattare le intestazioni di visualizzazione

Puoi assegnare un nome al rapporto e configurare la modalità di visualizzazione delle intestazioni di riga e colonna. Il collegamento Opzioni formato è disponibile per i tipi di layout pivot e personalizzato.

1. Create una richiesta sul [!UICONTROL Request Wizard: Step 1].
1. Fai clic su **[!UICONTROL Next]**.
1. Sul [!UICONTROL Request Wizard: Step 2] modulo, aggiungere dati di dimensioni e metriche alla richiesta, come desiderato.
1. Fai clic su **[!UICONTROL Format Options]**.
1. Configurare le [!UICONTROL Display] opzioni:

   | Elemento | Descrizione |
   |--- |--- |
   | Nome rapporto | Visualizza il nome del tipo di rapporto selezionato dalla struttura ad albero nella Richiesta guidata: Passaggio 1 (ad esempio [!DNL Traffic Report]) o il nome digitato nel [!DNL Name this Request] campo. |
   | Parametri dei filtri | Visualizza i filtri dimensionali, ad esempio un filtro di ricerca. |
   | Segmento | Visualizza il parametro del segmento. |
   | Data Recency | Visualizza i parametri di aggiornamento dei dati. Ad esempio:    Data Recency: Visualizzazioni di pagina (1.5 ora fa), Uscite (30 minuti fa) Vedere [Opzioni](/help/analyze/report-builder/options.md) per informazioni sull'elaborazione dati corrente. |

   Per quanto riguarda l'ordine di visualizzazione, se la [!UICONTROL Row Label] griglia (al passaggio 2) contiene un elemento, viene visualizzata per prima nella richiesta. In caso contrario, il sistema utilizza il primo elemento presente nella [!UICONTROL Column Label] griglia. Se non esistono elementi di riga o colonna, viene visualizzato il primo elemento della [!UICONTROL Metrics] griglia.

   **** Visualizza intestazioni riga e colonna: Aggiunge una riga e una colonna per visualizzare questi elementi.

   Nella versione 3.11, è possibile visualizzare un'intestazione per ogni elemento. La versione 4 visualizza tutti questi elementi o nessuno di essi. Se avete creato una richiesta nella versione 3.11 e l’avete aperta nella versione 4.x, il generatore di report vi chiede al passaggio 2 di aggiornare l’intervallo di una cella per gli elementi per i quali manca un’intestazione.

   **** Cambia intestazioni in filtri automatici Excel: Disponibile solo se sono visualizzate le intestazioni di riga e colonna. Questa impostazione crea un filtro automatico di Excel e lo aggiunge ai resi del generatore di report per questa richiesta.

   >[!NOTE]
   >
   >Excel supporta un solo filtro automatico per foglio di lavoro. Se si crea un nuovo filtro automatico in un foglio di lavoro in cui esiste già un filtro automatico, Excel non fornisce un avviso che avvisa che il filtro automatico esistente verrà sostituito.

   **** Esegui contorno automatico: Trasforma la data restituita dal generatore di report da una vista a elenco a una vista ad albero.

   **** Denominate questa richiesta: Consente di digitare un nome definito dall'utente per la richiesta o di utilizzare il nome predefinito selezionato al passaggio 1. Questo nome viene visualizzato come [!UICONTROL Report] nome nel [!UICONTROL Request Manager]. See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. Fai clic su **[!UICONTROL OK]**.
