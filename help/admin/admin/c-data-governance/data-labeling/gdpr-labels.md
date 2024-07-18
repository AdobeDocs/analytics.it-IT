---
description: Esempi di etichette sulla privacy dei dati per variabili Adobe Analytics
title: Etichette Privacy dei dati per le variabili di Analytics
feature: Data Governance
role: Admin
exl-id: b8c2143a-6e8e-465a-979b-aa8176e8d4e8
source-git-commit: 79f650a7168e0cc44194445f3164a3f981e39a91
workflow-type: tm+mt
source-wordcount: '3532'
ht-degree: 74%

---

# Etichette Privacy dei dati per le variabili di Analytics

## Perché etichettare i dati? {#why-label}

I clienti di Adobe, in qualità di titolari del trattamento dei dati, sono responsabili del rispetto delle leggi sulla Privacy dei dati applicabili, come GDPR e CCPA. I clienti devono consultare il proprio team legale per determinare come devono essere gestiti i propri dati in conformità con le leggi sulla Privacy dei dati. Adobe Adobe è consapevole del fatto che ciascuno dei suoi clienti ha esigenze specifiche in materia di privacy, ed è per questo che consente ai suoi clienti di personalizzare le impostazioni desiderate per l’elaborazione dei dati in questo ambito. Questo consente a ogni singolo cliente di elaborare le richieste di Privacy dei dati nella maniera più adatta al proprio marchio e al proprio specifico set di dati.

Adobe Analytics offre gli strumenti necessari per etichettare i dati in base al loro stato di riservatezza e a vincoli contrattuali. Le etichette sono un passaggio importante per: (1) identificare gli interessati, (2) determinare quali dati restituire come parte di una richiesta di accesso e (3) identificare i campi di dati che devono essere eliminati come parte di una richiesta di eliminazione.

Prima di capire quali etichette applicare a determinate variabili o campi, è necessario [conoscere gli ID](/help/admin/admin/c-data-governance/data-labeling/gdpr-analytics-ids.md) che vengono acquisiti nei dati di Analytics e decidere quali usare per le richieste di Privacy dei dati.

L’implementazione Privacy dei dati in Adobe Analytics supporta le seguenti etichette per i dati di identità, i dati sensibili e la governance dei dati.

## Etichette per i dati di identità {#identity-data-labels}

Le etichette “I” per i dati di identità sono usate per organizzare in categorie i dati che possono identificare o consentono di contattare una persona specifica.

| Etichetta | Definizione | Altri requisiti |
| --- | --- | --- |
| I1 | Direttamente identificabili: dati che possono identificare specificamente o consentire il contatto diretto con un individuo, ad esempio un nome o un indirizzo e-mail. | <ul><li>Non può essere impostata negli eventi</li><li>Non può essere impostata nelle eVars Merchandising</li></ul> |
| I2 | Indirettamente identificabili: dati che possono essere usati in combinazione con altri dati per identificare o consentire il contatto diretto con una persona o un dispositivo.  Da soli non consentono l’identificazione di una persona, ma possono essere combinati con altre informazioni (che potrebbero essere o meno in tuo possesso) per identificare un individuo. Ne sono esempi il numero fedeltà di un cliente o un ID usato da un sistema CRM di un’azienda univoco per ciascun cliente. | <ul><li>Non può essere impostata negli eventi</li><li>Non può essere impostata nelle eVars Merchandising</li></ul> |

{style="table-layout:auto"}

## Etichette per i dati sensibili {#sensitive-data-labels}

Le etichette “S” per i dati sensibili vengono usate per organizzare in categorie i dati sensibili, come i dati geografici. Per identificare altri tipi di informazioni riservate, verranno introdotte etichette di dati riservati aggiuntive.

| Etichetta | Definizione |
| --- | --- |
| S1 | Dati precisi di geolocalizzazione relativi alla latitudine e alla longitudine che possono essere usati per determinare la posizione esatta di un dispositivo (entro 100 m o meno). |
| S2 | Dati di geolocalizzazione che possono essere usati per determinare un’area geografica ampiamente definita. |

{style="table-layout:auto"}

## Etichette per la governance dei dati (Privacy dei dati) {#data-governance-labels}

Le etichette per la governance dei dati consentono agli utenti di classificare i dati che riflettono considerazioni relative alla privacy e condizioni contrattuali che consentono ai clienti di Adobe di rimanere conformi alle normative e alle politiche aziendali.

### Etichette di accesso alla privacy dei dati

| Etichetta | Definizione | Altri requisiti |
| --- | --- | --- |
| None | Seleziona questa opzione se questa variabile non contiene i dati da includere nei dati restituiti all’interessato come parte di una richiesta di accesso alla Privacy dei dati. | |
| ACC-ALL | I valori in questo campo devono essere inclusi in tutte le richieste di accesso alla Privacy dei dati. Se questo risultato deriva da un dispositivo condiviso tra più individui, applicando questa etichetta, l’utente, in qualità di controllore dei dati, indica che è accettabile la condivisione dei dati in questo campo con qualsiasi individuo che abbia accesso al dispositivo condiviso. | I campi con questa etichetta devono essere restituiti per tutte le richieste di Privacy dei dati. |
| ACC-PERSON | I valori in questo campo devono essere inclusi solo per le richieste di accesso Privacy dei dati quando si è ragionevolmente certi che l’hit provenga dall’interessato, come determinato da un ID di richiesta Privacy dei dati che corrisponde al valore di un campo ID-PERSON. | Inoltre, è necessario disporre di un’etichetta ID-PERSON impostata su alcune variabili in questa suite di rapporti e inviare richieste con tale ID, altrimenti l’etichetta non verrà mai applicata. |

{style="table-layout:auto"}

Si prevede che per molte variabili verranno applicate le etichette di accesso, mentre alcune variabili riceveranno altre etichette. Tuttavia, spetta a te, in consultazione con il tuo team legale, decidere quali dati hai raccolto devono essere condivisi con gli interessati.

### Etichette di cancellazione Privacy dei dati

Diversamente dalle altre etichette, le etichette di cancellazione non si escludono a vicenda. Puoi selezionarne una, entrambe o nessuna. Non è necessaria un’etichetta [!UICONTROL None] distinta, perché [!UICONTROL None] viene indicata automaticamente non selezionando alcuna delle opzioni di cancellazione.

L’etichetta Elimina è necessaria solo per i campi che contengono un valore che consentirebbe l’associazione di un hit all’interessato (ovvero che consentirebbe l’identificazione dell’interessato). Non è necessario cancellare altre informazioni personali (preferiti, cronologia di navigazione/acquisto, condizioni di salute e così via) non deve essere eliminato poiché l’associazione con l’interessato verrà interrotta.

| Etichetta | Definizione | Altri requisiti |
| --- | --- | --- |
| DEL-DEVICE | Per le richieste di cancellazione Privacy dei dati, i valori in questo campo devono essere resi anonimi solo per le richieste in cui è presente un ID-DEVICE specifico nel risultato.  Se lo stesso valore si verifica su altri hit che non vengono eliminati, queste altre istanze non verranno modificate. Questo comporterà una modifica dei conteggi per i rapporti che elaborano conteggi univoci in questo campo. Sui dispositivi condivisi, questo può rimuovere gli identificatori per altri individui, oltre alla sola persona interessata.  I conteggi non cambiano se il campo ha anche un’etichetta ID-DEVICE e il suo valore in questo campo è stato usato come un ID per la richiesta di Privacy dei dati. | <ul><li>Richiede anche l’etichetta I1 o I2 o S1</li><li>Non può essere impostata negli eventi</li><li>Non può essere impostata nelle eVars Merchandising</li></li><li>Non può essere impostata nelle classificazioni</li><li>È necessario inviare richieste utilizzando un ID-DEVICE o impostare expandIDs su true oppure l’etichetta non verrà mai applicata.</li></ul> |
| DEL-PERSON | Per le richieste di cancellazione Privacy dei dati, i valori in questo campo devono essere resi anonimi solo per le richieste in cui è presente un ID-PERSON specifico nel risultato.  Se lo stesso valore si verifica su altri risultati che non vengono eliminati, questi altri valori non verranno modificati. Ciò comporterà la modifica dei conteggi per i rapporti che calcolano conteggi univoci in questo campo. I conteggi non cambiano se il campo ha anche un’etichetta ID-PERSON e il suo valore in questo campo è stato usato come un ID per la richiesta Privacy dei dati. | <ul><li>Richiede anche l’etichetta I1 o I2 o S1</li><li>Non può essere impostata negli eventi</li><li>Non può essere impostata nelle eVars Merchandising</li></li><li>Non può essere impostata nelle classificazioni</li><li>È necessario inviare richieste utilizzando un’etichetta ID-PERSON impostata su alcune variabili in questa suite di rapporti e inviarle con tale ID, altrimenti l’etichetta non verrà mai applicata.</li></ul> |

{style="table-layout:auto"}

### Etichette di identità Privacy dei dati

| Etichetta | Definizione | Altri requisiti |
| --- | --- | --- |
| None | Questa variabile non contiene un ID che verrà usato per le richieste di Privacy dei dati. | Devi impostare una di queste altre etichette solo se questo campo contiene un ID che userai durante l’invio delle richieste di accesso o cancellazione tramite l’[API Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=it) o l’interfaccia utente. |
| ID-DEVICE | Questo campo contiene un ID che può essere utilizzato per identificare un dispositivo per una richiesta di Privacy dei dati, ma non può distinguere tra utenti diversi di un dispositivo condiviso.  Non è necessario specificare questa etichetta per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. | Richiede anche l’etichetta I1 o I2.<ul><li>Non può essere impostata negli eventi</li><li>Non può essere impostata nelle eVars Merchandising</li><li>Non può essere impostata nelle classificazioni</li></ul> |
| ID-PERSON | Questo campo contiene un ID che può essere usato per identificare un utente autenticato (una persona specifica) per una richiesta di Privacy dei dati.  Non è necessario specificare questa etichetta per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. | <ul><li>Richiede anche l’etichetta I1 o I2.</li><li>Non può essere impostata negli eventi</li><li>Non può essere impostata nelle eVars Merchandising</li><li>Non può essere impostata nelle classificazioni</li></ul> |

{style="table-layout:auto"}

## Fornisci uno spazio dei nomi quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile {#provide-namespace}

Quando si applica un’etichetta ID-DEVICE o ID-PERSON a una variabile, viene richiesto di fornire un namespace. Puoi usare il namespace definito in precedenza o puoi definirne uno nuovo.

### Utilizza uno spazio dei nomi definito in precedenza

Se in precedenza hai assegnato un’etichetta ID ad altre variabili in una delle suite di rapporti della società di accesso, puoi selezionare uno dei namespace esistenti. È consigliabile riutilizzare lo spazio dei nomi se questa variabile contiene lo stesso tipo di ID di altre variabili già etichettate con lo spazio dei nomi e si desidera eseguire la ricerca di tutte quando si invia una richiesta.

1. Fai clic su **[!UICONTROL Select Namespace]** e seleziona un namespace esistente.
   ![](assets/namespace.png)
1. Fai clic su **[!UICONTROL Apply]**.


### Definisci un nuovo spazio dei nomi

Puoi anche definire un nuovo namespace. Nelle stringhe del namespace consigliamo di usare solo caratteri alfanumerici oltre ai caratteri trattino basso, trattino e spazio. Tutti i caratteri verranno convertiti in lettere minuscole.

1. Fai clic su **[!UICONTROL Select Namespace]** e digita il titolo namespace.

   ![](assets/namespace2.png)

1. Premi **[!UICONTROL Enter]** per aggiungere questo namespace. Solo a questo punto si attiverà il pulsante Applica.
1. Fai clic su **[!UICONTROL Apply]**.

La stringa specificata come namespace è la stessa stringa che devi usare quando invii le richieste tramite l’API Privacy dei dati come valore del parametro “namespace”. La richiesta fa quindi in modo che Adobe Analytics esegua la ricerca di tutte le variabili in tutte le suite di rapporti che condividono questo spazio dei nomi per l’ID specificato nella richiesta.

Non è necessario specificare le etichette ID-DEVICE o ID-PERSON per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. Ad esempio, se eVar1 può contenere un indirizzo e-mail e eVar2 può contenere un nome utente di accesso, ma invierai le richieste usando solo il nome utente, puoi assegnare a eVar1 le etichette I1, ACC-PERSON, DEL-PERSON, ma a eVar2 le etichette I2, ACC-PERSON, DEL-PERSON, ID-PERSON con il namespace “nome utente”. Puoi quindi inviare una richiesta con un blocco JSON della sezione utente come ad esempio:

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

È consentito usare lo stesso namespace per variabili diverse all’interno della stessa suite di rapporti. Ad esempio, alcune implementazioni personalizzate memorizzano un CRM-ID sia nella proprietà che in eVar. Se CRM-ID si trova sempre in una delle due (ad esempio l’eVar) e solo occasionalmente nell’altra (prop) e non è mai presente nella prop quando non è presente anche nell’eVar eVar, solo CRM-ID richiede un’etichetta ID e uno spazio dei nomi, perché Adobe può cercare l’ID solo in quell’eVar. Se tuttavia CRM-ID si trova a volte in una variabile e a volte nell’altra, entrambe devono avere lo stesso namespace e Adobe cercherà in entrambe le variabili la presenza dell’ID specificato come parte di una richiesta di Privacy dei dati con questo namespace. È comunque necessario disporre di etichette DEL su tutte queste variabili, in modo che il valore sia anonimo indipendentemente da dove si verifica.

Un altro esempio: è possibile che CRM-ID venga inviato a volte tramite eVar1, a volte tramite prop7. In questo caso, una regola di elaborazione copia il valore da eVar1, se esiste, in eVar3. In caso contrario, copia il valore da prop7 in eVar3. In questo scenario, eVar3 conterrà sempre l’ID CRM se noto, pertanto solo eVar3 richiede un’etichetta ID-PERSON.

>[!CAUTION]
>
>I namespace “visitorId” e “customVisitorId” sono riservati per identificare il cookie di tracciamento legacy di Analytics e l’ID visitatore del cliente Analytics. Non utilizzare questi spazi dei nomi per le variabili di traffico o conversione personalizzate.

## Tipi di variabili ed etichette per la Privacy dei dati supportate {#variable-types}

L’etichettatura Privacy dei dati riguarda quattro grandi classi di variabili di Analytics. Le diverse etichette non sono supportate da tutte le variabili. Questa tabella mostra quali variabili supportano o meno le etichette.

| Tipo di variabile | Etichette supportate | Etichette non supportate |
|--- |--- |--- |
| <ul><li>Eventi di successo personalizzati</li><li>eVar di Merchandising</li><li>Variabili con più valori (mvVars)</li><li>Variabili di gerarchia</li></ul> | <ul><li>S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>I1/I2</li>  <li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| Classificazioni | <ul><li>I1/I2, S1/S2</li><li>ACC-ALL, ACC-PERSON</li></ul> | <ul><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON</li></ul> |
| <ul><li>Variabili di traffico (prop)</li><li>Variabili commerciali (eVars non merchandising)</li></ul> | Tutte le etichette | - |
| La maggior parte delle altre variabili (*Vedere la tabella seguente per le eccezioni*) | ACC-ALL, ACC-PERSON | <ul><li>I1/I2, S1/S2</li><li>ID-DEVICE, ID-PERSON</li><li>DEL-DEVICE, DEL-PERSON)</li></ul> |

{style="table-layout:auto"}

## Variabili a cui è possibile assegnare etichette diverse da ACC-ALL/ACC-PERSON o modificarle {#variables}

<table id="table_0972910DB2D7473588F23EA47988381D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gruppo </th> 
   <th colname="col2" class="entry"> Variabili </th> 
   <th colname="col3" class="entry"> Etichette modificabili </th> 
   <th colname="col4" class="entry"> Commento </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_62FA1BAA3B9245909509566D8C03F900"> 
     <li id="li_38F7C4E18ECB42C292370713F502B8EB">Dimensioni di conversione </li> 
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">Dimensioni del traffico personalizzate </li> 
    </ul> </td> 
   <td colname="col2"> <p>Tutte, ad eccezione delle classificazioni </p> </td> 
   <td colname="col3"> <p>Tutto </p> </td> 
   <td colname="col4"> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>Variabili di traffico </p> </td> 
   <td colname="col2"> <p>Proprietà elenco </p> </td> 
   <td colname="col3"> <p>Nessuno/S1/S2 </p> </td> 
   <td colname="col4"> <p>Le prop elenco possono contenere più valori e non sono consentite come identificatori di privacy.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Classificazioni </p> </td> 
   <td colname="col3"> <p>Nessuno/I1/I2 </p> <p>Nessuno/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventi di conversione </p> </td> 
   <td colname="col2"> <p>Tutto </p> </td> 
   <td colname="col3"> <p>Nessuno/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventi e dimensioni della soluzione </p> </td> 
   <td colname="col2"> <p>Collegamento alla Activity Map, </p> <p>Pagina di Activity Map </p> </td> 
   <td colname="col3"> <p>Nessuno/I1/I2 </p> <p>Nessuno/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Le variabili possono contenere i parametri dell’URL, che possono includere dati direttamente o indirettamente identificabili. Se l’implementazione non raccoglie dati direttamente o indirettamente identificabili in queste variabili, non sono necessarie le etichette di identità o cancellazione. </p> <p>Nota che la cancellazione elimina i parametri dell’URL, ma ne conserva la base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioni di elaborazione dei dati </p> </td> 
   <td colname="col2"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col3"> <p>ID-DEVICE / ID-PERSON </p> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Non è possibile rimuovere le etichette ID o DEL (impostate su Nessuno), ma è possibile modificarle nelle varianti DEVICE o PERSON, in base all’implementazione dell’ID personalizzata. </p> <p>Se non utilizzi l’ID visitatore personalizzato, le impostazioni non hanno importanza. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Dimensioni standard </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Dimensioni di elaborazione dei dati </li> 
    </ul> </td> 
   <td colname="col2"> <p>Indirizzo IP </p> <p>Indirizzo IP 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Non puoi rimuovere l’etichetta DEL, ma puoi modificarla in DEL-DEVICE or DEL-PERSON o in entrambe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Azione ClickMap (legacy), </p> <p>Contesto ClickMap (legacy), </p> <p>Pagina, </p> <p>URL della pagina, </p> <p>URL originale della pagina iniziale, </p> <p>Referrer, </p> <p>URL di visita alla pagina iniziale </p> </td> 
   <td colname="col3"> <p>Nessuno/I1/I2 </p> <p>Nessuno/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Le variabili possono contenere i parametri dell’URL, che possono includere dati direttamente o indirettamente identificabili. Se l’implementazione non raccoglie dati direttamente o indirettamente identificabili in queste variabili, non sono necessarie le etichette di identità o cancellazione. </p> <p>Nota che la cancellazione elimina i parametri dell’URL, ma ne conserva la base. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gestione dell’eliminazione {#deletion}

Il supporto Adobe Analytics per le richieste di eliminazione Privacy dei dati è progettato per ridurre l’impatto sulla creazione di rapporti. Nella maggior parte dei casi, le metriche visualizzate nei rapporti non devono essere modificate. Un rapporto storico eseguito prima dell’eliminazione Privacy dei dati corrisponde allo stesso rapporto eseguito dopo l’eliminazione. A tal fine, i dati eliminati vengono completamente dissociati dall’interessato, lasciando invariati i dati non identificabili in modo che i valori segnalati rimangano coerenti.

La tabella seguente descrive come vengono “eliminate” molte variabili. Questo non è un elenco completo.

| Variabili | Metodo di eliminazione |
| --- | --- |
| <ul><li>Variabili di traffico (prop)</li><li>Variabili commerciali (eVars)</li></ul> | Il valore esistente è sostituito da un nuovo valore del modulo “Privacy dei dati-356396D55C4F9C7AB3FBB2F2FA223482”, in cui il valore esadecimale a 32 cifre dopo il prefisso “Privacy dei dati-” è un numero pseudo-casuale e crittograficamente sicuro di 128 bit.<p>Poiché è essenzialmente sostituito da una stringa casuale, non esiste modo di determinare il valore originale a partire da questo nuovo valore né di ricavare il nuovo valore conoscendo il valore originale.  Per una determinata variabile, se il valore identico viene sostituito all’interno di altri punti che vengono anch’essi eliminati come parte della stessa richiesta Privacy dei dati, tutte le istanze di tale valore verranno sostituite con lo stesso nuovo valore.<p>Se alcune istanze di un valore vengono sostituite con una richiesta di cancellazione e una richiesta successiva cancella altre (nuove) istanze del valore originale, il nuovo valore di sostituzione sarà diverso dal valore di sostituzione originale. |
| ID acquisto | Il valore esistente è sostituito da un nuovo valore del modulo “G-7588FCD8642718EC50”, in cui il valore esadecimale a 18 cifre dopo il prefisso “G-” è un numero di 18 cifre pseudo-casuale e crittograficamente sicuro di 128 bit. Tutti i commenti che si applicano alla cancellazione delle variabili relative al traffico e al commercio si applicano anche in questo caso.<p>Questo è un ID di transazione il cui scopo principale è quello di garantire che un acquisto non venga accreditato due volte, ad esempio quando qualcuno aggiorna la pagina di conferma dell’acquisto. L’ID stesso può spostare l’acquisto in una riga nel proprio DB in cui viene registrato l’acquisto. Nella maggior parte dei casi non è necessario cancellare questo ID, quindi non viene cancellato per impostazione predefinita.<p>Se si riesce ancora a ricollegare l’acquisto ad un utente dopo la richiesta di cancellazione Privacy dei dati dei propri dati, allora potrebbe essere necessario cancellare questo campo, in modo che i dati di Analytics per questo visitatore non possano essere legati all’acquirente. |
| Visitor ID | Il valore è un numero intero di 128 bit e viene sostituito da un valore pseudo-casuale e crittograficamente sicuro di 128 bit. |
| <ul><li>MCID</li><li>ID visitatore personalizzato</li><li>Indirizzo IP</li><li>Indirizzo IP 2 | Il valore viene cancellato (impostato sulla stringa vuota o 0 a seconda del tipo della variabile). |
| <ul><li>Azione ClickMap (legacy)</li><li>Contesto ClickMap (legacy)</li><li>Pagina</li><li>URL della pagina</li><li>URL originale della pagina iniziale</li><li>Destinatario che inoltra</li><li>URL di visita alla pagina iniziale</li></ul> | I parametri URL vengono cancellati/rimossi. Se il valore non presenta le caratteristiche di un URL, allora viene cancellato (impostato sulla stringa vuota). |
| <ul><li>Latitudine</li><li>Longitudine</li></ul> | La precisione viene ridotta a non più di 1 km. |

{style="table-layout:auto"}

## Variabili che potrebbero non supportare le etichette di eliminazione previste {#no-delete-support}

Questa sezione contiene informazioni sulle variabili di Analytics che potrebbero non supportare l’eliminazione. A volte queste variabili vengono eliminate dagli utenti non Analytics (come il team legale) che non conoscono il tipo di dati contenuti nella variabile e fanno supposizioni in base al nome della variabile.

È importante comprendere il tipo di dati contenuti in ciascuna variabile prima di prendere una decisione in merito all’etichettatura o alla cancellazione, e non basarsi esclusivamente sul nome della variabile. Di seguito è riportato un elenco di alcune di queste variabili e del perché non richiedono l’eliminazione o perché non richiedono un’etichetta di eliminazione specifica:

| Variabile | Commenti |
| --- | --- |
| [!UICONTROL New Visitor ID] | L’ID nuovo visitatore è un valore booleano che è true la prima volta che viene visualizzato un ID visitatore. Non è necessario eliminarlo una volta che l’ID visitatore è reso anonimo. Una volta reso anonimo, corrisponde alla prima volta che questo ID è stato visto anonimo. |
| [!UICONTROL Zip Code]<p>[!UICONTROL Geo Zip Code] | I codici postali vengono impostati solo per risposte provenienti dagli Stati Uniti. Non vengono impostate per risposte provenienti dall’UE. Anche se impostate, forniscono solo un’ampia area geografica che rende difficile la reidentificazione dell’interessato. |
| [!UICONTROL Geo Latitude]<p>[!UICONTROL Geo Longitude] | Forniscono una posizione approssimativa derivata dall’indirizzo IP. Di norma, la precisione è simile a quella di un codice postale, entro alcune dozzine di chilometri dalla posizione effettiva. |
| [!UICONTROL User Agent] | L’agente utente identifica la versione del browser utilizzato. |
| [!UICONTROL User ID] | Specifica la suite di rapporti Analytics (come numero) contenente i dati. |
| [!UICONTROL Report Suite ID] | Specifica il nome della suite di rapporti Analytics contenente i dati. |
| [!UICONTROL Visitor ID]<p>[!UICONTROL MCID] / [!UICONTROL ECID] | Questi ID presentano un’etichetta DEL-DEVICE, ma non è possibile aggiungere l’etichetta DEL-PERSON. Se specifichi [!UICONTROL ID Expansion] con ogni richiesta, questi ID verranno eliminati automaticamente per tutte le richieste di eliminazione, anche quelle che utilizzano un ID-PERSON.<p>Se non si utilizza l’opzione Espansione dell’ID, ma si desidera che questi ID cookie siano resi anonimi nei risultati con un ID corrispondente in un prop o in un eVar, è possibile aggirare questa limitazione di etichettatura etichettando il prop o il eVar con un’etichetta ID-DEVICE, anche se identifica effettivamente una persona (tutte le etichette DEL-PERSON devono essere sostituite dalle etichette DEL-DEVICE). In questo caso, poiché solo alcune istanze dell’ID visitatore o ECID vengono rese anonime, i conteggi univoci dei visitatori cambieranno nei rapporti storici. |
| [!UICONTROL AMO ID] | L’ID Adobe Advertising Cloud è una variabile di soluzione con un’etichetta [!UICONTROL DEL-DEVICE] non modificabile. Viene compilato da un cookie come l’ID visitatore e l’MCID. Deve essere eliminato dai risultati ogni volta che vengono eliminati altri ID. Per ulteriori informazioni, consultare la descrizione di tali variabili. |

{style="table-layout:auto"}

## Campi di dati per le richieste di accesso {#access-requests}

Esistono cinque variabili standard che contengono la marca temporale:

| Marca Temporale | Definizione |
| --- | --- |
| Ora hit (UTC) | Il momento in cui Adobe Analytics ha ricevuto il risultato. |
| Ora hit personalizzata (UTC) | Il momento in cui si è verificato il risultato, che per alcune applicazioni mobili e altre implementazioni può essere precedente al momento in cui è stato ricevuto. Ad esempio, se una connessione di rete non era disponibile in quel momento, l’applicazione potrebbe conservare il risultato e inviarlo quando la connessione è nuovamente attiva. |
| Data e ora | Stesso valore dell’Ora hit personalizzata (UTC), ma nel fuso orario della suite di rapporti, anziché GMT. |
| Ora primo hit (GMT) | Il valore Ora hit personalizzata (UTC) per il primo risultato ricevuto per il valore dell’ID visitatore. |
| Ora inizio visita (UTC) | Il valore Ora hit personalizzata (UTC) per il primo risultato ricevuto per l’attuale visita di questo ID visitatore. |

{style="table-layout:auto"}

Il codice per generare i file restituiti per le richieste di accesso privacy dei dati richiede che almeno una delle prime tre variabili di marca temporale sia inclusa nella richiesta di accesso (che quindi abbia un’etichetta ACC applicabile al tipo di richiesta). Se nessuna di queste è inclusa, allora la marca Ora hit personalizzata (UTC) sarà elaborata come se avesse etichetta ACC-ALL.

Il file CSV restituito per le richieste di accesso Privacy dei dati convertirà i valori in questi campi da marche temporali unix a campi data/ora in formato `YYYY-MM-DD HH:MM:SS` (ad esempio, `2018-05-01 13:49:22`). Nel file di riepilogo di HTML, questi valori di marca temporale verranno troncati per includere solo la data, `YYYY-MM-DD`, per ridurre il numero di valori univoci che si verificano per questi campi.
