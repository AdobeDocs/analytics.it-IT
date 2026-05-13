---
description: Comprendi gli ID acquisiti nei dati di Analytics e decidi quale utilizzare per le richieste relative alla privacy dei dati.
title: Tecniche di etichettatura consigliate
feature: Data Governance
role: Admin
exl-id: 00da58b0-d613-4caa-b9c1-421b1b541f47
TQID: https://experienceleague.adobe.com/btvouuszSZn1h7xDCInebbqYE9vb1bwcU4-DMW3l3oM
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: c77ba355-6681-41fe-b719-563d3f507fdbid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c7d04a2c-412a-4c9d-9d7a-4456eaa5adebid: eddd9b14-83bd-4ff4-9072-54a4a484abb7id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 2340
ht-degree: 38%

---

# Tecniche di etichettatura consigliate

L’etichettatura deve essere rivista ogni volta che viene creata una nuova suite di rapporti o quando viene abilitata una nuova variabile all’interno di una suite di rapporti. Potrebbe essere inoltre necessario rivedere l’etichettatura quando vengono abilitate nuove integrazioni di soluzioni, in quanto queste possono esporre nuove variabili che possono richiedere l’etichettatura. Una reimplementazione delle app mobili o dei siti web potrebbe modificare il modo in cui vengono utilizzate le variabili esistenti, e potrebbe essere necessario aggiornare le etichette.

Le etichette I1, I2, S1 e S2 hanno lo stesso significato delle corrispondenti etichette DULE in Adobe Experience Platform. Tuttavia, sono utilizzati per scopi molto diversi. In Adobe Analytics, queste etichette vengono utilizzate per identificare i campi che devono essere resi anonimi a seguito di una richiesta Privacy Service. In Adobe Experience Platform vengono utilizzati per il controllo degli accessi, la gestione del consenso e l’applicazione di restrizioni di marketing ai campi etichettati. Adobe Experience Platform supporta molte etichette aggiuntive non utilizzate da Adobe Analytics. Se utilizzi il connettore dati di Analytics per importare i dati di Adobe Analytics in Adobe Experience Platform, accertati che tutte le etichette I1, I2, S1 e S2 applicate in Adobe Analytics vengano applicate anche agli schemi in Adobe Experience Platform utilizzati dalle suite di rapporti importate.

## ID direttamente e indirettamente identificabili {#direct-vs-indirect}

Prima di capire quali etichette applicare a determinate variabili o campi, è necessario conoscere gli ID che vengono acquisiti nei dati di Analytics e decidere quali usare per le richieste di Privacy dei dati. La Privacy dei dati espande l’ambito di definizione di ID. Gli ID rientrano in due grandi classi: direttamente identificabili (etichetta di identità: I1) e indirettamente identificabili (etichetta di identità: I2).

* **ID direttamente identificabile (I1)**: indica il nome della persona o fornisce un metodo diretto per contattarla. Alcuni esempi includono il nome di un utente (anche un nome comune come John Smith che può essere condiviso da centinaia di persone), qualsiasi indirizzo e-mail o numero di telefono, ecc. Un indirizzo postale senza un nome potrebbe essere considerato direttamente identificabile, anche se può identificare solo una famiglia o un’azienda piuttosto che una persona specifica all’interno di tale famiglia o azienda.
* **ID indirettamente identificabile (I2)**: non consente l&#39;identificazione di un individuo in sé, ma può essere combinato con altre informazioni (che possono essere o meno in tuo possesso), per identificare qualcuno. Esempi di ID indirettamente identificabili includono un numero di fedeltà di un cliente o un ID utilizzato dal sistema di gestione delle relazioni con i clienti di un’azienda che è univoco per ciascuno dei suoi clienti. In base alla Privacy dei dati, gli ID anonimi memorizzati nei cookie di monitoraggio usati da Analytics possono essere considerati identificativi indiretti, sebbene possano individuare solo un dispositivo invece di una persona; su un dispositivo condiviso, questi cookie non distinguono i diversi utenti del sistema. Ad esempio, anche se il cookie non può essere utilizzato per trovare un computer contenente il cookie, se un utente ha accesso al computer e individua il cookie, può ricollegare i dati del cookie di Analytics al computer.

Un indirizzo IP è anche considerato indirettamente identificabile, perché in un dato momento potrebbe essere assegnato a un solo dispositivo. Tuttavia, gli ISP possono e spesso modificano regolarmente gli indirizzi IP per la maggior parte degli utenti, quindi nel tempo un indirizzo IP potrebbe essere stato utilizzato da uno qualsiasi dei loro utenti. Inoltre, non è raro che molti clienti di un ISP o più dipendenti all’interno di un’azienda sulla stessa Intranet condividano lo stesso indirizzo IP esterno. Per questo motivo, Adobe non supporta l’utilizzo di un indirizzo IP come ID per una richiesta di Privacy dei dati. Tuttavia, quando un ID accettato viene utilizzato come parte di una richiesta di cancellazione, verranno cancellati anche gli indirizzi IP in cui era presente quell’ID. Devi decidere se esistono altri ID raccolti che possono rientrare in questa categoria, I1 o I2, ma che non sono idonei a essere utilizzati come ID distintivi per le richieste di Privacy dei dati.

Anche se l’azienda raccoglie molti ID diversi nei dati di Analytics, puoi scegliere di usare solo un sottoinsieme di questi ID per le richieste di Privacy dei dati. Questo può essere dovuto a:

* All’interno dei tuoi sistemi, puoi mappare uno degli ID (ad esempio, l’indirizzo e-mail) su un ID diverso (ad esempio, l’ID CRM). Successivamente, per coerenza, decidi di usare solo l’ID CRM per le richieste di Privacy dei dati nell’elaborazione della Privacy dei dati.
* Non si dispone di un metodo per verificare che una persona sia effettivamente la persona associata all’ID. Ad esempio, può essere molto difficile verificare che un indirizzo IP sia mai stato utilizzato da una sola persona e che la persona che presenta la richiesta sia effettivamente tale persona.
* Alcuni ID possono corrispondere a più persone e non si desidera rischiare di restituire informazioni su una persona a un&#39;altra persona con lo stesso ID. Ad esempio, anche se è possibile verificare che il nome di un utente sia John Smith, è possibile che non si desideri restituire tutti i dati relativi a tutti i John Smith nel sistema.
* Un altro esempio è un ID dispositivo, come l’ID cookie di Analytics. Se l’ID si verifica in un’app di telefonia cellulare, puoi decidere che tutte le interazioni che utilizzano tale ID siano disponibili per il proprietario del telefono cellulare. Tuttavia, se si verifica su un dispositivo condiviso, ad esempio un computer di casa o uno in una libreria o un internet cafè, è possibile decidere di non poter distinguere tra gli utenti di tale dispositivo e il rischio di restituire dati per un altro utente è troppo elevato per consentire l’utilizzo di questo tipo di ID.

## Best practice per gli ID supportati da Analytics {#best-practices-an}

Usa questa tabella per determinare i tipi di ID che userai durante l’invio delle richieste di Privacy dei dati ad Analytics. Una volta acquisite queste informazioni, sarà più semplice determinare le altre etichette da utilizzare per le variabili.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di ID </th> 
   <th colname="col2" class="entry"> Raccomandazioni </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID cookie </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-privacy.html?lang=it">(Legacy) Cookie di Analytics</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it"> Cookie del servizio Identity </a> (ECID), noto in precedenza come Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Questi cookie identificano un dispositivo o, più specificamente, un browser per l’utente di un dispositivo. Per un dispositivo condiviso in cui viene utilizzato un accesso comune, questo ID può essere applicato a uno o a tutti gli utenti del dispositivo. Adobe ha creato alcuni <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service/"> JavaScript unificati </a> che è possibile inserire nel sito web per raccogliere questi cookie al fine di utilizzarli per le richieste di Privacy dei dati. </p> <p>Anche gli utenti dell’SDK di Adobe Analytics per dispositivi mobili hanno un Experience Cloud ID (ECID). L’SDK contiene delle chiamate API per leggere questo ID, in modo che l’app possa raccoglierlo per una richiesta di Privacy dei dati. </p> <p>Molte aziende considerano gli ID cookie del browser come ID di dispositivi condivisi. Di conseguenza, consultando il proprio team legale, è possibile che decida di non supportarne l’utilizzo come ID accettabili per le richieste di Privacy dei dati. In alternativa, possono scegliere di restituire solo una quantità molto limitata di dati quando vengono utilizzati questi ID o possono accettarli solo per le richieste di cancellazione. </p> <p>Questi cookie hanno un’etichetta ID-DEVICE che non può essere modificata (così come le etichette I2 e DEL-DEVICE). La configurazione predefinita di Adobe Analytics restituirà solo informazioni generiche sul dispositivo, come tipo di dispositivo, sistema operativo, browser e così via, oltre all’ora/date in cui il sito web è stato visitato durante l’utilizzo di questi ID. Tuttavia, se si sceglie di supportare questi ID per le richieste di Privacy dei dati, come spiegato di seguito, è possibile aggiungere o rimuovere le etichette ACC-ALL per configurare l’esatto insieme di campi che si desidera restituire per una richiesta di accesso di Privacy dei dati. </p> <p>Se la suite di rapporti corrisponde a un’app mobile che richiede l’accesso, puoi decidere che l’Experience Cloud ID per il dispositivo corrisponda a un utente specifico. In tal caso, potrebbe essere utile etichettare altri campi con ACC-ALL, tra cui i nomi delle pagine visitate, i prodotti visualizzati e così via. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID nelle variabili personalizzate </p> </td> 
   <td colname="col2"> <p>Alcuni clienti inseriscono gli ID nelle <a href="/help/implement/vars/page-vars/evar.md">variabili di traffico personalizzate (proprietà) o nelle variabili di conversione personalizzate (eVars)</a>. Sebbene il più comune sia un ID CRM, gli altri includono indirizzi e-mail, nomi di login degli utenti, numeri di fidelizzazione dei clienti o hash di questi valori. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Se desideri usare uno di questi ID per le richieste di Privacy dei dati, devi assegnare al campo che lo contiene un’etichetta ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Caso molto meno comune) Se un ID in una di queste variabili personalizzate definisce solo un dispositivo che può essere condiviso tra più persone, puoi utilizzare un’etichetta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Questi campi richiedono anche etichette I1 o I2 e devono includere un’etichetta DEL-PERSON o DEL-DEVICE. In genere, l’opzione PERSON/DEVICE dell’etichetta DEL corrisponde all’opzione PERSON/DEVICE dell’etichetta ID. </li> 
    </ul> <p> Raramente una suite di rapporti ha più di una o due variabili personalizzate contenenti gli ID che desideri utilizzare per identificare gli interessati per le richieste di Privacy dei dati. Potresti avere più variabili a cui sono assegnate etichette I1 o I2, ma in genere solo una o due di queste avrebbero anche le etichette ID-PERSON o ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col2"> <p>Anche se questo non è ampiamente utilizzato, Analytics supporta anche un’implementazione in cui è possibile fornire un ID visitatore personalizzato che, se presente, viene utilizzato al posto del cookie di tracciamento legacy di Analytics. Questo campo contiene le etichette I2, ID-PERSON e DEL-PERSON. </p> <p>Molte implementazioni derivano questo ID da un ID del sistema di gestione delle relazioni con i clienti in modo che sia presente solo quando qualcuno è connesso al proprio sito. Questo consente di utilizzare lo stesso ID visitatore personalizzato tra i dispositivi. Uno svantaggio tecnico è che il tracciamento che si verifica prima dell’accesso dell’utente non può essere associato al tracciamento raccolto dopo l’accesso. Se invece utilizzi l’ID visitatore personalizzato per identificare semplicemente un dispositivo, devi cambiare le etichette ID-PERSON e DEL- PERSON rispettivamente in ID-DEVICE e DEL- DEVICE. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Tecniche consigliate per l’impostazione delle etichette di eliminazione {#best-practices-delete}

>[!NOTE]
>
>Le proprietà distinguono sempre tra maiuscole e minuscole. Le eVars distinguono tra maiuscole e minuscole per impostazione predefinita, ma non possono essere configurate nell’Assistenza clienti di Adobe affinché distinguano tra maiuscole e minuscole. Se possiedi un’eVar che distingue tra maiuscole e minuscole e che contiene un ID, è tua responsabilità usare la maiuscola/minuscola, in base al caso, quando invii una richiesta di Privacy dei dati, in modo che l’uso della maiuscola/minuscola nella richiesta corrisponda all’uso della maiuscola/minuscola nei risultati contenenti questi ID.

Le etichette di cancellazione DEL-DEVICE e DEL-PERSON devono essere usate con moderazione. Quando applicati a una variabile che non contiene un ID usata come parte della richiesta di Privacy dei dati, i conteggi (metriche) nei rapporti cronologici di Analytics cambieranno quasi sempre.

* Si consiglia di applicare una di queste etichette a una variabile con etichetta I1, I2 o S1. Non può essere applicata a una qualsiasi variabile che non abbia l’etichetta I1, I2 o S1.
* Le etichette DEL- risulteranno [anonime](/help/admin/tools/privacy-labeling/labels.md#data-governance-labels) in queste variabili (l’ID verrà sostituito da una stringa casuale con prefisso “Privacy dei dati-”). Lo stesso valore anonimizzato sostituirà tutte le istanze del valore originale in tutti gli hit identificati da un ID utilizzato nella richiesta. Se il valore originale in questo campo era uno di questi ID, le metriche del rapporto non cambieranno.
* In genere, se un campo ha l’etichetta ID-DEVICE, devi assegnare anche l’etichetta DEL-DEVICE.
* Allo stesso modo, se un campo ha l’etichetta ID-PERSON, devi assegnare anche l’etichetta DEL-PERSON.
* Se un campo non ha un&#39;etichetta ID, ma contiene informazioni identificabili che vuoi rendere anonime, l&#39;etichetta più appropriata da usare (DEVICE o PERSON) dipende dall&#39;implementazione. Se usi solo ID cookie per le richieste di Privacy dei dati, devi usare DEL-DEVICE.
* Se utilizzi ID personalizzati in un campo diverso con un’etichetta ID-PERSON e desideri cancellarli solo nelle righe in cui si trova l’ID, utilizza DEL-PERSON.
* Nota che se un&#39;etichetta DEL-DEVICE o DEL-PERSON viene specificata per una variabile che non viene usata come ID per la richiesta (incluso un ID esteso), i valori univoci in quella variabile verranno resi anonimi solo nei risultati in cui si trova un ID specifico (o esteso). Se altri risultati contengono lo stesso valore, questo non verrà aggiornato nelle altre posizioni. Questo può comportare la modifica dei conteggi (metriche).

  Ad esempio, se tre risultati contengono il valore “foo” in eVar7, ma solo uno di essi contiene anche un ID in una variabile diversa che corrisponde a una cancellazione, il valore “foo” in quei risultati verrà modificato in un valore simile a “Privacy dei dati-123456789”, mentre rimarrà invariato negli altri due risultati. Un rapporto che mostra il numero di valori univoci per eVar7 mostrerà ora anche un altro valore univoco. Un rapporto che mostra i valori più importanti per eVars può includere il valore “foo” con due sole istanze (invece delle 3 precedenti). Anche il nuovo valore verrà visualizzato con una sola istanza.

## Tecniche consigliate per l&#39;impostazione delle etichette di accesso {#best-practices-access}

Sebbene pochissimi campi avranno un’etichetta diversa, in molti campi spesso saranno presenti le etichette ACC. Il tipo di etichetta di accesso adeguato dipende dagli ID usati per le richieste di Privacy dei dati.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Versione utilizzata </th> 
   <th colname="col2" class="entry"> ...utilizza questi consigli </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Solo ID dispositivo </p> </td> 
   <td colname="col2"> <p>Se gli unici ID che utilizzi sono gli ID cookie o quelli con un'etichetta ID-DEVICE, devi usare solo l'etichetta ACC-ALL. </p> <p>Riceverai una coppia di file per ogni richiesta di accesso: un file contenente una riga per ogni hit corrispondente con tutti i campi ACC-ALL specificati e un file di riepilogo contenente un riepilogo di questi dati. </p> </td> 
  </tr> 
 </tbody> 
</table>
