---
description: nulle
seo-description: nulle
seo-title: Limitazioni e specifiche
title: Limitazioni e specifiche
uuid: 6717 b 6 ea -7 e 01-49 b 8-8 f 6 e-fb 733 a 03 b 687
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Limitazioni e specifiche

## Power BI publishing restrictions {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>Queste restrizioni si applicano solo all'opzione «Pubblica richieste Generatore di report come tabelle Dataset Power BI».

* È possibile esportare fino a 100 richieste di Generatore di report in Power BI per cartella di lavoro.
* Il processo di pianificazione interrompe le richieste di esportazione quando viene raggiunta la 101 ° richiesta.
* Solo le prime 10,000 righe di dati di Analytics verranno inviate a Power BI per Generatore di report. Le righe rimanenti verranno ignorate.

## Edit a Report Builder request after publishing to Power BI {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>Questa specifica si applica alle opzioni «Pubblica tutte le richieste di Generatore di report come tabelle Dataset Power BI» e «Pubblica tutte le tabelle formattate nella cartella di lavoro come tabelle Dataset Power BI».

La modifica di una richiesta di Generatore di report dopo averlo pubblicato in Power BI può causare problemi.

* **Caso 1**: È possibile pubblicare una cartella di lavoro su Power BI e creare una visualizzazione basata sui dati. Successivamente, si apporta modifiche alla cartella di lavoro, comportando la scomparsa di una delle colonne del set di dati. Quindi ripubblica. In questo modo la visualizzazione verrà interrotta in Power BI.

   **Ecco un esempio di come si interrompe la visualizzazione:**

   1. In Generatore di report, crea una cartella di lavoro con una richiesta, utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   1. [Pianificate questa richiesta](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) da pubblicare su Power BI.
   1. In Power BI, crea una visualizzazione per Page e Page Views (Visualizzazioni pagina).
   1. Ora modificate la cartella di lavoro rimuovendo Visualizzazioni pagina dalla richiesta.
   1. Modificate la pianificazione con la cartella di lavoro aggiornata e ripubblicate la richiesta su Power BI.
   1. Una volta che la nuova cartella di lavoro è stata inviata a Power BI

      1. Verificate che abbia sovrascritto il set di dati esistente creato al momento della pubblicazione.
      1. Verifica che la tabella page_ 1 sia aggiornata correttamente con le colonne Pagina e Visite.
      1. Verifica che la visualizzazione sia interrotta, poiché fa riferimento alla colonna Visualizzazioni pagina che non è più presente nella tabella pagina_ 1.
   **Esempio di come la visualizzazione NON intercetta:**

   1. In Generatore di report, crea una cartella di lavoro con una richiesta, utilizzando la dimensione Pagina e la metrica Visualizzazioni pagina.
   1. [Pianificate questa richiesta](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463) da pubblicare su Power BI.
   1. In Power BI, crea una visualizzazione per Page e Page Views (Visualizzazioni pagina).
   1. Ora puoi modificare la cartella di lavoro in Generatore di report, aggiungendo la metrica Visita mantenendo la pagina e visualizzazioni pagina.
   1. Modificate la pianificazione con la cartella di lavoro aggiornata e ripubblicate la richiesta su Power BI.
   1. Una volta che la nuova cartella di lavoro è stata inviata a Power BI

      1. Verificate che abbia sovrascritto il set di dati esistente creato al momento della pubblicazione.
      1. Verifica che la tabella pagina_ 1 sia aggiornata correttamente con le colonne Pagina, Visualizzazioni pagina e Visite.
      1. Verifica che la visualizzazione continui a funzionare correttamente, in quanto fa riferimento a due colonne ancora presenti nella tabella page_ 1.


* **Caso 2**: Potete fissare una sezione della cartella di lavoro su una dashboard in Power BI e successivamente rimuovere la sezione bloccata (ad esempio un grafico o una tabella) dalla cartella di lavoro. In questo modo la visualizzazione verrà interrotta.

## Change the name of a Power BI report {#section_2E7893A78B914EBFACB2B08CBD9E472E}

Per impostazione predefinita, il nome verrà popolato dal nome del file di cartelle (senza l'estensione.xlsx), fatta eccezione per gli spazi sostituiti con caratteri di sottolineatura.

Aspetti da considerare:

* L'etichetta non può essere una combinazione di lettere e numeri che potrebbero essere errate per una riga e l'indirizzo della colonna. Ad esempio, A 100 non può essere un'etichetta perché è l'indirizzo di una cella in un foglio di lavoro.
* I caratteri seguenti non sono caratteri di etichetta validi: ' #','@','! ','$','^','&amp;','*', ",'~',''. Vengono sostituiti da un carattere carattere di sottolineatura.
* Quando immettete un nome non valido, verrà visualizzato un messaggio di avviso che suggerisce un nome generato automaticamente. If you click **[!UICONTROL Yes]**, this name will be used. If you click **[!UICONTROL No]**, the Advanced Wizard UI will let you enter the new name.

