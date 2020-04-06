---
description: 'null'
title: Etichette Privacy dei dati per le variabili di Analytics
uuid: a37a1278-7a0d-4e14-ae35-43bc460e7d12
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Etichette Privacy dei dati per le variabili di Analytics

## Perché etichettare i dati? {#section_A075CDF3AD0744BD8CEB41CE3FB7BFB3}

Molti clienti Adobe dispongono di team legali che hanno rivisto le normative sulla Privacy dei dati (RGPD, CCPA, ecc.) e che hanno tratto le proprie conclusioni sul modo in cui i dati devono essere trattati per conformarsi a tali normative. Le interpretazioni giuridiche possono essere diverse in base alle aziende e anche le impostazioni di gestione dei dati desiderate possono differire tra i clienti. Poiché i clienti hanno preferenze diverse per quanto riguarda il trattamento dei dati in termini di privacy e diversi set di dati, in Adobe i clienti, in qualità di titolari dei dati, possono personalizzare le impostazioni desiderate per il trattamento dei propri dati in base alla Privacy dei dati. Questo consente a ogni singolo cliente di elaborare le richieste di Privacy dei dati nella maniera più adatta al proprio marchio e al proprio set di dati.

Adobe Analytics offre strumenti per l’etichettatura dei dati in base alla sensibilità e alle limitazioni contrattuali. Le etichette sono importanti e utili per aiutare: (1) identificare gli interessati, (2) determinare quali dati restituire come parte di una richiesta di accesso e (3) identificare i campi di dati che devono essere eliminati come parte di una richiesta di eliminazione.

Prima di capire quali etichette applicare a determinate variabili o campi, è necessario [conoscere gli ID](/help/admin/c-data-governance/gdpr-analytics-ids.md) che vengono acquisiti nei dati di Analytics e decidere quali usare per le richieste di Privacy dei dati.

L’implementazione Privacy dei dati in Adobe Analytics supporta le seguenti etichette per i dati di identità, i dati sensibili e la governance dei dati.

## Etichette DULE  {#section_B2E78130957647338495EF37DE21D6BC}

>[!NOTE] Il framework DULE (Data Usage Labeling &amp; Enforcement, etichettatura e applicazione per l’uso dei dati) è progettato per fornire un metodo uniforme per tutte le soluzioni, i servizi e le piattaforme di Adobe al fine di acquisire, comunicare e usare i metadati sui dati in Adobe Experience Cloud. I metadati consentono ai titolari del trattamento di indicare i dati che si riferiscono a informazioni personali, dati sensibili e vincoli di contratto associati a questi. In questa versione iniziale Analytics espone solo le etichette DULE pertinenti alla Privacy dei dati. Poiché altri prodotti Adobe implementano il supporto per le etichette DULE, le versioni future introdurranno altre etichette per i dati sensibili, nonché etichette contrattuali che garantiranno che i dati condivisi tra i prodotti verranno usati solo nei modi consentiti dalla legge.

## Etichette per i dati di identità (DULE)  {#identity-data-labels}

Le etichette dei dati di identità &quot;I&quot; vengono utilizzate per classificare i dati in grado di identificare o contattare una persona specifica.

<table id="table_6B5368D714424E52835D5DFE189BD080"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Altri requisiti </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>I1 </p> </td> 
   <td colname="col2"> <p><b>Direttamente identificabile</b>: Dati in grado di identificare o abilitare specificamente il contatto diretto con un individuo, ad esempio un nome o un indirizzo e-mail. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">Impossibile impostare gli eventi </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">Impossibile impostare su eVar di merchandising </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>Indirettamente identificabili</b>: Dati che possono essere utilizzati in combinazione con qualsiasi altro dato per identificare o abilitare il contatto diretto con un individuo o un dispositivo. </p> <p>Non consente l'identificazione di un individuo da solo, ma può essere combinato con altre informazioni (che potrebbero o meno essere in tuo possesso) per identificare qualcuno. Alcuni esempi includono un numero di fedeltà del cliente o un ID utilizzato dal sistema CRM di una società, univoco per ogni cliente. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">Impossibile impostare gli eventi </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">Impossibile impostare su eVar di merchandising </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Etichette per i dati sensibili (DULE)  {#sensitive-data-labels}

Le etichette dei dati sensibili &quot;S&quot; vengono utilizzate per classificare i dati sensibili, ad esempio i dati geografici. In futuro verranno introdotte etichette dati sensibili aggiuntive per identificare altri tipi di informazioni sensibili.

<table id="table_A778A508620545CCB37830E5CF1C75B7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>S1 </p> </td> 
   <td colname="col2"> <p> Dati di geolocalizzazione precisi relativi a latitudine e longitudine che possono essere utilizzati per determinare la posizione esatta di un dispositivo (entro 100 metri o meno). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> I dati di geolocalizzazione che possono essere utilizzati per determinare un'area di geofencing definita in senso ampio. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Etichette per la governance dei dati (Privacy dei dati) {#data-governance-labels}

Le etichette per la governance dei dati consentono agli utenti di classificare i dati che riflettono considerazioni relative alla privacy e condizioni contrattuali conformi alle norme e ai criteri aziendali.

**Etichette di accesso alla privacy dei dati**

<table id="table_663EFF43A454498386F7F3E60875E0F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Altri requisiti </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>None </p> </td> 
   <td colname="col2"> <p>Seleziona questa opzione se questa variabile non contiene i dati da includere nei dati restituiti alla persona interessata come parte di una richiesta di accesso alla Privacy dei dati. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-ALL </p> </td> 
   <td colname="col2"> <p>I valori in questo campo devono essere inclusi in <u>tutte</u> le richieste di accesso alla Privacy dei dati. </p> <p>Se questo risultato deriva da un dispositivo condiviso tra più individui, applicando questa etichetta, l’utente, in qualità di controllore dei dati, indica che è accettabile la condivisione dei dati in questo campo con qualsiasi individuo che abbia accesso al dispositivo condiviso. </p> </td> 
   <td colname="col3"> <p>I campi con questa etichetta devono essere restituiti per tutte le richieste di Privacy dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ACC-PERSON </p> </td> 
   <td colname="col2"> <p> I valori in questo campo devono essere inclusi solo per le richieste di accesso alla Privacy dei dati quando si è sufficientemente certi che il risultato derivi da una persona interessata, perché determinato dalla corrispondenza tra l’ID di una richiesta di Privacy dei dati e un valore del campo ID-PERSON. </p> </td> 
   <td colname="col3"> <p>Devi anche avere un'etichetta ID-PERSONA impostata su alcune variabili all'interno di questa suite di rapporti e inviare le richieste utilizzando quell'ID, altrimenti l'etichetta non verrà mai applicata. </p> </td> 
  </tr> 
 </tbody> 
</table>

Si prevede che per molte variabili verranno applicate le etichette di accesso, mentre alcune variabili riceveranno altre etichette. Tuttavia, spetta a voi, in consultazione con il team legale, decidere quali dati avete raccolto devono essere condivisi con gli interessati.

**Etichette di cancellazione della privacy dati**

<table id="table_59DFCE4D90214CB5972BDDE5B7391B4D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Altri requisiti </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> </td> 
   <td colname="col2"> <p>Diversamente dalle altre etichette, le etichette di cancellazione non si escludono a vicenda. Puoi selezionarne una, entrambe o nessuna. Non è necessaria un'etichetta Nessuno separata, perché Nessuno è indicato semplicemente non selezionando nessuna delle opzioni Elimina. </p> </td> 
   <td colname="col3"> <p>Un'etichetta di eliminazione è necessaria solo per i campi che contengono un valore che consentirebbe l'associazione di un hit all'oggetto dati (ovvero che consentirebbe l'identificazione dell'oggetto dati). </p> <p> Non è necessario cancellare altre informazioni personali (preferiti, cronologia di navigazione/acquisto, condizioni di salute e così via) non è necessario eliminarlo perché l'associazione con l'oggetto dati verrà interrotta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL DISPOSITIVO </p> </td> 
   <td colname="col2"> <p>Per le richieste di cancellazione Privacy dei dati, i valori in questo campo devono essere resi anonimi solo per le richieste in cui è presente un ID-DEVICE specifico nel risultato. </p> <p>Se lo stesso valore si verifica per altri hit che non vengono eliminati, le altre istanze non verranno modificate. In questo modo i conteggi dei rapporti vengono modificati e i conteggi univoci vengono calcolati in questo campo. Sui dispositivi condivisi, questo può rimuovere identificatori per altri individui, oltre all'oggetto solo dati. </p> <p>I conteggi non cambiano se il campo ha anche un’etichetta ID-DEVICE e il suo valore in questo campo è stato usato come un ID per la richiesta di Privacy dei dati. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">Richiede anche l'etichetta I1, I2 o S1 </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">Impossibile impostare gli eventi </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">Impossibile impostare su eVar di merchandising </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">Impossibile impostare in Classificazioni </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">È necessario inviare le richieste utilizzando un ID-DEVICE o impostare espandere gli ID su true, altrimenti l'etichetta non verrà mai applicata. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>Per le richieste di cancellazione Privacy dei dati, i valori in questo campo devono essere resi anonimi solo per le richieste in cui è presente un ID-PERSON specifico nel risultato. </p> <p>Se lo stesso valore si verifica su altri hit che non vengono eliminati, questi altri valori non verranno modificati. In questo modo i conteggi dei rapporti vengono modificati e i conteggi univoci vengono calcolati in questo campo. I conteggi non cambiano se il campo ha anche un’etichetta ID-PERSON e il suo valore in questo campo è stato usato come un ID per la richiesta Privacy dei dati. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">Richiede anche l'etichetta I1, I2 o S1 </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">Impossibile impostare gli eventi </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">Impossibile impostare su eVar di merchandising </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">Impossibile impostare in Classificazioni </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">Devi anche avere un'etichetta ID-PERSONA impostata su alcune variabili all'interno di questa suite di rapporti e inviare le richieste utilizzando quell'ID, altrimenti l'etichetta non verrà mai applicata. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Etichette di identità privacy dati**

<table id="table_F6BBC868457443A19A7B693BD6C55B4B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Etichetta </th> 
   <th colname="col2" class="entry"> Definizione </th> 
   <th colname="col3" class="entry"> Altri requisiti </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>None </p> </td> 
   <td colname="col2"> <p>Questa variabile non contiene un ID che verrà usato per le richieste di Privacy dei dati. </p> </td> 
   <td colname="col3"> <p>Devi impostare una di queste etichette solo se questo campo contiene un ID che userai durante l’invio delle richieste di accesso o cancellazione tramite l’API o l’interfaccia utente Privacy dei dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-DEVICE </p> </td> 
   <td colname="col2"> <p>Questo campo contiene un ID che può essere utilizzato per identificare un dispositivo per una richiesta di Privacy dei dati, ma non può distinguere tra utenti diversi di un dispositivo condiviso. </p> <p>Non è necessario specificare questa etichetta per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_618019CB8FCA4A5C94C47636240197B2"> 
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">Richiede anche l'etichetta I1 o I2 </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">Impossibile impostare gli eventi </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">Impossibile impostare su eVar di merchandising </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">Impossibile impostare in Classificazioni </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSONA </p> </td> 
   <td colname="col2"> <p>Questo campo contiene un ID che può essere usato per identificare un utente autenticato (una persona specifica) per una richiesta di Privacy dei dati. </p> <p>Non è necessario specificare questa etichetta per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">Richiede anche l'etichetta I1 o I2 </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">Impossibile impostare gli eventi </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">Impossibile impostare su eVar di merchandising </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">Impossibile impostare in Classificazioni </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile  {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

Quando si applica un’etichetta ID-DEVICE o ID-PERSON a una variabile, viene richiesto di fornire un namespace. È possibile utilizzare uno spazio nomi definito in precedenza o definirne uno nuovo.

**Utilizzare uno spazio dei nomi definito in precedenza**

Se in precedenza hai assegnato un’etichetta ID ad altre variabili in una delle suite di rapporti della società di accesso, puoi selezionare uno dei namespace esistenti. È necessario riutilizzare lo spazio dei nomi se questa variabile contiene lo stesso tipo di ID di altre variabili già etichettate con questo spazio dei nomi e si desidera eseguire una ricerca in tutte le variabili al momento dell&#39;invio di una richiesta.

1. Fai clic su **[!UICONTROL Select Namespace]** e seleziona un namespace esistente.
1. Fai clic su **[!UICONTROL Apply]**.

![](assets/namespace.png)

**Definire un nuovo spazio dei nomi**

Puoi anche definire un nuovo namespace. Nelle stringhe del namespace consigliamo di usare solo caratteri alfanumerici oltre ai caratteri trattino basso, trattino e spazio. Saranno convertiti in lettere minuscole.

1. Fai clic su **[!UICONTROL Select Namespace]** e digita il titolo namespace.

   ![](assets/namespace2.png)

1. Premi **[!UICONTROL Enter]** (Invio) per aggiungere questo namespace. Solo a questo punto si attiverà il pulsante Applica.
1. Fai clic su **[!UICONTROL Apply]**.

La stringa specificata come namespace è la stessa stringa che devi usare quando invii le richieste tramite l’API Privacy dei dati come valore del parametro “namespace”. La richiesta farà in modo che Adobe Analytics ricerchi tutte le variabili in tutte le suite di rapporti che condividono lo spazio dei nomi per l&#39;ID specificato con la richiesta.

Non è necessario specificare le etichette ID-DEVICE o ID-PERSON per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. Ad esempio, se eVar1 può contenere un indirizzo e-mail e eVar2 può contenere un nome utente di accesso, ma invierai le richieste usando solo il nome utente, puoi assegnare a eVar1 le etichette I1, ACC-PERSON, DEL-PERSON, ma a eVar2 le etichette I2, ACC-PERSON, DEL-PERSON, ID-PERSON con il namespace “nome utente”. Potete quindi inviare una richiesta con un blocco JSON della sezione utente, ad esempio:

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

È consentito usare lo stesso namespace per variabili diverse all’interno della stessa suite di rapporti. Ad esempio, alcune implementazioni personalizzate memorizzano un CRM-ID sia nella proprietà che in eVar. Se CRM-ID si trova sempre in una delle due (ad esempio in eVar) e solo di tanto in tanto nell’altra (prop) e non è mai in prop quando è assente anche in eVar, solo eVar richiede un’etichetta ID e uno spazio dei nomi, perché Adobe può cercare l’ID solo in quell’eVar. Se tuttavia CRM-ID si trova a volte in una variabile e a volte nell’altra, entrambe devono avere lo stesso namespace e Adobe cercherà in entrambe le variabili la presenza dell’ID specificato come parte di una richiesta di Privacy dei dati con questo namespace. Tutte queste variabili devono ancora contenere etichette DEL, in modo che il valore sia anonimo ovunque si verifichi.

Un altro esempio: è possibile che CRM-ID venga inviato a volte tramite eVar1, a volte tramite prop7. In questo caso, una regola di elaborazione copia il valore da eVar1, se esiste, in eVar3. Altrimenti copia il valore da prop7 in eVar3. In questo scenario, eVar3 conterrà sempre l&#39;ID CRM se è noto, quindi solo eVar3 richiede un&#39;etichetta ID-PERSON.

>[!CAUTION] I namespace “visitorId” e “customVisitorId” sono riservati per identificare il cookie di tracciamento legacy di Analytics e l’ID visitatore del cliente Analytics. Non utilizzare questi namespace per le variabili di traffico o conversione personalizzate.

## Tipi di variabili ed etichette Privacy dei dati/DULE supportate {#section_CE7C3EDE1344466A98BC45E394B40762}

Le etichette Privacy dei dati/DULE riguardano quattro grandi classi di variabili di Analytics. Non tutte le variabili supportano tutte le etichette. Questa tabella mostra le variabili che supportano o non supportano le etichette.

<table id="table_95D4416B3A8A40C28B2610D0003456E6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di variabile </th> 
   <th colname="col2" class="entry"> Etichette supportate </th> 
   <th colname="col3" class="entry"> Etichette non supportate </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_0615B545A5AD43F2A6F25698A47AAD3E"> 
     <li id="li_A4B3E8E241B149C99F2A71B21227AD72">Eventi di successo personalizzati </li> 
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">eVar di merchandising </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">Variabili con più valori (mvVars) </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">Variabili gerarchiche </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1/S2 </p> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2 </p> <p>ID-DISPOSITIVO, ID-PERSONA </p> <p>DEL-DISPOSITIVO, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Classificazioni </p> </td> 
   <td colname="col2"> <p>I1/I2, S1/S2 </p> <p>ACC-ALL, ACC-PERSON, </p> </td> 
   <td colname="col3"> <p>ID-DISPOSITIVO, ID-PERSONA </p> <p>DEL-DISPOSITIVO, DEL-PERSON </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_1C2FD4D606664965A88F10818E1C11A9"> 
     <li id="li_590975F5C7304317B22C80B20718E914">Variabili di traffico (prop) </li> 
     <li id="li_6E614B7036994434BFDA71A4424529A0">Variabili Commerce (eVar non merchandising) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Tutte le etichette </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maggior parte delle altre variabili </p> <p><i>(Vedere la tabella seguente per le eccezioni)</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2, S1/S2 </p> <p>ID-DISPOSITIVO, ID-PERSONA </p> <p>DEL-DISPOSITIVO, DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili alle quali è possibile assegnare/modificare etichette diverse da ACC-ALL/ACC-PERSON {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

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
     <li id="li_41CB61F927CB4402AAB4A62E219CD153">Dimensioni traffico personalizzate </li> 
    </ul> </td> 
   <td colname="col2"> <p>Tutti, tranne le classificazioni </p> </td> 
   <td colname="col3"> <p>Tutto </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Classificazioni </p> </td> 
   <td colname="col3"> <p>None / I1 / I2 </p> <p>None / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventi di conversione </p> </td> 
   <td colname="col2"> <p>Tutto </p> </td> 
   <td colname="col3"> <p>None / S1 / S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioni ed eventi della soluzione </p> </td> 
   <td colname="col2"> <p>Collegamento Activity Map, </p> <p>Pagina Activity Map </p> </td> 
   <td colname="col3"> <p>None / I1 / I2 </p> <p>None / DEL-DISPOSITIVO / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Le variabili possono contenere parametri URL, che possono includere dati identificabili direttamente o indirettamente. Se l’implementazione non raccoglie dati direttamente o indirettamente identificabili in queste variabili, non sono necessarie le etichette di identità o cancellazione. </p> <p>Nota che la cancellazione elimina i parametri dell’URL, ma ne conserva la base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioni di elaborazione dati </p> </td> 
   <td colname="col2"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col3"> <p>ID-DISPOSITIVO/ID-PERSONA </p> <p>DEL-DISPOSITIVO/DEL-PERSONA </p> </td> 
   <td colname="col4"> <p>Non è possibile rimuovere le etichette ID o DEL (impostate su Nessuno), ma è possibile modificarle nelle varianti DEVICE o PERSON, in base all’implementazione dell’ID personalizzata. </p> <p>Se non usi l’ID visitatore personalizzato, le impostazioni non hanno rilevanza. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Dimensioni standard </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Dimensioni di elaborazione dati </li> 
    </ul> </td> 
   <td colname="col2"> <p>Indirizzo IP </p> <p>Indirizzo IP 2 </p> </td> 
   <td colname="col3"> <p>DEL-DISPOSITIVO/DEL-PERSONA </p> </td> 
   <td colname="col4"> <p>Non è possibile rimuovere l'etichetta DEL, ma è possibile modificarla in modo che sia DEL-DISPOSITIVO o DEL-PERSON, oppure in entrambi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Azione ClickMap (legacy), </p> <p>Context ClickMap (Legacy), </p> <p>Pagina, </p> <p>URL della pagina, </p> <p>URL pagina di immissione originale, </p> <p>Referrer, </p> <p>Visita l’URL della pagina iniziale </p> </td> 
   <td colname="col3"> <p>None / I1 / I2 </p> <p>None / DEL-DISPOSITIVO / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Le variabili possono contenere parametri URL, che possono includere dati identificabili direttamente o indirettamente. Se l’implementazione non raccoglie dati direttamente o indirettamente identificabili in queste variabili, non sono necessarie le etichette di identità o cancellazione. </p> <p>Nota che la cancellazione elimina i parametri dell’URL, ma ne conserva la base. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gestione dell’eliminazione  {#section_F3DEE591671A4B16A8E043F91C137ECB}

Il supporto Adobe Analytics per le richieste di eliminazione Privacy dei dati è progettato per ridurre l’impatto sulla creazione di rapporti. Nella maggior parte dei casi, le metriche visualizzate nei rapporti non devono essere modificate. Un rapporto storico eseguito prima dell’eliminazione Privacy dei dati corrisponde allo stesso rapporto eseguito dopo l’eliminazione. Questa operazione viene eseguita disassociando completamente i dati eliminati dai dati interessati, lasciando intatti i dati non-identificabili in modo che i valori del rapporto rimangano coerenti.

La tabella seguente descrive come vengono “eliminate” molte variabili. Questo non è un elenco completo.

<table id="table_A329C2E2645F4685BC208826D070A5F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabili </th> 
   <th colname="col2" class="entry"> Metodo di eliminazione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>・ Variabili di traffico (prop) </p> <p>・ Variabili di commercio (eVar) </p> </td> 
   <td colname="col2"> <p>Il valore esistente è sostituito da un nuovo valore del modulo “Privacy dei dati-356396D55C4F9C7AB3FBB2F2FA223482”, in cui il valore esadecimale a 32 cifre dopo il prefisso “Privacy dei dati-” è un numero pseudo-casuale e crittograficamente sicuro di 128 bit. Poiché è essenzialmente sostituito da una stringa casuale, non esiste modo di determinare il valore originale a partire da questo nuovo valore né di ricavare il nuovo valore conoscendo il valore originale. </p> <p>Per una determinata variabile, se il valore identico viene sostituito all’interno di altri punti che vengono anch’essi eliminati come parte della stessa richiesta Privacy dei dati, tutte le istanze di tale valore verranno sostituite con lo stesso nuovo valore. </p> <p>Se alcune istanze di un valore vengono sostituite con una richiesta di eliminazione e una richiesta successiva elimina altre (nuove) istanze del valore originale, il nuovo valore di sostituzione sarà diverso dal valore originale di sostituzione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID acquisto </p> </td> 
   <td colname="col2"> <p>Il valore esistente è sostituito da un nuovo valore del modulo “G-7588FCD8642718EC50”, in cui il valore esadecimale a 18 cifre dopo il prefisso “G-” è un numero di 18 cifre pseudo-casuale e crittograficamente sicuro di 128 bit. Tutti i commenti che si applicano all'eliminazione delle variabili di traffico e commercio si applicano anche qui. </p> <p>L'ID acquisto è un ID transazione il cui scopo principale è assicurarsi che un acquisto non venga accreditato due volte, ad esempio quando un utente aggiorna la pagina di conferma dell'acquisto. L’ID stesso può spostare l’acquisto in una riga nel proprio DB in cui viene registrato l’acquisto. Nella maggior parte dei casi non è necessario eliminare questo ID, quindi per impostazione predefinita non viene eliminato. Se si riesce ancora a ricollegare l’acquisto ad un utente dopo la richiesta di cancellazione Privacy dei dati dei propri dati, allora potrebbe essere necessario cancellare questo campo, in modo che i dati di Analytics per questo visitatore non possano essere legati all’acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore </p> </td> 
   <td colname="col2"> <p>Il valore è un numero intero a 128 bit e viene sostituito con un valore pseudorandom a 128 bit crittografato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• ID visitatore personalizzato </p> <p>・ Indirizzo IP </p> <p>・ Indirizzo IP 2 </p> </td> 
   <td colname="col2"> <p>Il valore viene cancellato (impostato sulla stringa vuota o 0 a seconda del tipo della variabile). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Azione ClickMap (legacy) </p> <p>・ Context ClickMap (legacy) </p> <p>・ Pagina </p> <p>• URL della pagina </p> <p>・ URL pagina di immissione originale </p> <p>• Referrer </p> <p>・ Visita l’URL della pagina iniziale </p> </td> 
   <td colname="col2"> <p>I parametri URL vengono cancellati/rimossi. Se il valore non ha l’aspetto di un URL, viene cancellato il valore (impostato sulla stringa vuota). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>・ Latitudine </p> <p>・ Longitudine </p> </td> 
   <td colname="col2"> <p>La precisione è ridotta a non più di 1 km. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili che non supportano le etichette di eliminazione previste {#section_956B766EFFEC427E87E6CFF3A4217E86}

Questa sezione contiene informazioni sulle variabili Analytics che non supportano l’eliminazione. A volte queste variabili vengono eliminate dagli utenti non Analytics (come il team legale) che non conoscono il tipo di dati contenuti nella variabile e fanno supposizioni errate in base al nome della variabile. Segue un elenco di alcune di queste variabili e del perché non richiedono l’eliminazione o perché non richiedono un’etichetta di eliminazione specifica.

<table id="table_6FECF3D654514862912D371E6BE4143B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Commenti </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nuovo ID visitatore </p> </td> 
   <td colname="col2"> <p>L’ID nuovo visitatore è un booleano che è true la prima volta che viene visualizzato un ID visitatore. Non è necessario eliminarlo una volta che l’ID visitatore è reso anonimo. Dopo l'anonimizzazione, corrisponderà alla prima volta che abbiamo visto questo ID anonimo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CAP </p> <p>Codice postale geografico </p> </td> 
   <td colname="col2"> <p>I codici ZIP sono impostati solo per gli hit originari degli Stati Uniti. Non sono predisposti per i risultati ottenuti dall'UE. Anche se impostati, forniscono solo un'ampia area geografica che rende difficile la ri-identificazione della persona interessata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Latitudine geografica </p> <p>Longitudine geografica </p> </td> 
   <td colname="col2"> <p>Questi forniscono una posizione approssimativa derivata dall'indirizzo IP. La precisione è generalmente simile a quella di un codice di avviamento postale, entro poche decine di chilometri dalla posizione effettiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente utente </p> </td> 
   <td colname="col2"> <p>L'agente utente identifica la versione del browser utilizzata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente </p> </td> 
   <td colname="col2"> <p> Specifica la suite di rapporti di Analytics (sotto forma di numero) contenente i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID suite di rapporti </p> </td> 
   <td colname="col2"> <p> Specifica il nome della suite di rapporti di Analytics contenente i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore </p> <p>MCID / ECID </p> </td> 
   <td colname="col2"> <p> Queste presentano un’etichetta DEL-DEVICE, ma non è possibile aggiungere l’etichetta DEL-PERSON. Se si specifica  <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> Espansione dell’ID</a> con ogni richiesta, questi ID verranno eliminati automaticamente per tutte le richieste di eliminazione, anche quelle che utilizzano un ID-PERSON. </p> <p>Se non utilizzi ID Expansion, ma vuoi che questi cookie ID siano anonimi per gli hit che contengono un ID corrispondente in una prop o eVar, puoi aggirare questo limite di etichettatura etichettando la prop o eVar con un'etichetta ID-DEVICE, anche se identifica davvero una persona (tutte le etichette DEL-PERSON dovrebbero anche essere modificate in etichette DEL-DEVICE). In questo caso, poiché solo alcune istanze dell’ID visitatore o dell’ECID vengono rese anonime, i conteggi dei visitatori univoci cambiano nei rapporti storici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID AMO </p> </td> 
   <td colname="col2"> <p> L’ID Adobe Advertising Cloud è una variabile di soluzione con un’etichetta non modificabile DEL-DEVICE. Viene popolato da un cookie esattamente come i Visitor ID e MCID. Deve essere eliminato dagli hit ogni volta che gli altri ID vengono eliminati. Per ulteriori informazioni, vedere la descrizione di tali variabili. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campi di dati per le richieste di accesso  {#section_6678FB4FF42B481C9B78E64F61782397}

Esistono cinque variabili standard contenenti marche temporali:

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Timestamp </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ora di attivazione UTC </p> </td> 
   <td colname="col2"> <p>L’ora in cui Adobe Analytics ha ricevuto l’hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora hit personalizzata UTC </p> </td> 
   <td colname="col2"> <p>Ora in cui si è verificato l’hit, che per alcune app mobili e altre implementazioni potrebbe essere precedente al momento in cui è stato ricevuto. Ad esempio, se una connessione di rete non era disponibile quando si è verificata, l'app potrebbe contenere l'hit e inviarlo quando una connessione diventa disponibile. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data e ora </p> </td> 
   <td colname="col2"> <p>Stesso valore dell’Ora hit personalizzata (UTC), ma nel fuso orario della suite di rapporti, anziché GMT.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora primo hit GMT </p> </td> 
   <td colname="col2"> <p>Il valore UTC (Custom Hit Time) per il primo hit ricevuto per il valore ID visitatore per questo hit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora inizio visita UTC </p> </td> 
   <td colname="col2"> <p>Il valore Ora hit personalizzata (UTC) per il primo risultato ricevuto per l’attuale visita di questo ID visitatore.</p> </td> 
  </tr> 
 </tbody> 
</table>

Il codice per generare i file restituiti per le richieste di accesso privacy dei dati richiede che almeno una delle prime tre variabili di marca temporale sia inclusa nella richiesta di accesso (che quindi abbia un’etichetta ACC applicabile al tipo di richiesta). Se nessuna di queste è inclusa, allora la marca Ora hit personalizzata (UTC) sarà elaborata come se avesse etichetta ACC-ALL.

Il file CSV restituito per le richieste di accesso Privacy dei dati convertirà i valori in questi campi da marche temporali unix a campi data/ora in formato AAAA-MM-GG HH:MM:SS (per esempio, 2018-05-01 13:49:22). Nel file HTML di riepilogo, questi valori di marca temporale saranno troncati per includere solo la data, in formato AAAA-MM-GG, per ridurre il numero di valori univoci che si verificano per questi campi.
