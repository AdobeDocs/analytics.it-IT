---
description: 'null'
title: Limiti e specifiche
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: tm+mt
source-git-commit: 0f362008f0041a6ac31437ce4da934064c3fa134
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 1%

---


# Limiti e specifiche

## Limitazioni di pubblicazione Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Queste restrizioni si applicano solo all&#39;opzione &quot;Pubblica richieste di Report Builder come tabelle DataSet Power BI&quot;.

* È possibile esportare fino a 100 richieste di Report Builder in Power BI per cartella di lavoro.
* Il processo di pianificazione interrompe l&#39;esportazione delle richieste quando viene raggiunta la 101a richiesta.
* Solo le prime 10.000 righe di dati Analytics verranno inviate a Power BI per richiesta di Report Builder. Le righe rimanenti verranno ignorate.

## Modificare una richiesta di Report Builder dopo la pubblicazione in Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Questa specifica si applica alle opzioni &quot;Pubblica tutte le richieste di Report Builder come tabelle DataSet Power BI&quot; e &quot;Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle DataSet Power BI&quot;.

La modifica di una richiesta di Report Builder dopo la pubblicazione su Power BI potrebbe causare problemi.

* **Caso 1**: È possibile pubblicare una cartella di lavoro su Power BI e creare una visualizzazione basata sui relativi dati. Quindi, è possibile apportare modifiche alla cartella di lavoro, causando la scomparsa di una delle colonne del set di dati a cui fa riferimento. Quindi ripubblicate. In questo modo la visualizzazione verrà interrotta in Power BI.

   **Esempio di interruzione della visualizzazione:**

   1. Ad Report Builder, creare una cartella di lavoro con una richiesta, utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   2. Pianificare la pubblicazione della richiesta in Power BI.
   3. In Power BI, crea una visualizzazione per Visualizzazioni pagina e Visualizzazioni pagina.
   4. Modificare la cartella di lavoro rimuovendo Visualizzazioni pagina dalla richiesta.
   5. Modificate la pianificazione con la cartella di lavoro aggiornata e ripubblicate la richiesta in Power BI.
   6. Una volta che la nuova cartella di lavoro viene inviata a Power BI

      1. Verificate che abbia sovrascritto il set di dati esistente creato al momento della prima pubblicazione.
      2. Verificare che la tabella page_1 sia aggiornata correttamente con le colonne Pagina e Visite.
      3. Verifica che la visualizzazione sia interrotta, in quanto fa riferimento alla colonna Visualizzazioni di pagina che non è più presente nella tabella page_1.

   **Di seguito è riportato un esempio di come LA visualizzazione NON verrà interrotta:**

   1. Ad Report Builder, creare una cartella di lavoro con una richiesta, utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   2. Pianificare la pubblicazione della richiesta in Power BI.
   3. In Power BI, crea una visualizzazione per Visualizzazioni pagina e Visualizzazioni pagina.
   4. Ora modificare la cartella di lavoro in Report Builder, aggiungendo la metrica Visita mantenendo le Visualizzazioni pagina e Pagina.
   5. Modificate la pianificazione con la cartella di lavoro aggiornata e ripubblicate la richiesta in Power BI.
   6. Una volta che la nuova cartella di lavoro viene inviata a Power BI

      1. Verificate che abbia sovrascritto il set di dati esistente creato al momento della prima pubblicazione.
      2. Verificare che la tabella page_1 sia aggiornata correttamente con le colonne Page, Page Views e Visits.
      3. Verifica che la visualizzazione continui a funzionare correttamente, poiché fa riferimento a due colonne ancora presenti nella tabella page_1.


* **Caso 2**: È possibile fissare una sezione della cartella di lavoro su un dashboard in Power BI e successivamente rimuovere la sezione bloccata (ad esempio un grafico o una tabella) dalla cartella di lavoro. In questo modo si interrompe la visualizzazione.

## Modificare il nome di un rapporto Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Per impostazione predefinita, il nome viene popolato dal nome del file della cartella di lavoro (senza l’estensione .xlsx), ma gli spazi vengono sostituiti con caratteri di sottolineatura.

Nota bene

* L&#39;etichetta non può essere una combinazione di lettere e numeri che potrebbero essere erroneamente scambiate per un indirizzo di riga e colonna. Ad esempio, A100 non può essere un&#39;etichetta perché corrisponde all&#39;indirizzo di una cella in un foglio di lavoro.
* I seguenti caratteri non sono caratteri di etichetta validi: &#39;#&#39;, &#39;@&#39;, &#39;!&#39;, &#39;$&#39;, &#39;^&#39;, &#39;&amp;&#39;, &#39;*&#39;, &#39;`&#39;, &#39;~&#39;, &#39; &#39; &#39; . Saranno sostituiti da un carattere di sottolineatura.
* Quando si immette un nome non valido, viene visualizzato un messaggio di avviso che suggerisce un nome generato automaticamente. Se fai clic **[!UICONTROL Yes]**, verrà utilizzato questo nome. Se si fa clic su **[!UICONTROL No]**, l&#39;interfaccia utente della procedura guidata Avanzate consente di immettere il nuovo nome.

