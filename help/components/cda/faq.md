---
title: Domande frequenti su Analytics tra dispositivi
description: Domande frequenti per Analytics tra dispositivi
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '1923'
ht-degree: 100%

---

# Domande frequenti

## Come posso usare CDA per vedere come le persone passano da un dispositivo all’altro?

Puoi utilizzare una visualizzazione [!UICONTROL Flow] con la dimensione Tipo di dispositivo mobile.

1. Accedi ad Adobe Analytics e crea un nuovo progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra e trascina una visualizzazione Flusso sull’area di lavoro a destra.
3. Fai clic sulla scheda Componenti a sinistra e trascina la dimensione “Tipo di dispositivo mobile” nella posizione centrale denominata “Dimensione o elemento”.
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

## Posso vedere in che modo le persone passano da un’esperienza utente a un’altra (ad esempio, al browser desktop al browser mobile o all’app mobile)?

L’esempio per il tipo di dispositivo mobile illustrato qui sopra consente di vedere come le persone passano a tipi di dispositivi mobili e desktop. Tuttavia, non ti consente di distinguere tra browser desktop e browser mobili. Se desideri questa informazione, puoi creare una variabile personalizzata (ad esempio, prop o eVar) che registra se l’esperienza si verifica su un browser desktop, un browser mobile o un’app mobile. Puoi quindi creare un diagramma di flusso come descritto in precedenza, utilizzando la variabile personalizzata invece della dimensione Tipo di dispositivo mobile. Questo metodo fornisce una visualizzazione leggermente diversa del comportamento tra dispositivi diversi.

## Quanto indietro nel tempo va CDA nell’unire i visitatori?

L’unione tra dispositivi di CDA si verifica in due processi simultanei.

* Il primo processo è denominato “live stitching” e avviene durante il flusso dei dati in Adobe Analytics. Durante il live stitching, CDA fa del suo meglio per aggiornare i dati a livello di persona. Ma se la persona è sconosciuta al momento del live stitching, CDA la rappresenta mediante l’ID visitatore.

* Il secondo processo è denominato “ripetizione”. Durante la ripetizione, CDA torna indietro nel tempo e aggiorna i dati storici, ove possibile, all’interno di una finestra temporale specificata. Questo finestra temporale può essere di 1 giorno o 7 giorni, a seconda della configurazione di CDA. Durante la ripetizione, CDA tenta di aggiornare i risultati in cui la persona era precedentemente sconosciuta.

* **Se utilizzi un grafo di dispositivi**, Adobe mantiene le mappature del grafo di dispositivi per circa 6 mesi. Un ECID che non ha attività per più di sei mesi viene rimosso dal grafo. I dati già uniti in CDA non vengono influenzati, ma gli hit successivi per tale ECID vengono trattati come una nuova persona.

## In che modo CDA gestisce gli hit con marca temporale?

Adobe tratta gli hit con marca temporale come se fossero stati ricevuti al momento della marca temporale, non quando Adobe ha ricevuto l’hit. Gli hit con marca temporale superiore a 1 mese non vengono mai uniti in quanto non rientrano nell’intervallo utilizzato da Adobe per le unioni.

## Come si comporta CDA con gli ID visitatore personalizzati?

L’utilizzo di un ID visitatore personalizzato è un metodo legacy per [collegare gli utenti a dispositivi diversi](/help/implement/js/xdevice-visid/xdevice-connecting.md). Con un ID visitatore personalizzato, utilizzi la variabile [`visitorID`](/help/implement/vars/config-vars/visitorid.md) per impostare esplicitamente l’ID utilizzato per la logica del visitatore. La variabile `visitorID` sostituisce gli ID presenti basati su cookie.

Gli ID visitatore personalizzati hanno diversi effetti collaterali indesiderati che CDA supera o riduce al minimo. Ad esempio, la metodologia dell’ID visitatore personalizzato non ha la funzionalità di [ripetizione](replay.md). Se un utente si autentica nel mezzo di una visita, la prima parte della visita viene associata a un ID visitatore diverso rispetto all’ultima parte della visita. Gli ID visitatore separati generano un’inflazione di visite e visitatori. CDA aggiorna i dati storici in modo che gli hit non autenticati appartengano alla persona corretta.

## Posso effettuare l’aggiornamento dall’ID visitatore personalizzato a CDA?

I clienti che già utilizzano un ID visitatore personalizzato possono effettuare l’aggiornamento a CDA senza apportare alcuna modifica all’implementazione. La variabile `visitorID` viene ancora utilizzata nella suite di rapporti sorgente. Tuttavia, CDA ignora la variabile `visitorID` nella suite di rapporti virtuali se un utente si autentica.

## In che modo il grafo di dispositivi gestisce i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

* **Se utilizzi un grafo di dispositivi**, la capacità di gestire dispositivi condivisi è limitata. Il grafo di dispositivi utilizza un algoritmo per determinare a chi appartiene un “cluster” e può cambiare ogni volta che il cluster viene pubblicato. Gli utenti del dispositivo condiviso dipendono dal cluster a cui appartengono.
* **Se utilizzi l’unione basata sui campi**, la variabile prop o eVar scelta per identificare gli utenti connessi prevale sugli altri identificatori. I dispositivi condivisi sono considerati persone distinte, anche se provengono dallo stesso dispositivo.

## In che modo CDA gestisce le situazioni in cui una singola persona dispone di MOLTI dispositivi o ECID?

In alcune situazioni, un singolo utente può essere associato a un numero elevato di ECID. Questo può verificarsi se il singolo utente utilizza molti browser o app e può aggravarsi se cancella frequentemente i cookie o utilizza la modalità di navigazione privata o in incognito del browser.

* **Se utilizzi un grafo di dispositivi**, CDA limita a 50 il numero di ECID associati a un determinato ID utente. Se un ID utente è associato a un numero eccessivo di ECID, il grafo dei dispositivi presuppone che l’ID utente non sia valido e rimuove il cluster associato a tale ID utente. L’ID utente viene quindi inserito in un elenco di valori bloccati per impedire che in futuro venga aggiunto a eventuali cluster. Pertanto, nei rapporti l’ID utente non verrà unito per diversi dispositivi.
* **Se utilizzi l’unione basata sui campi**, il numero di dispositivi è irrilevante a favore della variabile prop o eVar scelta per identificare gli utenti connessi. Un singolo utente può appartenere a un numero qualsiasi di dispositivi senza influire sulla capacità di CDA di eseguire unioni tra dispositivi diversi.

## Qual è la differenza tra la metrica Persone in CDA e la metrica Visitatori univoci al di fuori di CDA?

Entrambe le metriche [Persone](/help/components/metrics/people.md) e [Visitatori univoci](/help/components/metrics/unique-visitors.md) hanno lo scopo di contare i visitatori distinti (i singoli utenti). Considera comunque la possibilità che 2 dispositivi diversi possano appartenere alla stessa persona. CDA mappa i 2 dispositivi sulla stessa persona, mentre i 2 dispositivi sono registrati come 2 “Visitatori univoci” distinti al di fuori di CDA.

## Qual è la differenza tra la metrica “Dispositivi univoci” in CDA e la metrica “Visitatori univoci” al di fuori di CDA?

Queste due metriche sono approssimativamente equivalenti tra loro. Si verificano differenze tra le 2 metriche quando:

* Un dispositivo condiviso è mappato su più persone. In questo scenario, viene conteggiato 1 visitatore univoco, ma sono conteggiati più dispositivi univoci.
* Un dispositivo dispone di traffico sia non unito sia unito dallo stesso visitatore. Ad esempio, un browser ha generato traffico identificato unito + traffico anonimo storico non unito. In questo caso, vengono conteggiati 1 visitatore univoco e 2 dispositivi univoci.

Per ulteriori esempi e dettagli su come funziona, vedi [Dispositivi univoci](/help/components/metrics/unique-devices.md).

## Posso includere le metriche di CDA utilizzando l’API 2.0?

Sì. Analysis Workspace utilizza l’API 2.0 per richiedere dati dai server Adobe e puoi visualizzare le chiamate API utilizzate da Adobe per creare i rapporti:

1. Dopo l’accesso ad Analysis Workspace, passa a [!UICONTROL Help] > [!UICONTROL Enable debugger].
2. Fai clic sull’icona di debug nel pannello desiderato, quindi seleziona la visualizzazione e l’ora desiderate per la richiesta.
3. Individua la richiesta JSON, che puoi utilizzare nella chiamata API ad Adobe.

## Analytics tra dispositivi può unire visitatori univoci. Può unire le visite?

Sì. Se un singolo utente invia hit da due dispositivi distinti entro il timeout di visita della suite di rapporti virtuali (30 minuti per impostazione predefinita), questi vengono uniti nella stessa visita.

## Qual è l’ID visitatore finale utilizzato da CDA? Posso esportarlo da Adobe Analytics?

* **Se utilizzi un grafo di dispositivi**, l’identificatore primario è un ID personalizzato basato sul cluster.
* **Se utilizzi l’unione basata sui campi**, l’identificatore primario è un ID personalizzato basato sulla variable prop o eVar scelta.

Entrambi gli identificatori sono calcolati da Adobe al momento dell’esecuzione del rapporto, ossia tramite [elaborazione al momento del rapporto](../vrs/vrs-report-time-processing.md). L’elaborazione al momento del rapporto non è compatibile con Data Warehouse, feed di dati o altre funzioni di esportazione offerte da Adobe.

## Come posso passare dal grafo di dispositivi all’unione basata sui campi e viceversa?

Per passare dal grafo di dispositivi all’unione basata sui campi o viceversa, rivolgiti all’Assistenza clienti. Tuttavia, questo cambiamento può richiedere un paio di settimane o più e *i dati uniti storici del metodo precedente andranno perduti.*

## In che modo Adobe gestisce i limiti univoci per una variabile prop o eVar utilizzata nell’unione basata sui campi?

CDA richiama gli elementi dimensione della variabile di identificazione prima che vengano ottimizzati per il reporting. Non devi preoccuparti di limiti univoci per gli scopi di CDA. Tuttavia, se hai provato a utilizzare la variabile prop o eVar in un progetto Workspace, puoi ancora visualizzare l’elemento dimensione [(Traffico ridotto)](/help/technotes/low-traffic.md).

## Quante suite di rapporti della mia azienda possono essere abilitate per CDA?

A decorrere dal 1° maggio 2022, ogni nuova implementazione di CDA sarà limitata a un massimo di tre ID di suite di rapporti (RSID) per cliente. CDA non unisce le suite di rapporti. Ogni suite di rapporti abilitata per CDA deve essere di natura cross-device (contenente dati provenienti da più superfici come web per desktop, web per dispositivi mobili, app per dispositivi mobili, ecc.).

## Se il mio ID organizzazione ha più aziende in diverse aree geografiche, posso abilitare CDA per tutte?

No. Per lo stesso ID organizzazione, CDA può essere abilitato in una sola regione.

## Quali sono i vantaggi e gli svantaggi di una ripetizione di 7 giorni rispetto a una ripetizione di 1 giorno?

Il vantaggio di una ripetizione con intervallo di lookback di 7 giorni è che CDA è in grado di tornare indietro nel tempo per tentare di associare eventi precedentemente anonimi a una persona che ha successivamente effettuato l’accesso in quei 7 giorni. L’intervallo di lookback di 7 giorni presenta tuttavia i seguenti svantaggi: 1) la ripeditione viene eseguita una sola volta alla settimana; 2) i 7 giorni più recenti sono soggetti a modifiche.

I vantaggi di un intervallo di lookback di 1 giorno sono i seguenti: 1) la ripetizione viene eseguita ogni giorno; e 2) solo il giorno immediatamente precedente è soggetto a modifiche. Lo svantaggio dell’intervallo di lookback di 1 giorno è che CDA è in grado di tornare indietro solo di 1 giorno per tentare di associare eventi precedentemente anonimi a una persona che ha effettuato l’accesso il girono precedente.

## Cosa succede ai dati uniti nelle suite di rapporti virtuali di CDA se si esegue il downgrade da Analytics Ultimate?

Se un cliente effettua un downgrade da Ultimate, non avrà più accesso ai dati uniti. Tutti i dati uniti in precedenza verranno rimossi. Ciò significa che le suite di rapporti virtuali di CDA non rifletteranno alcuna unione tra dispositivi diversi. I dati saranno simili a quelli della suite di rapporti originale senza dati uniti.

## Perché il numero totale di hit è diverso tra la suite di rapporti di origine e la suite di rapporti virtuali di CDA?

CDA utilizza una complessa pipeline di elaborazione parallela, con diversi componenti dipendenti. È previsto uno scostamento di circa 1% per il numero totale di hit tra la suite di rapporti originale e la suite di rapporti virtuali di CDA.

## Perché la metrica “Persone identificate” è più alta?

Il valore della metrica “Persone identificate” può essere leggermente superiore se per il valore prop/eVar dell’identificatore si verifica una [collisione hash](/help/implement/validate/hash-collisions.md).

Per le unioni basate sui campi, la variabile personalizzata dell’identificatore distingue tra maiuscole e minuscole. Il valore della metrica “Persone identificate” può essere significativamente più alto se i valori dell’identificatore usano maiuscole e minuscole diverse. Ad esempio, se per una stessa persona vengono trasmessi i valori `bob` e `Bob`, CDA li interpreta come due valori distinti.

## Quando visualizzo l’identificatore prop/eVar, perché trovo valori diversi da zero per la metrica “Persone non identificate”?

Questa situazione si verifica solitamente quando un visitatore genera hit autenticati e non autenticati nella finestra di reporting. Il visitatore appartiene sia a “Non identificato” che a “Identificato” nella dimensione [Stato identificato](/help/components/dimensions/identified-state.md), causando l’attribuzione di hit non identificati a un identificatore. Questo scenario può cambiare dopo esecuzioni di [Ripetizione](replay.md) in base alla frequenza di ripetizione e al tasso di successo.