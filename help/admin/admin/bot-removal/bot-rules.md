---
description: Regole bot consente di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web.
seo-description: Regole bot consente di rimuovere il traffico generato da spider noti e bot dalla suite di rapporti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web.
seo-title: Regole bot
solution: Analytics
subtopic: Regole bot
title: Panoramica delle regole bot
topic: Strumenti di amministrazione
uuid: 3 cb 9 e 29 d -1 c 37-43 de-b 7 ac -34441093 a 60 e
translation-type: tm+mt
source-git-commit: 5574b9e37e68971f7ecaa05056a30dab0b3d5d47

---


# Panoramica delle regole bot

Regole bot consente di rimuovere il traffico dalla suite di rapporti generata da spider e bot noti. La rimozione del traffico bot permette di misurare meglio l'attività degli utenti sul sito Web.

Dopo la definizione delle regole bot, tutto il traffico in arrivo viene confrontato con le regole definite. Il traffico che corrisponde a una di queste regole non viene raccolto nella suite di rapporti e non è incluso nelle metriche del traffico.

Per aggiornare o caricare le regole bot, passa **[!UICONTROL Analytics]** a &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**. Seleziona la suite di rapporti corretta, quindi vai a **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Bot Rules]**.

La rimozione del traffico bot in genere riduce il volume di traffico e le metriche di conversione. Molti clienti ritengono che la rimozione del traffico bot determini tassi di conversione aumentati e aumenti in altre metriche di usabilità. Prima di rimuovere il traffico bot, comunicate con i soggetti interessati affinché possano apportare le modifiche necessarie agli indicatori delle prestazioni chiave a seguito di questa modifica. Se possibile, consigliamo di rimuovere prima il traffico bot da una piccola suite di rapporti per stimare il potenziale impatto.

I dati del traffico bot vengono memorizzati in un archivio separato da visualizzare nei report Bots e Bot Pages. Esistono due opzioni per attivare il filtro bot:

| Tipo di regola | Descrizione |
|--- |--- |
| Regole bot IAB standard | Selezionando [!UICONTROL Enable IAB Bot Filtering Rules] usa l'elenco internazionale [di IAB](https://www.iab.com) (International Advertising Bureau) International Spiders &amp; Bots List per rimuovere il traffico bot. La maggior parte dei clienti seleziona questa opzione come minimo. |
| Regole bot personalizzate | Puoi definire e aggiungere regole bot personalizzate basate su agenti utente, indirizzi IP o intervalli IP. |

## Regole bot IAB standard

Le regole IAB bot possono essere attivate selezionando la [!UICONTROL Enable IAB Bot Filtering Rules] casella di controllo. Questa selezione rimuoverà i bot nell'elenco International Picco &amp; Bots International (International Advertising Bureau) internazionali per rimuovere il traffico bot. L'IAB aggiorna questo elenco al mese.

![](assets/bot-iab-checkbox.png)

Adobe non è in grado di fornire l'elenco bot IAB dettagliato ai clienti, anche se potete utilizzare il report Bots per visualizzare un elenco di bot che hanno eseguito l'accesso al sito. Per inviare un bot all'elenco IAB, visita [IAB](https://www.iab.com).

## Regole bot personalizzate

>[!Note]
>L'interfaccia utente consente di definire manualmente 500 regole. Una volta raggiunto tale limite, le regole devono essere gestite in gruppo tramite le opzioni Importa file ed Esporta regole bot.

Le regole bot personalizzate consentono di filtrare le condizioni basate sul traffico definite dall'utente.

Le regole bot personalizzate vengono definite utilizzando i seguenti tipi di condizione:

* Agente utente
* Indirizzo IP
* Intervallo IP

Per una singola regola è possibile definire più condizioni. Più condizioni sono associate a "OR". Ad esempio, se fornisci un valore per Agente utente e Indirizzo IP, il traffico viene considerato traffico bot se una condizione è soddisfatta.

### Agente utente

Una condizione Agente utente verifica il valore dell'agente utente per verificare se essa **[!UICONTROL starts with]** o **[!UICONTROL contains]** la stringa specificata. Se **[!UICONTROL contains]** è selezionata, la sottostringa viene rilevata se si verifica ovunque nell'agente utente.

I valori facoltativi possono essere inclusi **[!UICONTROL does not contain]** nell'elenco per definire valori che l'agente utente non deve contenere per una corrispondenza vincente. È possibile specificare più valori includendo un valore per linea. Se l'agente utente soddisfa i criteri specificati nella stringa di corrispondenza, ma contiene anche una stringa sull'elenco non viene considerato come corrispondenza.

**[!UICONTROL contains]** Il campo è limitato a 100 caratteri. L'elenco non contiene un massimo di 255 caratteri meno un carattere separatore per ogni nuova riga. (Corrisponde al numero di stringhe - 1. Se si specifica 4 *non contiene* stringhe, sono necessari 3 caratteri di separazione. Tutte le corrispondenze stringa non sono sensibili alle maiuscole/minuscole.

### Indirizzo IP (comprese le corrispondenze con caratteri jolly)

Corrisponde a un indirizzo IP o a più indirizzi nello stesso blocco utilizzando caratteri jolly (*). Inserite i valori numerici dell'indirizzo IP che desiderate corrispondere. Sostituite * per tutti i valori che desiderate corrispondere utilizzando un carattere jolly. Nell'elenco seguente sono riportati alcuni esempi di stringa di corrispondenza indirizzo IP:

```
10.10.10.1
10.10.10.*
```

### Intervallo indirizzi IP

Fornite gli intervalli di inizio e fine degli indirizzi IP per la corrispondenza. Sostituite * per tutti i valori che desiderate corrispondere utilizzando un carattere jolly.

### Definire una regola bot personalizzata

1. Vai a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]**, seleziona una o più suite di rapporti e fai clic **[!UICONTROL General]** su &gt; **[!UICONTROL Bot Rules]**.
1. Fare clic **[!UICONTROL Add Rule]** e definire una o più condizioni di corrispondenza.
1. Fai clic su **[!UICONTROL Save]**. La modifica dovrebbe diventare effettiva entro 30 minuti.

## Caricare regole bot

Per importare regole bot di importazione in massa, potete caricare un file CSV che definisca le regole.

Create un file CSV con le seguenti colonne, nell'ordine seguente:

| Colonna 1 | Colonna 2 | Colonna 3 | Colonna 4 | Colonna 5 |
|--- |--- |---|---|---|
| Nome bot | Inizio IP | Fine IP | Regola corrispondenza agente<br>(contiene o inizia con)</br> | Escludi agente<br>(limite di 255 caratteri)</br> |

Puoi definire tre tipi di regole bot:

* L'agente utente contiene o inizia con
* Indirizzo IP singolo o corrispondenza con caratteri jolly
* Corrispondenza intervallo IP

Ogni riga nel file di importazione può contenere solo una delle seguenti definizioni bot:

* **L'agente utente contiene o inizia con**: Fornite una stringa agente utente da far corrispondere nella colonna Agente. Specificate il tipo di corrispondenza da eseguire con il posizionamento *o* *con il* campo Corrispondenza agente. Un valore facoltativo può essere incluso nella colonna Agente esclusivo che definisce una o più stringhe delimitate dal vettore ( `|` ) che l'agente non contiene. Le corrispondenze stringa non sono sensibili alle maiuscole/minuscole. Entrambe le colonne Inizio IP e Fine IP devono essere vuote.

* **Indirizzo IP singolo o corrispondenza caratteri jolly**: Per associare un singolo indirizzo IP ( `10.10.10.1`) o un indirizzo IP jolly ( `10.10.*.*`), inserite lo stesso valore sia nelle colonne Inizio IP che Fine IP. Corrispondenza regola, Agente Include e Agente Escludi devono essere vuoti.

* **Corrispondenza intervallo IP**: Definite una serie di indirizzi IP utilizzando le colonne Inizio IP e Fine IP. I caratteri jolly possono essere utilizzati per associare ad esempio `10.10.10.*` intervalli IP `10.10.20.*`. Corrispondenza regola, Agente Include e Agente Escludi devono essere vuoti.

### Regole multiple combinate con OR

Per far corrispondere un bot utilizzando una combinazione di regole unite a un operatore OR (ad esempio, agente utente o indirizzo IP), fornite un nome identico per tutte le regole che desiderate combinare nel campo del nome bot. Le corrispondenze AND non sono supportate.

### Sovrascrivi tutte le regole con un file di caricamento

Selezionate la **[!UICONTROL Overwrite existing rules]** casella di controllo per eliminare tutte le regole esistenti e sostituirle con quelle definite nel file di caricamento.

### Regole di esportazione

**[!UICONTROL Export Uploaded Bot File]** Il pulsante esporta tutte le regole definite nell'interfaccia utente in formato CSV.


## Impatto delle regole bot sulla raccolta dati {#section_F01A3130E7A04A9993371CF26F6586F2}

Regole bot vengono applicate a tutti i dati di analisi. I dati rimossi da Regole bot sono visibili solo nei report Bots e Bot Pages.

Le regole VISTA vengono applicate dopo Regole bot (consultate [Ordine di elaborazione](../../../admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md#concept_8A6BBEA7F50C40C8A8D8755D4F579B1E)).

**Elaborazione visite ad alto hit:** Se in una visita si verificano più di 100 hit, il reporting determina se l'ora della visita in secondi è inferiore o uguale al numero di hit nella visita. In questa situazione, a causa del costo di elaborazione di visite lunghe e intense, il reporting inizia con una nuova visita. Le visite ad alto hit sono in genere causate da attacchi bot e non sono considerate esplorazioni normali dei visitatori.

>[!NOTE]
>
>Gli hit contrassegnati come *`bots`* sono fatturati come [chiamate al server](https://docs.adobe.com/content/help/en/analytics/admin/server-call-usage/overage-overview.html).

## Impatto dell'oscuramento IP sul filtro bot {#section_92E60B95BE8940D983F28C79E0CD6B12}

L'elenco bot IAB si basa unicamente sull'agente utente, pertanto il filtraggio basato su tale elenco non viene influenzato dalle impostazioni di offuscamento IP. Per filtraggio bot non IAB (regole personalizzate), l'IP potrebbe far parte dei criteri di filtro. Se si filtrano i bot utilizzando IP, il filtro bot viene eseguito dopo che l'ultimo ottetto è stato rimosso, se questa impostazione è attivata, ma prima delle altre opzioni di oscuramento IP, ad esempio eliminando l'intero IP o sostituendolo con un ID univoco.

Se l'offuscamento IP è abilitato, l'esclusione IP avviene prima che l'indirizzo IP non venga oscurato, in modo che i clienti non debbano modificare nulla quando abilitano l'offuscamento IP.

Se l'ultimo ottetto viene rimosso, viene eseguito prima del filtro IP. Pertanto, l'ultimo ottetto viene sostituito con un 0 e le regole di esclusione IP devono essere aggiornate per corrispondere agli indirizzi IP con uno zero alla fine. Corrispondenza * deve corrispondere a 0.
