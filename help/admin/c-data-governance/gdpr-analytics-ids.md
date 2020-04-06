---
description: 'null'
title: Tecniche di etichettatura consigliate
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Tecniche di etichettatura consigliate

>[!NOTE] Ricorda che l’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Potrebbe inoltre essere necessario rivedere l&#39;etichettatura quando sono abilitate nuove integrazioni di soluzioni, in quanto possono esporre nuove variabili che potrebbero richiedere l&#39;etichettatura. Una reimplementazione delle app mobili o dei siti Web potrebbe modificare il modo in cui vengono utilizzate le variabili esistenti, e questo potrebbe richiedere anche aggiornamenti delle etichette.

## ID direttamente e indirettamente identificabili {#section_030799AA1397433FBA61A2BC60A7A750}

Prima di capire quali etichette applicare a determinate variabili o campi, è necessario conoscere gli ID che vengono acquisiti nei dati di Analytics e decidere quali usare per le richieste di Privacy dei dati. La Privacy dei dati espande l’ambito di definizione di ID. Gli ID appartengono a due classi grandi: direttamente identificabili (etichetta di identità: I1) e indirettamente identificabili (etichetta di identità: I2).

* **Un ID direttamente identificabile (I1)**: Definisce la persona o fornisce un metodo diretto per contattarla. Esempi potrebbero includere il nome di qualcuno (anche un nome comune come John Smith che può essere condiviso da centinaia di persone), uno qualsiasi dei loro indirizzi email o numeri di telefono, ecc. Un indirizzo postale senza un nome può essere considerato direttamente identificabile, anche se può identificare solo una famiglia o un&#39;impresa piuttosto che una persona specifica all&#39;interno di tale famiglia o attività.
* **Un ID identificabile indirettamente (I2)**: Non consente l&#39;identificazione di un individuo da solo, ma può essere combinato con altre informazioni (che possono o non possono essere in tuo possesso), per identificare qualcuno. Esempi possono includere un numero di fedeltà del cliente o un ID utilizzato dal sistema CRM di una società che sia univoco per ciascuno dei suoi clienti. In base alla Privacy dei dati, gli ID anonimi memorizzati nei cookie di monitoraggio usati da Analytics possono essere considerati identificativi indiretti, sebbene possano individuare solo un dispositivo invece di una persona; su un dispositivo condiviso, questi cookie non distinguono i diversi utenti del sistema. Ad esempio, se il cookie non può essere utilizzato per trovare un computer contenente il cookie, se qualcuno ha accesso al computer e trova il cookie, può collegare nuovamente i dati del cookie di Analytics al computer.

   Anche un indirizzo IP è considerato indirettamente identificabile, perché in un dato caso temporale, potrebbe essere assegnato solo a un singolo dispositivo. Tuttavia, gli ISP possono e spesso cambiano gli indirizzi IP per la maggior parte degli utenti regolarmente, quindi nel tempo un indirizzo IP potrebbe essere stato utilizzato da qualsiasi utente. Inoltre, non è raro che molti clienti di un ISP o più dipendenti di un&#39;azienda sulla stessa Intranet condividano lo stesso indirizzo IP esterno. Per questo motivo, Adobe non supporterà l’uso di un indirizzo IP come ID per una [richiesta di Privacy dei dati.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Tuttavia, quando un ID accettato viene usato come parte di una richiesta di cancellazione, verranno cancellati anche gli indirizzi IP in cui era presente quell’ID. È necessario stabilire l’esistenza di altri ID raccolti che possono rientrare in questa categoria, I1 o I2, ma che non sono idonei a essere usati come ID distintivi per le richieste di Privacy dei dati.

Anche se l’azienda raccoglie molti ID diversi nei dati di Analytics, puoi scegliere di usare solo un sottoinsieme di questi ID per le richieste di Privacy dei dati. I motivi di tale scelta possono essere:

* All&#39;interno dei tuoi sistemi, puoi mappare uno degli ID (ad esempio, indirizzo e-mail) a un ID diverso (ad esempio, ID CRM). Successivamente, per coerenza, decidi di usare solo l’ID CRM per le richieste di Privacy dei dati nell’elaborazione della Privacy dei dati.
* Non esiste un metodo per verificare che qualcuno sia effettivamente la persona associata all’ID. Ad esempio, può essere molto difficile convalidare che un indirizzo IP sia mai stato utilizzato da una sola persona e che la persona che ha inviato la richiesta sia effettivamente quella persona.
* Alcuni ID possono corrispondere a più persone e non si desidera rischiare di restituire informazioni su una persona a un&#39;altra con lo stesso ID. Ad esempio, anche se puoi verificare che il nome di qualcuno sia John Smith, potresti non voler restituire tutti i dati su tutti i John Smiths nel tuo sistema.
* Un altro esempio è l&#39;ID dispositivo, ad esempio l&#39;ID cookie di Analytics. Se l’ID si verifica in un’app per telefoni cellulari, puoi decidere che tutte le interazioni che utilizzano tale ID siano disponibili al proprietario del cellulare. Tuttavia, se si verifica su un dispositivo condiviso, come un computer di casa o uno in una libreria o in un internet cafe, potete decidere che non è possibile distinguere tra gli utenti di quel dispositivo e che il rischio di restituzione dei dati per un altro utente è troppo grande per consentire l&#39;utilizzo di questo tipo di ID.

## Tecniche consigliate per gli ID supportati da Analytics  {#section_B6481505FF1949498D4B4B35B780D050}

Usa questa tabella per determinare i tipi di ID che userai durante l’invio delle richieste di Privacy dei dati ad Analytics. Una volta note queste informazioni, sarà più semplice determinare le altre etichette da utilizzare per le variabili.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo ID </th> 
   <th colname="col2" class="entry"> Recommendations </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Cookie ID </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/it_IT/whitepapers/cookies/cookies_analytics.html"> Cookie di Analytics (legacy) </a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/it_IT/mcvid/"> Cookie del servizio Identity </a> (ECID), noto in precedenza come Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Questi cookie identificano un dispositivo o, più nello specifico, un browser per l'utente di un dispositivo. Per un dispositivo condiviso in cui viene utilizzato un login comune, questo ID può essere valido per tutti gli utenti del dispositivo. Adobe ha creato alcuni <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm"> JavaScript unificati </a> che è possibile inserire nel sito web per raccogliere questi cookie al fine di utilizzarli per le richieste di Privacy dei dati. </p> <p>Anche gli utenti dell’SDK di Adobe Analytics per dispositivi mobili hanno un Experience Cloud ID (ECID). L’SDK contiene delle chiamate API per leggere questo ID, in modo che l’app possa raccoglierlo per una richiesta di Privacy dei dati. </p> <p>Molte aziende considerano gli ID cookie del browser come ID di dispositivi condivisi. Di conseguenza, consultando il proprio team legale, è possibile che si decida di non supportarne l’uso come ID accettabili per le richieste di Privacy dei dati o di restituire solo una quantità molto limitata di dati in cui sono usati questi ID o di accettarli solo per le richieste di cancellazione. </p> <p>Questi cookie hanno un’etichetta ID-DEVICE che non può essere modificata (così come le etichette I2 e DEL-DEVICE). La configurazione predefinita di Adobe Analytics restituisce solo informazioni generiche sul dispositivo, come il tipo di dispositivo, il sistema operativo, il browser, ecc. inoltre, l’ora o le date visitate dal sito Web quando utilizzate questi ID. Tuttavia, se si sceglie di supportare questi ID per le richieste di Privacy dei dati, come spiegato di seguito, è possibile aggiungere o rimuovere le etichette ACC-ALL per configurare l’esatto insieme di campi che si desidera restituire per una richiesta di accesso di Privacy dei dati. </p> <p>Soprattutto se la suite di rapporti corrisponde a un’app mobile che richiede l’accesso, puoi decidere che l’Experience Cloud ID per il dispositivo corrisponda a un utente specifico e pertanto è consigliabile etichettare altri campi con ACC-ALL, tra cui i nomi delle pagine visitate, i prodotti visualizzati e così via. </p> <p>Nota: se specifichi l’opzione “expandIds” nella richiesta di Privacy dei dati, le richieste includeranno sempre gli ID cookie, oltre ad altri ID specificati dall’utente. Per altre informazioni consulta la parte relativa all’<a href="/help/admin/c-data-governance/gdpr-id-expansion.md">espansione dell’ID </a>. In questi casi, gli hit che hanno solo un cookie ID, ma non un altro ID, restituiranno solo i dati etichettati ACC-ALL come parte della richiesta di accesso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID nelle variabili personalizzate </p> </td> 
   <td colname="col2"> <p>Alcuni clienti inseriscono gli ID nelle <a href="https://marketing.adobe.com/resources/help/it_IT/sc/implement/props_eVars.html">variabili di traffico personalizzate (proprietà) o nelle variabili di conversione personalizzate (eVars)</a>. Sebbene il più comune sia un ID CRM, gli altri includono indirizzi e-mail, nomi di login degli utenti, numeri di fidelizzazione dei clienti o hash di questi valori. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Se desideri usare uno di questi ID per le richieste di Privacy dei dati, devi assegnare al campo che lo contiene un’etichetta ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Caso molto meno comune) Se un ID in una di queste variabili personalizzate definisce solo un dispositivo che può essere condiviso tra più persone, puoi utilizzare un’etichetta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Questi campi richiedono anche etichette I1 o I2 e devono includere un'etichetta DEL-PERSON o DEL-DISPOSITIVO. In genere, l'opzione PERSONA/DISPOSITIVO dell'etichetta DEL corrisponderà all'opzione PERSONA/DISPOSITIVO dell'etichetta ID. </li> 
    </ul> <p> Raramente la suite di rapporti ha più di una o due variabili personalizzate contenenti gli ID che si desidera utilizzare per identificare i dati interessati per le richieste di Privacy dei dati. Potete avere più variabili a cui sono assegnate etichette I1 o I2, ma in genere solo una o due di queste dispone anche di etichette ID-PERSON o ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col2"> <p>Anche se questo non è ampiamente utilizzato, Analytics supporta anche un'implementazione in cui è possibile fornire un ID visitatore personalizzato, che se presente viene utilizzato al posto del cookie legacy di tracciamento di Analytics. Questo campo contiene le etichette I2, ID-PERSON e DEL-PERSON. </p> <p>Molte implementazioni derivano questo ID da un ID CRM, quindi è presente solo quando qualcuno ha eseguito l'accesso al proprio sito. Questo consente l'utilizzo dello stesso ID visitatore personalizzato tra dispositivi. Uno svantaggio tecnico è rappresentato dal fatto che il tracciamento che si verifica prima dell'accesso dell'utente non può essere legato al tracciamento raccolto dopo l'accesso. Se invece utilizzate l’ID visitatore personalizzato per identificare semplicemente un dispositivo, dovete modificare le etichette ID-PERSON e DEL-PERSON rispettivamente in ID-DISPOSITIVO e DEL-DISPOSITIVO. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tecniche consigliate per l’impostazione delle etichette di cancellazione {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE] Le proprietà sono sempre senza distinzione tra maiuscole e minuscole. Le eVars distinguono tra maiuscole e minuscole per impostazione predefinita, ma non possono essere configurate nell’Assistenza clienti di Adobe affinché distinguano tra maiuscole e minuscole. Se possiedi un’eVar che distingue tra maiuscole e minuscole e che contiene un ID, è tua responsabilità usare la maiuscola/minuscola, in base al caso, quando invii una richiesta di Privacy dei dati, in modo che l’uso della maiuscola/minuscola nella richiesta corrisponda all’uso della maiuscola/minuscola nei risultati contenenti questi ID.

Le etichette di cancellazione DEL-DEVICE e DEL-PERSON devono essere usate con moderazione. Quando applicati a una variabile che non contiene un ID usata come parte della richiesta di Privacy dei dati, i conteggi (metriche) nei rapporti cronologici di Analytics cambieranno quasi sempre.

* Si consiglia di applicare una di queste etichette a una variabile con etichetta I1, I2 o S1. Non può essere applicata a una qualsiasi variabile che non abbia l’etichetta I1, I2 o S1.
* Le etichette DEL- risulteranno [anonime](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) in queste variabili (l’ID verrà sostituito da una stringa casuale con prefisso “Privacy dei dati-”). Lo stesso valore anonimo sostituirà tutte le istanze del valore originale in tutti gli hit identificati da un ID utilizzato nella richiesta. Se il valore originale in questo campo era uno di questi ID, le metriche del rapporto non verranno modificate.
* In genere, se un campo ha l’etichetta ID-DISPOSITIVO, è necessario assegnare anche l’etichetta DEL-DISPOSITIVO.
* Allo stesso modo, se un campo ha l’etichetta ID-PERSON, devi anche assegnare l’etichetta DEL-PERSON.
* Se un campo non ha un&#39;etichetta ID, ma contiene informazioni identificabili che vuoi rendere anonime, l&#39;etichetta più appropriata da usare (DEVICE o PERSON) dipende dall&#39;implementazione. Se usi solo ID cookie per le richieste di Privacy dei dati, devi usare DEL-DEVICE.
* Se utilizzi ID personalizzati su un campo diverso con un’etichetta ID-PERSONA e vuoi che sia cancellato solo sulle righe in cui si trova l’ID, usa DEL-PERSON.
* Se utilizzi l’espansione ID e vuoi che tutti i valori siano cancellati per tutti gli hit su tutti i dispositivi identificati, usa IL-DISPOSITIVO. Puoi applicare sia le etichette DEL-DISPOSITIVO che DEL-PERSON in questo caso, se preferisci, ma l&#39;etichetta DEL-PERSON non è necessaria, perché l&#39;espansione ID indica che tutte le righe che corrispondono a un ID persona corrisponderanno anche a un ID dispositivo.
* Se non specificherai per utilizzare l&#39;espansione ID, ma utilizzerai un insieme di ID dispositivo e persona per richieste diverse, potresti voler specificare sia le etichette DEL-DISPOSITIVO che DEL-PERSONA per le variabili che devono essere eliminate quando si utilizza uno dei due tipi di ID.
* Nota che se un&#39;etichetta DEL-DEVICE o DEL-PERSON viene specificata per una variabile che non viene usata come ID per la richiesta (incluso un ID esteso), i valori univoci in quella variabile verranno resi anonimi solo nei risultati in cui si trova un ID specifico (o esteso). Se altri risultati contengono lo stesso valore, questo non verrà aggiornato nelle altre posizioni. Ciò può comportare la modifica dei conteggi (metriche).

   Ad esempio, se tre risultati contengono il valore “foo” in eVar7, ma solo uno di essi contiene anche un ID in una variabile diversa che corrisponde a una cancellazione, il valore “foo” in quei risultati verrà modificato in un valore simile a “Privacy dei dati-123456789”, mentre rimarrà invariato negli altri due risultati. Un rapporto che mostra il numero di valori univoci per eVar7 mostrerà ora anche un altro valore univoco. Un rapporto che mostra i valori più importanti per eVars può includere il valore “foo” con due sole istanze (invece delle 3 precedenti). Anche il nuovo valore verrà visualizzato con una sola istanza.

## Tecniche consigliate per l&#39;impostazione delle etichette di accesso  {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Sebbene pochissimi campi avranno un’etichetta diversa, in molti campi spesso saranno presenti le etichette ACC. Il tipo di etichetta di accesso adeguato dipende dagli ID usati per le richieste di Privacy dei dati.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Se usi... </th> 
   <th colname="col2" class="entry"> ...utilizza queste raccomandazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Solo ID dispositivo </p> </td> 
   <td colname="col2"> <p>Se gli unici ID utilizzati sono quelli dei cookie o quelli con un'etichetta ID-DEVICE, è consigliabile utilizzare solo l'etichetta ACC-ALL. </p> <p>Per ogni richiesta di accesso riceverete una coppia di file, una contenente una riga per ogni hit corrispondente con tutti i campi ACC-ALL specificati e una seconda contenente un riepilogo di questi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID persona senza espansione ID </p> </td> 
   <td colname="col2"> <p>Se utilizzi solo ID personalizzati con l’etichetta ID-PERSON e non stai eseguendo l’espansione ID, devi usare etichette ACC-PERSON. Tuttavia, non è necessario modificare le etichette ACC-ALL predefinite; questi campi verranno inclusi automaticamente nella richiesta di accesso. </p> <p>Per ogni richiesta di accesso riceverete una coppia di file, una contenente una riga per ogni hit corrispondente con tutti i campi ACC-DEVICE e ACC-PERSON specificati e una seconda contenente un riepilogo di questi dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID misti e/o espansione dell’ID </p> </td> 
   <td colname="col2"> <p>Se nelle richieste di Privacy dei dati includi sia gli ID persona che visitatore, o se usi gli ID personalizzati (ID visitatore personalizzato o un ID in una proprietà o in un’eVar), devi fare attenzione alle etichette ACC usate. Ogni richiesta di accesso restituirà due coppie di file di dati, una coppia con i dati dei risultati che contenevano un ID persona corrispondente e una seconda coppia con i dati dei risultati che non corrispondevano a un ID persona, ma a un ID dispositivo. </p> <p>I file "ID persona" contengono dati su tutti gli hit che corrispondono agli ID persona con tutti i campi che hanno un’etichetta ACC-PERSON o ACC-ALL (un file con tutti gli hit associati e l’altro come riepilogo). </p> <p>La coppia di file "ID dispositivo" contiene solo campi che hanno un'etichetta ACC-ALL e contiene solo risultati che non contengono ID persona corrispondenti. Questi file possono contenere dati generati da altri utenti di un dispositivo condiviso, pertanto è consigliabile considerare attentamente il set di campi che contengono l'etichetta ACC-ALL. L'etichetta predefinita in Analytics applica questa etichetta solo ai campi di informazioni generici relativi al dispositivo (tipo di dispositivo, sistema operativo, browser, ecc.) più la data/ora di ogni hit. </p> <p>È possibile scegliere di ricevere sia il set di file del dispositivo che il set di file delle persone da Adobe e quindi condividere solo i file delle persone, in modo da non condividere i dati potenzialmente generati da altri utenti di un dispositivo condiviso. In alternativa, è possibile combinare i dati di uno o entrambi i set con altre informazioni relative all'oggetto e restituirli nel proprio formato. </p> </td> 
  </tr> 
 </tbody> 
</table>

