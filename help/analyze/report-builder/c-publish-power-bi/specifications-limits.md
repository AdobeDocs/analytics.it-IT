---
description: Limitazioni durante l’utilizzo di Report Builder e Microsoft Power BI.
title: Limiti e specifiche
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 1%

---

# Limiti e specifiche

## Power BI restrizioni alla pubblicazione {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Queste restrizioni si applicano solo all’opzione &quot;Pubblica richieste di Report Builder come tabelle di set di dati di Power BI&quot;.

* È possibile esportare fino a 100 richieste di Report Builder in Power BI per cartella di lavoro.
* Il processo di pianificazione interrompe l’esportazione delle richieste quando viene raggiunta la 101a richiesta.
* Solo le prime 10.000 righe di dati Analytics verranno inviate a Power BI per richiesta di Report Builder. Le righe rimanenti verranno ignorate.

## Modificare una richiesta di Report Builder dopo la pubblicazione in Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Questa specifica si applica alle opzioni &quot;Pubblica tutte le richieste di Report Builder come tabelle di set di dati di Power BI&quot; e &quot;Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle di set di dati di Power BI&quot;.

La modifica di una richiesta di Report Builder dopo la pubblicazione nel Power BI può causare problemi.

* **Caso 1**: pubblichi una cartella di lavoro in Power BI e crei una visualizzazione basata sui relativi dati. Successivamente, si apportano modifiche alla cartella di lavoro, causando la scomparsa di una delle colonne del set di dati a cui fa riferimento. Poi ripubblichi. La visualizzazione verrà interrotta in Power BI.

   **Ecco un esempio di come la visualizzazione si interromperà:**

   1. In Report Builder, crea una cartella di lavoro con una richiesta, utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   2. Pianifica la pubblicazione di questa richiesta in Power BI.
   3. In Power BI, crea una visualizzazione per le visualizzazioni di pagina e pagina.
   4. Modificare la cartella di lavoro rimuovendo le Visualizzazioni pagina dalla richiesta.
   5. Modifica la pianificazione con la cartella di lavoro aggiornata e ripubblica la richiesta in Power BI.
   6. Una volta inviata la nuova cartella di lavoro a Power BI

      1. Verifica che abbia sovrascritto il set di dati esistente creato al momento della prima pubblicazione.
      2. Verifica che la tabella page_1 sia aggiornata correttamente con le colonne Pagina e Visite.
      3. Verifica che la visualizzazione sia interrotta, poiché fa riferimento alla colonna Visualizzazioni pagina che non è più presente nella tabella page_1.

   **Ecco un esempio di come la visualizzazione NON si interrompe:**

   1. In Report Builder, crea una cartella di lavoro con una richiesta, utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   2. Pianifica la pubblicazione di questa richiesta in Power BI.
   3. In Power BI, crea una visualizzazione per le visualizzazioni di pagina e pagina.
   4. Ora modifica la cartella di lavoro in Report Builder, aggiungendo la metrica Visita mantenendo le visualizzazioni di pagina e pagina.
   5. Modifica la pianificazione con la cartella di lavoro aggiornata e ripubblica la richiesta in Power BI.
   6. Una volta inviata la nuova cartella di lavoro a Power BI

      1. Verifica che abbia sovrascritto il set di dati esistente creato al momento della prima pubblicazione.
      2. Verifica che la tabella page_1 sia aggiornata correttamente con le colonne Pagina, Visualizzazioni pagina e Visite.
      3. Verifica che la visualizzazione continui a funzionare correttamente, poiché fa riferimento a due colonne ancora presenti nella tabella page_1.


* **Caso 2**: quando si fissa una sezione della cartella di lavoro a un dashboard in Power BI, la sezione bloccata (ad esempio un grafico o una tabella) viene rimossa dalla cartella di lavoro. La visualizzazione verrà interrotta.

## Modificare il nome di un report di Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Per impostazione predefinita, il nome viene popolato dal nome del file della cartella di lavoro (senza l&#39;estensione .xlsx), tranne per il fatto che gli spazi vengono sostituiti con caratteri di sottolineatura.

Nota bene

* L&#39;etichetta non può essere una combinazione di lettere e numeri che potrebbe essere scambiata per un indirizzo di riga e colonna. Ad esempio, A100 non può essere un&#39;etichetta perché è l&#39;indirizzo di una cella in un foglio di lavoro.
* I seguenti caratteri non sono caratteri di etichetta validi: `'#', '@', '!', '$', '^', '&', '&#42;', '`&quot;, e `'~', ' '` . Vengono sostituiti da un carattere di sottolineatura.
* Quando immetti un nome non valido, viene visualizzato un messaggio di avviso che suggerisce un nome generato automaticamente. Se si fa clic su **[!UICONTROL Yes]**, verrà utilizzato questo nome. Se si fa clic su **[!UICONTROL No]**, l&#39;interfaccia utente della procedura guidata avanzata consente di immettere il nuovo nome.
