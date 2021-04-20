---
description: Le regole bot consentono di rimuovere dalla suite di rapporti il traffico generato da spider e bot noti. La rimozione del traffico da bot può fornire una misurazione più precisa dell’attività degli utenti sul sito web.
subtopic: Bot rules
title: Panoramica delle regole bot
feature: Admin Tools
uuid: 3cb9e29d-1c37-43de-b7ac-34441093a60e
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 2%

---

# Panoramica delle regole bot

Le regole bot consentono di rimuovere il traffico dalla suite di rapporti generato da spider e bot noti. La rimozione del traffico da bot può fornire una misurazione più precisa dell’attività degli utenti sul sito web.

Una volta definite le regole bot, tutto il traffico in entrata viene confrontato con le regole definite. Il traffico che corrisponde a una qualsiasi di queste regole non viene raccolto nella suite di rapporti e non è incluso nelle metriche del traffico.

Per aggiornare o caricare le regole bot, passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**. Seleziona la suite di rapporti corretta, quindi vai a **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

La rimozione del traffico da bot riduce in genere il volume di traffico e le metriche di conversione. Molti clienti ritengono che la rimozione del traffico da bot determini tassi di conversione più elevati e aumenti in altre metriche di usabilità. Prima di rimuovere il traffico da bot, comunica con le parti interessate per assicurarsi di poter apportare le modifiche necessarie agli indicatori di prestazioni chiave risultanti da questo cambiamento. Se possibile, consigliamo prima di tutto di rimuovere il traffico da bot da una piccola suite di rapporti per stimare il potenziale impatto.

I dati sul traffico dei bot vengono memorizzati in un archivio separato per la visualizzazione nei rapporti Bots e Bot Pages. Sono disponibili due opzioni per abilitare il filtro bot:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot standard IAB | Selezionando [!UICONTROL Enable IAB Bot Filtering Rules] si utilizza l’ [elenco internazionale dei ragni e dei bot di IAB](https://www.iab.com) (International Advertising Bureau) per rimuovere il traffico da bot. La maggior parte dei clienti seleziona questa opzione al minimo. |
| Regole bot personalizzate | Puoi definire e aggiungere regole bot personalizzate in base agli agenti utente, agli indirizzi IP o agli intervalli IP. |

## Regole bot standard IAB

Per attivare le regole bot IAB standard, seleziona la casella di controllo [!UICONTROL Enable IAB Bot Filtering Rules] . Questa selezione rimuoverà i bot dall&#39;elenco internazionale Spiders &amp; Bots dell&#39;IAB (International Advertising Bureau) per rimuovere il traffico da bot. L’Adobe aggiorna questo elenco dall’IAB su base mensile.

![](assets/bot-iab-checkbox.png)

Adobe non è in grado di fornire ai clienti l’elenco dettagliato dei bot IAB, anche se puoi utilizzare il rapporto Bots per visualizzare un elenco dei bot che hanno effettuato l’accesso al tuo sito. Per inviare un bot all’elenco IAB, visita [IAB](https://www.iab.com).

## Regole bot personalizzate

>[!NOTE]
>
>L&#39;interfaccia utente consente di definire manualmente 500 regole. Una volta raggiunto questo limite, le regole devono essere gestite in blocco tramite le opzioni Importa file ed Esporta regole bot.

Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite.

Le regole bot personalizzate vengono definite utilizzando i seguenti tipi di condizioni:

* Agente utente
* Indirizzo IP
* Intervallo IP

È possibile definire più condizioni per una singola regola. Le condizioni multiple vengono soddisfatte utilizzando &quot;o&quot;. Ad esempio, se fornisci un valore per Agente utente e Indirizzo IP, il traffico viene considerato traffico da bot se viene soddisfatta una delle due condizioni.

### Agente utente

Una condizione Agente utente controlla il valore dell&#39;agente utente per vedere se **[!UICONTROL starts with]** o **[!UICONTROL contains]** corrisponde alla stringa specificata. Se è selezionato **[!UICONTROL contains]**, la sottostringa corrisponde se si trova in un punto qualsiasi dell’agente utente.

I valori facoltativi possono essere inclusi nell&#39;elenco **[!UICONTROL does not contain]** per definire i valori che l&#39;agente utente non deve contenere per una corrispondenza corretta. È possibile specificare più valori includendo un valore per riga. Se l’agente utente soddisfa i criteri specificati nella stringa di corrispondenza, ma contiene anche una stringa nell’elenco non contiene , non viene considerata una corrispondenza.

Il campo **[!UICONTROL contains]** è limitato a 100 caratteri. L’elenco non contiene è limitato a 255 caratteri meno un carattere separatore per ogni nuova riga. È uguale al numero di stringhe - 1. Se si specifica 4 *non contiene stringhe*, sono necessari 3 caratteri separatori.) Tutte le corrispondenze delle stringhe fanno distinzione tra maiuscole e minuscole.

### Indirizzo IP (comprese le corrispondenze con caratteri jolly)

Corrisponde a uno o più indirizzi IP nello stesso blocco utilizzando caratteri jolly (*). Immetti i valori numerici dell’indirizzo IP a cui desideri associare. Sostituisci * per tutti i valori che desideri associare utilizzando un carattere jolly. Il seguente elenco contiene esempi di stringa di corrispondenza dell’indirizzo IP:

```
10.10.10.1
10.10.10.*
```

### Intervallo indirizzi IP

Specifica gli intervalli iniziale e finale degli indirizzi IP da abbinare. Sostituisci * per tutti i valori che desideri associare utilizzando un carattere jolly.

### Definire una regola bot personalizzata

1. Vai a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, seleziona una o più suite di rapporti e fai clic su **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Fai clic su **[!UICONTROL Add Rule]** e definisci una o più condizioni di corrispondenza.
1. Fai clic su **[!UICONTROL Save]**. La modifica dovrebbe avere effetto entro 30 minuti.

## Caricare regole bot

Per importare in massa regole bot, puoi caricare un file CSV che definisce le regole.

Crea un file CSV con le seguenti colonne, nell’ordine indicato:

| Colonna 1 | Colonna 2 | Colonna 3 | Colonna 4 | Colonna 5 |
|--- |--- |---|---|---|
| Nome bot | Avvio IP | Fine IP | Regola di corrispondenza dell&#39;agente<br>(contiene o inizia con)</br> | Esclusione agente<br>(limite di 255 caratteri)</br> |

Puoi definire tre tipi di regole bot:

* L&#39;agente utente contiene o inizia con
* Indirizzo IP singolo o corrispondenza con carattere jolly
* Corrispondenza della gamma IP

Ogni riga del file di importazione può contenere solo una delle seguenti definizioni bot:

* **L&#39;agente utente contiene o inizia con**: Fornire una singola stringa dell&#39;agente utente da abbinare nella colonna Includi agente. Specifica il tipo di corrispondenza che desideri eseguire inserendo *contains* o *inizia con* nel campo Regola corrispondenza agente. Un valore facoltativo può essere incluso nella colonna Escludi agente che definisce una o più stringhe delimitate da barre verticali ( `|` ) che l&#39;agente non contiene. Le corrispondenze delle stringhe distinguono tra maiuscole e minuscole. Le colonne Avvio IP e Fine IP devono essere vuote.

* **Indirizzo IP singolo o carattere jolly corrispondente**: Per trovare una corrispondenza con un indirizzo IP singolo (  `10.10.10.1`) o con un indirizzo IP jolly (  `10.10.*.*`), inserisci lo stesso valore nelle colonne Start IP e Fine IP. La regola di corrispondenza, l&#39;inclusione dell&#39;agente e l&#39;esclusione dell&#39;agente devono essere vuote.

* **Corrispondenza** intervallo IP: Definisci un intervallo di indirizzi IP utilizzando le colonne Inizio IP e Fine IP . I caratteri jolly possono essere utilizzati per corrispondere agli intervalli IP, ad esempio da `10.10.10.*` a `10.10.20.*`. La regola di corrispondenza, l&#39;inclusione dell&#39;agente e l&#39;esclusione dell&#39;agente devono essere vuote.

### Più regole combinate con OR

Per associare un bot utilizzando una combinazione di regole unite a un operatore OR (ad esempio, agente utente o indirizzo IP), fornisci un nome identico per tutte le regole che desideri combinare nel campo del nome bot. Le corrispondenze AND non sono supportate.

### Sovrascrivi tutte le regole con un file di caricamento

Seleziona la casella di controllo **[!UICONTROL Overwrite existing rules]** per eliminare tutte le regole esistenti e sostituirle con le regole definite nel file di caricamento.

### Regole di esportazione

Il pulsante **[!UICONTROL Export Uploaded Bot File]** esporta tutte le regole definite nell’interfaccia utente in formato CSV.


## Impatto delle regole bot sulla raccolta dei dati {#section_F01A3130E7A04A9993371CF26F6586F2}

Le regole bot vengono applicate a tutti i dati di analisi. I dati rimossi dalle regole bot sono visibili solo nei rapporti Bots e Bot Pages.

Le regole VISTA vengono applicate dopo le regole bot (vedi [Ordine di elaborazione).](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)

**Elaborazione delle visite ad alto hit:** se si verificano più di 100 hit in una visita, il reporting determina se l’ora della visita in secondi è inferiore o uguale al numero di hit nella visita. In questa situazione, a causa dei costi di elaborazione di visite lunghe e intense, il reporting inizia con una nuova visita. Le visite ad alto hit sono solitamente causate da attacchi di bot e non sono considerate come normale navigazione dei visitatori.

>[!NOTE]
>
>Gli hit contrassegnati come *`bots`* vengono fatturati come chiamate server [.](/help/admin/c-server-call-usage/overage-overview.md)

## Impatto dell&#39;offuscamento dell&#39;IP sul filtro bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

L’elenco dei bot IAB si basa esclusivamente sull’agente utente, pertanto i filtri basati su tale elenco non sono influenzati dalle impostazioni di offuscamento dell’IP. Per il filtro bot non IAB (regole personalizzate), l’IP può far parte dei criteri di filtro. Se si filtrano i bot utilizzando l’IP, il filtro bot viene applicato dopo che l’ultimo ottetto è stato rimosso se tale impostazione è abilitata, ma prima delle altre opzioni di offuscamento dell’IP, ad esempio se si elimina l’intero IP o lo si sostituisce con un ID univoco.

Se l’offuscamento dell’IP è abilitato, l’esclusione IP si verifica prima che l’indirizzo IP sia offuscato, pertanto i clienti non devono apportare alcuna modifica quando abilitano l’offuscamento dell’IP.

Se l’ultimo ottetto viene rimosso, questo viene fatto prima del filtro IP. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano a zero agli indirizzi IP alla fine. La corrispondenza * deve corrispondere a 0.
