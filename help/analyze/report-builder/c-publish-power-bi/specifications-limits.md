---
description: Limitazioni per l'utilizzo di Report Builder e Microsoft Power BI.
title: Limiti e specifiche
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
feature: Report Builder
role: Business Practitioner, Administrator
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
source-git-commit: c420a9468dc39922bd02047160bb07623503eee4
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 1%

---

# Limiti e specifiche

## Restrizioni alla pubblicazione dei Power BI {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Queste restrizioni si applicano solo all’opzione &quot;Pubblica richieste di Report Builder come tabelle di set di dati di Power BI&quot;.

* È possibile esportare un massimo di 100 richieste di Report Builder in Power BI per cartella di lavoro.
* Il processo di pianificazione interrompe l’esportazione delle richieste quando viene raggiunta la 101a richiesta.
* Solo le prime 10.000 righe di dati Analytics verranno inviate a Power BI per richiesta di Report Builder. Le righe rimanenti verranno ignorate.

## Modificare una richiesta di Report Builder dopo la pubblicazione su Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Questa specifica si applica alle opzioni &quot;Pubblica tutte le richieste di Report Builder come tabelle di set di dati Power BI&quot; e &quot;Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle di set di dati Power BI&quot;.

La modifica di una richiesta di Report Builder dopo la pubblicazione su Power BI può causare problemi.

* **Caso 1**: È possibile pubblicare una cartella di lavoro in Power BI e crearne una visualizzazione basata sui relativi dati. Successivamente, le modifiche apportate alla cartella di lavoro causano la scomparsa di una delle colonne del set di dati a cui fa riferimento. Poi ripubblichi. In questo modo si interrompe la visualizzazione in Power BI.

   **Ecco un esempio di interruzione della visualizzazione:**

   1. Al Report Builder, crea una cartella di lavoro con una richiesta utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   2. Pianifica la pubblicazione della richiesta in Power BI.
   3. In Power BI, crea una visualizzazione per Visualizzazioni pagina e pagina.
   4. Ora modifica la cartella di lavoro rimuovendo Visualizzazioni pagina dalla richiesta.
   5. Modifica la pianificazione con la cartella di lavoro aggiornata e ripubblica la richiesta in Power BI.
   6. Una volta inviata la nuova cartella di lavoro a Power BI

      1. Verifica che abbia sovrascritto il set di dati esistente creato al momento della prima pubblicazione.
      2. Verifica che la tabella page_1 sia aggiornata correttamente con le colonne Pagina e Visite .
      3. Verifica che la visualizzazione sia interrotta, poiché fa riferimento alla colonna Visualizzazioni di pagina che non è più presente nella tabella page_1.

   **Ecco un esempio di come la visualizzazione NON verrà interrotta:**

   1. Al Report Builder, crea una cartella di lavoro con una richiesta utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   2. Pianifica la pubblicazione della richiesta in Power BI.
   3. In Power BI, crea una visualizzazione per Visualizzazioni pagina e pagina.
   4. Ora modifica la cartella di lavoro in Report Builder, aggiungendo la metrica Visita mantenendo le visualizzazioni di pagina e pagina.
   5. Modifica la pianificazione con la cartella di lavoro aggiornata e ripubblica la richiesta in Power BI.
   6. Una volta inviata la nuova cartella di lavoro a Power BI

      1. Verifica che abbia sovrascritto il set di dati esistente creato al momento della prima pubblicazione.
      2. Verifica che la tabella page_1 sia aggiornata correttamente con le colonne Page, Page Views e Visits (Pagina, Visualizzazioni pagina e Visite).
      3. Verifica che la visualizzazione continui a funzionare correttamente, poiché fa riferimento a due colonne ancora presenti nella tabella page_1.


* **Caso 2**: È possibile fissare una sezione della cartella di lavoro in un dashboard in Power BI e successivamente rimuovere la sezione bloccata (ad esempio un grafico o una tabella) dalla cartella di lavoro. Interrompe la visualizzazione.

## Modificare il nome di un rapporto Power BI {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Per impostazione predefinita, il nome verrà popolato dal nome del file della cartella di lavoro (senza l’estensione xlsx), tranne per il fatto che gli spazi vengono sostituiti con caratteri di sottolineatura.

Nota bene

* L’etichetta non può essere una combinazione di lettere e numeri che potrebbero essere erroneamente utilizzate per l’indirizzo di una riga o di una colonna. Ad esempio, A100 non può essere un&#39;etichetta perché è l&#39;indirizzo di una cella in un foglio di lavoro.
* I seguenti caratteri non sono caratteri di etichetta validi: `'#', '@', '!', '$', '^', '&', '&#42;', '`&#39; e `'~', ' '` . Vengono sostituiti da un carattere di sottolineatura.
* Quando si immette un nome non valido, viene visualizzato un messaggio di avviso che suggerirà un nome generato automaticamente. Se fai clic su **[!UICONTROL Yes]**, verrà utilizzato questo nome. Se si fa clic su **[!UICONTROL No]**, l&#39;interfaccia utente della procedura guidata avanzata consente di immettere il nuovo nome.
