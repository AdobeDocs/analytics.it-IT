---
description: 'null'
title: Tecniche di etichettatura consigliate
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: ht
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Tecniche di etichettatura consigliate

>[!NOTE] Ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Potrebbe essere necessario rivedere l&#39;etichettatura anche quando vengono abilitate nuove integrazioni della soluzione, perché queste potrebbero esporre nuove variabili che potrebbero richiedere le etichette. Una nuova implementazione delle app mobili o dei siti web potrebbe cambiare il modo in cui vengono usate le variabili esistenti. Anche per queste potrebbe essere necessario aggiornare le etichette.

## ID direttamente e indirettamente identificabili {#section_030799AA1397433FBA61A2BC60A7A750}

Prima di capire quali etichette applicare a determinate variabili o campi, è necessario conoscere gli ID che vengono acquisiti nei dati di Analytics e decidere quali usare per le richieste di Privacy dei dati. La Privacy dei dati espande l’ambito di definizione di ID. Gli ID rientrano in due grandi classi: direttamente identificabili (etichetta di identità: I1) e indirettamente identificabili (etichetta di identità: I2).

* **ID direttamente identificabile (I1)**: indica il nome di una persona o ne fornisce il metodo di contatto diretto. Tra gli esempi abbiamo il nome di una persona (persino un nome comune come Mario Rossi che potrebbe essere associato a centinaia di persone), indirizzi e-mail o numeri di telefono e così via. Un indirizzo postale senza un nome potrebbe essere considerato direttamente identificabile, sebbene possa identificare soltanto una famiglia o un&#39;azienda anziché una persona specifica all&#39;interno di quella famiglia o di quell&#39;azienda.
* **ID indirettamente identificabile (I2)**: da solo non consente l&#39;identificazione di una persona, ma può essere combinato con altre informazioni (che potrebbero essere o meno in tuo possesso) per identificare un individuo. Ne sono esempi il numero fedeltà di un cliente o un ID usato da un sistema CRM di un&#39;azienda univoco per ciascun cliente. In base alla Privacy dei dati, gli ID anonimi memorizzati nei cookie di monitoraggio usati da Analytics possono essere considerati identificativi indiretti, sebbene possano individuare solo un dispositivo invece di una persona; su un dispositivo condiviso, questi cookie non distinguono i diversi utenti del sistema. Ad esempio, anche se il cookie non può essere utilizzato per trovare un computer che contiene il cookie, se qualcuno ha accesso al computer e individua il cookie, può ricollegare i dati del cookie Analytics al computer.

   Anche un indirizzo IP viene considerato indirettamente identificabile, perché in una determinata istanza nel tempo potrebbe essere assegnato a un unico dispositivo. Tuttavia, gli ISP possono cambiare gli indirizzi IP, come spesso avviene, per la maggior parte degli utenti, pertanto con il passare del tempo un indirizzo IP potrebbe essere usato da uno qualsiasi dei loro utenti. Inoltre, non è insolito per molti clienti di un ISP o per più dipendenti di un&#39;azienda nella stessa Intranet condividere lo stesso indirizzo IP esterno. Per questo motivo, Adobe non supporterà l’uso di un indirizzo IP come ID per una [richiesta di Privacy dei dati.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Tuttavia, quando un ID accettato viene usato come parte di una richiesta di cancellazione, verranno cancellati anche gli indirizzi IP in cui era presente quell’ID. È necessario stabilire l’esistenza di altri ID raccolti che possono rientrare in questa categoria, I1 o I2, ma che non sono idonei a essere usati come ID distintivi per le richieste di Privacy dei dati.

Anche se l’azienda raccoglie molti ID diversi nei dati di Analytics, puoi scegliere di usare solo un sottoinsieme di questi ID per le richieste di Privacy dei dati. Ecco delle possibili ragioni per questa scelta:

* All&#39;interno dei tuoi sistemi puoi mappare uno degli ID (ad esempio l&#39;indirizzo e-mail) per un ID diverso (ad esempio l&#39;ID CRM). Successivamente, per coerenza, decidi di usare solo l’ID CRM per le richieste di Privacy dei dati nell’elaborazione della Privacy dei dati.
* Non hai un metodo per verificare l&#39;associazione tra un ID e una persona. Ad esempio, può risultare piuttosto complicato verificare che un indirizzo IP sia stato sempre usato da una sola persona, che è effettivamente la persona che invia la richiesta.
* Alcuni ID possono corrispondere a più persone e non è consigliabile rischiare di restituire informazioni su una persona a un&#39;altra persona con lo stesso ID. Ad esempio, anche se puoi verificare che il nome di una persona è Mario Rossi, non è consigliabile restituire tutti i dati su tutti i Mario Rossi nel tuo sistema.
* Un altro esempio è l&#39;ID di un dispositivo, ad esempio l&#39;ID cookie di Analytics. Se l&#39;ID si presenta in un&#39;app per cellulare, puoi decidere che tutte le interazioni che usano quell&#39;ID debbano essere disponibili per il proprietario del cellulare. Tuttavia se questo si verifica su un dispositivo condiviso, ad esempio un computer usato in casa, di una biblioteca o di un Internet café, non puoi distinguere i vari utenti del dispositivo e il rischio di restituire i dati a un utente diverso è troppo elevato per poter usare questo tipo di ID.

## Tecniche consigliate per gli ID supportati da Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Usa questa tabella per determinare i tipi di ID che userai durante l’invio delle richieste di Privacy dei dati ad Analytics. Una volta appresa questa informazione, sarà più facile determinare le altre etichette da usare per le variabili.

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
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/ec-cookies/cookies-privacy.html"> (Legacy) Cookie di Analytics </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://docs.adobe.com/content/help/it-IT/id-service/using/home.html"> Cookie del servizio Identity </a> (ECID), noto in precedenza come Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Questi cookie identificano un dispositivo o, in particolare, un browser per un utente di un dispositivo. Per un dispositivo condiviso in cui viene usato un accesso comune, questo ID può essere applicato a tutti gli utenti del dispositivo. Adobe ha creato alcuni <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm"> JavaScript unificati </a> che è possibile inserire nel sito web per raccogliere questi cookie al fine di utilizzarli per le richieste di Privacy dei dati. </p> <p>Anche gli utenti dell’SDK di Adobe Analytics per dispositivi mobili hanno un Experience Cloud ID (ECID). L’SDK contiene delle chiamate API per leggere questo ID, in modo che l’app possa raccoglierlo per una richiesta di Privacy dei dati. </p> <p>Molte aziende considerano gli ID cookie del browser come ID di dispositivi condivisi. Di conseguenza, consultando il proprio team legale, è possibile che si decida di non supportarne l’uso come ID accettabili per le richieste di Privacy dei dati o di restituire solo una quantità molto limitata di dati in cui sono usati questi ID o di accettarli solo per le richieste di cancellazione. </p> <p>Questi cookie hanno un'etichetta ID-DEVICE che non può essere modificata (così come le etichette I2 e DEL-DEVICE). La configurazione predefinita di Adobe Analytics restituirà solo informazioni generiche sul dispositivo, quali il tipo di dispositivo, il sistema operativo, il browser e così via, oltre all'ora/data in cui il sito Web è stato visitato usando questi ID. Tuttavia, se si sceglie di supportare questi ID per le richieste di Privacy dei dati, come spiegato di seguito, è possibile aggiungere o rimuovere le etichette ACC-ALL per configurare l’esatto insieme di campi che si desidera restituire per una richiesta di accesso di Privacy dei dati. </p> <p>Soprattutto se la suite di rapporti corrisponde a un’app mobile che richiede l’accesso, puoi decidere che l’Experience Cloud ID per il dispositivo corrisponda a un utente specifico e pertanto è consigliabile etichettare altri campi con ACC-ALL, tra cui i nomi delle pagine visitate, i prodotti visualizzati e così via. </p> <p>Nota: se specifichi l’opzione “expandIds” nella richiesta di Privacy dei dati, le richieste includeranno sempre gli ID cookie, oltre ad altri ID specificati dall’utente. Per altre informazioni consulta la parte relativa all’<a href="/help/admin/c-data-governance/gdpr-id-expansion.md">espansione dell’ID </a>. In queste istanze, i risultati che hanno solo un ID cookie, non altri ID, restituiranno solo dati con etichetta ACC-ALL come parte della richiesta di accesso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID nelle variabili personalizzate </p> </td> 
   <td colname="col2"> <p>Alcuni clienti inseriscono gli ID nelle <a href="https://docs.adobe.com/content/help/it-IT/analytics/implementation/vars/page-vars/evar.html">variabili di traffico personalizzate (proprietà) o nelle variabili di conversione personalizzate (eVars)</a>. Sebbene il più comune sia un ID CRM, gli altri includono indirizzi e-mail, nomi di login degli utenti, numeri di fidelizzazione dei clienti o hash di questi valori. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Se desideri usare uno di questi ID per le richieste di Privacy dei dati, devi assegnare al campo che lo contiene un’etichetta ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Caso molto meno comune) Se un ID in una di queste variabili personalizzate definisce solo un dispositivo che può essere condiviso tra più persone, puoi utilizzare un’etichetta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Questi campi richiedono inoltre le etichette I1 o I2 e devono includere un'etichetta DEL-PERSON o DEL-DEVICE. Generalmente, l'opzione PERSON/DEVICE dell'etichetta DEL corrisponderà all'opzione PERSON/DEVICE dell'etichetta ID. </li> 
    </ul> <p> Raramente la suite di rapporti ha più di una o due variabili personalizzate contenenti gli ID che si desidera utilizzare per identificare i dati interessati per le richieste di Privacy dei dati. È possibile avere variabili multiple a cui sono assegnate le etichette I1 o I2, ma normalmente solo una o due di queste avrebbero anche le etichette ID-PERSON o ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col2"> <p>Benché non sia ampiamente usata, Analytics supporta anche un'implementazione in cui è possibile fornire un ID visitatore personalizzato, che, se presente, viene usato per sostituire il cookie di monitoraggio di Analytics legacy. Il campo ha le etichette I2, ID-PERSON e DEL-PERSON. </p> <p>Molte implementazioni derivano questo ID da un ID CRM, pertanto esso è presente solo quando una persona effettua l'accesso al sito. Questo consente di usare per i dispositivi lo stesso ID visitatore personalizzato. Uno svantaggio tecnico consiste nel fatto che i rilevamenti di ciò che accade prima che l'utente acceda non possono essere collegati ai rilevamenti effettuati in seguito all'accesso. Se invece si utilizza l'ID visitatore personalizzato per identificare semplicemente un dispositivo, è necessario modificare le etichette ID-PERSON e DEL-PERSON rispettivamente in ID-DEVICE e DEL-DEVICE. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tecniche consigliate per l’impostazione delle etichette di cancellazione {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE] Le proprietà sono sempre senza distinzione tra maiuscole e minuscole. Le eVars distinguono tra maiuscole e minuscole per impostazione predefinita, ma non possono essere configurate nell’Assistenza clienti di Adobe affinché distinguano tra maiuscole e minuscole. Se possiedi un’eVar che distingue tra maiuscole e minuscole e che contiene un ID, è tua responsabilità usare la maiuscola/minuscola, in base al caso, quando invii una richiesta di Privacy dei dati, in modo che l’uso della maiuscola/minuscola nella richiesta corrisponda all’uso della maiuscola/minuscola nei risultati contenenti questi ID.

Le etichette di cancellazione DEL-DEVICE e DEL-PERSON devono essere usate con moderazione. Quando applicati a una variabile che non contiene un ID usata come parte della richiesta di Privacy dei dati, i conteggi (metriche) nei rapporti cronologici di Analytics cambieranno quasi sempre.

* Si consiglia di applicare una di queste etichette a una variabile con etichetta I1, I2 o S1. Non può essere applicata a una qualsiasi variabile che non abbia l’etichetta I1, I2 o S1.
* Le etichette DEL- risulteranno [anonime](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) in queste variabili (l’ID verrà sostituito da una stringa casuale con prefisso “Privacy dei dati-”). Lo stesso valore anonimizzato sostituirà tutte le istanze del valore originale in tutti i risultati identificati da un ID usato nella richiesta. Se il valore originale in questo campo è uno degli ID, le metriche del rapporto non cambieranno.
* In generale, se un campo ha l&#39;etichetta ID-DEVICE, devi assegnare anche l&#39;etichetta DEL-DEVICE.
* Analogamente, se un campo ha l&#39;etichetta ID-PERSON, devi assegnare anche l&#39;etichetta DEL-PERSON.
* Se un campo non ha un&#39;etichetta ID, ma contiene informazioni identificabili che vuoi rendere anonime, l&#39;etichetta più appropriata da usare (DEVICE o PERSON) dipende dall&#39;implementazione. Se usi solo ID cookie per le richieste di Privacy dei dati, devi usare DEL-DEVICE.
* Se usi gli ID personalizzati in un campo diverso con un&#39;etichetta ID-PERSON e vuoi cancellarli solo nelle righe in cui si trova l&#39;ID, usa DEL-PERSON.
* Se usi un&#39;espansione dell&#39;ID e vuoi cancellare tutti i valori per tutti i risultati in tutti i dispositivi identificati, allora usa DEL-DEVICE. In questo caso puoi applicare sia l&#39;etichetta DEL-DEVICE che l&#39;etichetta DEL-PERSON, se lo preferisci; tuttavia l&#39;etichetta DEL-PERSON non è necessaria perché l&#39;espansione dell&#39;ID indica che tutte le righe che corrispondono a un ID persona corrisponderanno anche a un ID dispositivo.
* Se non si specifica di voler usare l&#39;espansione dell&#39;ID, ma verranno usati gli ID persona e dispositivi insieme per le diverse richieste, ti conviene specificare sia l&#39;etichetta DEL-DEVICE che l&#39;etichetta DEL-PERSON per le variabili che devono essere cancellate quando viene usata una delle due tipologie di etichetta.
* Nota che se un&#39;etichetta DEL-DEVICE o DEL-PERSON viene specificata per una variabile che non viene usata come ID per la richiesta (incluso un ID esteso), i valori univoci in quella variabile verranno resi anonimi solo nei risultati in cui si trova un ID specifico (o esteso). Se altri risultati contengono lo stesso valore, questo non verrà aggiornato nelle altre posizioni. Tutto ciò può provocare una modifica del conteggio (metriche).

   Ad esempio, se tre risultati contengono il valore “foo” in eVar7, ma solo uno di essi contiene anche un ID in una variabile diversa che corrisponde a una cancellazione, il valore “foo” in quei risultati verrà modificato in un valore simile a “Privacy dei dati-123456789”, mentre rimarrà invariato negli altri due risultati. Un rapporto che mostra il numero di valori univoci per eVar7 mostrerà ora anche un altro valore univoco. Un rapporto che mostra i valori più importanti per eVars può includere il valore “foo” con due sole istanze (invece delle 3 precedenti). Anche il nuovo valore verrà visualizzato con una sola istanza.

## Tecniche consigliate per l&#39;impostazione delle etichette di accesso {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Sebbene pochissimi campi avranno un’etichetta diversa, in molti campi spesso saranno presenti le etichette ACC. Il tipo di etichetta di accesso adeguato dipende dagli ID usati per le richieste di Privacy dei dati.

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
   <td colname="col1"> <p>ID misti e/o espansione dell’ID </p> </td> 
   <td colname="col2"> <p>Se nelle richieste di Privacy dei dati includi sia gli ID persona che visitatore, o se usi gli ID personalizzati (ID visitatore personalizzato o un ID in una proprietà o in un’eVar), devi fare attenzione alle etichette ACC usate. Ogni richiesta di accesso restituirà due coppie di file di dati, una coppia con i dati dei risultati che contenevano un ID persona corrispondente e una seconda coppia con i dati dei risultati che non corrispondevano a un ID persona, ma a un ID dispositivo. </p> <p>I file "ID persona" contengono dati su tutti i punti che corrispondono agli ID persona con tutti i campi dotati di etichetta ACC-PERSON e/o ACC-ALL (un file con tutti i punti corrispondenti e l'altro come riepilogo). </p> <p>La coppia di file "ID dispositivo" contiene solo campi che hanno un'etichetta ACC-ALL e contiene solo risultati che non contengono ID persona corrispondenti. Questi file possono contenere dati generati da altri utenti di un dispositivo condiviso, pertanto è consigliabile considerare attentamente il set di campi che contengono l'etichetta ACC-ALL. Le etichette predefinite in Analytics applicano questa etichetta solo a campi di informazioni generiche correlati al dispositivo (tipo di dispositivo, sistema operativo, browser e così via) oltre all'ora/data di ogni risultato. </p> <p>Puoi scegliere di ricevere da Adobe sia i set di file relativi alla persona che quelli relativi al dispositivo e di condividere solo i file relativi alla persona, in modo da non condividere dati che potrebbero essere generati da altri utenti di un dispositivo condiviso. Oppure puoi combinare i dati di uno o di entrambi i set con altre informazioni note sui dati interessati e restituirli nel formato desiderato. </p> </td> 
  </tr> 
 </tbody> 
</table>

