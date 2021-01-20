---
description: Esempi di etichette sulla privacy dei dati per  variabili Adobe Analytics
title: Etichette Privacy dei dati per le variabili di Analytics
uuid: a37a1278-7a0d-4e14-ae35-43bc460e7d12
translation-type: tm+mt
source-git-commit: b3ea538d0d6e6ebbbbd17871aacaed7527cf3976
workflow-type: tm+mt
source-wordcount: '3642'
ht-degree: 99%

---


# Etichette Privacy dei dati per le variabili di Analytics

## Perché etichettare i dati? {#section_A075CDF3AD0744BD8CEB41CE3FB7BFB3}

Molti clienti Adobe dispongono di team legali che hanno rivisto le normative sulla Privacy dei dati (RGPD, CCPA, ecc.) e che hanno tratto le proprie conclusioni sul modo in cui i dati devono essere trattati per conformarsi a tali normative. Le interpretazioni giuridiche possono essere diverse in base alle aziende e anche le impostazioni di gestione dei dati desiderate possono differire tra i clienti. Poiché i clienti hanno preferenze diverse per quanto riguarda il trattamento dei dati in termini di privacy e diversi set di dati, in Adobe i clienti, in qualità di titolari dei dati, possono personalizzare le impostazioni desiderate per il trattamento dei propri dati in base alla Privacy dei dati. Questo consente a ogni singolo cliente di elaborare le richieste di Privacy dei dati nella maniera più adatta al proprio marchio e al proprio set di dati.

Adobe Analytics offre gli strumenti necessari per etichettare i dati in base al loro stato di riservatezza e a vincoli contrattuali. Le etichette sono importanti e utili per: (1) individuare le persone interessate, (2) determinare i dati da restituire come parte di una richiesta di accesso e (3) individuare i campi di dati da cancellare in seguito a una richiesta di cancellazione.

Prima di capire quali etichette applicare a determinate variabili o campi, è necessario [conoscere gli ID](/help/admin/c-data-governance/gdpr-analytics-ids.md) che vengono acquisiti nei dati di Analytics e decidere quali usare per le richieste di Privacy dei dati.

L’implementazione Privacy dei dati in Adobe Analytics supporta le seguenti etichette per i dati di identità, i dati sensibili e la governance dei dati.

## Etichette DULE {#section_B2E78130957647338495EF37DE21D6BC}

>[!NOTE]
>
>Il framework DULE (Data Usage Labeling &amp; Enforcement, etichettatura e applicazione dell’uso dei dati) è progettato per fornire un metodo uniforme per tutte le soluzioni, i servizi e le piattaforme di Adobe al fine di acquisire, comunicare e usare i metadati sui dati in Adobe Experience Cloud. I metadati consentono ai titolari del trattamento di indicare i dati che si riferiscono a informazioni personali, dati sensibili e vincoli di contratto associati a questi. In questa versione iniziale Analytics espone solo le etichette DULE pertinenti alla Privacy dei dati. Poiché altri prodotti Adobe implementano il supporto per le etichette DULE, le versioni future introdurranno altre etichette per i dati sensibili, nonché etichette contrattuali che garantiranno che i dati condivisi tra i prodotti verranno usati solo nei modi consentiti dalla legge.

## Etichette per i dati di identità (DULE)  {#identity-data-labels}

Le etichette “I” per i dati di identità sono usate per organizzare in categorie i dati che possono identificare o consentono di contattare una persona specifica.

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
   <td colname="col2"> <p><b>Direttamente identificabili</b>: dati che possono identificare specificamente o consentire il contatto diretto con un individuo, ad esempio un nome o un indirizzo e-mail. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_4E2AD59D119E40D28B869D0BB63B9FD9"> 
     <li id="li_AC3E99B57E3A4AE2A12BE219680AFC58">Non può essere impostata negli eventi </li> 
     <li id="li_BB66992863C8402F8D58656293F31E71">Non può essere impostata nelle eVars Merchandising </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>I2 </p> </td> 
   <td colname="col2"> <p><b>Indirettamente identificabili</b>: dati che possono essere usati in combinazione con altri dati per identificare o consentire il contatto diretto con una persona o un dispositivo. </p> <p>Da soli non consentono l’identificazione di una persona, ma possono essere combinati con altre informazioni (che potrebbero essere o meno in tuo possesso) per identificare un individuo. Ne sono esempi il numero fedeltà di un cliente o un ID usato da un sistema CRM di un’azienda univoco per ciascun cliente. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_A0EF0F3DC5804D4FBE228946D697ABEB"> 
     <li id="li_A592EA6DA82C4D8C80E03F02ADF4E20E">Non può essere impostata negli eventi </li> 
     <li id="li_46CE7B1E84884CDAB356A6DF89397849">Non può essere impostata nelle eVars Merchandising </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Etichette per i dati sensibili (DULE)  {#sensitive-data-labels}

Le etichette “S” per i dati sensibili vengono usate per organizzare in categorie i dati sensibili, come i dati geografici. Per identificare altri tipi di informazioni riservate, verranno introdotte etichette di dati riservati aggiuntive.

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
   <td colname="col2"> <p> Dati precisi di geolocalizzazione relativi alla latitudine e alla longitudine che possono essere usati per determinare la posizione esatta di un dispositivo (entro 100 m o meno). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>S2 </p> </td> 
   <td colname="col2"> <p> Dati di geolocalizzazione che possono essere usati per determinare un’area geografica ampiamente definita. </p> </td> 
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
   <td colname="col3"> <p>Inoltre, è necessario disporre di un’etichetta ID-PERSON impostata su alcune variabili in questa suite di rapporti e inviare richieste con tale ID, altrimenti l’etichetta non verrà mai applicata. </p> </td> 
  </tr> 
 </tbody> 
</table>

Si prevede che per molte variabili verranno applicate le etichette di accesso, mentre alcune variabili riceveranno altre etichette. Tuttavia spetta all’utente, dopo aver consultato il team legale, decidere quali tra i dati raccolti condividere con le persone interessate.

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
   <td colname="col2"> <p>Diversamente dalle altre etichette, le etichette di cancellazione non si escludono a vicenda. Puoi selezionarne una, entrambe o nessuna. Non è necessaria un’etichetta None diversa, perché None viene indicata automaticamente non selezionando alcuna delle opzioni di cancellazione. </p> </td> 
   <td colname="col3"> <p>L’etichetta di cancellazione è necessaria solo per i campi che contengono un valore che consentirebbe l’associazione di un risultato alla persona interessata (ovvero che consentirebbe di identificare la persona interessata). </p> <p> Non è necessario cancellare altre informazioni personali (preferiti, cronologia di navigazione/acquisto, condizioni di salute e così via) perché l’associazione alla persona interessata verrà impedita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-DEVICE </p> </td> 
   <td colname="col2"> <p>Per le richieste di cancellazione Privacy dei dati, i valori in questo campo devono essere resi anonimi solo per le richieste in cui è presente un ID-DEVICE specifico nel risultato. </p> <p>Se lo stesso valore ricorre in altri risultati, che non vengono cancellati, tali istanze non verranno modificate. Questo comporterà una modifica dei conteggi per i rapporti che elaborano conteggi univoci in questo campo. Nei dispositivi condivisi, questa operazione può rimuovere gli identificatori per altri individui, oltre alla sola persona interessata. </p> <p>I conteggi non cambiano se il campo ha anche un’etichetta ID-DEVICE e il suo valore in questo campo è stato usato come un ID per la richiesta di Privacy dei dati. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_45C3A09E1F05492B97C3F3DEA7C78FBC"> 
     <li id="li_BAB277F92F284ADE9D7B6839BDD716E2">Richiede anche l’etichetta I1 o I2 o S1 </li> 
     <li id="li_6DDFC0571457489CBA9D76F547247F20">Non può essere impostata negli eventi </li> 
     <li id="li_E79C6DFC6C58478EAA1504E3820D512C">Non può essere impostata nelle eVars Merchandising </li> 
     <li id="li_B78E273212E447D49D0707E174B66DEC">Non può essere impostata nelle classificazioni </li> 
     <li id="li_F0F52D0DE7454557A6A97063C1FBC372">È necessario inviare richieste utilizzando un ID-DEVICE o impostare expandIDs su true oppure l’etichetta non verrà mai applicata. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>DEL-PERSON </p> </td> 
   <td colname="col2"> <p>Per le richieste di cancellazione Privacy dei dati, i valori in questo campo devono essere resi anonimi solo per le richieste in cui è presente un ID-PERSON specifico nel risultato. </p> <p>Se lo stesso valore ricorre in altri risultati, che non vengono cancellati, tali valori non verranno modificati. Questo comporterà una modifica dei conteggi per i rapporti che elaborano conteggi univoci in questo campo. I conteggi non cambiano se il campo ha anche un’etichetta ID-PERSON e il suo valore in questo campo è stato usato come un ID per la richiesta Privacy dei dati. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_6722E42E036E47B4B5E17DC213636D51"> 
     <li id="li_6C1A64FF68AF428A827D8C6C33E22970">Richiede anche l’etichetta I1 o I2 o S1 </li> 
     <li id="li_8053533FFE874EE795C8B6043A4F73B3">Non può essere impostata negli eventi </li> 
     <li id="li_D6700CF4D03E44DDA83C4DDBB5B70CC3">Non può essere impostata nelle eVars Merchandising </li> 
     <li id="li_B6C2B15484B344889DBF29B62E2EA8FD">Non può essere impostata nelle classificazioni </li> 
     <li id="li_3BBD0C27D9644C2B9618457A0BFC15EF">Inoltre, è necessario disporre di un’etichetta ID-PERSON impostata su alcune variabili in questa suite di rapporti e inviare richieste con tale ID, altrimenti l’etichetta non verrà mai applicata. </li> 
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
     <li id="li_0E5ADED36FF24A348FDD434E2CC8C8EE">Richiede anche l’etichetta I1 o I2 </li> 
     <li id="li_20BCFF07B2BF468C8E0D477C10B2EF9F">Non può essere impostata negli eventi </li> 
     <li id="li_0BD73EEF4184475D8E97878CF8DBEB90">Non può essere impostata nelle eVars Merchandising </li> 
     <li id="li_129851035C4A4BF0922296B4C3BEE39B">Non può essere impostata nelle classificazioni </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID-PERSON </p> </td> 
   <td colname="col2"> <p>Questo campo contiene un ID che può essere usato per identificare un utente autenticato (una persona specifica) per una richiesta di Privacy dei dati. </p> <p>Non è necessario specificare questa etichetta per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. </p> </td> 
   <td colname="col3"> 
    <ul id="ul_0C7EEC8FCB5C4BCDA5D48F3C98770A67"> 
     <li id="li_2E781AE8D7A046A7996C7300CA854B86">Richiede anche l’etichetta I1 o I2 </li> 
     <li id="li_EB4C6430C218405DAAE81DEE010DCAA2">Non può essere impostata negli eventi </li> 
     <li id="li_05AA67B45974474F9DA520E8B877BA11">Non può essere impostata nelle eVars Merchandising </li> 
     <li id="li_8A6BF4B40ED249289EAD46FE1C755FB0">Non può essere impostata nelle classificazioni </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Fornire un namespace quando si applicano etichette come ID-DEVICE o ID-PERSON a una variabile  {#section_F0A47AF8DA384A26BD56032D0ABFD2D7}

Quando si applica un’etichetta ID-DEVICE o ID-PERSON a una variabile, viene richiesto di fornire un namespace. Puoi usare il namespace definito in precedenza o puoi definirne uno nuovo.

**Usare un namespace definito in precedenza**

Se in precedenza hai assegnato un’etichetta ID ad altre variabili in una delle suite di rapporti della società di accesso, puoi selezionare uno dei namespace esistenti. È consigliabile riutilizzare lo spazio dei nomi se questa variabile contiene lo stesso tipo di ID di altre variabili già etichettate con lo spazio dei nomi e si desidera eseguire la ricerca di tutte quando si invia una richiesta.

1. Fai clic su **[!UICONTROL Select Namespace]** e seleziona un namespace esistente.
1. Fai clic su **[!UICONTROL Apply]**.

![](assets/namespace.png)

**Definire un nuovo namespace**

Puoi anche definire un nuovo namespace. Nelle stringhe del namespace consigliamo di usare solo caratteri alfanumerici oltre ai caratteri trattino basso, trattino e spazio. Tutti i caratteri verranno convertiti in lettere minuscole.

1. Fai clic su **[!UICONTROL Select Namespace]** e digita il titolo namespace.

   ![](assets/namespace2.png)

1. Premi **[!UICONTROL Enter]** per aggiungere questo namespace. Solo a questo punto si attiverà il pulsante Applica.
1. Fai clic su **[!UICONTROL Apply]**.

La stringa specificata come namespace è la stessa stringa che devi usare quando invii le richieste tramite l’API Privacy dei dati come valore del parametro “namespace”. Per via della richiesta, Adobe Analytics cercherà tutte le variabili in tutte le suite di rapporti che condividono questo namespace per l’ID specificata con la richiesta.

Non è necessario specificare le etichette ID-DEVICE o ID-PERSON per tutte le variabili che contengono un ID (per questo si devono usare le etichette I1/I2). Usa questa etichetta se invii le richieste di Privacy dei dati usando gli ID memorizzati in questa variabile e vuoi cercare la variabile per l’ID specificato. Ad esempio, se eVar1 può contenere un indirizzo e-mail e eVar2 può contenere un nome utente di accesso, ma invierai le richieste usando solo il nome utente, puoi assegnare a eVar1 le etichette I1, ACC-PERSON, DEL-PERSON, ma a eVar2 le etichette I2, ACC-PERSON, DEL-PERSON, ID-PERSON con il namespace “nome utente”. Puoi quindi inviare una richiesta con un blocco JSON della sezione utente come ad esempio:

```
{
     "namespace": "user name",
     "type": "analytics",
     "value": "rocketman123"
}
```

È consentito usare lo stesso namespace per variabili diverse all’interno della stessa suite di rapporti. Ad esempio, alcune implementazioni personalizzate memorizzano un CRM-ID sia nella proprietà che in eVar. Se CRM-ID si trova sempre in una delle due (ad esempio in eVar) e solo di tanto in tanto nell’altra (prop) e non è mai in prop quando è assente anche in eVar, solo eVar richiede un’etichetta ID e uno spazio dei nomi, perché Adobe può cercare l’ID solo in quell’eVar. Se tuttavia CRM-ID si trova a volte in una variabile e a volte nell’altra, entrambe devono avere lo stesso namespace e Adobe cercherà in entrambe le variabili la presenza dell’ID specificato come parte di una richiesta di Privacy dei dati con questo namespace. È comunque necessario disporre di etichette DEL su tutte queste variabili, in modo che il valore sia anonimo indipendentemente da dove si verifica.

Un altro esempio: è possibile che CRM-ID venga inviato a volte tramite eVar1, a volte tramite prop7. In questo caso, una regola di elaborazione copia il valore da eVar1, se esiste, in eVar3. Altrimenti copia il valore da prop7 in eVar3. In questo scenario, eVar3 conterrà sempre l’ID CRM se noto, pertanto solo eVar3 richiede un’etichetta ID-PERSON.

>[!CAUTION]
>
>I namespace “visitorId” e “customVisitorId” sono riservati per identificare il cookie di tracciamento legacy di Analytics e l’ID visitatore del cliente Analytics. Non utilizzare questi namespace per le variabili di traffico o conversione personalizzate.

## Tipi di variabili ed etichette Privacy dei dati/DULE supportate {#section_CE7C3EDE1344466A98BC45E394B40762}

Le etichette Privacy dei dati/DULE riguardano quattro grandi classi di variabili di Analytics. Le diverse etichette non sono supportate da tutte le variabili. Questa tabella mostra le variabili e le relative etichette supportate da ognuna di esse.

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
     <li id="li_8AEF688AE9B8426C82D199E4B195330D">eVar di Merchandising </li> 
     <li id="li_DFFCA65DCC6146AEB6D47476B4D4CC3B">Variabili con più valori (mvVars) </li> 
     <li id="li_3192D08B12C249D1AAA8AAEEDE2FD7D7">Variabili di gerarchia </li> 
    </ul> </td> 
   <td colname="col2"> <p>S1/S2 </p> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2 </p> <p>ID-DEVICE, ID-PERSON </p> <p>DEL-DEVICE, DEL-PERSON </p> </td> 
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
     <li id="li_6E614B7036994434BFDA71A4424529A0">Variabili commerciali (eVars non merchandising) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Tutte le etichette </p> </td> 
   <td colname="col3"> - </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La maggior parte delle altre variabili </p> <p><i>(Consulta la tabella seguente per le eccezioni)</i> </p> </td> 
   <td colname="col2"> <p>ACC-ALL, ACC-PERSON </p> </td> 
   <td colname="col3"> <p>I1/I2, S1/S2 </p> <p>ID-DISPOSITIVO, ID-PERSONA </p> <p>DEL-DISPOSITIVO, DEL-PERSON </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili a cui è possibile assegnare etichette diverse da ACC-ALL/ACC-PERSON/Modificata da  {#section_4FA003003D1B4E2EBCFCDB1A7CD4A824}

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
   <td colname="col3"> <p>Tutte </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Classificazioni </p> </td> 
   <td colname="col3"> <p>Nessuno/I1/I2 </p> <p>Nessuno/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventi di conversione </p> </td> 
   <td colname="col2"> <p>Tutte </p> </td> 
   <td colname="col3"> <p>Nessuno/S1/S2 </p> </td> 
   <td colname="col4"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Eventi e dimensioni della soluzione </p> </td> 
   <td colname="col2"> <p>Collegamento alla Activity Map, </p> <p>Pagina della Activity Map </p> </td> 
   <td colname="col3"> <p>Nessuno/I1/I2 </p> <p>Nessuno/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Le variabili possono contenere i parametri dell’URL, che possono includere dati direttamente o indirettamente identificabili. Se l’implementazione non raccoglie dati direttamente o indirettamente identificabili in queste variabili, non sono necessarie le etichette di identità o cancellazione. </p> <p>Nota che la cancellazione elimina i parametri dell’URL, ma ne conserva la base. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensioni di elaborazione dei dati </p> </td> 
   <td colname="col2"> <p>ID visitatore personalizzato </p> </td> 
   <td colname="col3"> <p>ID-DEVICE / ID-PERSON </p> <p>DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Non è possibile rimuovere le etichette ID o DEL (impostate su Nessuno), ma è possibile modificarle nelle varianti DEVICE o PERSON, in base all’implementazione dell’ID personalizzata. </p> <p>Se non usi l’ID visitatore personalizzato, le impostazioni non hanno rilevanza. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1" morerows="1"> 
    <ul id="ul_5EB0193732D44A20AEA08CE9DFE01DBD"> 
     <li id="li_F70D969F83314A94BD8567449968EE2F">Dimensioni standard </li> 
     <li id="li_6046764B19FF4679B51E55671C2C0ADB">Dimensioni di elaborazione dei dati </li> 
    </ul> </td> 
   <td colname="col2"> <p>Indirizzo IP </p> <p>Indirizzo IP 2 </p> </td> 
   <td colname="col3"> <p>DEL-DEVICE / DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Non puoi rimuovere l’etichetta DEL, ma puoi modificarla in DEL-DEVICE or DEL-PERSON o in entrambe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col2"> <p>Azione ClickMap (legacy), </p> <p>Contesto ClickMap (legacy), </p> <p>Pagina, </p> <p>URL della pagina, </p> <p>URL originale della pagina iniziale, </p> <p>Referrer, </p> <p>URL di visita alla pagina iniziale </p> </td> 
   <td colname="col3"> <p>Nessuno/I1/I2 </p> <p>Nessuno/DEL-DEVICE/DEL-PERSON </p> </td> 
   <td colname="col4"> <p>Le variabili possono contenere i parametri dell’URL, che possono includere dati direttamente o indirettamente identificabili. Se l’implementazione non raccoglie dati direttamente o indirettamente identificabili in queste variabili, non sono necessarie le etichette di identità o cancellazione. </p> <p>Nota che la cancellazione elimina i parametri dell’URL, ma ne conserva la base. </p> </td> 
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
   <td colname="col1"> <p>• Variabili di traffico (prop) </p> <p>• Variabili commerciali (eVars) </p> </td> 
   <td colname="col2"> <p>Il valore esistente è sostituito da un nuovo valore del modulo “Privacy dei dati-356396D55C4F9C7AB3FBB2F2FA223482”, in cui il valore esadecimale a 32 cifre dopo il prefisso “Privacy dei dati-” è un numero pseudo-casuale e crittograficamente sicuro di 128 bit. Poiché è essenzialmente sostituito da una stringa casuale, non esiste modo di determinare il valore originale a partire da questo nuovo valore né di ricavare il nuovo valore conoscendo il valore originale. </p> <p>Per una determinata variabile, se il valore identico viene sostituito all’interno di altri punti che vengono anch’essi eliminati come parte della stessa richiesta Privacy dei dati, tutte le istanze di tale valore verranno sostituite con lo stesso nuovo valore. </p> <p>Se alcune istanze di un valore vengono sostituite con una richiesta di cancellazione e una richiesta successiva cancella altre (nuove) istanze del valore originale, il nuovo valore di sostituzione sarà diverso dal valore di sostituzione originale. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID acquisto </p> </td> 
   <td colname="col2"> <p>Il valore esistente è sostituito da un nuovo valore del modulo “G-7588FCD8642718EC50”, in cui il valore esadecimale a 18 cifre dopo il prefisso “G-” è un numero di 18 cifre pseudo-casuale e crittograficamente sicuro di 128 bit. Tutti i commenti che si applicano alla cancellazione delle variabili relative al traffico e al commercio si applicano anche in questo caso. </p> <p>Questo è un ID di transazione il cui scopo principale è quello di garantire che un acquisto non venga accreditato due volte, ad esempio quando qualcuno aggiorna la pagina di conferma dell’acquisto. L’ID stesso può spostare l’acquisto in una riga nel proprio DB in cui viene registrato l’acquisto. Nella maggior parte dei casi non è necessario cancellare questo ID, quindi non viene cancellato per impostazione predefinita. Se si riesce ancora a ricollegare l’acquisto ad un utente dopo la richiesta di cancellazione Privacy dei dati dei propri dati, allora potrebbe essere necessario cancellare questo campo, in modo che i dati di Analytics per questo visitatore non possano essere legati all’acquirente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore </p> </td> 
   <td colname="col2"> <p>Il valore è un numero intero di 128 bit e viene sostituito da un valore pseudo-casuale e crittograficamente sicuro di 128 bit. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• MCID </p> <p>• ID visitatore personalizzato </p> <p>• Indirizzo IP </p> <p>• Indirizzo IP 2 </p> </td> 
   <td colname="col2"> <p>Il valore viene cancellato (impostato sulla stringa vuota o 0 a seconda del tipo della variabile). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• Azione ClickMap (legacy) </p> <p>• Contesto ClickMap (legacy) </p> <p>• Pagina </p> <p>• URL della pagina </p> <p>• URL originale della pagina iniziale </p> <p>• Referrer </p> <p>• URL di visita alla pagina iniziale </p> </td> 
   <td colname="col2"> <p>I parametri URL vengono cancellati/rimossi. Se il valore non presenta le caratteristiche di un URL, allora viene cancellato (impostato sulla stringa vuota). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>• Latitudine </p> <p>• Longitudine </p> </td> 
   <td colname="col2"> <p>La precisione viene ridotta a non più di 1 km. </p> </td> 
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
   <td colname="col1"> <p>ID nuovo visitatore </p> </td> 
   <td colname="col2"> <p>L’ID nuovo visitatore è un booleano che è true la prima volta che viene visualizzato un ID visitatore. Non è necessario eliminarlo una volta che l’ID visitatore è reso anonimo. Una volta reso anonimo, corrisponde alla prima volta che questo ID è stato visto anonimo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice postale </p> <p>Codice postale geografico </p> </td> 
   <td colname="col2"> <p>I codici postali vengono impostati solo per risposte provenienti dagli Stati Uniti. Non vengono impostate per risposte provenienti dall’UE. Anche se è impostati, forniscono solo un’area geografica ampia che rende difficile la reidentificazione dei dati interessati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Latitudine geografica </p> <p>Longitudine geografica </p> </td> 
   <td colname="col2"> <p>Forniscono una posizione approssimativa derivata dall’indirizzo IP. Di norma, la precisione è simile a quella di un codice postale, entro alcune dozzine di chilometri dalla posizione effettiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente utente </p> </td> 
   <td colname="col2"> <p>L’agente utente identifica la versione del browser utilizzato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID utente </p> </td> 
   <td colname="col2"> <p> Specifica la suite di rapporti Analytics (come numero) contenente i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID suite di rapporti </p> </td> 
   <td colname="col2"> <p> Specifica il nome della suite di rapporti Analytics contenente i dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID visitatore </p> <p>MCID/ECID </p> </td> 
   <td colname="col2"> <p> Queste presentano un’etichetta DEL-DEVICE, ma non è possibile aggiungere l’etichetta DEL-PERSON. Se si specifica <a href="/help/admin/c-data-governance/gdpr-id-expansion.md"> Espansione dell’ID</a> con ogni richiesta, questi ID verranno eliminati automaticamente per tutte le richieste di eliminazione, anche quelle che utilizzano un ID-PERSON. </p> <p>Se non si utilizza l’opzione Espansione dell’ID, ma si desidera che questi ID cookie siano resi anonimi nei risultati con un ID corrispondente in un prop o in un eVar, è possibile aggirare questa limitazione di etichettatura etichettando il prop o il eVar con un’etichetta ID-DEVICE, anche se identifica effettivamente una persona (tutte le etichette DEL-PERSON devono essere sostituite dalle etichette DEL-DEVICE). In questo caso, poiché solo alcune istanze dell’ID visitatore o di ECID vengono rese anonime, i conteggi dei visitatori univoci verranno modificati nella cronologia. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID AMO </p> </td> 
   <td colname="col2"> <p> L’ID Adobe Advertising Cloud è una variabile di soluzione con un’etichetta non modificabile DEL-DEVICE. Viene compilato da un cookie come l’ID visitatore e l’MCID. Deve essere eliminato dai risultati ogni volta che vengono eliminati altri ID. Per ulteriori informazioni, consultare la descrizione di tali variabili. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campi di dati per le richieste di accesso  {#section_6678FB4FF42B481C9B78E64F61782397}

Esistono cinque variabili standard che contengono la marca temporale:

<table id="table_49A9255366254F799E1682C30CBD98EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Marca Temporale </th> 
   <th colname="col2" class="entry"> Definizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ora hit (UTC) </p> </td> 
   <td colname="col2"> <p>Il momento in cui Adobe Analytics ha ricevuto il risultato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora hit personalizzata (UTC) </p> </td> 
   <td colname="col2"> <p>Il momento in cui si è verificato il risultato, che per alcune applicazioni mobili e altre implementazioni può essere precedente al momento in cui è stato ricevuto. Ad esempio, se una connessione di rete non era disponibile in quel momento, l’applicazione potrebbe conservare il risultato e inviarlo quando la connessione è nuovamente attiva. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Data e ora </p> </td> 
   <td colname="col2"> <p>Stesso valore dell’Ora hit personalizzata (UTC), ma nel fuso orario della suite di rapporti, anziché GMT.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora primo hit (GMT) </p> </td> 
   <td colname="col2"> <p>Il valore Ora hit personalizzata (UTC) per il primo risultato ricevuto per il valore dell’ID visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ora inizio visita (UTC) </p> </td> 
   <td colname="col2"> <p>Il valore Ora hit personalizzata (UTC) per il primo risultato ricevuto per l’attuale visita di questo ID visitatore.</p> </td> 
  </tr> 
 </tbody> 
</table>

Il codice per generare i file restituiti per le richieste di accesso privacy dei dati richiede che almeno una delle prime tre variabili di marca temporale sia inclusa nella richiesta di accesso (che quindi abbia un’etichetta ACC applicabile al tipo di richiesta). Se nessuna di queste è inclusa, allora la marca Ora hit personalizzata (UTC) sarà elaborata come se avesse etichetta ACC-ALL.

Il file CSV restituito per le richieste di accesso Privacy dei dati convertirà i valori in questi campi da marche temporali unix a campi data/ora in formato AAAA-MM-GG HH:MM:SS (per esempio, 2018-05-01 13:49:22). Nel file HTML di riepilogo, questi valori di marca temporale saranno troncati per includere solo la data, in formato AAAA-MM-GG, per ridurre il numero di valori univoci che si verificano per questi campi.
