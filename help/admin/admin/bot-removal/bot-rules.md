---
description: Le regole bot consentono di rimuovere dalla suite di rapporti il traffico generato da spider e bot noti. La rimozione del traffico da bot può fornire una misurazione più precisa dell’attività degli utenti sul sito web.
title: Panoramica delle regole bot
feature: Bot Removal
exl-id: 1c0009f6-2746-4ef1-8dcb-e2693617e91e
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '1322'
ht-degree: 100%

---

# Panoramica delle regole bot

Le regole bot consentono di rimuovere il traffico dalla suite di rapporti generato da spider e bot noti. La rimozione del traffico da bot può fornire una misurazione più precisa dell’attività degli utenti sul sito web.

Ecco un video sulla configurazione delle regole bot:

>[!VIDEO](https://video.tv.adobe.com/v/335738/?quality=12)

Una volta definite le regole bot, tutto il traffico in entrata viene confrontato con le regole definite. Il traffico che corrisponde a una qualsiasi di queste regole non viene inserito nella suite di rapporti e non è incluso nelle metriche di traffico.

Per aggiornare o caricare le regole bot, passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**. Seleziona la suite di rapporti corretta, quindi vai a **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.

La rimozione del traffico da bot riduce in genere il volume di traffico e le metriche di conversione. Molti clienti ritengono che la rimozione del traffico da bot determini tassi di conversione più elevati e aumenti in altre metriche di usabilità. Prima di rimuovere il traffico da bot, comunica con le parti interessate per assicurarti di poter apportare le modifiche necessarie agli indicatori di prestazioni chiave risultanti da questo cambiamento. Se possibile, consigliamo prima di tutto di rimuovere il traffico da bot da una piccola suite di rapporti in modo da stimarne il potenziale impatto.

I dati sul traffico generato dai bot vengono memorizzati in un archivio separato e visualizzati nei rapporti Bots e Bot Pages. Sono disponibili due opzioni per abilitare il filtro dei bot:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot standard IAB | Se si seleziona [!UICONTROL Enable IAB Bot Filtering Rules], per rimuovere il traffico da bot viene utilizzata la lista internazionale Spiders e Bots di [IAB](https://www.iab.com) (International Advertising Bureau). La maggior parte dei clienti seleziona come minimo questa opzione. |
| Regole bot personalizzate | Puoi definire e aggiungere regole bot personalizzate in base ad agenti utente, indirizzi IP o intervalli IP. |

## Regole bot standard IAB

Le regole IAB standard possono essere attivate selezionando la casella di controllo [!UICONTROL Enable IAB Bot Filtering Rules]. Questa selezione rimuoverà i bot inseriti nell’elenco internazionale Spiders e Bots di IAB (International Advertising Bureau) per eliminare il traffico generato da bot. Adobe aggiorna questo elenco da IAB su base mensile.

![](assets/bot-iab-checkbox.png)

Adobe non è in grado di fornire ai clienti l’elenco dettagliato dei bot IAB; tuttavia puoi utilizzare il rapporto Bots per ottenere un elenco dei bot che hanno effettuato l’accesso al tuo sito. Per segnalare un bot da inserire nell’elenco IAB, visita [IAB](https://www.iab.com).

## Regole bot personalizzate

>[!NOTE]
>
>L’interfaccia utente consente di definire manualmente 500 regole. Al raggiungimento di tale limite, le regole devono essere gestite in gruppo usando le opzioni Importa file ed Esporta regole bot.

Le regole bot personalizzate consentono di filtrare il traffico sulla base delle condizioni definite.

Le regole bot personalizzate vengono definite utilizzando i seguenti tipi di condizioni:

* Agente utente
* Indirizzo IP
* Intervallo IP

È possibile definire più condizioni per una singola regola. Più condizioni vengono applicate utilizzando “or”. Ad esempio, se fornisci un valore per Agente utente e Indirizzo IP, il traffico viene considerato traffico da bot se viene soddisfatta una delle due condizioni.

### Agente utente

Una condizione Agente utente controlla il valore dell’agente utente per verificaree se **[!UICONTROL starts with]** o **[!UICONTROL contains]** la stringa specificata. Se se è selezionato **[!UICONTROL contains]**, la sottostringa viene rilevata se si trova in un punto qualsiasi dell’agente utente.

Eventuali valori possono essere inclusi nell’elenco **[!UICONTROL does not contain]** per rilevare gli agenti utenti che non contengono tali valori. È possibile specificare più valori includendo un valore per riga. Se l’agente utente soddisfa i criteri specificati nella stringa di corrispondenza, ma contiene anche una stringa dell’elenco “does not contain”, non viene considerata una corrispondenza.

Il campo **[!UICONTROL contains]** è limitato a 100 caratteri. L’elenco “does not contain” è limitato a 255 caratteri meno un carattere separatore per ogni nuova riga. Il numero di caratteri separatori è uguale al numero di stringhe - 1. Se si specificano 4 stringhe *does not contain*, sono necessari 3 caratteri separatori. La corrispondenza delle stringhe fa distinzione tra maiuscole e minuscole.

### Indirizzo IP (comprese le corrispondenze con caratteri jolly)

Trova uno o più indirizzi IP nello stesso blocco utilizzando caratteri jolly (*). Specifica i valori numerici dell’indirizzo IP da trovare. Sostituisci * per tutti i valori da trovare utilizzando un carattere jolly. Il seguente elenco contiene esempi di stringa di corrispondenza dell’indirizzo IP:

```
10.10.10.1
10.10.10.*
```

### Intervallo indirizzi IP

Specifica gli intervalli iniziale e finale degli indirizzi IP da rilevare. Sostituisci * per tutti i valori da trovare utilizzando un carattere jolly.

### Definire una regola bot personalizzata

1. Passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin]**, seleziona una o più suite di rapporti e fai clic su **[!UICONTROL General]** > **[!UICONTROL Bot Rules]**.
1. Fai clic su **[!UICONTROL Add Rule]** e definisci una o più condizioni di corrispondenza.
1. Fai clic su **[!UICONTROL Save]**. La modifica dovrebbe avere effetto entro 30 minuti.

## Caricare regole bot

Per importare in blocco le regole bot, puoi caricare un file CSV che le definisce.

Crea un file CSV con le seguenti colonne, nell’ordine indicato:

| Colonna 1 | Colonna 2 | Colonna 3 | Colonna 4 | Colonna 5 |
|--- |--- |---|---|---|
| Nome bot | Inizio IP | Fine IP | Regola di corrispondenza agente<br>(contiene o inizia con)</br> | Esclusione agente<br>(limite di 255 caratteri)</br> |

Puoi definire tre tipi di regole bot:

* L’agente utente contiene o inizia con
* Corrispondenza indirizzo IP singolo o con caratteri jolly
* Corrispondenza intervallo IP

Ogni riga del file di importazione può contenere solo una delle seguenti definizioni di bot:

* **L’agente utente contiene o inizia con**: specifica una singola stringa dell’agente utente da rilevare nella colonna degli agenti da includere. Per specificare il tipo di corrispondenza da eseguire, inserisci *contains* o *starts with* nel campo Regola di corrispondenza agente. Un valore facoltativo può essere incluso nella colonna Esclusione agente che definisce una o più stringhe delimitate da barre verticali (`|`) che l’agente non contiene. La corrispondenza delle stringhe non fa distinzione tra maiuscole e minuscole. Le colonne Inizio IP e Fine IP devono essere vuote.

* **Corrispondenza indirizzo IP singolo o con caratteri jolly**: per far corrispondere un singolo indirizzo IP ( `10.10.10.1`) o indirizzo IP con caratteri jolly (`10.10.*.*`), inserisci lo stesso valore nelle colonne Inizio IP e Fine IP. Regola di corrispondenza, Inclusione agente ed Esclusione agente devono essere vuoti.

* **Corrispondenza intervallo IP**: definisci un intervallo di indirizzi IP utilizzando le colonne Inizio IP e Fine IP. I caratteri jolly possono essere utilizzati per rilevare intervalli IP, ad esempio `10.10.10.*` a `10.10.20.*`. Regola di corrispondenza, Inclusione agente ed Esclusione agente devono essere vuoti.

### Più regole combinate con OR

Per rilvare un bot utilizzando una combinazione di regole unite con un operatore OR (ad esempio, agente utente o indirizzo IP), specifica nel campo del nome del bot un nome identico per tutte le regole che desideri combinare. Le corrispondenze AND non sono supportate.

### Sovrascrivere tutte le regole con un file di caricamento

Seleziona la casella di controllo **[!UICONTROL Overwrite existing rules]** per eliminare tutte le regole esistenti e sostituirle con le regole definite nel file caricato.

### Esportare le regole

Il pulsante **[!UICONTROL Export Uploaded Bot File]** esporta tutte le regole definite nell’interfaccia utente in formato CSV.


## Impatto delle regole bot sulla raccolta dei dati {#section_F01A3130E7A04A9993371CF26F6586F2}

Le regole bot vengono applicate a tutti i dati di analisi. I dati rimossi dalle regole bot sono visibili solo nei rapporti su bot e pagine bot.

Le regole VISTA vengono applicate dopo le regole bot (vedi [Ordine di elaborazione).](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md)

**Elaborazione di visite con numero elevato di hit:** se in una visita si verificano più di 100 hit, il reporting determina se la durata della visita in secondi è inferiore o uguale al numero di hit nella visita. In questa situazione, a causa dei costi di elaborazione di visite lunghe e intense, il reporting inizia da capo con una nuova visita. Le visite con molti hit sono solitamente causate da attacchi di bot e non sono considerate come normale attività di navigazione dei visitatori.

>[!NOTE]
>
>Gli hit contrassegnati come *`bots`* sono fatturati come [chiamate al server.](/help/admin/c-server-call-usage/overage-overview.md)

## Impatto dell’offuscamento dell’IP sul filtro dei bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

L’elenco dei bot IAB si basa esclusivamente sull’agente utente, pertanto i filtri basati su tale elenco non sono influenzati dalle impostazioni di offuscamento dell’IP. Per il filtro bot non IAB (regole personalizzate), l’IP può far parte dei criteri di filtro. Se si filtrano i bot utilizzando l’IP, il filtro bot viene applicato dopo che l’ultimo ottetto è stato rimosso se tale impostazione è abilitata, ma prima delle altre opzioni di offuscamento dell’IP, ad esempio se si elimina l’intero IP o lo si sostituisce con un ID univoco.

Se l’offuscamento dell’IP è abilitato, l’esclusione di tale IP si verifica prima che l’indirizzo IP sia offuscato, pertanto i clienti non devono apportare alcuna modifica quando abilitano l’offuscamento dell’IP.

Se l’ultimo ottetto viene rimosso, questa operazione viene eseguita prima del filtro dell’IP. Di conseguenza, l’ultimo ottetto viene sostituito da 0 e le regole di esclusione IP devono essere aggiornate in modo che corrispondano agli indirizzi IP con uno zero alla fine. La corrispondenza * deve corrispondere a 0.
