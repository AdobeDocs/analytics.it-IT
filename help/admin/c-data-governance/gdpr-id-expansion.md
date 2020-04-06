---
description: 'Gli ID che invii non sempre comprendono tutti i dati dei risultati che Analytics può associare alla persona interessata. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di Privacy dei dati. È possibile richiedere questa opzione con un parametro opzionale per ogni richiesta di Privacy dei dati inviata, aggiunta alla richiesta JSON '
title: Espansione dell’ID
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Espansione dell’ID

Gli ID che invii non sempre comprendono tutti i dati dei risultati che Analytics può associare alla persona interessata. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di Privacy dei dati. È possibile richiedere questa opzione con un parametro opzionale per ogni richiesta di Privacy dei dati inviata, aggiunta alla richiesta JSON:

```
"expandIds": true
```

Per un esempio su come includere questa opzione nella richiesta, consultare [Esempio di richiesta JSON](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request). Per altre informazioni consulta la [documentazione sulle API del servizio Privacy](https://www.adobe.io/apis/experienceplatform/gdpr.html).

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Considerazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Espansione ID cookie </p> </td> 
   <td colname="col2"> <p>Molti clienti di Analytics utilizzavano originariamente il <a href="https://marketing.adobe.com/resources/help/it_IT/whitepapers/cookies/cookies_analytics.html"> cookie di Analytics </a>(legacy), ma ora utilizzano il <a href="https://marketing.adobe.com/resources/help/it_IT/mcvid/"> servizio Identity (ECID) </a>, precedentemente noto come servizio Marketing Cloud ID (MCID). Per i visitatori del sito Web che hanno visitato per la prima volta dopo la transizione, esiste solo l’ECID. Tuttavia, per coloro che hanno visitato per la prima volta quando era disponibile solo il cookie legacy, ma che hanno successivamente visitato: alcuni dei loro dati avranno entrambi i cookie, ma i dati precedenti avranno solo il cookie di Analytics, e in alcuni rari casi, i dati più recenti potrebbero avere solo un ECID. </p> <p>Vuoi essere sicuro di trovare tutti i dati per un visitatore identificato tramite un cookie Analytics (Visitor ID) o un ECID. Pertanto, se utilizzate l'ECID e in precedenza il cookie di Analytics, ogni volta che inviate una richiesta utilizzando uno dei due tipi di ID, dovrete includere entrambi gli ID nella richiesta, oppure specificare l'opzione espandereIds. Quando specificate ExpandIds, Adobe controllerà la presenza di altri ECID o cookie di Analytics corrispondenti agli ID dei cookie forniti. La richiesta verrà espansa automaticamente per includere questi ID di cookie appena identificati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID personalizzato per espansione ID cookie </p> </td> 
   <td colname="col2"> <p>Sui siti Web di e-commerce, non è raro per un visitatore navigare nel sito, aggiungere elementi al suo carrello e quindi avviare il processo di estrazione prima di accedere al sito. Se l’ID utilizzato per identificare gli utenti per una richiesta di Privacy dei dati è memorizzato in una variabile personalizzata solo quando l’utente è connesso, allora questa attività precedente all’accesso non sarà associata all’ID. Usando l’ID cookie di Analytics, i clienti possono scegliere di associare la navigazione che ha preceduto l’accesso all’acquisto completato dopo l’accesso, poiché l’ID cookie continua a essere presente durante la sessione di accesso. </p> <p>Supponiamo che la tua implementazione memorizzi un ID di accesso (CRM ID, nome utente, numero fedeltà, indirizzo e-mail, ecc., o un hash di uno qualsiasi di questi valori) in una variabile personalizzata (prop o eVar) o un ID visitatore personalizzato e quindi utilizzi questo ID per una richiesta di accesso di Privacy dei dati. La persona interessata potrebbe sorprendersi del fatto che non tutte le informazioni sulla propria navigazione vengano restituite come parte di una richiesta di accesso, soprattutto se hai pubblicizzato loro gli articoli visualizzati ma non ancora acquistati. </p> <p>L’elaborazione di Privacy dei dati di Analytics supporta quindi l’espansione dell’ID, laddove Analytics trova tutti gli ID cookie che ricorrono nello stesso risultato come ID personalizzato e quindi espande la richiesta per includere anche quegli ID. </p> <p>Quando si specificano espandere gli ID insieme a uno spazio nomi diverso da uno spazio nomi cookie, la richiesta verrà espansa per includere eventuali ID cookie (cookie ECID o Analytics), reperibili negli hit contenenti uno degli ID specificati. L'espansione dell'ID del cookie, come descritto in precedenza, verrà quindi eseguita su qualsiasi ID di cookie trovato di recente. </p> <p>Quando l’opzione espandereIDs viene utilizzata per una richiesta di accesso e l’ID specificato ha un’etichetta ID-PERSON, vengono restituiti due set di file. Il primo set (il set persona) conterrà i dati solo dai punti in cui è stato trovato l’ID specificato. Il secondo set (il set di dispositivi) conterrà solo dati provenienti dagli hit degli ID espansi, dove l’ID specificato non era presente. </p> </td> 
  </tr> 
 </tbody> 
</table>

Nei primi mesi dall’entrata in vigore della Privacy dei dati, la stragrande maggioranza delle richieste di Privacy dei dati di Analytics non aveva bisogno dell’espansione dell’ID. Tuttavia puoi spetta a te determinare quale sia il valore appropriato per la tua organizzazione. Devi consultare il tuo team legale per sapere se l&#39;espansione ID è necessaria per i tuoi dati con gli ID che utilizzi e i dati raccolti in Adobe Analytics. Una considerazione principale dovrebbe essere che su un dispositivo condiviso, dal quale più utenti hanno visitato il sito, l&#39;utilizzo dell&#39;espansione ID includerà i dati provenienti dagli hit di altri utenti del dispositivo nei dati restituiti dalle richieste di accesso (nel file del dispositivo). Anche se avete seguito le procedure ottimali nell&#39;etichettatura, in modo che nessun dato privato sia incluso nel file del dispositivo, come le pagine visitate, il file del dispositivo conterrà il numero di pagine visitate e l&#39;ora di ciascuna di queste visite. Va bene se condividete queste informazioni con qualcuno che potrebbe non essere stato il visitatore?

Per una richiesta di eliminazione, in cui l’espansione ID non è utilizzata, se utilizzi un ID non cookie (qualsiasi ID diverso dal cookie ECID o Analytics) per identificare gli hit da eliminare, e tale ID ha un’etichetta ID-DEVICE, i conteggi dei visitatori univoci nei rapporti cambieranno, perché solo alcune istanze degli ID cookie saranno anonime, mentre altre rimarranno invariate. Se non state specificando l’espansione ID, si consiglia di utilizzare un ID cookie per le richieste, oppure ID con un’etichetta ID-PERSONA.

Quando Adobe esegue l’espansione ID, può richiedere un’ulteriore scansione completa dei dati, che aumenterà il tempo necessario ad Adobe per completare la richiesta, spesso aggiungendo una settimana al tempo di elaborazione.

## Altri flag di richiesta di Privacy dei dati

Oltre al flag “expandIDS”, Analytics supporta altri due flag che possono essere passati come parte di una richiesta di Privacy dei dati. Questi flag con i loro valori predefiniti sono:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

In futuro, “AnalyticsDeleteMethod” potrebbe supportare un valore di “purge” oltre al valore predefinito di “anonymize”. Una volta supportato, comporterà l’eliminazione dell’intero hit anziché semplicemente l&#39;aggiornamento dei valori dei campi di hit con etichette CANC.

Oltre al valore predefinito, il campo priorità supporta anche un valore di “low”. È necessario specificare questo valore per le richieste che non sono il risultato di una richiesta dell’interessato e per le quali quindi non sussiste l&#39;obbligo legale di completamento entro 30 giorni. Nota che Adobe scoraggia l’uso dell’API Privacy dei dati per motivi diversi dalle richieste avviate dall’interessato. L’API Servizio di privacy non è uno strumento appropriato per la pulizia o la riparazione dei dati e avrà conseguenze indesiderate.

>[!NOTE] L’[API del servizio Privacy](https://www.adobe.io/apis/experienceplatform/gdpr.html) è fornita per aiutarti a soddisfare le richieste relative alla Privacy dei dati, soggette a scadenza. L’utilizzo di questa API per altri scopi non è supportato da Adobe e potrebbe influire sulla capacità di Adobe di fornire tempestivamente richieste di Privacy dei dati avviate dall’utente ad alta priorità per altri clienti Adobe. Chiediamo all’utente di non utilizzare l’API Servizio di privacy per altri scopi, come la cancellazione dei dati che sono stati accidentalmente inviati in grandi gruppi di visitatori.

È inoltre necessario tenere presente che ogni visitatore con un hit eliminato (aggiornato o anonimizzato) a seguito di una richiesta di cancellazione di Privacy dei dati avrà le informazioni sullo stato reimpostate. La volta successiva che il visitatore torna sul sito Web, sarà un nuovo visitatore. L&#39;attribuzione di eVar verrà riavviata, così come le informazioni quali numeri di visita, referenti, prima pagina visitata e così via. Questo effetto collaterale non è opportuno nelle situazioni in cui si desidera cancellare i campi di dati ed evidenzia un motivo per cui l’API Servizio di privacy è inappropriata per questo utilizzo.

Contatta il tuo Account Manager (CSM) per coordinarti con il nostro team di consulenza ingegneristico per eseguire un’ulteriore esame e rimuovere eventuali problemi di PII o dati.

