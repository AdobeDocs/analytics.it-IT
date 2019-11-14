---
description: Le regole bot consentono di rimuovere il traffico generato da spider e bot noti dalla suite di rapporti. La rimozione del traffico bot può fornire una misurazione più precisa dell’attività degli utenti sul sito Web.
solution: Analytics
subtopic: Bot rules
title: Panoramica delle regole bot
topic: Admin tools
uuid: 3cb9e29d-1c37-43de-b7ac-34441093a60e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Panoramica delle regole bot

Le regole bot consentono di rimuovere il traffico dalla suite di rapporti generato da spider e bot noti. La rimozione del traffico bot può fornire una misurazione più precisa dell’attività degli utenti sul sito Web.

Una volta definite le regole bot, tutto il traffico in entrata viene confrontato con le regole definite. Il traffico corrispondente a una di queste regole non viene raccolto nella suite di rapporti e non è incluso nelle metriche del traffico.

Per aggiornare o caricare le regole bot, andate a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Selezionate la suite di rapporti corretta, quindi passate a **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

La rimozione del traffico bot riduce in genere il volume del traffico e le metriche di conversione. Molti clienti ritengono che la rimozione del traffico bot determini un aumento dei tassi di conversione e aumenti delle altre metriche di usabilità. Prima di rimuovere il traffico bot, comunicare con le parti interessate per assicurarsi di poter apportare le modifiche necessarie agli indicatori di prestazioni chiave come risultato di questa modifica. Se possibile, si consiglia innanzitutto di rimuovere il traffico bot da una piccola suite di rapporti per stimare l'impatto potenziale.

I dati relativi al traffico dei bot vengono memorizzati in un archivio separato per la visualizzazione nei rapporti Bots and Bot Pages. Esistono due opzioni per attivare il filtro bot:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot IAB standard | La selezione [!UICONTROL Enable IAB Bot Filtering Rules] utilizza l' [IAB](https://www.iab.com) (International Advertising Bureau's) International Spiders &amp; Bots List per rimuovere il traffico bot. La maggior parte dei clienti seleziona questa opzione almeno. |
| Regole bot personalizzate | Potete definire e aggiungere regole bot personalizzate basate su agenti utente, indirizzi IP o intervalli IP. |

## Regole bot IAB standard

Le regole standard per bot IAB possono essere attivate selezionando la [!UICONTROL Enable IAB Bot Filtering Rules] casella di controllo. Questa selezione rimuoverà i bot in IAB (International Advertising Bureau's) International Spiders &amp; Bots List per rimuovere il traffico bot. L'IAB aggiorna questo elenco mensilmente.

![](assets/bot-iab-checkbox.png)

Adobe non è in grado di fornire ai clienti l'elenco dettagliato dei bot IAB, anche se potete utilizzare il rapporto Bots per visualizzare un elenco dei bot che hanno eseguito l'accesso al sito. Per inviare un bot alla lista IAB, visitate [IAB](https://www.iab.com).

## Regole bot personalizzate

>[!NNota] L'interfaccia utente consente di definire manualmente 500 regole. Una volta raggiunto questo limite, le regole devono essere gestite in blocco tramite le opzioni Importa file ed Esporta regole bot.

Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite dall'utente.

Le regole bot personalizzate sono definite utilizzando i seguenti tipi di condizione:

* Agente utente
* Indirizzo IP
* Intervallo IP

È possibile definire più condizioni per una singola regola. Per condizioni multiple viene utilizzato "or". Ad esempio, se specificate un valore per Agente utente e Indirizzo IP, il traffico viene considerato traffico bot se una delle due condizioni è soddisfatta.

### Agente utente

Una condizione Agente utente verifica il valore dell'agente utente per verificare se si tratta **[!UICONTROL starts with]** o meno **[!UICONTROL contains]** della stringa specificata. Se **[!UICONTROL contains]** è selezionata, la sottostringa corrisponde se si trova in un punto qualsiasi dell'agente utente.

I valori facoltativi possono essere inclusi nell' **[!UICONTROL does not contain]** elenco per definire i valori che l'agente utente non deve contenere per una corrispondenza di successo. È possibile specificare più valori includendo un valore per riga. Se l'agente utente soddisfa i criteri specificati nella stringa di corrispondenza, ma contiene anche una stringa nell'elenco non contiene, non viene considerata una corrispondenza.

Il **[!UICONTROL contains]** campo è limitato a 100 caratteri. L'elenco non contiene un massimo di 255 caratteri meno un carattere separatore per ogni nuova riga. È uguale al numero di stringhe - 1. Se si specifica 4 *non contiene* stringhe, sono necessari 3 caratteri di separazione. Tutte le corrispondenze stringa non fanno distinzione tra maiuscole e minuscole.

### Indirizzo IP (comprese le corrispondenze con caratteri jolly)

Corrisponde a uno o più indirizzi IP nello stesso blocco utilizzando i caratteri jolly (*). Specificare i valori numerici dell'indirizzo IP che si desidera abbinare. Sostituisci * per tutti i valori che vuoi far corrispondere utilizzando un carattere jolly. Il seguente elenco contiene esempi di stringa di corrispondenza indirizzo IP:

```
10.10.10.1
10.10.10.*
```

### Intervallo indirizzi IP

Specificare gli intervalli iniziale e finale degli indirizzi IP da associare. Sostituisci * per tutti i valori che vuoi far corrispondere utilizzando un carattere jolly.

### Definire una regola bot personalizzata

1. Vai a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, seleziona una o più suite di rapporti e fai clic su **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.
1. Fate clic su **[!UICONTROL Add Rule]** e definite una o più condizioni di corrispondenza.
1. Fai clic su **[!UICONTROL Save]**. La modifica dovrebbe avere effetto entro 30 minuti.

## Caricare regole bot

Per importare in massa regole bot, potete caricare un file CSV che definisce le regole.

Create un file CSV con le seguenti colonne, nell'ordine indicato:

| Colonna 1 | Colonna 2 | Colonna 3 | Colonna 4 | Colonna 5 |
|--- |--- |---|---|---|
| Nome bot | Inizio IP | Fine IP | Regola<br>corrispondenza agente (contiene o inizia con)</br> | Escludi<br>agente (limite di 255 caratteri)</br> |

Potete definire tre tipi di regole bot:

* L'agente utente contiene o inizia con
* Indirizzo IP singolo o corrispondenza carattere jolly
* Corrispondenza della gamma IP

Ogni riga del file di importazione può contenere solo una delle seguenti definizioni di bot:

* **L'agente utente contiene o inizia con**: Specifica una singola stringa agente utente da corrispondere nella colonna Include agente. Specificate il tipo di corrispondenza da eseguire inserendo *contains* o *inizia con* nel campo Regola corrispondenza agente. Un valore facoltativo può essere incluso nella colonna Escludi agente che definisce una o più stringhe delimitate da pipe ( `|` ) che l'agente non contiene. Le corrispondenze delle stringhe non fanno distinzione tra maiuscole e minuscole. Le colonne Inizio IP e Fine IP devono essere vuote.

* **Indirizzo IP singolo o corrispondenza** carattere jolly: Per corrispondere a un indirizzo IP singolo ( `10.10.10.1`) o a un indirizzo IP jolly ( `10.10.*.*`), inserite lo stesso valore sia nelle colonne Inizio IP che Fine IP. Regola di corrispondenza, Include agente e Escludi agente devono essere vuoti.

* **Corrispondenza** gamma IP: Definite un intervallo di indirizzi IP utilizzando le colonne Inizio IP e Fine IP. I caratteri jolly possono essere utilizzati per corrispondere agli intervalli IP, ad esempio `10.10.10.*` a `10.10.20.*`. Regola di corrispondenza, Include agente e Escludi agente devono essere vuoti.

### Regole multiple combinate con OR

Per far corrispondere un bot utilizzando una combinazione di regole collegate con un operatore OR (ad esempio, agente utente o indirizzo IP), immettete un nome identico per tutte le regole che desiderate combinare nel campo del nome del bot. Le corrispondenze AND non sono supportate.

### Sovrascrivi tutte le regole con un file di caricamento

Selezionate la **[!UICONTROL Overwrite existing rules]** casella di controllo per eliminare tutte le regole esistenti e sostituirle con quelle definite nel file di caricamento.

### Regole di esportazione

Il **[!UICONTROL Export Uploaded Bot File]** pulsante consente di esportare tutte le regole definite nell’interfaccia in formato CSV.


## Impatto delle regole bot sulla raccolta dei dati {#section_F01A3130E7A04A9993371CF26F6586F2}

Le regole bot vengono applicate a tutti i dati di analisi. I dati rimossi dalle regole bot sono visibili solo nei rapporti Bots and Bot Pages.

Le regole VISTA vengono applicate dopo le regole bot (consultate Ordine di [elaborazione).](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)

**** Elaborazione delle visite ad alta qualità: Se si verificano più di 100 hit in una visita, il reporting determina se l’ora della visita, in secondi, è minore o uguale al numero di hit presenti nella visita. In questa situazione, a causa dei costi di elaborazione di visite lunghe e intense, la segnalazione inizia con una nuova visita. Le visite ad alto impatto sono in genere causate da attacchi bot e non sono considerate normali esplorazioni dei visitatori.

> [!NOTE] Gli hit contrassegnati come *`bots`* vengono fatturati come chiamate [server.](/help/admin/c-server-call-usage/overage-overview.md)

## Impatto dell'offuscamento IP sui filtri bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

L'elenco dei bot IAB è basato esclusivamente sull'agente utente, pertanto il filtraggio basato su tale elenco non viene influenzato dalle impostazioni di oscuramento dell'IP. Per i filtri bot non IAB (regole personalizzate), l'IP potrebbe essere parte dei criteri di filtro. Se filtrate i bot tramite IP, il filtraggio dei bot avviene dopo che l'ultimo ottetto è stato rimosso se tale impostazione è attivata, ma prima delle altre opzioni di offuscamento dell'IP, ad esempio l'eliminazione dell'intero IP o la sostituzione con un ID univoco.

Se l'offuscamento IP è abilitato, l'esclusione IP avviene prima che l'indirizzo IP sia oscurato, quindi i clienti non devono cambiare nulla quando attivano l'offuscamento IP.

Se l'ultimo ottetto viene rimosso, questo viene fatto prima del filtro IP. Di conseguenza, l'ultimo ottetto viene sostituito con 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0.
