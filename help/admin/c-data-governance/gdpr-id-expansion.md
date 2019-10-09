---
description: 'Gli ID che invii non sempre comprendono tutti i dati dei risultati che Analytics può associare alla persona interessata. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di privacy dei dati. Puoi richiedere questa opzione con un parametro opzionale per ogni richiesta di privacy di dati che invii e che aggiungi alla richiesta JSON '
seo-description: 'Gli ID che invii non sempre comprendono tutti i dati dei risultati che Analytics può associare alla persona interessata. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di privacy dei dati. Puoi richiedere questa opzione con un parametro opzionale per ogni richiesta di privacy di dati che invii e che aggiungi alla richiesta JSON '
seo-title: Espansione dell’ID
title: Espansione dell’ID
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Espansione dell’ID

Gli ID che invii non sempre comprendono tutti i dati dei risultati che Analytics può associare alla persona interessata. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di privacy dei dati. Puoi richiedere questa opzione con un parametro opzionale a ogni richiesta di privacy di dati inviata, aggiunta alla richiesta JSON:

```
"expandIds": true
```

Per un esempio su come includere questa opzione nella richiesta, consultare [Esempio di richiesta JSON](/help/admin/c-data-governance/gdpr-submit-access-delete.md#section_DB9DE6492FE740918F91D413E7BAB88F). For more details, refer to the [Privacy Service API documentation.](https://www.adobe.io/apis/experienceplatform/gdpr.html)

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Considerazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Espansione dell’ID cookie </p> </td> 
   <td colname="col2"> <p>Many Analytics customers originally used the (Legacy) <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external"> Analytics Cookie </a>, but are now using the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service (ECID) </a>, previously known as the Marketing Cloud ID Service (MCID). Per i visitatori che hanno visitato il loro sito per la prima volta in seguito alla transizione, esiste solo l’ECID. Tuttavia, per coloro che hanno visitato il sito per la prima volta quando era disponibile solo il cookie legacy, ma che da allora lo hanno visitato ancora: alcuni dei loro dati avranno entrambi i cookie, ma i dati meno recenti avranno solo il cookie di Analytics, mentre i dati più recenti potrebbero avere solo un ECID. </p> <p>Accertarsi di trovare tutti i dati di un visitatore identificato tramite un cookie di Analytics (ID visitatore) o ECID. Pertanto, se attualmente si utilizza l’ECID e in precedenza si è utilizzato il Cookie Analytics, ogni volta che si invia una richiesta utilizzando uno dei due tipi di ID, è necessario includere entrambi gli ID nella richiesta o specificare l’opzione expandIDs. Quando si specifica expandIDs, Adobe verifica la presenza di altri ECID o cookie di Analytics che corrispondono a qualsiasi ID cookie fornito. La richiesta viene automaticamente estesa per includere i nuovi ID cookie identificati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID personalizzati per l’espansione dell’ID cookie </p> </td> 
   <td colname="col2"> <p>Nei siti Web di e-commerce, non è raro per un visitatore navigare nel sito, aggiungere articoli al carrello e iniziare il processo di pagamento prima di effettuare l’accesso al sito. Se l'ID utilizzato per identificare gli utenti per una richiesta di privacy dei dati è memorizzato in una variabile personalizzata solo quando l'utente ha eseguito l'accesso, questa attività pre-login non sarà associata all'ID. Usando l’ID cookie di Analytics, i clienti possono scegliere di associare la navigazione che ha preceduto l’accesso all’acquisto completato dopo l’accesso, poiché l’ID cookie continua a essere presente durante la sessione di accesso. </p> <p>Supponiamo che l'implementazione memorizzi un ID di login (ID CRM, nome utente, numero di fedeltà, indirizzo e-mail, ecc., o un hash di uno di questi valori) in una variabile personalizzata (proprietà o eVar) o un ID visitatore personalizzato, quindi utilizza questo ID per una richiesta di accesso alla privacy dei dati. La persona interessata potrebbe sorprendersi del fatto che non tutte le informazioni sulla propria navigazione vengano restituite come parte di una richiesta di accesso, soprattutto se hai pubblicizzato loro gli articoli visualizzati ma non ancora acquistati. </p> <p>L'elaborazione della privacy dei dati di Analytics supporta pertanto l'espansione dell'ID, dove Analytics trova tutti gli ID di cookie che si verificano nello stesso hit di qualsiasi ID personalizzato e quindi espande la richiesta per includere anche tali ID. </p> <p>Quando viene specificato expandIDs insieme a uno spazio dei nomi (o namespace) diverso da un cookie spazio dei nomi, la richiesta viene estesa in modo da includere tutti gli ID cookie (ECID o cookie di Analytics), reperibili nei risultati contenenti uno qualsiasi degli ID specificati. L’espansione dell’ID cookie, come descritto in precedenza, verrà eseguita su tutti i nuovi ID cookie. </p> <p>Quando l’opzione expandIDs viene utilizzata per una richiesta di accesso e l’ID specificato ha un’etichetta di ID-PERSON, vengono restituiti due set di file. Il primo set (il set persona) conterrà i dati solo dai punti in cui è stato trovato l’ID specificato. Il secondo set (il set dispositivo) conterrà solo i dati provenienti dagli ID espansi, in cui l’ID specificato non era presente. </p> </td> 
  </tr> 
 </tbody> 
</table>

Nei primi mesi successivi all'attivazione della privacy dei dati, la stragrande maggioranza delle richieste di privacy dei dati di Analytics non ha richiesto l'espansione degli ID, ma la determinazione del valore appropriato per la tua organizzazione dipende da te. È consigliabile consultare il proprio team legale per sapere se è necessaria un’espansione degli ID per i propri dati con gli ID utilizzati e i dati raccolti all’interno di Adobe Analytics. È bene considerare innanzitutto che per un dispositivo condiviso da cui più utenti hanno visitato il tuo sito, se utilizzi l’espansione dell’ID, le richieste di accesso (nel file del dispositivo) restituiranno anche i dati dagli hit di altri utenti del dispositivo. Anche seguendo le migliori pratiche di etichettatura in modo tale che nessun dato privato, come le pagine visitate, sia incluso nel file del dispositivo, questo conterrà il numero di pagine visitate e gli orari di ciascuna di queste visite. Queste informazioni potranno essere condivise con un utente che potrebbe non essere il visitatore?

Per una richiesta di cancellazione, in cui l’espansione dell’ID non viene utilizzata, se si usa un ID non cookie (qualsiasi ID diverso dall’ECID o dal cookie Analytics) per identificare i risultati che devono essere eliminati, e tale ID ha un’etichetta ID-DEVICE, allora i conteggi dei visitatori univoci nei report cambierà: solo alcune istanze degli ID cookie, infatti, saranno rese anonime, mentre altre rimarranno invariate. Se non si specifica l’espansione dell’ID, si consiglia di utilizzare un ID cookie per le richieste o ID con un’etichetta ID-PERSON.

Quando Adobe esegue l’espansione dell’ID, può richiedere un’ulteriore scansione completa dei dati, che aumenterà il tempo necessario per completare la richiesta, spesso aggiungendo una settimana al tempo di elaborazione.

## Altri flag di richiesta della privacy

Oltre al flag "espandiID", Analytics supporta altri due flag che possono essere passati come parte di una richiesta di privacy dei dati. Questi flag con i loro valori predefiniti sono:

```
"analyticsDeleteMethod": “anonymize”
“priority”: “normal”
```

In futuro, “AnalyticsDeleteMethod” potrebbe supportare un valore di “purge” oltre al valore predefinito di “anonymize”. Una volta supportato, comporterà l’eliminazione dell’intero hit anziché semplicemente l'aggiornamento dei valori dei campi di hit con etichette CANC.

Oltre al valore predefinito, il campo priorità supporta anche un valore di “low”. È necessario specificare questo valore per le richieste che non sono il risultato di una richiesta dell’interessato e per le quali quindi non sussiste l'obbligo legale di completamento entro 30 giorni. Adobe scoraggia l'utilizzo dell'API del servizio sulla privacy per motivi diversi dalle richieste avviate dall'interessato. L'API del servizio Privacy non è uno strumento adeguato per la pulizia o la riparazione dei dati e avrà conseguenze indesiderate.

[!NOTE]
L'API [del servizio](https://www.adobe.io/apis/experienceplatform/gdpr.html) Privacy è stata fornita per aiutarti a soddisfare le richieste di privacy relative ai dati, che sono sensibili al tempo. L'utilizzo di questa API per altri scopi non è supportato da Adobe e potrebbe avere un impatto sulla capacità di Adobe di fornire un cambiamento tempestivo delle richieste di privacy dei dati ad alta priorità, avviate dall'utente, per altri clienti Adobe. Vi chiediamo di non utilizzare l'API del servizio Privacy per altri scopi, ad esempio per cancellare i dati inviati accidentalmente da gruppi di visitatori di grandi dimensioni.

Devi anche essere consapevole del fatto che qualsiasi visitatore che abbia eliminato (aggiornato o anonimo) un hit a seguito di una richiesta di eliminazione della privacy dei dati avrà le informazioni sullo stato reimpostato. La prossima volta che il visitatore ritorna sul tuo sito web, sarà un nuovo visitatore. Tutte le attribuzioni eVar ricominceranno, così come informazioni quali numeri di visita, referrer, prima pagina visitata, ecc. Questo effetto collaterale non è desiderabile per le situazioni in cui si desidera cancellare i campi dati ed evidenzia una ragione per cui l'API del servizio sulla privacy è inappropriata per questo uso.

Contatta il tuo Account Manager (CSM) per coordinare con il nostro team di consulenza di Engineering Architect per esaminare e fornire il livello di impegno necessario per rimuovere eventuali problemi PII o di dati.

