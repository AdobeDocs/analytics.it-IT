---
description: nulle
seo-description: nulle
seo-title: Tecniche di etichettatura consigliate
title: Tecniche di etichettatura consigliate
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: 2e78524a1ec88ace687ef293332bbee532388c7a

---


# Tecniche di etichettatura consigliate

>[!NOTE]
>
>Ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l'etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette.

## ID direttamente e indirettamente identificabili {#section_030799AA1397433FBA61A2BC60A7A750}

Prima di capire quali etichette devono essere applicate a quali variabili/campi, è necessario comprendere gli ID acquisiti nei dati di Analytics e decidere quali utilizzare per le richieste di privacy dei dati. La privacy dei dati amplia l'ambito di ciò che può essere considerato un ID. Gli ID rientrano in due grandi classi: direttamente identificabili (etichetta di identità: I1) e indirettamente identificabili (etichetta di identità: I2).

* **ID direttamente identificabile (I1)**: indica il nome di una persona o ne fornisce il metodo di contatto diretto. Tra gli esempi abbiamo il nome di una persona (persino un nome comune come Mario Rossi che potrebbe essere associato a centinaia di persone), indirizzi e-mail o numeri di telefono e così via. Un indirizzo postale senza un nome potrebbe essere considerato direttamente identificabile, sebbene possa identificare soltanto una famiglia o un'azienda anziché una persona specifica all'interno di quella famiglia o di quell'azienda.
* **ID indirettamente identificabile (I2)**: da solo non consente l'identificazione di una persona, ma può essere combinato con altre informazioni (che potrebbero essere o meno in tuo possesso) per identificare un individuo. Ne sono esempi il numero fedeltà di un cliente o un ID usato da un sistema CRM di un'azienda univoco per ciascun cliente. In Privacy dei dati, gli ID anonimi memorizzati nei cookie di tracciamento utilizzati da Analytics possono essere considerati indirettamente identificativi, anche se possono identificare solo un dispositivo anziché un individuo; su un dispositivo condiviso, questi cookie non sono in grado di distinguere tra i diversi utenti del sistema. Ad esempio, anche se il cookie non può essere utilizzato per trovare un computer che contiene il cookie, se qualcuno ha accesso al computer e individua il cookie, può ricollegare i dati del cookie Analytics al computer.

   Anche un indirizzo IP viene considerato indirettamente identificabile, perché in una determinata istanza nel tempo potrebbe essere assegnato a un unico dispositivo. Tuttavia, gli ISP possono cambiare gli indirizzi IP, come spesso avviene, per la maggior parte degli utenti, pertanto con il passare del tempo un indirizzo IP potrebbe essere usato da uno qualsiasi dei loro utenti. Inoltre, non è insolito per molti clienti di un ISP o per più dipendenti di un'azienda nella stessa Intranet condividere lo stesso indirizzo IP esterno. Because of this, Adobe will not support using an IP address as the ID for a [Data Privacy request.](../../admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Tuttavia, quando un ID accettato viene usato come parte di una richiesta di cancellazione, verranno cancellati anche gli indirizzi IP in cui era presente quell'ID. Devi decidere se esistono altri ID raccolti che possono rientrare in questa categoria, di I1 o I2, ma che non possono essere utilizzati come ID distintivo per le richieste sulla privacy dei dati.

Anche se l'azienda raccoglie molti ID diversi all'interno dei dati di Analytics, potete scegliere di utilizzare solo un sottoinsieme di questi ID per le richieste di privacy dei dati. Ecco delle possibili ragioni per questa scelta:

* All'interno dei tuoi sistemi puoi mappare uno degli ID (ad esempio l'indirizzo e-mail) per un ID diverso (ad esempio l'ID CRM). Quindi, per coerenza, decidi di utilizzare l'ID CRM solo per le richieste di privacy dei dati nell'elaborazione della privacy dei dati.
* Non hai un metodo per verificare l'associazione tra un ID e una persona. Ad esempio, può risultare piuttosto complicato verificare che un indirizzo IP sia stato sempre usato da una sola persona, che è effettivamente la persona che invia la richiesta.
* Alcuni ID possono corrispondere a più persone e non è consigliabile rischiare di restituire informazioni su una persona a un'altra persona con lo stesso ID. Ad esempio, anche se puoi verificare che il nome di una persona è Mario Rossi, non è consigliabile restituire tutti i dati su tutti i Mario Rossi nel tuo sistema.
* Un altro esempio è l'ID di un dispositivo, ad esempio l'ID cookie di Analytics. Se l'ID si presenta in un'app per cellulare, puoi decidere che tutte le interazioni che usano quell'ID debbano essere disponibili per il proprietario del cellulare. Tuttavia se questo si verifica su un dispositivo condiviso, ad esempio un computer usato in casa, di una biblioteca o di un Internet café, non puoi distinguere i vari utenti del dispositivo e il rischio di restituire i dati a un utente diverso è troppo elevato per poter usare questo tipo di ID.

## Tecniche consigliate per gli ID supportati da Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Utilizza questa tabella per determinare i tipi di ID che utilizzerai per l'invio delle richieste di privacy ai dati Analytics. Una volta appresa questa informazione, sarà più facile determinare le altre etichette da usare per le variabili.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di ID </th> 
   <th colname="col2" class="entry"> Tecniche consigliate </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID cookie </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external">Cookie di Analytics (legacy)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Cookie del servizio Identity</a> (ECID), noto in precedenza come Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Questi cookie identificano un dispositivo o, in particolare, un browser per un utente di un dispositivo. Per un dispositivo condiviso in cui viene usato un accesso comune, questo ID può essere applicato a tutti gli utenti del dispositivo. Adobe has created some <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> unified JavaScript </a> that you can place on your website to collect these cookies if you want to allow them to be used for Data Privacy requests. </p> <p>Anche gli utenti dell'SDK di Adobe Analytics per dispositivi mobili hanno un Experience Cloud ID (ECID). All’interno dell’SDK sono presenti chiamate API per leggere questo ID, in modo da poter migliorare l’app per la raccolta per una richiesta di privacy dei dati. </p> <p>Molte aziende considerano gli ID cookie del browser come ID di dispositivi condivisi. Di conseguenza, in consultazione con i loro team legali, possono scegliere di non supportare l'utilizzo di tali ID come ID accettabili per le richieste di privacy dei dati, oppure possono scegliere di restituire solo una quantità molto limitata di dati quando questi ID vengono utilizzati o possono solo accettarli per le richieste di eliminazione. </p> <p>Questi cookie hanno un'etichetta ID-DEVICE che non può essere modificata (così come le etichette I2 e DEL-DEVICE). La configurazione predefinita di Adobe Analytics restituirà solo informazioni generiche sul dispositivo, quali il tipo di dispositivo, il sistema operativo, il browser e così via, oltre all'ora/data in cui il sito Web è stato visitato usando questi ID. Tuttavia, se si sceglie di supportare questi ID per le richieste di privacy dei dati, come illustrato di seguito, è possibile aggiungere o rimuovere le etichette ACC-ALL per configurare l'esatto set di campi che si desidera venga restituito per una richiesta di accesso alla privacy dei dati. </p> <p>Soprattutto se la suite di rapporti corrisponde a un'app mobile che richiede l'accesso, puoi decidere che l'Experience Cloud ID per il dispositivo corrisponda a un utente specifico e pertanto è consigliabile etichettare altri campi con ACC-ALL, tra cui i nomi delle pagine visitate, i prodotti visualizzati e così via. </p> <p>Nota:  Se specifichi l’opzione "espandereIds" nella richiesta di privacy dei dati, le tue richieste includeranno sempre ID cookie, oltre a qualsiasi altro ID specificato. Per altre informazioni consulta la parte relativa all’<a href="../../admin/c-data-governance/gdpr-id-expansion.md" format="dita" scope="local">espansione dell’ID</a>. In queste istanze, i risultati che hanno solo un ID cookie, non altri ID, restituiranno solo dati con etichetta ACC-ALL come parte della richiesta di accesso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID nelle variabili personalizzate </p> </td> 
   <td colname="col2"> <p>Alcuni clienti inseriscono gli ID nelle <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">variabili di traffico personalizzate (proprietà) o nelle variabili di conversione personalizzate (eVars) </a>. Sebbene il più comune sia un ID CRM, gli altri includono indirizzi e-mail, nomi di login degli utenti, numeri di fidelizzazione dei clienti o hash di questi valori. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Se vuoi utilizzare uno di questi ID per le richieste sulla privacy dei dati, devi assegnare al campo che lo contiene un'etichetta ID-PERSONA. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Caso molto meno comune) Se un ID in una di queste variabili personalizzate definisce solo un dispositivo che può essere condiviso tra più persone, puoi utilizzare un'etichetta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Questi campi richiedono inoltre le etichette I1 o I2 e devono includere un'etichetta DEL-PERSON o DEL-DEVICE. Generalmente, l'opzione PERSON/DEVICE dell'etichetta DEL corrisponderà all'opzione PERSON/DEVICE dell'etichetta ID. </li> 
    </ul> <p> È raro che una suite di rapporti contenga più di una o due variabili personalizzate contenenti ID da utilizzare per identificare gli oggetti dati per le richieste di privacy dei dati. È possibile avere variabili multiple a cui sono assegnate le etichette I1 o I2, ma normalmente solo una o due di queste avrebbero anche le etichette ID-PERSON o ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col2"> <p>Benché non sia ampiamente usata, Analytics supporta anche un'implementazione in cui è possibile fornire un ID visitatore personalizzato, che, se presente, viene usato per sostituire il cookie di monitoraggio di Analytics legacy. Il campo ha le etichette I2, ID-PERSON e DEL-PERSON. </p> <p>Molte implementazioni derivano questo ID da un ID CRM, pertanto esso è presente solo quando una persona effettua l'accesso al sito. Questo consente di usare per i dispositivi lo stesso ID visitatore personalizzato. Uno svantaggio tecnico consiste nel fatto che i rilevamenti di ciò che accade prima che l'utente acceda non possono essere collegati ai rilevamenti effettuati in seguito all'accesso. Se invece si utilizza l'ID visitatore personalizzato per identificare semplicemente un dispositivo, è necessario modificare le etichette ID-PERSON e DEL-PERSON rispettivamente in ID-DEVICE e DEL-DEVICE. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tecniche consigliate per l’impostazione delle etichette di cancellazione {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]
>
>Le proprietà distinguono sempre tra maiuscole e minuscole. Le eVars distinguono tra maiuscole e minuscole per impostazione predefinita, ma non possono essere configurate nell'Assistenza clienti di Adobe affinché distinguano tra maiuscole e minuscole. Se disponi di un'eVar sensibile alle maiuscole/minuscole contenente un ID, è tua responsabilità utilizzare il caso corretto quando invii una richiesta di privacy dei dati in modo che il caso utilizzato nella richiesta corrisponda al caso utilizzato negli hit che contengono tali ID.

Le etichette di cancellazione DEL-DEVICE e DEL-PERSON devono essere usate con moderazione. Se applicati a una variabile che non contiene un ID utilizzato come parte della richiesta di privacy dei dati, i conteggi (metriche) nei rapporti storici di Analytics saranno quasi sempre modificati.

* Si consiglia di applicare una di queste etichette a una variabile con etichetta I1, I2 o S1. Non può essere applicata a una qualsiasi variabile che non abbia l'etichetta I1, I2 o S1.
* The DEL-labels will result in these variables being [anonymized](../../admin/c-data-governance/gdpr-labels.md#section_F3DEE591671A4B16A8E043F91C137ECB) (the ID will be replaced with a random string prefixed with "Data Privacy-"). Lo stesso valore anonimizzato sostituirà tutte le istanze del valore originale in tutti i risultati identificati da un ID usato nella richiesta. Se il valore originale in questo campo è uno degli ID, le metriche del rapporto non cambieranno.
* In generale, se un campo ha l'etichetta ID-DEVICE, devi assegnare anche l'etichetta DEL-DEVICE.
* Analogamente, se un campo ha l'etichetta ID-PERSON, devi assegnare anche l'etichetta DEL-PERSON.
* Se un campo non ha un'etichetta ID, ma contiene informazioni identificabili che vuoi rendere anonime, l'etichetta più appropriata da usare (DEVICE o PERSON) dipende dall'implementazione. Se utilizzi solo i cookie ID per le richieste di privacy dei dati, devi usare DEL-DEVICE.
* Se usi gli ID personalizzati in un campo diverso con un'etichetta ID-PERSON e vuoi cancellarli solo nelle righe in cui si trova l'ID, usa DEL-PERSON.
* Se usi un'espansione dell'ID e vuoi cancellare tutti i valori per tutti i risultati in tutti i dispositivi identificati, allora usa DEL-DEVICE. In questo caso puoi applicare sia l'etichetta DEL-DEVICE che l'etichetta DEL-PERSON, se lo preferisci; tuttavia l'etichetta DEL-PERSON non è necessaria perché l'espansione dell'ID indica che tutte le righe che corrispondono a un ID persona corrisponderanno anche a un ID dispositivo.
* Se non si specifica di voler usare l'espansione dell'ID, ma verranno usati gli ID persona e dispositivi insieme per le diverse richieste, ti conviene specificare sia l'etichetta DEL-DEVICE che l'etichetta DEL-PERSON per le variabili che devono essere cancellate quando viene usata una delle due tipologie di etichetta.
* Nota che se un'etichetta DEL-DEVICE o DEL-PERSON viene specificata per una variabile che non viene usata come ID per la richiesta (incluso un ID esteso), i valori univoci in quella variabile verranno resi anonimi solo nei risultati in cui si trova un ID specifico (o esteso). Se altri risultati contengono lo stesso valore, questo non verrà aggiornato nelle altre posizioni. Tutto ciò può provocare una modifica del conteggio (metriche).

   Ad esempio, se avete tre hit contenenti il valore "foo" in eVar7, ma solo uno di essi contiene anche un ID in una variabile diversa che viene confrontata con un'eliminazione, il valore "foo" di quell'hit verrà modificato in un valore come "Data Privacy-123456789", mentre rimarrà invariato nelle altre due hit. Un rapporto che mostra il numero di valori univoci per eVar7 mostrerà ora anche un altro valore univoco. Un rapporto che mostra i valori più importanti per eVars può includere il valore "foo" con due sole istanze (invece delle 3 precedenti). Anche il nuovo valore verrà visualizzato con una sola istanza.

## Tecniche consigliate per l'impostazione delle etichette di accesso {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Sebbene pochissimi campi avranno un'etichetta diversa, in molti campi spesso saranno presenti le etichette ACC. Le etichette di accesso appropriate dipenderanno dagli ID utilizzati per le richieste di privacy dei dati.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID utilizzato </th> 
   <th colname="col2" class="entry"> Tecniche consigliate </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Solo ID dispositivo </p> </td> 
   <td colname="col2"> <p>Se gli unici ID che usi sono ID cookie o quelli con un'etichetta ID-DEVICE, devi usare solo l'etichetta ACC-ALL. </p> <p>Otterrai una coppia di file per ogni richiesta di accesso, uno contenente una riga per ogni risultato corrispondente a tutti i campi ACC-ALL specificati e l'altro contenente un riepilogo di questi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID persona senza espansione dell'ID </p> </td> 
   <td colname="col2"> <p>Se usi solo ID personalizzati che hanno l'etichetta ID-PERSON e non eseguono l'espansione dell'ID, devi usare le etichette ACC-PERSON. Tuttavia, non devi cambiare le etichette ACC-ALL predefinite; questi campi verranno inclusi automaticamente nella richiesta di accesso. </p> <p>Otterrai una coppia di file per ogni richiesta di accesso, uno contenente una riga per ogni risultato corrispondente a tutti i campi ACC-DEVICE e ACC-PERSON specificati e l'altro contenente un riepilogo di questi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID misti e/o espansione dell'ID </p> </td> 
   <td colname="col2"> <p>Se includi sia gli ID dispositivo che gli ID persona nelle richieste di privacy dei dati, o se utilizzi ID personalizzati (ID visitatore personalizzato o ID in una prop o eVar), devi prestare attenzione alle etichette ACC utilizzate. Ogni richiesta di accesso restituirà due coppie di file di dati, una coppia con i dati dei risultati che contenevano un ID persona corrispondente e una seconda coppia con i dati dei risultati che non corrispondevano a un ID persona, ma a un ID dispositivo. </p> <p>I file "ID persona" contengono dati su tutti i punti che corrispondono agli ID persona con tutti i campi dotati di etichetta ACC-PERSON e/o ACC-ALL (un file con tutti i punti corrispondenti e l'altro come riepilogo). </p> <p>La coppia di file "ID dispositivo" contiene solo campi che hanno un'etichetta ACC-ALL e contiene solo risultati che non contengono ID persona corrispondenti. Questi file possono contenere dati generati da altri utenti di un dispositivo condiviso, pertanto è consigliabile considerare attentamente il set di campi che contengono l'etichetta ACC-ALL. Le etichette predefinite in Analytics applicano questa etichetta solo a campi di informazioni generiche correlati al dispositivo (tipo di dispositivo, sistema operativo, browser e così via) oltre all'ora/data di ogni risultato. </p> <p>Puoi scegliere di ricevere da Adobe sia i set di file relativi alla persona che quelli relativi al dispositivo e di condividere solo i file relativi alla persona, in modo da non condividere dati che potrebbero essere generati da altri utenti di un dispositivo condiviso. Oppure puoi combinare i dati di uno o di entrambi i set con altre informazioni note sui dati interessati e restituirli nel formato desiderato. </p> </td> 
  </tr> 
 </tbody> 
</table>

