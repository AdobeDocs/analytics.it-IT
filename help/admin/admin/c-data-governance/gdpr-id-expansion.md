---
description: Gli ID inviati non sempre coprono tutti i dati hit che Analytics può associare all'interessato. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di Privacy dei dati. È possibile richiedere questa opzione con un parametro opzionale per ogni richiesta di Privacy dei dati inviata, aggiunta alla richiesta JSON
title: Espansione dell’ID
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '1348'
ht-degree: 33%

---

# Espansione dell’ID

Gli ID inviati non sempre coprono tutti i dati hit che Analytics può associare all&#39;interessato. Analytics può creare un set esteso di ID per includere questi dati associati nelle richieste di Privacy dei dati. È possibile richiedere questa opzione con un parametro opzionale per ogni richiesta di Privacy dei dati inviata, aggiunta alla richiesta JSON:

```
"expandIds": true
```

Per altre informazioni consulta la [documentazione sulle API del servizio Privacy](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it).


| Tipo | Considerazioni |
| --- | --- |
| Espansione dell’ID cookie | Molti clienti di Analytics utilizzavano originariamente il (legacy) [Cookie di Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en), ma utilizzano ora il [Servizio Experience Cloud Identity (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). Per i visitatori che hanno visitato il loro sito per la prima volta in seguito alla transizione, esiste solo l’ECID. Tuttavia, per coloro che hanno visitato per la prima volta quando era disponibile solo il cookie legacy, ma che nel frattempo hanno visitato: alcuni dei loro dati contengono entrambi i cookie. Tuttavia, i dati più vecchi hanno solo il cookie di Analytics e, in rari casi, i dati più recenti possono avere solo un ECID.<p>Assicurati di trovare tutti i dati di un visitatore identificato tramite un cookie di Analytics (ID visitatore) o un ECID. Se utilizzi attualmente l’ECID e in precedenza hai utilizzato il cookie di Analytics, ogni volta che invii una richiesta utilizzando uno dei due tipi di ID, devi includere entrambi gli ID nella richiesta o specificare `expandIds` opzione. Quando si specifica `expandIds`, Adobe controlla altri ECID o cookie di Analytics che corrispondono a qualsiasi ID cookie fornito. La richiesta viene espansa automaticamente per includere questi ID cookie appena identificati. |
| ID personalizzati per l’espansione dell’ID cookie | Nei siti Web di e-commerce, non è raro per un visitatore navigare nel sito, aggiungere articoli al carrello e iniziare il processo di pagamento prima di effettuare l’accesso al sito. Se l’ID utilizzato per identificare gli utenti per una richiesta di Privacy dei dati è memorizzato in una variabile personalizzata solo quando l’utente è connesso, allora questa attività di pre-accesso non è associata all’ID. Usando l’ID cookie di Analytics, i clienti possono scegliere di associare la navigazione che ha preceduto l’accesso all’acquisto completato dopo l’accesso, poiché l’ID cookie continua a essere presente durante la sessione di accesso.<p>Supponiamo che la tua implementazione memorizzi un ID di accesso (CRM ID, nome utente, numero fedeltà, indirizzo e-mail, ecc., o un hash di uno qualsiasi di questi valori) in una variabile personalizzata (prop o eVar) o un ID visitatore personalizzato e quindi utilizzi questo ID per una richiesta di accesso di Privacy dei dati. L’interessato potrebbe sorprendersi del fatto che non tutte le informazioni sulla sua navigazione vengano restituite come parte di una richiesta di accesso, soprattutto se hai promosso elementi che sono stati visualizzati ma non ancora acquistati. L’elaborazione di Privacy dei dati di Analytics supporta quindi l’espansione dell’ID, laddove Analytics trova tutti gli ID cookie che ricorrono nello stesso risultato come ID personalizzato e quindi espande la richiesta per includere anche quegli ID.<p>Quando `expandIDs` viene specificata insieme a qualsiasi namespace diverso da quello di un cookie, la richiesta viene espansa per includere tutti gli ID cookie (ECID o cookie di Analytics) presenti negli hit contenenti uno degli ID specificati. L’espansione dell’ID cookie, come descritto in precedenza, viene quindi eseguita su qualsiasi ID cookie appena trovato.<p>Quando `expandIDs` L’opzione viene utilizzata per una richiesta di accesso e l’ID specificato ha un’etichetta ID-PERSON, quindi verranno restituiti due set di file. Il primo set (il set persona) conterrà i dati solo dai punti in cui è stato trovato l’ID specificato. Il secondo set (il set dispositivo) conterrà solo i dati provenienti dagli ID espansi, in cui l’ID specificato non era presente. |

{style="table-layout:auto"}

## Quando utilizzare l’espansione dell’ID

Nei primi mesi dall’entrata in vigore della Privacy dei dati, la stragrande maggioranza delle richieste di Privacy dei dati di Analytics non richiedeva l’espansione dell’ID. Tuttavia, spetta a te determinare il valore appropriato per la tua organizzazione. Consulta il team legale per sapere se l&#39;espansione dell&#39;ID è necessaria per i tuoi dati con gli ID utilizzati e i dati raccolti all&#39;interno di Adobe Analytics.

Un aspetto importante da considerare potrebbe essere: su un dispositivo condiviso, dal quale più utenti hanno visitato il tuo sito, l’utilizzo dell’espansione dell’ID include i dati provenienti dagli hit di altri utenti del dispositivo, nei dati restituiti dalle richieste di accesso (nel file del dispositivo). Anche se hai seguito le best practice nell’etichettatura (ad esempio, non includi dati privati nel file del dispositivo, come le pagine visitate), il file del dispositivo contiene il numero di pagine visitate e gli orari di ciascuna di tali visite. Potresti chiederti: &quot;Va bene se condividi queste informazioni con qualcuno che potrebbe non essere stato il visitatore?&quot;

Quando l’espansione dell’ID è *non* utilizzato per una richiesta di eliminazione: se utilizzi un ID non cookie (qualsiasi ID diverso da ECID o cookie di Analytics) per identificare gli hit da eliminare e tale ID ha un’etichetta ID-DEVICE, i conteggi di visitatori univoci nei rapporti non cambiano. Questo perché solo alcune istanze degli ID cookie verranno rese anonime, mentre altre verranno lasciate invariate. Se non specifichi l’espansione dell’ID, ti consigliamo di utilizzare un ID cookie per le richieste o ID con l’etichetta ID-PERSON.

Quando Adobe esegue l’espansione dell’ID, può essere necessaria un’ulteriore scansione completa dei dati. Questo aumenta il tempo necessario ad Adobe per completare la richiesta, spesso aggiungendo una settimana al tempo di elaborazione.

## Altri flag di richiesta di Privacy dei dati

Oltre al flag “expandIDS”, Analytics supporta altri due flag che possono essere passati come parte di una richiesta di Privacy dei dati. Questi flag con i loro valori predefiniti sono:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

In futuro, il `analyticsDeleteMethod` può supportare un valore di &quot;purge&quot; in aggiunta al valore predefinito di &quot;anonymize&quot;. Se supportato, causerà l’eliminazione dell’intero hit anziché semplicemente l’aggiornamento dei valori dei campi di hit con etichette CANC.

Oltre al valore predefinito, il `priority` supporta anche un valore &quot;low&quot;. È necessario specificare questo valore per le richieste che non sono il risultato di una richiesta dell’interessato e che pertanto non hanno un obbligo legale di completamento entro un determinato arco temporale.

## Utilizzi dell’API Privacy Service

>[!IMPORTANT]
>
>L&#39;Adobe non consente l&#39;uso del [API PRIVACY SERVICE](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it) per motivi diversi dalle richieste valide avviate dall’interessato. L’API Privacy Service non è uno strumento appropriato per la pulizia o la riparazione dei dati. Qualsiasi uso improprio dell’API Privacy Service per richieste non avviate dall’interessato avrà conseguenze indesiderate. L’API Privacy Service viene fornita ai clienti Adobe per aiutarti a soddisfare le richieste relative alla Privacy dei dati, soggette a scadenza. L’utilizzo di questa API per altri scopi non è supportato da Adobe e potrebbe influire sulla capacità di Adobe di fornire tempestivamente richieste di Privacy dei dati avviate dall’utente ad alta priorità per altri clienti Adobe. Chiediamo all’utente di non utilizzare l’API Privacy Service per altri scopi, come l’igiene dei dati o la cancellazione dei dati che sono stati accidentalmente inviati in grandi gruppi di visitatori.

È inoltre necessario tenere presente che ogni visitatore con un hit eliminato (aggiornato o anonimizzato) a seguito di una richiesta di cancellazione di Privacy dei dati avrà le informazioni sullo stato reimpostate. La prossima volta che il visitatore ritorna sul tuo sito web, sarà un nuovo visitatore. Tutte le attribuzioni eVar ricominceranno, così come informazioni quali numeri di visita, referrer, prima pagina visitata, ecc. Il risultato non è opportuno nelle situazioni in cui si desidera cancellare i campi di dati ed evidenzia un motivo per cui l’API Privacy Service è inappropriata per questo utilizzo.

Contatta il tuo Account Manager (CSM) per coordinarti con il nostro team di consulenza ingegneristico per eseguire un’ulteriore esame e rimuovere eventuali PII o risolvere problemi relativi ai dati.
