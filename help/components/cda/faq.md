---
title: Domande frequenti su Analytics tra dispositivi
description: Domande frequenti su Analytics tra dispositivi
exl-id: 7f5529f6-eee7-4bb9-9894-b47ca6c4e9be
source-git-commit: a99ef87e9b131beba3fceb8dbb98da503a9d528d
workflow-type: tm+mt
source-wordcount: '1937'
ht-degree: 5%

---

# Domande frequenti

## Come posso utilizzare CDA per vedere come le persone si spostano da un tipo di dispositivo all&#39;altro?

Puoi utilizzare un [!UICONTROL Flow] visualizzazione con la dimensione Tipo di dispositivo mobile.

1. Accedi ad Adobe Analytics e crea un nuovo progetto Workspace vuoto.
2. Fai clic sulla scheda Visualizzazioni a sinistra e trascina una visualizzazione Flusso sull’area di lavoro a destra.
3. Fai clic sulla scheda Componenti a sinistra e trascina la dimensione &quot;Tipo di dispositivo mobile&quot; nella posizione centrale abilitata &quot;Dimension o elemento&quot;.
4. Questo rapporto di flusso è interattivo. Fai clic su uno dei valori per espandere i flussi alle pagine successive o precedenti. Utilizza il menu di scelta rapida per espandere o comprimere le colonne. Possono essere utilizzate anche dimensioni diverse all’interno dello stesso rapporto di flusso.

## Posso visualizzare il modo in cui le persone si spostano tra diverse esperienze utente (ad esempio, browser desktop e browser mobile rispetto all’app mobile)?

L’esempio di tipo di dispositivo mobile illustrato qui sopra consente di vedere come le persone si spostano tra i tipi di dispositivi mobili e quelli di dispositivi desktop. Tuttavia, non ti consente di distinguere i browser desktop dai browser mobili. Se desideri ottenere questo risultato, puoi creare una variabile personalizzata (ad esempio una proprietà o un eVar) che registra l’esperienza se si verifica su un browser desktop, un browser mobile o un’app mobile. Puoi quindi creare un diagramma di flusso come descritto in precedenza, utilizzando la variabile personalizzata invece della dimensione Tipo di dispositivo mobile. Questo metodo fornisce una visualizzazione leggermente diversa del comportamento tra dispositivi.

## Quanto tempo fa CDA unisce i visitatori?

L’unione tra dispositivi di CDA si verifica in due processi simultanei.

* Il primo processo è denominato &quot;live stitching&quot;, che avviene durante lo streaming dei dati in Adobe Analytics. Durante l’unione in tempo reale CDA fa del suo meglio per ripristinare i dati a livello di persona. Tuttavia, se la persona è sconosciuta al momento dell’unione live, CDA ritorna all’ID visitatore per rappresentare la persona.

* Il secondo processo si chiama &quot;replay&quot;. Durante la riproduzione, CDA torna indietro nel tempo e ristabilisce i dati storici, ove possibile, all’interno di un intervallo di lookback specificato. Questo intervallo di lookback è di 1 giorno o 7 giorni, a seconda di come hai richiesto la configurazione di CDA. Durante la riproduzione, CDA tenta di ripristinare i risultati in cui la persona era precedentemente sconosciuta.

* **Se utilizzi un grafico dei dispositivi**, in Adobe le mappature dei dispositivi vengono mantenute in Co-op Graph e Private Graph per circa 6 mesi. Un ECID che non ha attività per più di sei mesi viene rimosso dal grafico. I dati già uniti in CDA non vengono interessati, ma gli hit successivi per tale ECID vengono trattati come una nuova persona.

## In che modo CDA gestisce gli hit con marca temporale?

L’Adobe tratta gli hit con marca temporale come se fossero stati ricevuti al momento della marca temporale, non quando Adobe ha ricevuto l’hit. Gli hit con marca temporale superiore a 1 mese non vengono mai uniti in quanto non rientrano nell’intervallo utilizzato dall’Adobe per le unioni.

## Come si confronta CDA con gli ID visitatore personalizzati?

L&#39;utilizzo di un ID visitatore personalizzato è un metodo legacy per [connettere utenti tra dispositivi](/help/implement/js/xdevice-visid/xdevice-connecting.md). Con un ID visitatore personalizzato utilizzi la funzione [`visitorID`](/help/implement/vars/config-vars/visitorid.md) per impostare esplicitamente l’ID utilizzato per la logica del visitatore. La `visitorID` sostituisce gli ID basati su cookie presenti.

Gli ID visitatore personalizzati hanno diversi effetti collaterali indesiderati che CDA supera o riduce al minimo. Ad esempio, la metodologia ID visitatore personalizzato non ha [ripetizione](replay.md) funzionalità. Se un utente si autentica nel mezzo di una visita, la prima parte della visita viene associata a un ID visitatore diverso rispetto all’ultima parte della visita. Gli ID visitatore separati generano un’inflazione di visite e visitatori. CDA riafferma i dati storici in modo che gli hit non autenticati appartengano alla persona corretta.

## Posso effettuare l’aggiornamento dall’ID visitatore personalizzato a CDA?

I clienti che utilizzano già un ID visitatore personalizzato possono effettuare l’aggiornamento a CDA senza alcuna modifica all’implementazione. La `visitorID` viene ancora utilizzata nella suite di rapporti sorgente. Tuttavia, CDA ignora il `visitorID` nella suite di rapporti virtuali se un utente si autentica.

## In che modo il grafico del dispositivo gestisce i dispositivi condivisi?

In alcune situazioni è possibile che più persone accedano dallo stesso dispositivo. Ad esempio, un dispositivo condiviso da casa, PC condivisi in una libreria o un chiosco in un punto vendita.

* **Se utilizzi un grafico dei dispositivi**, la capacità di gestire dispositivi condivisi è limitata. Il grafico dei dispositivi utilizza un algoritmo per determinare la proprietà di un &quot;cluster&quot; e può cambiare ogni volta che il cluster viene pubblicato. Gli utenti del dispositivo condiviso sono soggetti al cluster a cui appartengono.
* **Se si utilizza l’unione basata sui campi**, la proprietà o l’eVar scelto per aiutare a identificare gli utenti connessi sostituisce altri identificatori. I dispositivi condivisi sono considerati persone separate, anche se provengono dallo stesso dispositivo.

## In che modo CDA gestisce le situazioni in cui una singola persona dispone di MOLTI dispositivi/ECID?

In alcune situazioni, un singolo utente può associarsi a un numero elevato di ECID. Questo può verificarsi se l&#39;individuo utilizza molti browser o app, e può essere esacerbato se cancella frequentemente i cookie o utilizzano la modalità di navigazione privata o in incognito del browser.

* **Se utilizzi un grafico dei dispositivi**, CDA limita a 50 il numero di ECID che si collega a un determinato ID utente. Se un ID utente viene associato a un numero eccessivo di ECID, il grafico del dispositivo presuppone che l&#39;ID utente non sia valido e rimuove il cluster associato a tale ID utente. L’ID utente viene quindi aggiunto a un inserire nell&#39;elenco Bloccati per impedirne l’aggiunta a eventuali cluster in futuro. Il risultato nel reporting è che l’ID utente non è vincolato a diversi dispositivi.
* **Se si utilizza l’unione basata sui campi**, il numero di dispositivi è irrilevante a favore del prop/eVar scelto per aiutare a identificare gli utenti connessi. Un singolo utente può appartenere a qualsiasi numero di dispositivi senza influire sulla capacità di CDA di eseguire unioni tra dispositivi.

## Qual è la differenza tra la metrica Persone in CDA e la metrica Visitatori unici al di fuori di CDA?

Entrambi [Persone](/help/components/metrics/people.md) e [Visitatori unici](/help/components/metrics/unique-visitors.md) Le metriche hanno lo scopo di contare visitatori distinti (singoli utenti). Tuttavia, considerare la possibilità che 2 dispositivi diversi possano appartenere alla stessa persona. CDA mappa i 2 dispositivi alla stessa persona, mentre i 2 dispositivi sono registrati come 2 &quot;Visitatori unici&quot; separati al di fuori di CDA.

## Qual è la differenza tra la metrica &quot;Dispositivi unici&quot; in CDA e la metrica &quot;Visitatori unici&quot; al di fuori di CDA?

Queste due metriche sono approssimativamente equivalenti tra loro. Le differenze tra le 2 metriche si verificano quando:

* Un dispositivo condiviso si mappa a più persone. In questo scenario, viene conteggiato 1 visitatore univoco, mentre vengono conteggiati più dispositivi univoci.
* Un dispositivo dispone sia di traffico non vincolato che vincolato dallo stesso visitatore. Ad esempio, un browser generato identificava il traffico vincolato + il traffico anonimo storico che non era vincolato. In questo caso, viene conteggiato 1 visitatore univoco, mentre vengono conteggiati 2 dispositivi univoci.

Vedi [Dispositivi univoci](/help/components/metrics/unique-devices.md) per ulteriori esempi e dettagli su come funziona.

## Posso includere le metriche CDA utilizzando l’API 2.0?

Sì. Analysis Workspace utilizza l’API 2.0 per richiedere dati dai server Adobe e puoi visualizzare le chiamate API che l’Adobe utilizza per creare rapporti personalizzati:

1. Quando hai effettuato l’accesso ad Analysis Workspace, passa a [!UICONTROL Help] > [!UICONTROL Enable debugger].
2. Fai clic sull’icona di debug nel pannello desiderato, quindi seleziona la visualizzazione e l’ora desiderate per la richiesta.
3. Individua la richiesta JSON, che puoi utilizzare nella chiamata API ad Adobe.

## Cross-Device Analytics può unire visitatori unici. Può unire le visite?

Sì. Se una persona invia hit da due dispositivi diversi entro il timeout di visita della suite di rapporti virtuali (30 minuti per impostazione predefinita), viene unita alla stessa visita.

## Qual è l’ID visitatore finale utilizzato da CDA? Posso esportarlo da Adobe Analytics?

* **Se utilizzi un grafico dei dispositivi**, un ID personalizzato basato sul cluster è l&#39;identificatore principale.
* **Se si utilizza l’unione basata sui campi**, un ID personalizzato basato sulla proprietà/eVar scelto è l’identificatore principale.

Entrambi gli identificatori sono calcolati per Adobe al momento dell&#39;esecuzione del rapporto, noto anche come [Elaborazione a tempo di rapporto](../vrs/vrs-report-time-processing.md). La natura dell’elaborazione al momento del rapporto indica che non è compatibile con Data Warehouse, feed di dati o altre funzioni di esportazione offerte da Adobe.

## Come posso passare dal grafico del dispositivo all’unione basata sui campi o viceversa?

Il passaggio dal grafico del dispositivo all’unione basata sui campi o viceversa può essere richiesto tramite l’Assistenza clienti. Tuttavia, fare un tale interruttore può richiedere un paio di settimane o più per completare e *i dati uniti storici del metodo precedente vengono persi.*

## In che modo Adobe gestisce i limiti univoci per una prop o un eVar utilizzato nella cucitura basata sul campo?

CDA richiama gli elementi dimensionali della variabile di identificazione prima che siano ottimizzati per il reporting. Non devi preoccuparti di limiti unici per gli scopi di CDA. Tuttavia, se hai provato a utilizzare la proprietà o l’eVar in un progetto Workspace, puoi ancora visualizzare la [(traffico ridotto)](/help/technotes/low-traffic.md) elemento dimensione.

## Quante suite di rapporti della mia azienda possono essere abilitate per CDA?

È possibile abilitare più suite di rapporti, tuttavia ogni suite di rapporti aggiuntiva aumenterà il tempo di provisioning complessivo se vengono richieste più suite di rapporti contemporaneamente. CDA non unisce le suite di rapporti. Ogni suite di rapporti abilitata per CDA deve essere di natura multi-dispositivo (contenente dati provenienti da più superfici come web per desktop, web per dispositivi mobili, app per dispositivi mobili, ecc.)

## Se la mia organizzazione Experience Cloud (anche nota come organizzazione IMS) ha più aziende in diverse regioni, posso abilitare CDA per tutte?

No. Per la stessa organizzazione, solo una regione può avere CDA abilitato.

## Quali sono i vantaggi e gli svantaggi di una riproduzione di 7 giorni rispetto a una riproduzione di 1 giorno?

Il vantaggio dell’intervallo di lookback di 7 giorni è che CDA è in grado di tornare indietro nel tempo per cercare di associare eventi precedentemente anonimi a una persona che successivamente ha effettuato l’accesso in quei 7 giorni. Gli svantaggi dell’intervallo di lookback di 7 giorni sono 1) la riproduzione viene eseguita una sola volta alla settimana e 2) i più recenti 7 giorni sono soggetti a modifiche.

I vantaggi dell&#39;utilizzo dell&#39;intervallo di lookback a 1 giorno sono 1) la riproduzione viene eseguita ogni giorno e 2) solo ieri è soggetto a modifiche. Lo svantaggio dell’intervallo di lookback di 1 giorno è che CDA è in grado di tornare indietro solo 1 giorno per cercare di associare eventi precedentemente anonimi a una persona che ha effettuato l’accesso ieri.

## Cosa succede ai dati uniti nelle suite di rapporti virtuali CDA se la mia azienda decide di eseguire il downgrade da Analytics Ultimate?

Se un cliente effettua un downgrade da Ultimate, non avrà più accesso ai dati uniti. Tutti i dati uniti in precedenza verranno rimossi. Ciò significa che le suite di rapporti virtuali CDA ora non riflettono alcuna unione tra dispositivi. I dati saranno simili alla suite di rapporti non uniti originale.

## Perché il numero totale di hit è diverso tra la suite di rapporti sorgente e la suite di rapporti virtuale CDA?

CDA utilizza una pipeline di elaborazione parallela complessa, con più componenti dipendenti. È prevista una mancata corrispondenza dei dati di circa l’1% per il numero totale di hit tra la suite di rapporti originale e la suite di rapporti virtuale CDA.

## Perché la metrica &quot;Persone identificate&quot; è gonfiata?

Il numero della metrica &quot;Persone identificate&quot; può essere leggermente superiore se il valore dell’identificatore prop/eVar si trova in un [collisione di hash](/help/implement/validate/hash-collisions.md).

Per le unioni basate su campi, la variabile personalizzata dell’identificatore distingue tra maiuscole e minuscole. Il numero della metrica &quot;Persone identificate&quot; può essere significativamente più alto se i valori degli identificatori non corrispondono a maiuscole e minuscole. Ad esempio, se `bob` e `Bob` vengono inviati e devono essere la stessa persona, CDA interpreta questi due valori come distinti.

## Quando visualizzo l’identificatore prop/eVar, perché visualizzo valori diversi da zero per la metrica &quot;Persone non identificate&quot;?

Questa situazione si verifica solitamente quando un visitatore genera hit autenticati e non autenticati nell’intervallo di reporting. Il visitatore appartiene sia a &quot;Non identificato&quot; che a &quot;Identificato&quot; nel [Stato identificato](/help/components/dimensions/identified-state.md) , causando l’attribuzione di hit non identificati a un identificatore . Questo scenario può cambiare dopo [Riproduci](replay.md) in base alla frequenza di riproduzione e alla frequenza di successo.