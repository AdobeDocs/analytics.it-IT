---
description: Variabili di configurazione impostate in AppMeasurement.js.
keywords: Implementazione di Analytics
seo-description: Variabili di configurazione impostate in AppMeasurement.js per Adobe Analytics
seo-title: Variabili di configurazione
solution: Analytics
subtopic: Variabili
title: Variabili di configurazione
topic: Sviluppatore e implementazione
uuid: a19484b6-e350-4c12-b4d6-a31c79a42db0
translation-type: tm+mt
source-git-commit: 5b55b865629628da0ec42773355a1cf66ad7d9b7

---


# Variabili di configurazione

Le variabili di configurazione controllano il modo in cui i dati vengono catturati ed elaborati nel reporting. Le variabili di configurazione più comuni, solitamente impostate nel JavaScript AppMeasurement.js globale principale. Queste variabili possono essere impostate all’interno del codice a livello di pagina di Analytics e, se appropriato, dei collegamenti.

Per impostazione predefinita, non tutte queste variabili vengono visualizzate nel codice quando si genera codice tramite **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Alcune di queste variabili di configurazione potrebbero non essere applicabili alle esigenze di implementazione del sito.

Alcuni degli obiettivi di utilizzo di queste variabili di configurazione sono:

* Consente di tenere traccia di più siti/domini.
* Utilizzate qualsiasi valuta sugli acquisti.
* Acquisire dati in lingue diverse.
* Tracciamento dei collegamenti (numero di file scaricati, collegamenti a siti esterni).
* Tieni traccia dei collegamenti personalizzati per scopi unici.

>[!NOTE]
>
>[!DNL AppMeasurement] richiede che tutte le variabili di configurazione siano impostate prima della chiamata iniziale alla funzione track, `t()`. Se le variabili di configurazione sono impostate dopo la chiamata a `t()`, potrebbero verificarsi risultati imprevisti. Per garantire la corretta raccolta dei dati, tutte le variabili di configurazione devono essere al di sopra della `doPlugins` funzione.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

La variabile determina la suite di rapporti in cui i dati vengono memorizzati e segnalati.

Se si inviano a più suite di rapporti (tag con più suite), `s.account` può trattarsi di un elenco di valori separati da virgola. L'ID suite di rapporti è determinato da Adobe.

**Parametri**

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| 40 byte | Nel percorso URL | N/D | N/D |

Ogni ID suite di rapporti deve corrispondere al valore creato nel [!DNL Admin Console]. Ogni ID suite di rapporti deve essere di 40 byte o inferiore, ma l'aggregazione di tutte le suite di rapporti (l'intero elenco separato da virgole) non ha limiti.

La suite per report è il livello di segmentazione più fondamentale nei report. Puoi impostare un numero illimitato di suite di rapporti. Ogni suite di rapporti fa riferimento a un set dedicato di tabelle popolate nei server di raccolta di Adobe. Una suite di rapporti è identificata dalla `s_account` variabile nel codice JavaScript.

All'interno [!DNL Analytics]della casella a discesa del sito in alto a sinistra dei rapporti viene visualizzata la suite di rapporti corrente. Ciascuna suite di rapporti ha un identificatore univoco denominato ID suite di rapporti. La `s_account` variabile contiene uno o più ID suite di rapporti a cui vengono inviati i dati. Il valore ID suite di rapporti, invisibile agli [!DNL Analytics] utenti, deve essere fornito o approvato da Adobe prima di utilizzarlo. A ogni suite di rapporti è associato un "nome descrittivo" che può essere modificato nella sezione suite di rapporti di [!DNL Admin Console].

La `s_account` variabile viene normalmente dichiarata all'interno del file JavaScript (s_code.js). È possibile dichiarare la `s_account` variabile sulla pagina HTML, una pratica comune quando il valore di `s_account` può cambiare da una pagina all’altra. Poiché la `s_account` variabile ha un ambito globale, deve essere dichiarata immediatamente prima di includere il file JavaScript di Adobe. Se `s_account` non è presente un valore quando il file JavaScript viene caricato, non viene inviato alcun dato a [!DNL Analytics].

Adobe [!DNL DigitalPulse Debugger] visualizza il valore di `s_account` nel percorso dell'URL che appare appena sotto la parola "Immagine", subito dopo /b/ss/. In alcuni casi, il valore di `s_account` viene visualizzato anche nel dominio, prima di 112.2o7.net. Il valore nel percorso è l'unico valore che determina la suite di rapporti di destinazione. Il testo in grassetto riportato di seguito mostra le suite di rapporti a cui vengono inviati i dati, così come appaiono nel debugger. Vedere [Digital Pulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**Sintassi e valori** possibili {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

L'ID suite di rapporti è una stringa alfanumerica di caratteri ASCII, con una lunghezza massima di 40 byte. L'unico carattere non alfanumerico consentito è un trattino. Spazi, punti, virgole e altre punteggiature non consentiti. La `s_account` variabile può contenere più suite di rapporti, tutte le quali ricevono dati da quella pagina.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Tutti i valori di `s_account` devono essere forniti o approvati da Adobe.

**Esempi** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**Configurazione della variabile in Analytics**{#section_7DFB2CCF02F045AFB1AD4F376638393B}

Il nome descrittivo associato a ciascun ID suite di rapporti può essere modificato da Adobe [!DNL Customer Care]. Il nome descrittivo è visibile [!DNL Analytics] nella casella a discesa del sito, nella sezione superiore sinistra della schermata.

**Insidie, domande e suggerimenti**{#section_BFFDA5C0AF31442494B0E02F0925CF93}

* Se `s_account` è vuoto, non dichiarato o contiene un valore imprevisto, non viene raccolto alcun dato.
* Se la `s_account` variabile è un elenco separato da virgole (tag per più suite), non inserite spazi tra gli ID delle suite di rapporti.
* Se [!UICONTROL s.dynamicAccountSelection] è impostato su *True* , l'URL viene utilizzato per determinare la suite di rapporti di destinazione. Utilizzate l'icona [!DNL DigitalPulse Debugger] per determinare le suite di rapporti di destinazione.

* In alcuni casi, [!DNL VISTA] può essere utilizzato per modificare la suite di rapporti di destinazione. Quando si utilizzano cookie di prime parti, o se il sito include più di 20 suite di rapporti attive, si consiglia [!DNL VISTA] di utilizzare per il reindirizzamento o la copia dei dati in un'altra suite di rapporti.

* Dichiarare sempre `s_account` all'interno del file JS o subito prima che venga incluso.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

La variabile consente di selezionare dinamicamente la suite di rapporti in base all'URL di ogni pagina.

>[!NOTE]
>
>`dynamicAccountSelection` non funziona con il tracciamento personalizzato dei collegamenti.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | False |

>[!NOTE]
>
>Entrambi `dynamicAccountList` e `dynamicAccountMatch` vengono ignorati se la `dynamicAccountSelection` variabile non è dichiarata o impostata su 'false'.

**Sintassi e valori** possibili {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Solo 'true' e 'false' sono consentiti come valori di *`dynamicAccountSelection`*.

**Esempi** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**Impostazioni** di configurazione {#section_F052FA38144B4F84B015A263A8E711CF}

Nessuno

**Insidie, domande e suggerimenti**{#section_62F0B0895BC84A05840AEEED0643DE60}

* La selezione di account dinamici non è supportata da [AppMeasurement per JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Usa sempre [!DNL DigitalPulse Debugger] per determinare quale suite di rapporti riceve i dati da ogni pagina.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

[!DNL AppMeasurement] per JavaScript è possibile selezionare in modo dinamico una suite di rapporti alla quale inviare i dati. La variabile contiene le regole utilizzate per determinare la suite di rapporti di destinazione.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Questa variabile viene utilizzata insieme alle *`dynamicAccountSelection`* variabili e *`dynamicAccountMatch`* . Le regole in *`dynamicAccountList`* vengono applicate se *`dynamicAccountSelection`* sono impostate su 'true' e si applicano alla sezione dell'URL specificato in *`dynamicAccountMatch`*.

Se nessuna delle regole in *`dynamicAccountList`* corrisponde all'URL della pagina, viene utilizzata la suite di rapporti identificata in `s_account` . Le regole elencate in questa variabile vengono applicate in ordine da sinistra a destra. Se l'URL della pagina corrisponde a più regole, per determinare la suite di rapporti viene utilizzata la regola più a sinistra. Di conseguenza, le regole più generiche dovrebbero essere spostate a destra dell'elenco.

Negli esempi seguenti, l’URL della pagina è `www.mycompany.com/path1/?prod_id=12345` e `dynamicAccountSelection` è impostato su *true* e `s_account` su `mysuitecom.`

| Valore DynamicAccountList | Valore DynamicAccountMatch | Suite di rapporti per ricevere i dati |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuite ecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**Sintassi e valori** possibili {#section_7360E4354ED345E8BAAE210DBD58A7EC}

La `dynamicAccountList` variabile è un elenco separato da punto e virgola di coppie nome=valore (regole). Ogni parte dell'elenco deve contenere i seguenti elementi:

* uno o più ID suite di rapporti (separati da virgole)
* un segno uguale
* uno o più filtri URL (separati da virgole)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

Nella stringa devono essere utilizzati solo i caratteri ASCII standard (senza spazi).

**Esempi** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**Impostazioni** di configurazione {#section_9F99CD741BC7449B8CCC108094B2EB85}

Nessuno

**Insidie, domande e suggerimenti**{#section_3E10534FCC05457AB67147BB480C8BB3}

* La selezione di account dinamici non è supportata da [AppMeasurement per JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Se l’URL della pagina corrisponde a più regole, viene utilizzata la regola più a sinistra.
* Se nessuna regola corrisponde, viene utilizzata la suite di rapporti predefinita.
* Se la pagina viene salvata sul disco rigido di un utente o tradotta tramite un motore di traduzione basato sul Web (come le pagine tradotte di Google), la selezione dell'account dinamico probabilmente non funzionerà. Per un tracciamento più preciso, compila la `s_account` variabile lato server.
* Le `dynamicAccountSelection` regole si applicano solo alla sezione dell'URL specificato in `dynamicAccountMatch`.

* Quando utilizzate la selezione di account dinamici, accertatevi di eseguire l'aggiornamento *`dynamicAccountList`* ogni volta che ottenete un nuovo dominio.
* Utilizzate l' [!DNL DigitalPulse Debugger] icona quando tentate di identificare la suite di rapporti di destinazione. La `dynamicAccountSelection` variabile sostituisce sempre il valore di `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

La variabile utilizza l'oggetto DOM per recuperare la sezione dell'URL a cui vengono applicate tutte le regole in.

Questa variabile è valida solo se *`dynamicAccountSelection`* è impostata su 'True'. Poiché il valore predefinito è [!DNL window.location.host], questa variabile non è necessaria per [!UICONTROL Dynamic Account Selection] funzionare. Per ulteriori informazioni, vedere [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

Le regole riportate in `dynamicAccountList` vengono applicate al valore di `dynamicAccountMatch`. Se `dynamicAccountMatch` contiene solo [!DNL window.location.host] (impostazione predefinita), le regole in `dynamicAccountList` questione si applicano solo al dominio della pagina.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | window.location.host |

**Sintassi e valori** possibili {#section_95CD81972C22419B80A921CA137D3841}

La `dynamicAccountMatch` variabile viene generalmente compilata dal consulente Adobe che fornisce AppMeasurement per il file JavaScript. Tuttavia, i valori elencati di seguito possono essere applicati in qualsiasi momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descrizione | Valore |
|---|---|
| Dominio (predefinito) | window.location.host |
| Percorso | window.location.pathname |
| Stringa di query | (window.location.search?window.location.search:"?") |
| Dominio e percorso | window.location.host+window.location.pathname |
| Percorso e stringa query | window.location.pathname+(window.location.search?window.location.search:"?") |
| URL completo | window.location.href |

**Esempi** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**Impostazioni** di configurazione {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

Nessuno

**Insidie, domande e suggerimenti**{#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* La selezione di account dinamici non è supportata da [AppMeasurement per JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Quando le pagine vengono salvate su un disco rigido, [!DNL window.location.host] è vuota e tali visualizzazioni di pagina vengono inviate alla suite di rapporti predefinita (in `s_account`).

* Quando una pagina viene tradotta tramite un motore di traduzione basato sul Web, come Google, [!UICONTROL Dynamic Account Selection] non funziona correttamente. Per un tracciamento più preciso, compila la [!UICONTROL s_account]variabile lato server.

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

La variabile consente alla distribuzione di contrassegnare le variabili, che devono essere popolate in modo dinamico.

I cookie, le intestazioni delle richieste e i parametri delle stringhe delle query sulle immagini possono essere compilati in modo dinamico.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | D= | Any | D= |

**Sintassi e valori** possibili {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

OPPURE UTILIZZARE IL FLAG PERSONALIZZATO PER LE VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

**Esempi** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

OPPURE UTILIZZARE IL FLAG PERSONALIZZATO PER LE VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**Insidie, domande e suggerimenti**{#section_6889908FBD78488D955F67DDB17617B1}

* Le variabili dinamiche possono essere utilizzate per ridurre notevolmente la lunghezza totale dell’URL copiando i valori in altre variabili.
* Le variabili dinamiche possono essere utilizzate per raccogliere dati da intestazioni e cookie non altrimenti disponibili per la raccolta dei dati.

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

La proprietà charSet, normalmente impostata nel file JavaScript, viene utilizzata da Analytics per convertire i dati in entrata in UTF-8 per l'archiviazione e il reporting da parte di Analytics.

>[!N] Nota: La proprietà charSet è obbligatoria quando si inviano dati a una suite di rapporti multibyte e non deve mai essere utilizzata con una suite di rapporti standard. L'impostazione della proprietà charSet con una suite di rapporti ISO standard può determinare il troncamento variabile o una conversione di caratteri imprevista.

Il valore della proprietà charSet deve corrispondere alla codifica della pagina Web nel tag META o nell'intestazione http, anche se la sintassi può variare leggermente. Anche se il tag META può utilizzare un alias per la codifica, il valore di charSet deve utilizzare il nome preferito (o ufficiale) della codifica.

Alcune delle codifiche più comuni con il nome e gli alias preferiti sono elencate nella tabella seguente.

| Nome preferito | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cicrilico |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Poiché esistono numerose codifiche e alias, contatta il tuo Consulente per l’implementazione o l’Assistenza clienti Adobe per confermare il valore corretto per charSet, se non viene visualizzato nella tabella precedente.

Se un sito dispone di codifiche Web diverse su pagine diverse, o se per più siti viene utilizzato un singolo file JavaScript, la proprietà charSet può essere impostata su un valore predefinito nel file JavaScript e quindi reimpostata su pagine specifiche, in base alle esigenze, per ignorare il valore predefinito; ad esempio `s.charSet="UTF-8"` o `s.charSet="SJIS"`.

Qualsiasi valore non vuoto del parametro charSet causerà la conversione dei dati in UTF-8 per l'archiviazione. Tutti i caratteri nell'intervallo 128-255 saranno convertiti nella sequenza UTF-8 a due byte corretta e memorizzati. Questi caratteri non verranno visualizzati correttamente in una suite di rapporti standard. Pertanto, la proprietà charSet non deve mai essere utilizzata con una suite di rapporti standard.

Analogamente, un valore vuoto del parametro charSet bypasserà il processo di conversione dei dati e tutti i caratteri compresi nell'intervallo 128-255 saranno memorizzati come un singolo byte. Questi caratteri non verranno visualizzati correttamente in una suite di rapporti multibyte, poiché i codici a byte singolo per questi caratteri non sono UTF-8 validi. Pertanto, il parametro charSet deve sempre essere utilizzato con una suite di rapporti multibyte. Inoltre, il valore corretto deve essere utilizzato per la codifica delle pagine Web.

Se la *`charSet`* variabile contiene un valore non corretto, i dati di tutte le altre variabili vengono convertiti in modo non corretto. Se variabili JavaScript nelle pagine (ad esempio *`pageName`*, [!UICONTROL prop1]o *`channel`*) contengono solo caratteri ASCII, *`charSet`* non è necessario definirli. Tuttavia, se le variabili nelle pagine contengono caratteri non ASCII, è necessario compilare la *`charSet`* variabile.

**Parametri**

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | CE | N/D | "" |

**Sintassi e valori** possibili {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**Esempi** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

La variabile determina il tasso di conversione da applicare alle entrate.

Tutti gli importi monetari sono memorizzati in una valuta di vostra scelta. Se la valuta è la stessa specificata in *`currencyCode`*, o *`currencyCode`* è vuota, non viene applicata alcuna conversione.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | cc | Conversione &gt; Acquisti &gt; Ricavi Tutti i rapporti Conversione che mostrano i valori di ricavi o monetari | "USD" |

Se il sito consente ai visitatori di acquistare in più valute, è necessario utilizzare la *`currencyCode`* variabile per assicurarsi che le entrate siano memorizzate nella valuta appropriata. Ad esempio, se la valuta di base per la suite di rapporti è USD e si vende un articolo per 40 Euro, è necessario compilare il *`currencyCode`* campo con "EUR" nella pagina HTML. Non appena la raccolta dei dati riceve i dati, utilizza il tasso di conversione corrente per convertire i 40 euro nel suo equivalente in USD.

La compilazione della *`currencyCode`* variabile sulla pagina HTML invece che nel file JavaScript è consigliabile se si vende in più valute. Se si desidera utilizzare i tassi di conversione personalizzati invece che quelli utilizzati da Adobe, impostare l'opzione su un valore pari *`currencyCode`* alla valuta di base della suite di rapporti. Quindi tutte le entrate vengono convertite prima di inviarle [!DNL Analytics].

La conversione della valuta è valida sia per i ricavi che per eventuali eventi di valuta. Si tratta di eventi che vengono utilizzati per sommare valori simili alle entrate, come tasse e spedizioni. Gli eventi relativi alle entrate e alla valuta sono specificati nella stringa products. Per ulteriori informazioni sui prodotti, vedere [Eventi](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE).

**Sintassi e valori** possibili {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

**Esempi** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**Impostazioni** di configurazione {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] può modificare l'impostazione della valuta predefinita per la suite di rapporti. Quando si modifica la valuta di base per una suite di rapporti, i ricavi esistenti nel sistema non vengono convertiti. Tutti i nuovi valori delle entrate verranno convertiti di conseguenza.

**Insidie, domande e suggerimenti**{#section_08A80A87B54A4861905953A6FA61FF8F}

* Se notate sorprendentemente grandi quantità di ricavi nei report, accertatevi che la *`currencyCode`* variabile e la valuta di base della suite per report siano impostate correttamente.
* La *`currencyCode`* variabile non è persistente, il che significa che deve essere passata nella stessa richiesta di immagine come qualsiasi altro dato relativo alle entrate o alla valuta.
* Gli eventi valutari non devono essere utilizzati a fini non valutari. Se è necessario contare valori arbitrari o dinamici che non sono valuta, utilizzare il tipo di [!UICONTROL numeric] evento.
* Se la *`currencyCode`* variabile è vuota, non viene applicata alcuna conversione.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

La variabile determina il dominio in cui [!DNL Analytics] sono impostati i cookie `s_cc` e `s_sq` .

Comunemente, `s.cookieDomainPeriods` è utilizzato per generare `s.cookieDomain` da `window.location.hostnam`e. Invece di utilizzare `s.cookieDomainPeriods`, potete impostare esplicitamente `s.cookieDomain` ciò che desiderate utilizzare nell'implementazione. Ad esempio, puoi impostare i cookie sul nome di pagina completo utilizzando:

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Questa variabile viene utilizzata anche da alcuni plug-in per determinare il dominio corretto per impostare il cookie del plug-in.

Il valore predefinito per *`cookieDomainPeriods`* è "2". Questo è il valore utilizzato se *`cookieDomainPeriods`* viene omesso. Ad esempio, utilizzando il dominio `www.mysite.com`, *`cookieDomainPeriods`* dovrebbe essere "2". Ad `www.mysite.co.jp`esempio, *`cookieDomainPeriods`* dovrebbe essere "3".

Se *`cookieDomainPeriods`* è impostato su "2" ma il dominio contiene tre punti, il file JavaScript tenta di impostare i cookie sul suffisso del dominio.

Ad esempio, se si imposta *`cookieDomainPeriods`* "2" sul dominio `www.mysite.co.jp`, i `s_cc` cookie e `s_sq` i cookie vengono creati sul dominio `co.jp`. Poiché `co.jp` è un dominio non valido, quasi tutti i browser rifiutano questi cookie. Di conseguenza, i dati delle mappe dei clic dei visitatori vengono persi e il rapporto [!UICONTROL Visitor Profile] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] indica che quasi il 100% dei visitatori rifiuta i cookie.

Se *`cookieDomainPeriods`* è impostato su "3" ma il dominio contiene solo due punti, il file JavaScript imposta i cookie sul sottodominio del sito. Ad esempio, se si imposta *`cookieDomainPeriods`* "3" sul dominio `www2.mysite.com`, i `s_cc` cookie e `s_sq` i cookie vengono creati sul dominio `www2.mysite.com`. Quando un visitatore accede a un altro sottodominio del sito (ad esempio `www4.mysite.com`), non `www2.mysite.com` è possibile leggere tutti i cookie impostati con.

>[!NOTE]
>
>Non includete sottodomini aggiuntivi come parte di *`cookieDomainPeriods`*. Ad esempio, `store.toys.mysite.com` avrebbe comunque *`cookieDomainPeriods`* impostato su "2". Questa definizione di variabile imposta correttamente i cookie sul dominio principale [!DNL mysite.com]. L'impostazione *`cookieDomainPeriods`* su "3" in questo esempio imposta i cookie sul dominio [!DNL toys.mysite.com], con le stesse implicazioni dell'esempio precedente.

Vedere anche [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | CDP | Interessa più rapporti in quanto controlla il modo in cui l’ID visitatore viene memorizzato e gestito. | "2" |

>[!NOTE]
>
>Alcuni servizi di cloud computing sono considerati Domini di primo livello, che non consentono la scrittura di cookie. (ad esempio `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`ecc.) Se implementi questi servizi, potresti essere potenzialmente influenzato dall'impostazione della privacy di Analytics che rimuove gli utenti che hanno bloccato tutti i cookie se non hai impostato il tuo dominio (ad esempio, se stai testando la tua implementazione). In questo caso, qualsiasi hit in cui il sistema ha determinato che i cookie sono disattivati, non funzionali o inaccessibili viene escluso e quindi escluso dalla segnalazione.

**Esempi** {#section_4218BE29FA5E49F58975A2094329B268}

Impostazione manuale della variabile:

```js
s.cookieDomainPeriods = "3";
```

Diversi esempi per impostare in modo dinamico la variabile se il file JavaScript di base contiene entrambi i tipi:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**Insidie, domande e suggerimenti**{#section_F3BE3F039E5C4359B694DBB61369822C}

* Se noti che i dati della mappa del clic del visitatore sono assenti o che il rapporto [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] mostra una grande percentuale di visitatori che rifiutano i cookie, verifica che il valore di *`cookieDomainPeriods`* sia corretto.

* Se *`cookieDomainPeriods`* è superiore al numero di sezioni del dominio, i cookie verranno impostati con l'intero dominio. Ciò può causare la perdita di dati quando i visitatori passano da un sottodominio all'altro.
* La *`cookieDomainPeriods`* variabile è stata utilizzata nelle implementazioni obsolete prima di *`trackingServer`* impostare il cookie ID visitatore. Anche se presente solo in codice obsoleto, la mancata definizione corretta *`cookieDomainPeriods`* in questa circostanza mette la vostra implementazione a rischio di perdita di dati.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

La variabile si riferisce ai cookie impostati da JavaScript (s_sq, s_cc, plug-in) che sono intrinsecamente cookie di prime parti anche se la vostra implementazione utilizza i domini di terze parti 2o7.net o omtrdc.net.

La *`fpCookieDomainPeriods`* variabile non deve mai essere impostata dinamicamente. Se si utilizza *`cookieDomainPeriods`*, è buona norma specificare *`fpCookieDomainPeriods`* anche un valore. *`fpCookieDomainPeriods`* eredita il *`cookieDomainPeriods`* valore. Tieni presente che *`fpCookieDomainPeriods`* non influisce sul dominio in cui è impostato il cookie dell’ID visitatore, anche se l’implementazione lo tratta come cookie di prime parti.

Il nome " *`fpCookieDomainPeriods`*" si riferisce al numero di punti (".") nel dominio quando il dominio inizia con "www." Ad esempio, `www.mysite.com` contiene due periodi, mentre `www.mysite.co.jp` contiene tre periodi. Un altro modo per descrivere la variabile è il numero di sezioni nel dominio principale del sito (due per `mysite.com` e tre per `mysite.co.jp`).

Il file [!DNL AppMeasurement] per JavaScript utilizza la *`fpCookieDomainPeriods`* variabile per determinare il dominio con cui impostare cookie di prime parti diversi dal cookie [!UICONTROL visitor ID] (s_vi). Questa variabile ha almeno due cookie, tra cui s_sq e s_cc (utilizzati rispettivamente per il controllo delle mappe dei clic dei visitatori e dei cookie). Anche i cookie utilizzati da plug-in come [!UICONTROL getValOnce] vengono modificati.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | cookieDomainPeriods |

**Codice di esempio per l'impostazione delle variabili** di dominio del cookie {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**Sintassi e valori** possibili {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

La *`cookieDomainPeriods`* variabile deve essere una stringa, come illustrato di seguito.

```js
s.fpCookieDomainPeriods="3"
```

**Esempi** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**Impostazioni** di configurazione {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

Nessuno

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

La variabile viene utilizzata sia dai server JavaScript che dai server di raccolta dati per determinare la durata di vita di un cookie.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | cl | Traffico &gt; Tecnologia &gt; Cookie Tutti i rapporti relativi ai visitatori | "" |

Se *`cookieLifetime`* è impostato, sostituisce qualsiasi altra scadenza del cookie per i server JavaScript e di raccolta dati, con una delle eccezioni descritte di seguito. La *`cookieLifetime`* variabile può avere uno dei tre valori seguenti:

* [!DNL Analytics] Cookie
* Cookie
* Impostazioni e plug-in JavaScript

**Sintassi e valori** possibili {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

I valori possibili sono elencati di seguito:

* ""
* "NONE"
* "SESSION"
* Un numero intero che rappresenta il numero di secondi fino alla scadenza

**Esempi** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**Impostazioni** di configurazione {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

Nessuno

**Insidie, domande e suggerimenti**{#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* influisce sul [!DNL Analytics] tracciamento. Se, ad esempio, *`cookieLifetime`* è di due giorni, i rapporti sui visitatori univoci mensili, trimestrali e annuali non saranno corretti. Prestate attenzione quando impostate *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

La variabile è un riferimento alla funzione e consente di richiamare la funzione nella posizione appropriata all'interno del file JavaScript.

La *`s_doPlugins`* funzione viene chiamata ogni volta che si verifica una delle seguenti situazioni:

* La *`t()`* funzione viene chiamata
* La *`tl()`* funzione viene chiamata
* Fate clic su un collegamento di uscita o di download
* Viene fatto clic su qualsiasi elemento di pagina tracciato dalla mappa clic del visitatore

La *`doPlugins`* funzione viene utilizzata per eseguire routine personalizzate per raccogliere o modificare i dati. Se utilizzate un nome di oggetto diverso da "s", accertatevi che l'oggetto *`s_doPlugins`* sia rinominato in modo appropriato. Ad esempio, se il nome dell'oggetto è s_mc, la *`s_doPlugins`* funzione deve essere denominata s_mc_doPlugins.

**Sintassi e valori** possibili {#section_5CFB94598521455E80947964A306EA89}

La *`s_doPlugins`* funzione non deve essere racchiusa tra virgolette e *`doPlugins`* deve essere sempre assegnata al nome esatto della *`s_doPlugins`* funzione (se la funzione viene rinominata).

```js
s.doPlugins=s_doPlugins;
```

**Esempi** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**Impostazioni** di configurazione {#section_641F0EC55E3349E5A3F8671446797074}

Nessuno

**Insidie, domande e suggerimenti**{#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* L'unico motivo per cambiare il nome dell'oggetto (ad esempio da s a s_mc) è se condividete contenuto con altri clienti o estraete contenuto da essi. Se si rinomina la *`s_doPlugins`* funzione per [!UICONTROL s_mc_doPlugins] assicurare che il file JavaScript di un altro client non sovrascriva la *`doPlugins`* funzione,

* Se iniziate inaspettatamente a richiamare contenuti da un altro cliente Adobe e la vostra *`s_doPlugins`* funzione viene sovrascritta, è possibile rinominare semplicemente la *`s_doPlugins`* funzione senza modificare il nome dell'oggetto. La soluzione migliore è utilizzare un nome oggetto diverso rispetto ad altri file JavaScript sulla stessa pagina, ma non è necessario farlo.

## s.registerPreTrackCallback e s.registerPostTrackCallback

Queste funzioni assumono come parametri: il callback (una funzione) e i parametri di tale funzione. Ad esempio:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

La callback viene richiamata con i parametri `requestUrl` e tutti quelli passati quando la callback viene registrata. Ciò si verifica prima o dopo la chiamata di tracciamento, a seconda del metodo utilizzato per registrare il callback.

L'ordine in cui vengono chiamate queste callback non è garantito. I callback registrati nella funzione pre vengono richiamati dopo la creazione dell'URL di tracciamento finale. Le callback di post vengono richiamate a una chiamata di tracciamento riuscita (se la chiamata di tracciamento non riesce, queste funzioni non vengono chiamate). Qualsiasi callback registrato con `registerPreTrackCallback` non influisce sulla chiamata di tracciamento. Inoltre, non è consigliabile chiamare uno dei metodi di tracciamento in qualsiasi callback registrato e potrebbe causare un ciclo infinito.

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

Impostate su 'true' se desiderate tenere traccia dei collegamenti ai file scaricabili sul sito.

Se *`trackDownloadLinks`* è 'true', *`linkDownloadFileTypes`* viene utilizzato per determinare quali collegamenti sono file scaricabili.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

La *`trackDownloadLinks`* variabile deve essere impostata su "false" solo se non sono presenti collegamenti ai file scaricabili sul sito, oppure se non si desidera tenere traccia del numero di clic sui file scaricabili. Se *`trackDownloadLinks`* è 'true', quando si fa clic su un collegamento per il download di un file, i dati vengono inviati immediatamente a [!DNL Analytics]. I dati inviati con un collegamento per il download includono l’URL del download del collegamento e il clic del visitatore sulla mappa dei dati per tale collegamento. Se *`trackDownloadLinks`* è 'false', il visitatore fa clic sui dati della mappa per i collegamenti ai file scaricabili sul sito probabilmente non sarà incluso nei rapporti.

**Sintassi e valori** possibili {#section_828492CC2A144BC68D18C30CF397EEFC}

La *`trackDownloadLinks`* variabile deve essere 'true' o 'false'.

**Esempi** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```
js
s.trackDownloadLinks=true 
```

```
js
s.trackDownloadLinks=false
```

**Impostazioni** di configurazione {#section_9A5F69966BAF433A8DA2BCF655A652D1}

Nessuno

**Insidie, domande e suggerimenti**{#section_B3764520D81143968F96CB69AADD457F}

* Quando *`trackDownloadLinks`* è 'false', i collegamenti che le persone usano per scaricare i file sul tuo sito sono probabilmente sotto segnalati nella mappa clic del visitatore.
* Quando *`trackDownloadLinks`* è "true", i dati vengono inviati ogni volta che un visitatore fa clic su un collegamento per il download di un file.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

Se è "true" e vengono utilizzati per determinare se un collegamento selezionato è un collegamento di uscita.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

La *`trackExternalLinks`* variabile deve essere impostata su "false" solo se sul sito non sono presenti collegamenti di uscita o se non si desidera tenere traccia del numero di clic su tali collegamenti di uscita. Un collegamento di uscita è qualsiasi collegamento che porta un visitatore fuori dal sito. Se *`trackExternalLinks`* 'true', quando fai clic su un collegamento di uscita i dati di tracciamento vengono inviati immediatamente. I dati inviati con un collegamento di uscita includono l’URL del collegamento, il nome del collegamento e i dati della mappa del clic del visitatore per tale collegamento. Se *`trackExternalLinks`* è 'false', è probabile che i dati della mappa di clic del visitatore per i collegamenti di uscita sul sito siano sotto segnalazione.

**Sintassi e valori** possibili {#section_267748949A7544658E1D838AAEF964B2}

La *`trackExternalLinks`* variabile deve essere 'true' o 'false'.

```
js
s.trackExternalLinks=true|false
```

**Esempi** {#section_EF18DB05884240F5B5062631E68E10A7}

```
js
s.trackExternalLinks=true 
```

```
js
s.trackExternalLinks=false
```

**Impostazioni** di configurazione {#section_C8748CFE36324FAFB14C23E3E1FB5082}

Nessuno

**Insidie, domande e suggerimenti**{#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* Quando *`trackExternalLinks`* è 'false', i collegamenti che portano le persone lontano dal sito sono probabilmente sotto segnalati nella mappa clic del visitatore.
* Quando *`trackExternalLinks`* è "true", i dati vengono inviati ogni volta che un visitatore fa clic su un collegamento di uscita (prima del caricamento della destinazione del collegamento).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

La variabile determina se i dati ClickMap vengono raccolti o meno.

Se *`trackInlineStats`* è "true", i dati sulla pagina e il collegamento su cui si fa clic vengono memorizzati in un cookie denominato s_sq. Se 'false', s_sq avrà un valore di "[[B]]", che viene considerato null.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | ClickMap | False |

**Sintassi e valori** possibili {#section_46B2C1DD0D104A01A9C239929420CD90}

```
js
s.trackInlineStats=true|false
```

La *`trackInlineStats`* variabile deve essere 'true' o 'false'.

**Esempi** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**Impostazioni** di configurazione {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

Nessuno

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

La variabile è un elenco separato da virgole di estensioni di file.

Se il sito contiene collegamenti a file con una di queste estensioni, gli URL di questi collegamenti verranno visualizzati nel [!UICONTROL File Downloads] rapporto.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Traffico &gt; Traffico sito &gt; Download file | "exe,zip,wav,mp3,mov,mpg,avi,wmv, doc,pdf,xls" |

La *`linkDownloadFileTypes`* variabile è pertinente solo se *`trackDownloadLinks`* è impostata su "True".

Nel [!UICONTROL File Downloads] rapporto vengono contati solo i clic con il pulsante sinistro del mouse su un collegamento. Tutti i download di file che iniziano automaticamente quando una pagina viene caricata, o che vengono scaricati solo dopo un reindirizzamento, non vengono conteggiati nel [!UICONTROL File Downloads] rapporto. Quando fai clic con il pulsante destro del mouse su un file e seleziona "Salva destinazione con nome..." non viene conteggiata nel [!UICONTROL File Downloads] rapporto.

La *`linkDownloadFileTypes`* variabile può essere utilizzata per monitorare i clic sui feed RSS. Se disponete di collegamenti ai feed RSS con un .xml o un'altra estensione, aggiungendo ",xml" all' *`linkDownloadFileTypes`* elenco potete vedere la frequenza con cui viene fatto clic su ogni collegamento RSS.

**Sintassi e valori** possibili {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

Includete solo estensioni di file (senza spazi).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

Qualsiasi estensione di file può essere inclusa nell'elenco. Fate attenzione a non includere un'estensione file comune, come htm o aspx, in *`linkDownloadFileTypes`*. In questo modo viene inviata una richiesta immagine aggiuntiva per ogni clic, che verrà fatturata come chiamata server principale.

**Esempi** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**Impostazioni** di configurazione {#section_CE24D5852E4D441A958A4EDDB82382A7}

Nessuno

**Insidie, domande e suggerimenti**{#section_786CF22D5553429EB6524B13774793BC}

* Nel [!UICONTROL File Downloads] rapporto vengono visualizzati solo i clic con il pulsante sinistro del mouse sui file di download.
* L'inclusione di un'estensione di file comune in *`linkDownloadFileTypes`* potrebbe aumentare notevolmente il totale delle chiamate server inviate ai server Adobe.
* I collegamenti ai reindirizzamenti sul lato server o alle pagine HTML che iniziano automaticamente il download di un file non vengono conteggiati a meno che l'estensione del file non sia inclusa *`linkDownloadFileTypes`*.
* I collegamenti che utilizzano JavaScript (come javascript:openLink( )) non vengono conteggiati nei download dei file.

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

La variabile viene utilizzata per determinare quali collegamenti sul sito sono collegamenti di uscita.

Si tratta di un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Percorsi &gt; Voci ed uscite &gt; Esci dai collegamenti |  |

>[!NOTE]
>
>In precedenza avevamo suggerito di impostare linkInternalFilters su javascript:. Tuttavia, ciò ha comportato la visualizzazione di tutti i domini esterni, compreso il dominio corrente su cui risiede il tag. Se desiderate che più domini siano considerati interni, potete aggiungerli, come mostrato negli esempi seguenti.

La *`linkInternalFilters`* variabile viene utilizzata per determinare se un collegamento è un collegamento di uscita, definito come qualsiasi collegamento che allontani un visitatore dal sito. Se la finestra di destinazione di un collegamento di uscita è una finestra a comparsa o una finestra esistente, il collegamento non influisce sulla visualizzazione del collegamento nel rapporto dei collegamenti di uscita. I collegamenti di uscita vengono tracciati solo se *`trackExternalLinks`* è impostata su `"true"`. (Per informazioni su come Gestione dinamica dei tag gestisce i collegamenti di uscita, consulta [Tracciamento](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) dei collegamenti nella documentazione di Gestione dinamica dei tag.) I filtri non *`linkInternalFilters`* fanno distinzione tra maiuscole e minuscole.

Per impostazione predefinita, l’elenco dei filtri *`linkInternalFilters`* si applica al dominio e al percorso di qualsiasi collegamento. Se *`linkLeaveQueryString`* è impostato su `"true"`, i filtri si applicano all’intero URL (dominio, percorso e stringa di query). I filtri vengono sempre applicati al percorso assoluto dell'URL, anche se come valore href viene utilizzato un percorso relativo.

Fai attenzione a includere tutti i domini del tuo sito (e tutti i partner che utilizzano il file JavaScript) in *`linkInternalFilters`*. Se non hai tutti i domini inclusi nell'elenco, tutti i collegamenti a tali domini vengono considerati collegamenti di uscita, aumentando le chiamate al server inviate. Se si desidera che più domini o società utilizzino un singolo [!DNL AppMeasurement] per il file JavaScript, è consigliabile compilare *`linkInternalFilters`* la pagina, ignorando il valore specificato nel file JavaScript. Se hai domini vanità che si reindirizzano immediatamente al tuo dominio principale, quei domini vanità non devono essere inclusi nell'elenco.

L’esempio seguente illustra come viene utilizzata questa variabile. In questo esempio, l’URL della pagina è `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**Sintassi e valori** possibili {#section_810966F09912415B96EA9C2EDAE0CEA0}

La *`linkInternalFilters`* variabile è un elenco separato da virgole di caratteri ASCII. Non sono consentiti spazi.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**Esempi** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**Impostazioni** di configurazione {#section_546AC1FACB664ABFBCF312990097C987}

Nessuno

**Insidie, domande e suggerimenti**{#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Includete tutti i domini in cui può essere servito il file [!DNL AppMeasurement] per JavaScript nell'elenco dei filtri.
* Controllate periodicamente il rapporto [!UICONTROL Paths] &gt; [!UICONTROL Entries & Exits] &gt; [!UICONTROL Exit] Collegamenti per verificare che nessuna delle voci del rapporto sia corretta.

* Rivedete periodicamente i contratti dei partner per determinare se contengono restrizioni al tracciamento dei collegamenti. Ad esempio, potrebbe essere vietato tenere traccia dei collegamenti visualizzati negli annunci visualizzati dai partner. Filtra i collegamenti dei partner aggiungendo il dominio a *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeftQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

Per impostazione predefinita, le stringhe di query sono escluse da tutti i rapporti.

Per alcuni collegamenti di uscita e di download, la parte importante dell’URL può trovarsi nella stringa di query, come illustrato nell’URL di esempio seguente.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

Il nome del file di download può essere definito nella stringa di query e, di conseguenza, la stringa di query è necessaria per rendere il [!UICONTROL File Downloads] rapporto più accurato.

La *`linkLeaveQueryString`* variabile determina se la stringa di query deve essere inclusa nei [!UICONTROL Exit Links] report e [!UICONTROL File Download] .

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|--- |--- |--- |--- |
| N/D | N/D | Esci dai download dei file dei collegamenti | false |

>[!NOTE]
>
>L'impostazione `linkLeaveQueryString=true` include tutti i parametri della stringa di query per tutti i collegamenti di uscita e i collegamenti di download.

**Sintassi** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**Esempi** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**Valori possibili**{#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**Impostazioni** di configurazione {#section_835FD74D3CA9425A9D091CACF88A6F1F}

Per questa variabile non è necessaria alcuna configurazione.

**Insidie, domande e suggerimenti**{#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* L'impostazione `s.linkLeaveQueryString=true` include tutti i parametri della stringa di query per tutti i collegamenti di uscita e i collegamenti di download.
* La `linkLeaveQueryString` variabile non influisce sugli URL delle pagine registrati, sulla mappa clic del visitatore o sui [!UICONTROL Path] rapporti.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

La variabile è un elenco separato da virgole di variabili che vengono inviate con collegamenti personalizzati, di uscita e di download.

Se *`linkTrackVars`* è impostato su "", tutte le variabili con valori vengono inviate con dati di collegamento. Per evitare l'inflazione delle istanze o delle visualizzazioni di pagina associate ad altre variabili, Adobe consiglia di compilare *`linkTrackVars`* e *`linkTrackEvents`* nel [!UICONTROL onClick] caso di un collegamento utilizzato per il tracciamento dei collegamenti.

Tutte le variabili che devono essere inviate con dati di collegamento (collegamenti personalizzati, di uscita e di download) devono essere elencate in *`linkTrackVars`*. Se *`linkTrackEvents`* viene utilizzato, *`linkTrackVars`* deve contenere "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Any | "Nessuno" |

Durante la compilazione *`linkTrackVars`*, non utilizzare 's.'.per le variabili. Ad esempio, invece di compilare *`linkTrackVars`* con "s.prop1", è consigliabile compilarlo con "prop1". L'esempio seguente illustra come *`linkTrackVars`* utilizzare il prodotto.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Poiché il collegamento a google.com è un collegamento di uscita (a meno che non siate Google), event1 e eVar1 vengono inviati con i dati del collegamento di uscita, aumentando le istanze associate a eVar1 e il numero di volte in cui event1 viene attivato. Nel collegamento a [!DNL test.php], [!UICONTROL eVar1] viene inviato con il valore "C", perché corrisponde al valore corrente di [!UICONTROL eVar1] al momento in cui *`tl()`* viene chiamato.

**Sintassi e valori** possibili {#section_DCC239F5CFE74959856764DAB1862BA7}

La *`linkTrackVars`* variabile è un elenco di nomi di variabili con distinzione tra maiuscole e minuscole, senza il prefisso del nome dell'oggetto. Utilizzate 'eVar1' invece di 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La *`linkTrackVars`* variabile può contenere solo variabili a cui è inviato [!DNL Analytics], ovvero: *`events`*, *`campaign`*, *`purchaseID`*, *`products`*, [!UICONTROL eVar1-75], [!UICONTROL prop1-75], [!UICONTROL hier1-5], *`channel`*, *`server`*, *`state`**`zip`**`pageType`*, , e .

**Esempi** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**Impostazioni** di configurazione {#section_E387604B8A434A7F89A82A886649A89D}

Nessuno

**Insidie, domande e suggerimenti**{#section_99E0783A608C4462945F35D21AB4AC2B}

* Se *`linkTrackVars`* è vuoto, tutte le variabili con valori vengono tracciate con tutte le chiamate server.
* Vengono tracciate tutte le variabili elencate in *`linkTrackVars`* cui è associato un valore al momento del download, dell'uscita o del collegamento personalizzato.
* Se *`linkTrackEvents`* viene utilizzato, *`linkTrackVars`* deve contenere "events".

* Non utilizzare "s". o "s_objectname." per le variabili.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

La variabile è un elenco separato da virgole di eventi inviati con un [!UICONTROL custom], [!UICONTROL exit]o [!UICONTROL download] collegamento.

Se un evento non si trova in *`linkTrackEvents`*, non viene inviato a [!DNL Analytics], anche se viene popolato in [!UICONTROL onClick] caso di collegamento, come illustrato nell'esempio seguente:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

Nel primo collegamento a [!DNL help.php], la variabile degli eventi mantiene il valore impostato prima che sia fatto clic sul collegamento. Questo consente di inviare event1 con il collegamento personalizzato. Nel secondo esempio, il collegamento a [!DNL test.php], event2 non viene registrato perché non è elencato in *`linkTrackEvents`*.

Per evitare confusione e potenziali problemi, Adobe consiglia di compilare *`linkTrackVars`* e *`linkTrackEvents`* nel [!UICONTROL onClick] caso di un collegamento utilizzato per il tracciamento dei collegamenti.

La *`linkTrackEvents`* variabile contiene gli eventi da inviare con [!UICONTROL custom], [!UICONTROL download]e [!UICONTROL exit] i collegamenti. Questa variabile viene considerata solo se *`linkTrackVars`* contiene "events".

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Conversione | "Nessuno" |

**Sintassi e valori** possibili {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

La *`linkTrackEvents`* variabile è un elenco di eventi separati da virgole (senza spazi).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

In *`linkTrackEvents`*. Questi eventi sono elencati in [Eventi](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Se uno spazio compare prima o dopo il nome dell’evento, l’evento non può essere inviato con richieste di immagini di collegamento.

**Esempi** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**Impostazioni** di configurazione {#section_D938A47346D94A0C9E98FB327F2EF349}

Nessuno

**Insidie, domande e suggerimenti**{#section_DBB68BECC9D44380816113DB2566C38C}

* Il file JavaScript viene utilizzato solo *`linkTrackEvents`* se *`linkTrackVars`* contiene la variabile "events". "events" deve essere incluso *`linkTrackVars`* solo quando *`linkTrackEvents`* è definito.

* Attenzione se un evento viene attivato su una pagina ed è elencato in *`linkTrackEvents`*. Tale evento viene registrato nuovamente con eventuali [!UICONTROL exit], [!UICONTROL download]o [!UICONTROL custom] collegamenti, a meno che la variabile degli eventi non venga reimpostata prima di tale evento (in [!UICONTROL onClick] un collegamento o dopo la chiamata alla *`t()`* funzione).

* Se *`linkTrackEvents`* contiene spazi tra i nomi degli eventi, gli eventi non vengono registrati.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

Se il sito contiene molti collegamenti a siti esterni e non si desidera tenere traccia di tutti i collegamenti di uscita, utilizzare per creare rapporti su un sottoinsieme specifico di collegamenti di uscita.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | Percorsi &gt; Voci ed uscite &gt; Esci dai collegamenti | "" |

La *`linkExternalFilters`* variabile è una variabile opzionale utilizzata insieme *`linkInternalFilters`* per determinare se un collegamento è un collegamento di uscita. Un collegamento di uscita è definito come qualsiasi collegamento che allontani un visitatore dal sito. A prescindere dal fatto che la finestra di destinazione di un collegamento di uscita sia una finestra a comparsa o una finestra esistente, il collegamento non influisce sulla sua visualizzazione nel rapporto dei collegamenti di uscita. I collegamenti di uscita vengono tracciati solo se *`trackExternalLinks`* è impostato su 'true'. I filtri in *`linkExternalFilters`* e *`linkInternalFilters`* non fanno distinzione tra maiuscole e minuscole.

>[!NOTE]
>
>Se non si desidera utilizzare *`linkExternalFilters`*, cancellarlo o impostarlo su "".

L'elenco dei filtri *`linkExternalFilters`* e *`linkInternalFilters`* si applica al dominio e al percorso di qualsiasi collegamento per impostazione predefinita. Se *`linkLeaveQueryString`* è impostato su 'true', i filtri si applicano all'intero URL (dominio, percorso e stringa di query). Questi filtri vengono sempre applicati al percorso assoluto dell'URL, anche se come valore href viene utilizzato un percorso relativo.

La maggior parte delle aziende ritiene che *`linkInternalFilters`* gli dia un controllo sufficiente sui collegamenti di uscita di cui non hanno bisogno *`linkExternalFilters`*. Utilizzando *`linkExternalFilters`* semplicemente diminuisce la probabilità che un collegamento di uscita venga considerato esterno. Se *`linkExternalFilters`* ha un valore, un collegamento viene considerato esterno solo se non corrisponde *`linkInternalFilters`* e non corrisponde *`linkExternalFilters`*.

L’esempio seguente illustra come viene utilizzata questa variabile. In questo esempio, l’URL della pagina è `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**Sintassi e valori** possibili {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

La *`linkExternalFilters`* variabile è un elenco separato da virgole di caratteri ASCII. Non sono consentiti spazi.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Qualsiasi parte di un URL può essere inclusa in *`linkExternalFilters`*, separata da virgole.

**Esempi** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**Impostazioni** di configurazione {#section_2D0CA911855B4B3698145FC18D5021C3}

Nessuno

**Insidie, domande e suggerimenti**{#section_8B40E6F539E3473B934A8DB7C5086D73}

* L'utilizzo *`linkExternalFilters`* può ridurre i collegamenti del sito. Non utilizzare questa variabile invece di *`linkInternalFilters`* forzare i collegamenti interni a diventare collegamenti di uscita.

* Se *`linkExternalFilters`* si desidera applicare alla stringa di query di un collegamento, assicurarsi che *`linkLeaveQueryString`* sia impostata su 'true'. Vedere [linkLasciaQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) prima dell'impostazione su `"true"`.

* Per disattivare il tracciamento dei collegamenti di uscita, impostate *`trackExternalLinks`* su `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

Se la funzione è disponibile e contiene codice utile, [!UICONTROL s_usePlugins] impostare su 'true'.

Quando [!UICONTROL usePlugins] è 'true', la *`s_doPlugins`* funzione viene chiamata prima di ogni richiesta di immagine.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

**Sintassi e valori** possibili {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

La [!UICONTROL usePlugins] variabile deve essere 'true' o 'false'.

**Esempi** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

La [!UICONTROL usePlugins] variabile deve essere false (o non dichiarata) solo se la *`s_doPlugins`* funzione non è dichiarata nel file JavaScript.

**Impostazioni** di configurazione {#section_DFD41717134147E988B6AFC7DE5BB9E3}

Nessuno