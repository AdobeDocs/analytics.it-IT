---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Implementazione di Analytics
seo-description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
seo-title: Variabili di pagina
solution: Analytics
subtopic: Variabili
title: Variabili di pagina
topic: Sviluppatore e implementazione
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Variabili di pagina

Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

La variabile visualizza l'altezza della finestra del browser.

<!-- 
browserheight.xml
-->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

**Parametri**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Query Param </th> 
   <th class="entry"> Valore </th> 
   <th class="entry"> Esempio  </th> 
   <th class="entry"> Report interessati </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Un numero intero positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Traffico &gt; Tecnologia &gt; Altezza browser </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

La variabile visualizza la larghezza della finestra del browser.

<!-- 

browserwidth.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

**Parametri**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Query Param</b> </p> </td> 
   <td> <p> <b>Valore</b> </p> </td> 
   <td> <p> <b>Esempio</b> </p> </td> 
   <td> <p> <b>Report interessati</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Un numero intero positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Traffico &gt; Tecnologia &gt; Larghezza browser </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

La variabile identifica le campagne di marketing utilizzate per portare i visitatori sul sito. Il valore di viene in genere ricavato da un parametro di stringa di query.

<!-- 

campaign.xml

 -->

**Parametri**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 byte </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversione &gt; Campagne &gt; Codice di tracciamento </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

A ogni elemento di una campagna di marketing deve essere associato un codice di tracciamento univoco. Ad esempio, una parola chiave del motore di ricerca a pagamento può avere un codice di tracciamento pari a 112233. Quando un utente fa clic sulla parola chiave con il codice di tracciamento 112233 e viene instradato al sito Web corrispondente, la *`campaign`* variabile registra il codice di tracciamento.

Esistono due modi principali per compilare la *`campaign`* variabile:

* Il [!UICONTROL getQueryParam] plug-in, utilizzato nel file JavaScript, recupera un parametro della stringa di query dall'URL. Per ulteriori informazioni sul [!UICONTROL getQueryParam] plug-in, consultate Plug-in [di](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F)implementazione.

* Assegnare un valore alla *`campaign`* variabile nell’HTML della pagina Web.

Con entrambi i metodi di compilazione della *`campaign`* variabile, il traffico del pulsante Indietro può aumentare il numero effettivo di click-through da un elemento della campagna.

Ad esempio, un visitatore accede al sito facendo clic su una parola chiave di ricerca a pagamento. Quando il visitatore arriva sulla pagina di destinazione, l’URL contiene un parametro della stringa di query che identifica il codice di tracciamento per la parola chiave. Il visitatore fa clic su un collegamento a un’altra pagina, quindi fa clic immediatamente sul pulsante Indietro per tornare alla pagina di destinazione. Quando il visitatore arriva una seconda volta sulla pagina di destinazione, l’URL con il parametro della stringa di query identifica nuovamente il codice di tracciamento. E un secondo click-through viene registrato, gonfiando falsamente il numero di click-through.

Per evitare questo aumento dei click-through, Adobe consiglia di utilizzare il [!UICONTROL getValOnce] plug-in per forzare il conteggio dei click-through di ogni campagna solo una volta per sessione. Per ulteriori informazioni sul [!UICONTROL getValOnce] plug-in, consultate Plug-in [di](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F)implementazione.

**Sintassi e valori** possibili {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

La *`campaign`* variabile presenta le stesse limitazioni di tutte le altre variabili. Adobe consiglia di limitare il valore ai caratteri ASCII standard.

**Sensibilità** caso {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

Le eVar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di eVar1 è impostata su "Accesso", ma tutte le istanze successive vengono passate come "Accesso", i rapporti mostrano sempre "Accesso" come valore dell'eVar.

**Esempi** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Impostazioni** di configurazione {#section_4083F281968443169EAF8C0E8529D7BC}

Ciascun valore della campagna rimane attivo per un utente e riceve credito per le attività e gli eventi di successo di tale utente fino alla scadenza. Puoi modificare la scadenza della variabile della campagna in Admin Console.

**Insidie, domande e suggerimenti**{#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* Per evitare che i click-through vengano ingranditi, usate il [!UICONTROL getValOnce] plug-in per consentire il conteggio dei click-through per una campagna solo una volta per sessione. Per ulteriori informazioni sul [!UICONTROL getValOnce] plug-in, consultate Plug-in [di](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F)implementazione.

* Per ulteriori informazioni sul tracciamento delle campagne di marketing e degli acquisti di parole chiave, vedi [Campagne](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Utilizzate l'icona [!DNL DigitalPulse Debugger] per visualizzare il valore effettivo delle campagne (v0 nel debugger). Se v0 non viene visualizzato nel debugger, non vengono registrati dati della campagna per quella pagina.

## channel {#concept_C7770B8C15724A99B10F8F468AF82D0D}

La variabile viene utilizzata più spesso per identificare una sezione del sito.

<!-- 

channel.xml

 -->

Ad esempio, un esercente può avere sezioni quali Elettronica, Giocattoli o Abbigliamento. Un sito multimediale può contenere sezioni quali News, Sport o Business.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | CH | Contenuto del sito &gt; Sezioni del sito | "" |

Adobe consiglia di compilare la variabile del canale su ogni pagina. È inoltre possibile attivare una correlazione tra le *`channel`* variabili e le [!UICONTROL page name] variabili.

Se le sezioni hanno uno o più livelli di sottosezioni, è possibile mostrare tali sezioni nella *`channel`* variabile o utilizzare variabili separate per identificare i livelli.

**Sintassi e valori** possibili {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

La *`channel`* variabile non presenta ulteriori limitazioni ai suoi valori.

**Esempi** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Insidie, domande e suggerimenti**{#section_61941D5E4E644B59A267A4F44FD5DE8C}

Se il sito contiene più livelli, potete utilizzare la *`hierarchy`* o un'altra variabile per definirli. Il *`channel`* valore non persiste, ma gli eventi di successo attivati sulla stessa pagina sono attribuiti al *`channel`* valore.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

La variabile viene utilizzata per mostrare il numero di bit utilizzati per visualizzare il colore su ogni pixel dello schermo.

<!-- 

colordepth.xml

 -->

Ad esempio, 32 rappresenta 32 bit di colore sullo schermo. Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in `props/eVars`, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| c | 8,16 e 32 | 32 | Traffic &gt; Technology &gt; Monitor Colour Depth |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

La variabile, in Internet Explorer, indica se il browser è configurato su una connessione LAN o modem.

<!-- 

conntype.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in `props/eVars`, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| ct | lan o modem | lan | Traffico &gt; Tecnologia &gt; Tipo di connessione |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

La variabile indica se un cookie di sessione di prima parte può essere impostato da JavaScript.

<!-- 

cookiesenabled.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in `props/eVars`, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  |
|---|---|---|
| k | Y o N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Obsoleto) La variabile consente di selezionare il centro dati al quale vengono inviati i dati.

<!-- 

dc.xml

 -->

>[!NOTE]
>
>La variabile dc è obsoleta. È necessario impostare *`trackingServer`* per tutte le implementazioni il valore generato da [!UICONTROL Code Manager] in s_code.js.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | 112 |

Il data center è identificato nella *`dc`* variabile per poter corrispondere [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

Le [!UICONTROL eVar] variabili vengono utilizzate per creare rapporti personalizzati.

<!-- 

eVarN.xml

 -->

Quando un eVar viene impostato su un valore per un visitatore, il valore viene memorizzato fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | V1-v75 ( [o v100 o v250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) | Conversione personalizzata | "" |

**Scadenza**{#section_6DB5882B960D4660AE248B91B76883C4}

[!UICONTROL eVars] scade dopo un periodo di tempo specificato. Dopo la scadenza dell'eVar, non riceve più credito per gli eventi di successo. Le eVar possono anche essere configurate per scadere in caso di eventi di successo. Ad esempio, se si dispone di una promozione interna che scade al termine di una visita, la promozione interna riceve credito solo per gli acquisti o le registrazioni che si verificano durante la visita in cui sono stati attivati.

Esistono due modi per scadere di un'eVar:

* Potete impostare la scadenza dell'eVar dopo un periodo di tempo o un evento specificato.
* È possibile utilizzare Forza scadenza di un'eVar, utile per riproporre una variabile.

Se un eVar viene utilizzato in maggio per riflettere le promozioni interne e scade dopo 21 giorni, e in giugno viene utilizzato per acquisire le parole chiave di ricerca interna, il 1 giugno è necessario forzare la scadenza o reimpostare la variabile. In questo modo, i rapporti di giugno consentiranno di mantenere i valori di promozione interni.

**Sensibilità** caso {#section_6E9145B7FCC2438E95BB35AAE3857412}

Le eVar non fanno distinzione tra maiuscole e minuscole, ma vengono visualizzate nelle maiuscole della prima occorrenza. Ad esempio, se la prima istanza di eVar1 è impostata su "Accesso", ma tutte le istanze successive vengono passate come "Accesso", i rapporti mostrano sempre "Accesso" come valore dell'eVar.

**Contatori**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Sebbene le eVar siano utilizzate più spesso per contenere valori stringa, possono anche essere configurate per fungere da contatori. Le eVar sono utili come contatori quando si tenta di contare il numero di azioni eseguite da un utente prima di un evento. Ad esempio, potete utilizzare un'eVar per acquisire il numero di ricerche interne prima dell'acquisto. Ogni volta che un visitatore effettua una ricerca, l'eVar deve contenere il valore '+1.' Se un visitatore effettua una ricerca quattro volte prima di un acquisto, verrà visualizzata un’istanza per ciascun conteggio totale: 1,00, 2,00, 3,00 e 4,00. Tuttavia, solo la versione 4.00 riceve credito per l'evento di acquisto (Metriche Ordini e Entrate). Solo i numeri positivi sono consentiti come valori di un contatore eVar.

**Sottorelazioni** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

Un requisito comune per un [!UICONTROL Custom eVar] rapporto è la possibilità di suddividere un [!UICONTROL Custom eVar] rapporto per un altro. Ad esempio, se una eVar contiene il genere e un'altra contiene lo stipendio, è possibile porre la seguente domanda: delle donne che hanno visitato il mio sito, quante entrate sono state generate dalle donne che guadagnano più di 50.000 dollari l'anno. Qualsiasi eVar completamente correlata consente questo tipo di suddivisione nei rapporti. Ad esempio, se per l'eVar per genere sono abilitate le sottorelazioni complete, tutti gli altri rapporti eVar personalizzati possono essere suddivisi per genere e il genere può essere suddiviso per tutti gli altri. Per visualizzare la relazione tra due rapporti, è necessario abilitare solo una delle due sottorelazioni complete. Per impostazione predefinita, [!UICONTROL Campaigns], [!UICONTROL Products]e [!UICONTROL Category] i rapporti sono completamente correlati sotto-livello (qualsiasi eVar può essere suddiviso per campagna o prodotti).

**Sintassi e valori** possibili {#section_BD46438B14F3488FB9AC42994C317B06}

Anche se le eVar possono essere rinominate, devono sempre essere indicate nel file JavaScript da eVarX, dove X è un numero compreso tra 1 e 75 ( [o 100 o 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

Se non viene utilizzato come contatore, le eVar hanno le stesse limitazioni di tutte le altre variabili. Se l'eVar è un "contatore", si prevede che riceva valori numerici come "1" o "2.5". Se vengono date più di due posizioni decimali, il contatore eVar arrotonda a due posizioni decimali. Un contatore eVar non può contenere numeri negativi.

**Esempi** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Impostazioni** di configurazione {#section_BD1FE63001C84D3DB69F3DEE243960B6}

Le eVar possono essere configurate in [!UICONTROL Analytics > Admin > Report Suites > Edit Settings > Conversion > Conversion Variables]. Tutte le eVar possono essere configurate con un [!UICONTROL Name], [!UICONTROL Type], [!UICONTROL Allocation], [!UICONTROL Expire After Setting]o [!UICONTROL Reset]. Ogni impostazione di configurazione è indirizzata separatamente.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Impostazione </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nome </td> 
   <td> Consente di modificare il nome del rapporto eVar in <span class="keyword"> Analytics </span>. <p>Nel codice JavaScript deve essere sempre fatto riferimento all'eVarX come s.eVarX, indipendentemente dal nome assegnato al report in <span class="keyword"> Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Type (Tipo) </td> 
   <td> Consente di mostrare se l'eVar è una stringa di testo o un contatore. </td> 
  </tr> 
  <tr> 
   <td> Allocazione </td> 
   <td> Utilizzato per configurare quale valore dell'eVar riceve il credito per gli eventi di successo. <p>Se l'allocazione è impostata su "Most Recent (Last)", allora B riceve credito. </p> <p>Se l'opzione Allocazione è impostata su "Valore originale (primo)", A riceve credito. </p> <p>Se l'opzione Allocazione è impostata su "Lineare", sia A che B ricevono credito per metà del valore di acquisto. </p> </td> 
  </tr> 
  <tr> 
   <td> Scade dopo </td> 
   <td> Consente di determinare se un eVar scade in un evento specifico, come l'acquisto, o dopo un periodo di tempo personalizzato o predefinito. </td> 
  </tr> 
  <tr> 
   <td> Reset </td> 
   <td> Selezionando la <span class="wintitle"> casella di controllo Ripristina </span> per una eVar e facendo clic su <span class="wintitle"> Salva </span> nella parte inferiore della pagina, tutti i valori di tale eVar sono immediatamente scaduti. In seguito, solo i nuovi valori dell'eVar ricevono credito per gli eventi di successo. </td> 
  </tr> 
 </tbody> 
</table>

**Insidie, domande e suggerimenti**{#section_DA6912C802E445F986C6DE4234C6C737}

* A differenza delle [!UICONTROL prop] variabili, le variabili eVar non possono essere elenchi di valori delimitati. Se si compila un eVar con un elenco di valori, ad esempio "uno,due,tre", la stringa esatta verrà visualizzata nei report.
* I contatori eVar non possono contenere numeri negativi.

## Eventi {#concept_FFD115543D54401B98FE683BD7D5B3FE}

La variabile viene utilizzata per registrare eventi di successo comuni del carrello e eventi di successo personalizzati.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessun limite </td> 
   <td> events </td> 
   <td> <p>Eventi carrello acquisti </p> <p>Eventi personalizzati </p> </td> 
   <td> N/D </td> 
  </tr> 
 </tbody> 
</table>

Un sito [!UICONTROL event] deve essere considerato una pietra miliare. Gli eventi di successo sono popolati più comunemente nella pagina finale di conferma di un processo, ad esempio un processo di registrazione o di registrazione alla newsletter. Gli eventi personalizzati sono definiti compilando la variabile degli eventi con i valori letterali definiti nella sezione Valori possibili riportata di seguito.

Per impostazione predefinita, gli eventi di successo sono configurati come eventi *contatore* . Gli eventi contatore contano il numero di volte in cui un evento di successo viene impostato (x+1). Gli eventi possono essere configurati anche come eventi *numerici* . Gli eventi numerici consentono di specificare il numero da incrementare (come potrebbe essere necessario quando si contano valori dinamici o arbitrari, ad esempio il numero di risultati restituiti da una ricerca interna).

Un tipo di evento finale, *valuta*, consente di definire l'importo da aggiungere (simile agli eventi numerici), ma viene visualizzato come valuta nei rapporti ed è soggetto a conversioni valutarie basate su s. valore *`currencyCode`* e impostazione della valuta predefinita per la suite di rapporti. Per ulteriori informazioni sull'utilizzo di eventi numerici e valutari, vedere [Prodotti](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configurazione della variabile**{#section_9195286C34C54B02B2598E2B856492C3}

La [!UICONTROL s.events] variabile è abilitata per impostazione predefinita per tutte le implementazioni. I sette eventi di conversione preconfigurati vengono automaticamente attivati per tutte le nuove suite di rapporti. I nuovi eventi personalizzati (event1- [event100 o event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) possono essere attivati da qualsiasi utente a livello di amministratore tramite Admin Console.

**Valori possibili**{#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

Di seguito è riportato un elenco di valori possibili per la variabile event:

| Evento | Descrizione | Rapporti Popolato |
|---|---|---|
| all'evento | Visualizzazioni prodotto | Prodotti |
| scOpen | Aprire / Inizializzare un nuovo carrello | Carrelli |
| scAdd | Aggiungere elementi al carrello | Aggiunte carrello |
| scRemove | Rimuovere elementi dal carrello | Rimozioni carrello |
| scView | Visualizza carrello | Visualizzazioni carrello |
| scCheckout | Inizio del processo di estrazione | Pagamenti |
| purchase | Completamento di un acquisto (ordine) | Ordini |
| event1 - event1000 (event100 per il prodotto principale) | Eventi personalizzati | Eventi personalizzati |

**Sintassi ed esempi**{#section_45A159DF00114066B8551DDEB15E084C}

Gli eventi contatore vengono impostati posizionando gli eventi desiderati nella [!UICONTROL s.events] variabile, in un elenco separato da virgole (se devono essere passati più eventi).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

Se nel codice H23 o superiore, agli eventi contatore possono essere assegnati numeri interi maggiori di uno.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

Gli eventi contatore di implementazione con valori interi assegnati gestiscono l’evento come se fosse stato attivato più volte all’interno della richiesta di immagine. Gli eventi contatore non consentono i decimali. È consigliabile utilizzare gli eventi numerici invece se questa funzionalità è necessaria.
Gli eventi numerici e valutari devono essere inclusi nella [!UICONTROL s.events] variabile, anche se in genere ricevono il valore numerico (ad esempio, 24,99) nella [!UICONTROL s.products] variabile. Questo consente di collegare valori numerici e valutari specifici a singole voci di prodotto.

**Serializzazione degli eventi** {#section_A89488EF4471405AAFC4D6DD05E77621}

Per impostazione predefinita, un evento viene conteggiato ogni volta che l’evento viene impostato sul sito.

Per ulteriori informazioni, consultate Serializzazione [degli](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) eventi.

**Sintassi** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Esempi** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

La [!UICONTROL hierarchy] variabile determina la posizione di una pagina nella gerarchia del sito.

<!-- 

hierN.xml

 -->

Questa variabile è particolarmente utile per i siti con più di tre livelli nella struttura del sito. Ad esempio, un sito multimediale può avere 4 livelli nella sezione Sport: Sport, sport locali, baseball e Red Sox. Se qualcuno visita la pagina di baseball, Sport, Sport e Baseball, tutti i livelli riflettono quella visita.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | H1-H5 | Gerarchia | "" |

Sono disponibili cinque [!UICONTROL hierarchy] variabili, che devono essere abilitate dall'Assistenza clienti Adobe. Quando la gerarchia è abilitata, è necessario definire un delimitatore per la variabile e il numero massimo di livelli per la gerarchia. Ad esempio, se il delimitatore è una virgola, la gerarchia sportiva potrebbe essere visualizzata come segue.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Accertatevi che nessuno dei nomi di sezione contenga il delimitatore. Ad esempio, se una delle sezioni è denominata "Coach Griffin, Jim", è consigliabile scegliere un carattere di delimitazione diverso dalla virgola. Ciascuna sezione gerarchica è limitata a 255 byte, mentre il limite totale della variabile è di 255 byte. Dopo aver selezionato un delimitatore (al momento della creazione della gerarchia), questo non viene facilmente modificato.

Contatta l’Assistenza clienti Adobe per modificare il delimitatore di una gerarchia esistente. I delimitatori possono anche essere costituiti da più caratteri, come|| o /|\, che hanno meno probabilità di apparire in una sezione gerarchica.

**Sintassi e valori** possibili {#section_0739948A68A2420DAB1CBEA3115A5A66}

Non inserite uno spazio tra ciascun delimitatore. Nell'esempio seguente, N è un numero compreso tra uno e cinque.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

Non utilizzate il carattere di delimitazione tranne per delimitare i livelli della gerarchia. Il carattere di delimitazione può essere uno o più caratteri di vostra scelta.

**Esempi** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Impostazioni** di configurazione {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Nessuno

**Insidie, domande e suggerimenti**{#section_104E5BD320764BDEA5FA8D13A70C78E3}

* Il delimitatore non può essere modificato dopo la configurazione della gerarchia. Se il carattere di delimitazione della gerarchia deve essere modificato, contatta l’Assistenza clienti Adobe.
* Il numero di livelli potrebbe non essere modificato dopo la configurazione della gerarchia.

>[!NOTE]
>
>Le modifiche alle gerarchie possono determinare un costo di servizio.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

La variabile, in Internet Explorer, indica se la pagina corrente è impostata come home page dell'utente.

<!-- 

homepage.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| hp | Y o N | Y | Traffico &gt; Tecnologia &gt; Home Page |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

La variabile indica se Java è abilitato nel browser.

<!-- 

javaEnabled.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell'esecuzione di doPlugins.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| v | Y o N | Y | Traffico &gt; Tecnologia &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

La variabile indica la versione di JavaScript supportata dal browser.

<!-- 

javascriptVersion.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Traffic &gt; Technology &gt; Versione JavaScript |

La versione H.10 e successiva del file JavaScript rileva accuratamente fino alla versione 1.7 (la versione più elevata al momento del rilascio di H.10). Versioni precedenti del file JavaScript rilevate solo fino alla versione 1.3

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

La variabile è una variabile opzionale utilizzata in [!UICONTROL Link Tracking] che determina il nome di un collegamento personalizzato, di download o di uscita.

<!-- 

linkName.xml

 -->

La *`linkName`* variabile non è normalmente necessaria perché il terzo parametro della *`tl()`* funzione la sostituisce.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 byte </td> 
   <td> pev2 </td> 
   <td> <p>Download dei file </p> <p>Collegamenti personalizzati </p> <p>Esci dai collegamenti </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Custom Links] fare riferimento ai collegamenti che inviano dati di tracciamento. La *`linkName`* variabile (o il terzo parametro della *`tl()`* funzione) viene utilizzato per identificare il valore visualizzato nel [!UICONTROL Custom], [!UICONTROL Download]o [!UICONTROL Exit Links] report. Se non *`linkName`* viene popolato, l'URL del collegamento viene visualizzato nel rapporto.

**Sintassi e valori** possibili {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

Non esistono limitazioni *`linkName`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Impostazioni** di configurazione {#section_F15FF429FC274F708D50DF79D4668EA3}

Nessuno

**Insidie, domande e suggerimenti**{#section_170A78452A7340B5B229713AC1FB71FA}

* La *`linkName`* variabile viene sostituita dal terzo parametro della *`tl()`* funzione.

* Se la *`linkName`* variabile e il terzo parametro della *`tl()`* funzione sono vuoti, l'URL completo del collegamento (ad eccezione della stringa di query) viene visualizzato nel rapporto (anche se il collegamento è relativo).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

La variabile è una variabile opzionale utilizzata nel tracciamento dei collegamenti che determina quale rapporto viene visualizzato un nome o un URL di collegamento (collegamenti personalizzati, di download o di uscita).

<!-- 

linkType.xml

 -->

La *`linkType`* variabile non è normalmente necessaria perché il secondo parametro della *`tl()`* funzione la sostituisce.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Un carattere </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Download dei file </p> <p>Collegamenti personalizzati </p> <p>Esci dai collegamenti </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

I collegamenti personalizzati inviano dati ad Analytics. La *`linkType`* variabile (o il secondo parametro nella *`tl()`* funzione) viene utilizzato per identificare il rapporto in cui viene visualizzato il nome del collegamento o l'URL ( [!UICONTROL Custom], [!UICONTROL Download]o [!UICONTROL Exit Links] rapporto).

Per i collegamenti di uscita e di download, la *`linkType`* variabile viene compilata automaticamente a seconda che il collegamento selezionato sia un collegamento di uscita o di download. È possibile configurare un collegamento personalizzato per inviare dati a uno qualsiasi dei tre rapporti con questa variabile o con il secondo parametro della *`tl()`* funzione. Impostando *`linkType`* su 'o', 'e' o 'd', l'URL *`linkName`* o il collegamento viene inviato rispettivamente al [!UICONTROL Custom Links], [!UICONTROL Exit Links]o [!UICONTROL File Downloads] report.

**Sintassi e valori** possibili {#section_18DB3A8083FB4F75B970055ED336DA4E}

La sintassi della *`linkType`* variabile dipende dall'utilizzo di una stringa XML o di query.

Se si utilizza XML, la variabile può contenere solo un singolo carattere, ad esempio 'o,' 'e,' o 'd'.

```js
s.tl(this,’o’,’Link Name’);
```

Se si utilizza la stringa di query `pe`, è necessario utilizzare `lnk_d`, `lnk_e`o `lnk_o`.

**Esempi** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Impostazioni** di configurazione {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Nessuno

**Insidie, domande e suggerimenti**{#section_F0D01DDE3FDA486C987162DA50A79C45}

* Se non *`linkType`* viene specificato, vengono utilizzati collegamenti personalizzati ('o').

## Proprietà elenco {#concept_83ED74232225431F83A796E22FFC75B4}

Le proprietà elenco sono un elenco delimitato di valori che vengono passati in una variabile e quindi segnalati come singole voci. Le proprietà elenco sono comunemente implementate nelle pagine che contengono valori selezionabili dall'utente, come gli elementi elencati con caselle di controllo o pulsanti di scelta. Sono utili in qualsiasi circostanza in cui si desidera definire più valori in una variabile senza inviare più richieste di immagini.

<!-- 

list_props.xml

 -->

**Considerazioni**

* Le proprietà elenco sono abilitate solo sulle variabili di traffico ( [prop](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)).
* Impossibile abilitare percorsi e correlazioni per le proprietà dell'elenco.
* Analytics fornisce visite e visitatori unici a quasi tutti i report, inclusi tutti i report prop degli elenchi.
* Le classificazioni sono supportate per le proprietà elenco.
* Qualsiasi variabile di traffico personalizzata può diventare una proprietà elenco. (Eccezioni: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D)e [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2).)

* Quando si definiscono valori duplicati nella stessa richiesta di immagine, le istanze non vengono deduplicate.

È possibile modificare una proprietà in una proprietà elenco nella pagina Strumenti di amministrazione &gt; Suite di rapporti &gt; Variabili di traffico abilitando Supporto elenco e selezionando un carattere di delimitazione. I delimitatori più comuni sono due punti, due punti e virgola, una virgola o un’estremità. Il delimitatore può essere tecnicamente uno dei primi 127 caratteri ASCII.

**Esempi** di implementazione {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

Quando si richiede l'abilitazione di prop elenco, indicare il delimitatore da utilizzare. Dopo aver attivato *`s.prop`* la scelta, nella variabile possono essere impostati più valori, come illustrato negli esempi seguenti:

Un prop di elenco delimitato da una tubazione, che trasmette due valori:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Un prop elenco delimitato da una virgola che trasmette diversi valori:

```js
s.prop2="cerulean,vermilion,saffron"
```

Le proprietà elenco possono essere inviate anche con un singolo valore:

```js
s.prop3="Single value"
```

Il delimitatore può essere modificato in qualsiasi momento. Tuttavia, l'implementazione deve corrispondere al nuovo delimitatore. Se non si utilizza il delimitatore corretto, nel reporting il valore prop dell'elenco viene trattato come un singolo elemento concatenato.

Poiché un prop elenco è ancora una variabile di traffico, è soggetto a limitazioni della variabile di traffico. Le proprietà elenco sono limitate a 100 byte di dati e sono influenzate dalle impostazioni di sensibilità maiuscole/minuscole.

## Variabile elenco {#concept_AC42F2D69B674C02A484137CE5B4E687}

Noto anche come Var elenco. Analogamente alla funzione Elenco proprietà, le Var elenco consentono più valori all’interno della stessa richiesta di immagine. Inoltre, agiscono in modo simile alle eVar, che persistono oltre la richiesta di immagine sulla quale sono state definite. Potete utilizzare queste variabili per visualizzare la causa e l'effetto tra più elementi su una singola pagina, come elenchi di prodotti, elenchi di desideri, elenchi di miglioramenti della ricerca o elenchi di annunci visualizzati.

<!-- 

listN.xml

 -->

**Considerazioni**

* Le variabili elenco ricordano i loro valori specifici facendo riferimento al cookie VisitorID nel browser del visitatore.
* Un limite massimo di 250 valori viene memorizzato alla volta per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.
* Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se si utilizzano caratteri multibyte). Questa è la lunghezza massima di ogni elemento.
* Non esiste alcun limite al numero di caratteri all'interno di questa variabile. L’unica eccezione a questa limitazione è rappresentata dai browser Internet Explorer meno recenti, che impongono un limite di 2083 caratteri per tutte le richieste URL.
* Per suite di rapporti sono disponibili in totale tre variabili elenco.
* L'utilizzo di List Vars richiede il codice H23 o superiore.
* Le variabili elenco possono essere classificate.
* Se i valori duplicati sono definiti nella stessa richiesta di immagine, le variabili elenco deduplicano tutte le istanze di tali valori.
* Le variabili di elenco più granulari possono essere segmentate a livello di hit (o visualizzazione pagina). Se nella stessa richiesta di immagine è presente una variabile di elenco con tre valori, tutte e tre le regole di segmento che corrispondono a un valore verranno sottoposte a reporting. Al contrario, se viene definita una regola di esclusione che corrisponde a un singolo valore, tutti e tre i valori sono esclusi.

**Configurazione** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

Puoi accedere alla configurazione in Admin Console e aggiornarla senza dover coinvolgere Adobe Client Care:

1. Vai a  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. Seleziona la suite di rapporti.
1. Clic  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **Nome**:Ogni valore delimitato può contenere un massimo di 255 caratteri (o meno se si utilizzano caratteri multibyte). Questa è la lunghezza massima di ogni elemento.
* **Delimitatore** valore: Il carattere utilizzato per separare i valori all'interno della Var elenco. Nella maggior parte dei casi, si tratta di caratteri quali virgole, due punti, una tubatura o qualcosa di simile.

   >[!NOTE]
   >
   >I caratteri multibyte non sono supportati come delimitatori nelle variabili di elenco. Il delimitatore deve essere a byte singolo.

* **Scadenza**: Simile alla scadenza dell'eVar, questo determina la quantità di tempo che può trascorrere tra la Var dell'elenco e l'evento di conversione per il relativo collegamento.

   * **A un livello** di visualizzazione pagina o visita: Gli eventi di successo oltre la visualizzazione della pagina o la visita non verrebbero collegati ad alcun valore all’interno della Var elenco.
   * **In base a un periodo di tempo, ad esempio giorno, settimana, mese, ecc**.: Gli eventi di successo oltre il periodo di tempo specificato non verranno collegati ai valori all'interno della Var elenco. È inoltre possibile definire un numero personalizzato di giorni.
   * **Eventi** di conversione specifici: Eventuali altri eventi di successo attivati dopo lo specifico evento designato non verranno collegati ai valori all'interno della Var elenco.
   * **Mai**: Qualsiasi quantità di tempo può passare tra la Var elenco e l'evento success.

* **Allocazione**: Questa impostazione determina in che modo gli eventi di successo dividono il credito tra i valori:

   * **Completa**: Tutti i valori delle variabili definiti prima della scadenza della variabile ottengono il credito completo per gli eventi di successo.
   * **Lineare**: Tutti i valori delle variabili definiti prima della scadenza della variabile ricevono credito diviso per gli eventi di conversione.
   * I valori delle variabili non vengono mai sovrascritti, ma vengono aggiunti ai valori che vengono accreditati per gli eventi di successo.

* **Valori** max: Indica il numero di valori attivi consentiti per questa variabile dell'elenco. Ad esempio, se è impostato su 3, vengono salvati solo gli ultimi 3 valori acquisiti e tutti i valori acquisiti in precedenza vengono scartati. Tenere presente che se più valori per lo stesso elenco var vengono inviati nello stesso hit e avete applicato delle restrizioni utilizzando i valori massimi, ogni valore avrà la stessa marca temporale e non vi è alcuna garanzia per quale valore viene salvato.

   Un limite massimo di 250 valori viene memorizzato alla volta per visitatore. Se vengono superati i 250 valori per visitatore, vengono usati gli ultimi 250 valori. La scadenza di tali valori si basa sulla scadenza configurata per la variabile.

   L’impostazione Valori massimi è utile per limitare l’attribuzione a un numero specifico di valori. Ad esempio, se una variabile di elenco è impostata su "A,B,C" nella prima pagina di una visita e quindi su "X,Y,Z" nella pagina successiva, l'attribuzione viene distribuita a questi sei valori in base all'allocazione. Se desiderate limitare l’attribuzione solo a "X,Y,Z", potete impostare i valori massimi su tre.

Per impostare o modificare le Var elenco, scegliere **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**Esempi** di implementazione {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

Per ciascuno degli esempi seguenti viene utilizzata una virgola come delimitatore di valori.

**Definizione di un singolo valore all'interno di una Var elenco:**

```js
s.list1="Cat";
```

**Trasmissione di più valori:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Attribuzione delle entrate a una variabile di elenco:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Questo risultato mostrerebbe tre voci con $50 ciascuna in entrate. (Annuncio banner superiore; Annuncio barra laterale; e campagna interna 1.) Il totale per questo rapporto deduplica le entrate, pertanto il totale riflette anche $50.

**Attribuzione delle entrate a una Var elenco impostata più volte durante una visita:**

**Allocazione**: Full

**Scadenza**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pagina </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Pagina 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (non impostato) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pagina 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Risultato**: Tutti i valori impostati nell'elenco var1 in qualsiasi punto della visita (valore1,valore2,valore3,valore4,valore5,valore6) ottengono il credito completo per l'acquisto.

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

La variabile s.maxDelay è utilizzata principalmente nelle integrazioni DFA di Genesis per determinare il periodo di timeout durante il contatto con l’host del DFA. Se Adobe non riceve una risposta dai server DFA entro il periodo specificato impostato nella variabile, la connessione viene interrotta e i dati vengono elaborati normalmente. Implementa questa variabile se hai a che fare con il tempo di risposta del DFAE su ogni pagina. È consigliabile sperimentare con questo valore per determinare il periodo di timeout ottimale.

<!-- 

maxDelay.xml

 -->

**Esempio**

```
s.maxDelay="750";
```

**Proprietà**

* Questa variabile è una metrica di evento opzionale compilata tramite JavaScript implementato sul sito.
* Se l’ospitante del DFA non risponde entro il tempo specificato, l’evento designato per Timeout viene eseguito (assegnato tramite la procedura guidata di integrazione di Genesis).
* Questa variabile può contenere solo un valore numerico.
* Il tempo specificato viene misurato in millisecondi.
* Aumentando il tempo di attesa si raccolgono più dati DFA, ma aumenta anche il rischio di perdere i dati hit di Analytics.

   La perdita dei dati di hit di Analytics si verifica quando l'utente si allontana dalla pagina durante il *`s.maxDelay`* periodo.

* Una riduzione del tempo di attesa ridurrà il rischio di perdita dei dati hit di Analytics, ma potrebbe ridurre la quantità di dati DFA inviati con i dati hit.

   La perdita dei dati di integrazione DFAE si verificherebbe quando il *`s.maxDelay`* periodo non contiene il tempo sufficiente per consentire all’ospitante del DFAE di rispondere.

>[!NOTE]
>
>Adobe non ha il controllo sui tempi di risposta del DFAE. Se riscontri problemi coerenti anche dopo aver aumentato il periodo di ritardo massimo a un intervallo di tempo ragionevole, consulta l’amministratore di account DFA della tua organizzazione.

## mediaLength {#concept_F52B1670122C4461824223E525307060}

La variabile specifica la lunghezza totale del contenuto multimediale riprodotto.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessuna dimensione massima per l'intera richiesta pev3 - la dimensione è limitata al limite di lunghezza URL del browser. </td> 
   <td> pev3 </td> 
   <td> Tempo trascorso sul video; <p>Segmenti video visualizzati </p> </td> 
   <td> Nessuno </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi e valori** possibili {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** Metodo AutoTrack: **

Se si utilizza [!UICONTROL s.Media.autoTrack], la [!UICONTROL mediaLength] variabile non deve essere implementata in modo esplicito. Viene determinato automaticamente da AppMeasurement per il codice JavaScript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Esempi** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Insidie, domande e suggerimenti**{#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando [!UICONTROL s.Media.autoTrack] = true.
* Se non esegui il tracciamento tramite [!UICONTROL autoTrack], accertati di impostare la lunghezza in secondi.

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

Questa variabile specifica il nome del video o dell’elemento multimediale.

<!-- 

mediaName.xml

 -->

È disponibile solo tramite [!UICONTROL Data Insertion API] e [!UICONTROL Full Processing Data Source].

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 64 KB | pev3 | Video; Flusso video successivo; Flusso video precedente; Segmenti Video Visualizzati; Tempo trascorso sul video | Nessuno |

**Sintassi e valori** possibili {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Metodo autoTrack:**

Se si utilizza [!UICONTROL s.Media.autoTrack], la *`mediaName`* variabile non deve essere implementata in modo esplicito. Viene determinato automaticamente da AppMeasurement per il codice JavaScript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Esempi** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Insidie, domande e suggerimenti**{#section_941A445BB52E4063B0F6920E61BB90DE}

* È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando [!UICONTROL s.Media.autoTrack] = true.
* Questa variabile viene memorizzata come variabile mySQL TEXT anziché come VARCHAR(100).

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

Questa variabile specifica il lettore utilizzato per utilizzare un elemento video o multimediale.

<!-- 

mediaPlayer.xml

 -->

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | pev3 | Riproduttori video | Nessuno |

**Sintassi e valori** possibili {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Metodo autoTrack:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Metodo di tracciamento manuale:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Esempi** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Insidie, domande e suggerimenti**{#section_0020E031338F4A4880B9AC5B9A85BEF5}

È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando s.Media.autoTrack = true.

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

Questa variabile specifica i segmenti di una risorsa video o multimediale utilizzata.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 byte </td> 
   <td> pev3 </td> 
   <td>  Tempo trascorso sul video <p>Segmenti video visualizzati </p> </td> 
   <td> Nessuno </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi e valori** possibili {#section_9A63266633C4427CB4A6549E4D887B85}

**Metodo autoTrack:**

Se si utilizza [!UICONTROL s.Media.autoTrack], *`mediaName`* non è necessario implementarlo esplicitamente. Sarà determinato automaticamente da AppMeasurement per il codice JavaScript.

**Metodo di tracciamento manuale:**

Sintassi:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valori possibili:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Esempi** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Insidie, domande e suggerimenti**{#section_1BCEB037AB724B6EBE87420BD3604B88}

È necessario chiamare i metodi di tracciamento dei supporti solo se il lettore non può essere tracciato utilizzando [!UICONTROL s.Media.autoTrack] = true.

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

La variabile identifica gli eventi da inviare con un hit per contenuti multimediali.

<!-- 

media_trackEvents.xml

 -->

È applicabile solo con JavaScript e [!UICONTROL ActionSource].

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackEvents="None" |

**Sintassi e valori** possibili {#section_66A978EF56914BEAAE73359A268A1B4A}

Nomi evento come event1 o purchase.

**Esempi** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**Insidie, domande e suggerimenti**{#section_030B11C64EE84D46A85CA550DB732D28}

Assicurarsi di compilare [!UICONTROL trackVars] gli "eventi" ogni volta che questa variabile viene compilata.

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

La variabile identifica le variabili da inviare con un hit per file multimediali.

<!-- 

media_trackVars.xml

 -->

È applicabile solo con JavaScript e [!UICONTROL ActionSource].

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | s.Media.trackVars="None" |

**Sintassi e valori** possibili {#section_7374684A7EB34AE685E8C40A66CFD289}

Nomi di variabili quali [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`* e così via.

**Esempi** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**Insidie, domande e suggerimenti**{#section_615AE1B696124B00B78F651B03813EAB}

* Anche se eVar3 è specificato in [!UICONTROL trackVars], viene inviato con l’hit del supporto.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variabile controlla l’ordine in cui i cookie e gli ID utente iscritto vengono utilizzati per identificare i visitatori.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | /5/ o /1/ nel percorso dell'URL dell'immagine | N/D | Nessuno |

**Sintassi e valori** possibili {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Insidie, domande e suggerimenti**{#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilizzate l'identificazione cross-visitor per attenuare i possibili picchi nel traffico dei visitatori quando utilizzate la *`s.mobile`* variabile con l'implementazione dei cookie JavaScript.

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

La variabile contiene il nome di ogni pagina del sito.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 byte </td> 
   <td> pageName </td> 
   <td> <p>Pagine </p> <p>Paths (Percorsi) </p> </td> 
   <td> URL pagina </td> 
  </tr> 
 </tbody> 
</table>

La *`pageName`* variabile deve essere compilata con un valore riconosciuto dagli utenti aziendali. Nella maggior parte dei casi, il *`pageName`* valore non è l'URL o il percorso del file. I *`pageName`* valori comuni includono nomi come "Home Page", "Checkout", "Purchase Thank you" (Grazie all’acquisto) o "Registration" (Registrazione).

Prestate attenzione a non consentire la visualizzazione di trattini di nuova riga, -em o -en, né di eventuali caratteri HTML nel nome della pagina e in altre variabili. Alcuni browser inviano nuovi caratteri di riga mentre altri no, causando la divisione dei dati in Analytics tra due nomi di pagina apparentemente identici. Molti elaboratori di testi e client di posta elettronica convertono automaticamente un trattino in un trattino -en o -em durante la digitazione. Poiché i trattini -en e -em sono caratteri non validi nelle variabili di Analytics (caratteri ASCII con codici superiori a 127), Analytics non registra il nome della pagina contenente il carattere non valido e mostra l'URL.

Se *`pageName`* viene lasciato vuoto, l’URL viene utilizzato per rappresentare il nome della pagina. Lasciare *`pageName`* vuoto è spesso problematico perché l’URL potrebbe non essere sempre lo stesso per una pagina `www.mysite.com` e `mysite.com` corrispondere a una pagina con URL diversi).

**Sintassi e valori** possibili {#section_7A61EE70F1A84D26B414404998C84BA8}

La *`pageName`* variabile deve contenere un identificatore utile per gli utenti aziendali di Analytics.

```js
s.pageName="page_name"
```

Non esistono limitazioni *`pageName`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Impostazioni** di configurazione {#section_58CBC68C805344A999EB47455FEBA8D5}

Gli amministratori possono modificare il nome della pagina visibile in Analytics con lo [!UICONTROL Name Pages] strumento, che è potenzialmente pericoloso e può influire negativamente sui rapporti. Contatta l'Assistenza clienti Adobe prima di utilizzare lo [!UICONTROL Name Pages] strumento.

**Insidie, domande e suggerimenti**{#section_BB41DC9682C34385B9CAA80D5257C113}

Assicurarsi che *`pageName`* non contenga caratteri non validi.

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

La variabile viene utilizzata solo per designare una pagina di errore 404 Pagina non trovata.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 byte </td> 
   <td> pageType </td> 
   <td> Percorsi &gt; Pagine &gt; Pagine <p>Non trovato </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

La *`pageType`* variabile acquisisce l'URL errante quando viene visualizzata una pagina di errore 404, che consente di trovare rapidamente collegamenti interrotti e percorsi non più validi sul sito personalizzato. Impostare la *`pageType`* variabile sulla pagina di errore esattamente come illustrato di seguito.

Non utilizzate la variabile del nome della pagina su 404 pagine di errore. La *`pageType`* variabile viene utilizzata solo per la pagina Errore 404.

Nella maggior parte dei casi, la pagina 404 Error (Errore 404) è una pagina statica codificata. In questi casi, è importante che il riferimento al file JS sia impostato su un percorso/directory globale o relativo appropriato.

**Sintassi e valori** possibili {#section_C1C59968226446559B05F6EE7374D525}

L'unico valore consentito di *`pageType`* è "errorPage" come mostrato di seguito.

```js
s.pageType="errorPage"
```

**Esempi** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Impostazioni** di configurazione {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Nessuno

**Insidie, domande e suggerimenti**{#section_943681AB01FE47BEAC72E93CB60C53C8}

Per acquisire altri errori sul lato server (ad esempio, 500 errori), utilizzate un prop per acquisire il messaggio di errore e inserite "`500 Error: <URL>`" dove `<URL>` è l'URL richiesto nella *`pageName`* variabile. Seguendo questo corso di azione, puoi utilizzare [!UICONTROL Pathing] i rapporti per vedere quali percorsi hanno causato 500 errori agli utenti. Il prop spiega quale messaggio di errore viene fornito dal server.

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

La variabile sostituisce l’URL effettivo della pagina.

<!-- 

pageURL.xml

 -->

In alcuni rari casi, l’URL della pagina non è l’URL da includere nei rapporti in Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nessun limite* </td> 
   <td> <p>G </p> </td> 
   <td> Traffico &gt; Segmentazione &gt; Percorsi delle pagine più comuni </td> 
   <td> URL della pagina </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Anche se Adobe consente *`pageURL`* valori fino a 64 k, alcuni browser impongono un limite di dimensione all’URL delle richieste di immagini. Per evitare il troncamento di altri dati, gli URL di pagina di lunghezza superiore a 255 byte vengono suddivisi, con i primi 255 byte visualizzati nel `g=` parametro, con i rimanenti byte che vengono visualizzati successivamente nella stringa di query nel parametro della `-g=` query.

**Sintassi e valori** possibili {#section_22AF3BF7C2F743549967B0C760A095C0}

La *`pageURL`* variabile deve essere un URL valido, con un protocollo valido. Il dominio verrà forzato a essere visualizzato in lettere minuscole prima di essere popolato nei report, e la stringa di query potrebbe essere rimossa, a seconda delle impostazioni di Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

Solo i caratteri compatibili con l’URL sono consentiti come URL della pagina.

>[!NOTE]
>
>Prima di utilizzare la *`pageURL`* variabile per scopi personalizzati, si consiglia vivamente di contattare il consulente Adobe o l'Assistenza clienti.

**Esempi** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Impostazioni** di configurazione {#section_A8F77DAD88164528ACC5C16C066B47DF}

Nessuno

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

La variabile, nei browser Netscape e Mozilla, elenca i plug-in installati nel browser.

<!-- 

plugins.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| p | Plug-in riconosciuti | plugin di scheda IE;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Windows Media Player Plug-in Dynamic Link Library;Microsoft® DRM; | Traffico &gt; Tecnologia &gt; Plugin |

## products {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

La variabile viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti, nonché della quantità di acquisto e del prezzo di acquisto. I prodotti vengono generalmente impostati insieme a un evento cart o un evento.

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. Questo aggiornamento può causare l'aumento degli *eventi`prodView`* *`prodViews`* aumenteranno solo nei casi in cui:
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. The *`products`* variable is not empty.
>
>
A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

La *`products`* variabile tiene traccia di come gli utenti interagiscono con i prodotti sul sito. Ad esempio, la variabile "products" può tenere traccia del numero di volte in cui un prodotto viene visualizzato, aggiunto al carrello, estratto e acquistato. Può inoltre tenere traccia dell’efficacia relativa delle categorie di merchandising sul sito. Gli scenari riportati di seguito sono comuni per l'utilizzo della variabile "products".

La *`products`* variabile deve sempre essere impostata insieme a un evento success.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Dimensioni massime </th> 
   <th class="entry"> Parametro debugger </th> 
   <th class="entry"> Report compilati </th> 
   <th class="entry"> Valore predefinito </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>La stringa " <span class="wintitle"> products </span>" ha una dimensione massima di 64 k. </p> </td> 
   <td> products </td> 
   <td> Prodotti <p>Categorie (facoltativo) </p> <p>Entrate (facoltativo) </p> <p>Unità (facoltativo) </p> <p>Eventi personalizzati (facoltativo) </p> <p>eVar (facoltativo) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintassi** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definizione |
|---|---|
| Categoria | Contiene la categoria di prodotti associata. Nella versione 15, i prodotti possono essere associati a più categorie, il che risolve una limitazione presente nella versione 14. Se in precedenza non si registrava una categoria di prodotti, si consiglia di iniziare a compilare il campo per le suite di rapporti che si trovano sulla versione 15. |
| Prodotto | (Obbligatorio) Identificatore utilizzato per tenere traccia di un prodotto. Questo identificatore viene utilizzato per compilare il [!UICONTROL Products] rapporto. Assicuratevi di utilizzare lo stesso identificatore attraverso il processo di estrazione. |
| Quantità | Numero di unità acquistate. Questo campo deve essere impostato con un [!UICONTROL purchase] evento da registrare. |
| Prezzo | Si riferisce al costo combinato della quantità totale acquistata (unità x prezzo unitario singolo), non al prezzo individuale. Questo campo deve essere impostato con un [!UICONTROL purchase] evento da registrare. |
| Eventi | Eventi valuta associati al prodotto specificato. Vedere Eventi [valuta specifici per](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) il prodotto ed Eventi [valuta a livello di](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0)ordine. |
| eVar | Valore eVar di merchandising associato a un prodotto specifico. Consultate Variabili [di](/help/components/c-variables/c-merch-variables/var-merchandising.md)merchandising. |

I valori inclusi nella *`products`* variabile si basano sul tipo di evento che si sta registrando. Il delimitatore di categoria/prodotto (;) è richiesto come segnaposto quando si omette Categoria. Altri delimitatori sono richiesti solo se sono necessari per distinguere il parametro da includere, come mostrato negli esempi in questa pagina.

**Impostazione di prodotti con eventi** non di acquisto {#section_D5E689D4AAE941EC851CA9B98328A4DE}

La *`products`* variabile deve essere impostata insieme a un evento success.

**Impostazione di prodotti con un evento** di acquisto {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

L' *`purchase`* evento deve essere impostato sulla conferma finale ("Grazie!") pagina del processo di ordine. Il nome del prodotto, la categoria, la quantità e il prezzo sono tutti acquisiti nella *`products`* variabile. Sebbene la *`purchaseID`* variabile non sia obbligatoria, è fortemente consigliata per evitare ordini duplicati.

**Eventi** valuta specifici per il prodotto {#section_F814DF053C0D463A97DA039E6323720C}

Se un evento relativo alla valuta riceve un valore nella variabile anziché nella variabile *`products`* event, esso si applica solo a tale valore. Questo è utile per monitorare gli sconti specifici per prodotto, la spedizione di prodotti e valori simili. Ad esempio, se hai configurato l'evento 1 per monitorare la spedizione del prodotto, un prodotto con una spesa di spedizione "4.50" potrebbe essere simile al seguente:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

In questo esempio, il valore 4.50 è associato direttamente al prodotto "Running Shoes". Se aggiungete event1 al rapporto sui prodotti, vedrete "4.50" elencato per la voce "Scarpe in esecuzione". Simile a Prezzo, questo valore deve riflettere il totale per la quantità indicata. Se avete 2 articoli con una spesa di spedizione di 4.50 ciascuno, event1 deve essere "9.00".

**Eventi** valuta a livello di ordine {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Se un evento relativo alla valuta riceve un valore nell'elenco eventi anziché nella *`products`* variabile, questo viene applicato a tutti i prodotti della *`products`* variabile. Questo è utile per tenere traccia degli sconti, delle spedizioni e di valori simili a livello di ordine, senza modificare il prezzo del prodotto o registrarlo separatamente nell'elenco dei prodotti.

Ad esempio, se hai configurato event10 per contenere sconti a livello di ordine, un acquisto con uno sconto del 10% potrebbe essere simile al seguente:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

Nei rapporti evento valuta, il totale del rapporto rappresenta il totale degli eventi deduplicati (in questo esempio, l'importo totale degli sconti durante il periodo di reporting), non la somma dei valori evento per ciascun prodotto. Ad esempio, vedreste "9.95" sia per "Scarpe In Corsa" che per "Calzature In Corsa", e il totale sarebbe anche "9.95".

>[!NOTE]
>
>se un valore per lo stesso evento Numerico/Valuta è specificato nella *`products`* variabile e nella *`events`* variabile, viene utilizzato il valore del *`events`* .

**Insidie, domande e suggerimenti**{#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* La *`products`* variabile deve sempre essere impostata insieme a un [!UICONTROL success] evento (eventi). Se non viene [!UICONTROL success] specificato alcun evento, l'evento predefinito è [!UICONTROL prodView].

* Rimuovere tutte le virgole e i punti e virgola dai nomi di prodotti e categorie prima di compilare i prodotti.
* Rimuovete tutti i caratteri HTML (simboli registrati, marchi registrati e così via).
* Elimina simboli di valuta ($) dal prezzo.

**Esempi** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Categoria3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Categoria;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Categoria;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;event3=2.9;evar3=20% di sconto" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Categoria;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;event3=2.9;evar3=20% di sconto" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

Le variabili di proprietà ( [!UICONTROL prop]) vengono utilizzate per creare rapporti personalizzati all'interno del [!UICONTROL Traffic Module].

<!-- 

propN.xml

 -->

La variabile props può essere utilizzata come contatori (per contare il numero di volte che una visualizzazione di pagina viene inviata), per i report dei percorsi o nei rapporti di correlazione.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | c1-c75 | Traffico personalizzato | "" |

**Sintassi e valori** possibili {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

Non esistono limitazioni sulle [!UICONTROL property] variabili al di fuori delle limitazioni standard.

**Esempi** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Impostazioni** di configurazione {#section_25FDEB6ECA8242A2A44EE540C083078A}

Contatta l'Assistenza clienti Adobe per visualizzare [!UICONTROL Visit], [!UICONTROL Visitor]e [!UICONTROL Path] le metriche per [!UICONTROL prop] le variabili.

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

Viene utilizzato per impedire che un ordine venga conteggiato più volte nel reporting.

<!-- 

purchaseID.xml

 -->

Ogni volta che l’ [!UICONTROL purchase] evento viene utilizzato sul sito, dovreste utilizzare la *`purchaseID`* variabile.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 20 byte | purchaseID | Conversione &gt; Acquisti &gt; Conversione ricavi | "" |

Quando un visitatore acquista un elemento dal sito, *`purchaseID`* viene popolato sulla pagina "Grazie" nello stesso punto in cui viene attivato l’ [!UICONTROL purchase] evento. Se *`purchaseID`* viene compilato, i prodotti nella pagina "Grazie" vengono conteggiati una sola volta *`purchaseID`*. Questo è importante perché molti visitatori del sito salveranno la pagina di ringraziamento o di conferma per i propri scopi. Gli acquisti *`purchaseID`* vengono conteggiati ogni volta che viene visualizzata la pagina.

Oltre a impedire che i dati di acquisto vengano conteggiati due volte, *`purchaseID`* quando vengono utilizzati, tutti i dati di conversione vengono conteggiati due volte nei rapporti.

**Sintassi e valori** possibili {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

Deve *`purchaseID`* contenere un massimo di 20 caratteri ed essere in formato ASCII standard.

**Esempi** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Impostazioni** di configurazione {#section_1808631C96674380BF9C4A6D9A2C568E}

Nessuno

**Insidie, domande e suggerimenti**{#section_F5D010F234ED43F19AD1FCD2CD64E060}

La *`purchaseID`* variabile consente di contare tutte le variabili di conversione sulla pagina solo una volta nei rapporti.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

La variabile può essere utilizzata per ripristinare le informazioni di referente perse.

<!-- 

referrer.xml

 -->

I reindirizzamenti lato server e JavaScript sono spesso utilizzati per indirizzare i visitatori verso le posizioni corrette. Tuttavia, quando un browser viene reindirizzato, l'URL di provenienza originale viene perso.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 255 byte | R | Traffico &gt; Ricerca metodi Conversione &gt; Ricerca metodi | document.referrer |

Molte aziende utilizzano i reindirizzamenti in molti punti all'interno dei loro siti web. Ad esempio, un visitatore può essere inviato tramite un reindirizzamento da un motore di ricerca con risultati di ricerca a pagamento. Quando un browser viene reindirizzato, il referente viene spesso perso. La *`referrer`* variabile può essere utilizzata per ripristinare il *`referrer`* valore originale sulla prima pagina dopo un reindirizzamento. È *`referrer`* possibile compilare il file sul lato server o tramite JavaScript dalla stringa di query.

Affinché Analytics possa registrare un referente, deve essere "formato correttamente", ovvero deve seguire il formato URL standard, con un protocollo e una posizione appropriata.

**Sintassi e valori** possibili {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Solo i valori compatibili con l’URL dovrebbero essere inclusi nel *`referrer`*. Verificate che la stringa sia codificata tramite URL (nessun spazio).

**Esempi** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Impostazioni** di configurazione {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Nessuno

**Insidie, domande e suggerimenti**{#section_B42BF7FBA1094FF9805707FEA810CFE1}

Deve *`referrer`* avere l'aspetto di un URL standard e includere un protocollo.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

La variabile indica la risoluzione del monitor del visitatore che visualizza la pagina Web.

<!-- 

resolution.xml

 -->

Questa variabile viene compilata dopo il codice della pagina e prima dell' *`doPlugins`* esecuzione.

>[!NOTE]
>
>Questa variabile deve essere letta e non impostata.

Potete leggere questi valori e copiarli in prop/eVar, ma non dovreste mai modificarli. Questa variabile viene introdotta con la versione H.11 del file JavaScript.

| Query Param | Valore | Esempio  | Report interessati |
|---|---|---|---|
| s | WxH | 1680x1050 | Traffico &gt; Tecnologia &gt; Risoluzione monitor |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

La variabile è una variabile globale che deve essere impostata in [!UICONTROL onClick] caso di collegamento.

<!-- 

s_objectID.xml

 -->

Creando un ID oggetto univoco per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il tracciamento dell’attività del visitatore oppure utilizzare [!UICONTROL Activity Map] per creare rapporti su un tipo o una posizione di collegamento, anziché sull’URL del collegamento.

>[!NOTE]
>
>È necessario un punto e virgola finale (;) quando si utilizza s_objectID con [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | URL assoluto di un collegamento con clic |

Esistono tre motivi comuni per utilizzare *`s_objectID`*:

* Per aggregare l'attività del visitatore che cambia spesso durante un giorno.
* Per separare l'attività dei collegamenti che [!UICONTROL Activity Map] si combina.
* Per migliorare la precisione della generazione di rapporti [!UICONTROL Activity Map] sui dati.

**Aggrega clic su collegamenti** altamente dinamici {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Se il sito è altamente dinamico e i collegamenti su alcune pagine cambiano durante la giornata, *`s_objectID`* può essere utilizzato per identificare la posizione di un collegamento sulla pagina. Se *`s_objectID`* è impostato su "top left 1" o "top left 2", che ad esempio rappresenta il primo collegamento in alto a sinistra della pagina, tutti i collegamenti che compaiono in quella posizione (o che hanno *`s_objectID`* impostato lo stesso valore) vengono segnalati insieme alla mappa clic del visitatore. Se non si utilizza *`s_objectID`*, viene visualizzato il numero di volte in cui è stato fatto clic su un collegamento specifico, ma si perde la comprensione di come tutti gli altri collegamenti in tale posizione sono stati utilizzati dai visitatori del sito.

**Clic Separate**{#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Se la *`pageName`* variabile sul sito viene utilizzata per mostrare la sezione o il modello che un visitatore sta visualizzando, anziché la pagina specifica che il visitatore sta visualizzando, potete utilizzare *`s_objectID`* per separare i collegamenti visualizzati su più versioni di tale modello di pagina. Ad esempio, se disponete di una pagina di modello per tutti i prodotti sul sito, è probabile che esista un collegamento alla pagina principale e a una casella di ricerca da tale modello su tutte le pagine. Se desiderate visualizzare il modo in cui tali collegamenti vengono utilizzati in base a un singolo prodotto (anziché in base a un modello), potete compilare *`s_objectID`* con un valore specifico del prodotto, ad esempio "prod 123789 home page" o "prod 123789 search". Una volta completati, [!UICONTROL Activity Map] rapporti su tali collegamenti a livello di singolo prodotto.

**Maggiore[!UICONTROL Activity Map]precisione**{#section_08B3406821294DCCABEEB99C90CF5C52}

In alcuni casi, i browser diversi da Internet Explorer, Firefox, Netscape, Opera e Safari non vengono segnalati. Anche se si tratta di una percentuale ridotta, può gestire alcuni clic e altre metriche. Utilizzate *`s_objectID`* all'interno dei collegamenti per identificare in modo univoco gli indirizzi del problema di reporting del browser. Di seguito è riportato un esempio di come aggiornare i collegamenti da utilizzare *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintassi e valori** possibili {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID può contenere qualsiasi identificatore di testo.

```js
s_objectID="unique_id" 
```

Non esistono limitazioni *`s_objectID`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Impostazioni** di configurazione {#section_95396657D55B41ECB66B83D0534EA827}

Nessuno

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

La variabile viene utilizzata per mostrare il dominio di una pagina Web (per mostrare i domini a cui arrivano gli utenti) o il server che distribuisce la pagina (per un riferimento rapido per il bilanciamento del carico).

<!-- 

server.xml

 -->

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | server | Server | "" |

Se il sito contiene più domini che gestiscono lo stesso contenuto, la *`server`* variabile può essere utilizzata per tenere traccia dei domini che i visitatori utilizzano. Il seguente JavaScript comporrà il dominio della pagina nella variabile server.

```js
s.server=window.location.hostname
```

Se si utilizza la variabile server per fornire una guida rapida al bilanciamento del carico, è possibile inserire un nome o un numero di server nella variabile server. Vedere l'esempio seguente:

```js
s.server="server 14"
```

Anche se il [!UICONTROL Most Popular Servers] rapporto può essere utilizzato come riferimento rapido per il bilanciamento del carico, non è una misura precisa del carico del server. Ad esempio, il traffico del pulsante Indietro non aumenta il carico del server, ma viene mostrato nei rapporti. Il rapporto non mostra quali server trasmettono immagini o grandi download.

**Sintassi e valori** possibili {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

Non esistono limitazioni alla *`server`* variabile al di fuori delle limitazioni standard.

**Esempi** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Impostazioni** di configurazione {#section_969DB379D5BD469FBEE8D505D3000E49}

Nessuno

**Insidie, domande e suggerimenti**{#section_42A28F9B01574F38891D9D54B411D8FE}

La *`server`* variabile può essere utilizzata per mostrare quali domini sono più popolari o quali server servono più pagine.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

Le variabili e sono variabili di conversione.

<!-- 

state.xml

 -->

Sono come eVar in quanto catturano eventi, ma a differenza delle eVar, non persistono. Le variabili *`zip`* e *`state`* sono come eVar che scadono immediatamente.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 50 byte | state | Conversione &gt; Profilo visitatore &gt; Stato visitatore | "" |

Poiché le *`state`* variabili e le *`zip`* variabili scadono immediatamente, gli unici eventi associati sono gli eventi attivati sulla stessa pagina in cui sono popolati. Ad esempio, se si utilizza *`state`* per confrontare i tassi di conversione per stato, è necessario compilare la *`state`* variabile in ogni pagina del processo di estrazione. Per i siti di conversione, Adobe consiglia di utilizzare l'indirizzo di fatturazione come origine per il Codice postale, ma potete scegliere di utilizzare l'indirizzo di spedizione al posto (supponendo che esista un solo indirizzo di spedizione per l'ordine). Un sito multimediale può scegliere di utilizzare *`zip`* e *`state`* per la registrazione o il tracciamento del click-through degli annunci.

**Sintassi e valori** possibili {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

La *`state`* variabile non impone alcuna limitazione di valore o di formato speciale. Non esistono limitazioni *`state`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Impostazioni** di configurazione {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Nessuno

**Insidie, domande e suggerimenti**{#section_02F1620D0BB14AA6A838966FDB9A234F}

* Compilate *`state`* su ogni pagina un evento rilevante (ad esempio ogni pagina del processo di estrazione).
* Le *`zip`* variabili e *`state`* le variabili si comportano come eVar che scadono nella visualizzazione pagina.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

Questa variabile consente di personalizzare la marca temporale di un hit in modo simile alle librerie AppMeasurement per altre piattaforme.

<!-- 

timestamp.xml

 -->

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 4 byte | Data/ora | Non segnalati direttamente. | Impostato dai server di raccolta dati. |

**Sintassi** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

La *`timestamp`* variabile deve essere nel formato descritto nella sezione successiva.

>[!IMPORTANT]
>
>Per poter usare la *`timestamp`* variabile, l'Assistenza clienti deve abilitare le marche temporali nella suite di rapporti. Una volta abilitato il supporto per le marche temporali, tutti gli hit inviati a questa suite di rapporti da JavaScript devono avere una marca temporale impostata manualmente (tramite *`s.timestamp`*), altrimenti gli hit non verranno registrati.
>
>Inoltre, se attivi il supporto delle marche temporali in una suite di rapporti per supportare il tracciamento offline, tutti gli hit inviati a questa suite di rapporti da JavaScript devono avere anche una marca temporale impostata manualmente (utilizzando *`s.timestamp`*). Non puoi inviare hit con marca temporale e non con marca temporale alla stessa suite di rapporti.
>
>Puoi anche utilizzare l’impostazione [Marca temporale](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F)opzionale per combinare dati con marca temporale e senza marca nella stessa suite di rapporti globale, inviare dati con marca temporale da un’app mobile a una suite di rapporti globale e aggiornare le app per utilizzare marche temporali senza dover creare una nuova suite di rapporti.

**Formati** timestamp {#section_C12CBCECCD7047D38EF63A5800761CE9}

Le marche temporali devono essere in formato UNIX (in secondi dal 1° gennaio 1970) o ISO-8601, con le seguenti limitazioni al formato ISO-8601 accettato:

* Devono essere fornite sia la data che l'ora, separate da "T"
* La data deve essere una data di calendario con precisione completa (anno, mese e giorno).. Le date della settimana e quelle ordinali non sono supportate.
* La data può essere in formato standard o esteso ( `YYYY-MM-DD` o `YYYYMMDD`), ma deve includere l’ora e il minuto. I secondi sono facoltativi ( `HH:MM`, `HH:MM:SS`, `HHMM`o `HHMMSS`). È possibile trasmettere minuti e secondi frazionari, ma la parte frazionaria viene ignorata.

* Un fuso orario opzionale può essere specificato in formato standard o esteso ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`o Z)

Le marche temporali UNIX continuano a essere supportate (secondi dal 1° gennaio 1970).

**Esempi** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

L'elenco seguente contiene esempi di marche temporali valide in formato ISO-8601:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Impostazioni** di configurazione {#section_5275D206F2CB4009B3681E8C4457124A}

Per poter utilizzare questa variabile, è necessario abilitare una suite di rapporti per accettare marche temporali personalizzate dall'Assistenza clienti. Una volta abilitate le marche temporali personalizzate, tutti gli hit inviati alla suite di rapporti devono contenere una marca temporale o vengono scartati.

**Insidie, domande e suggerimenti**{#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Le marche temporali sono utilizzate principalmente per tenere traccia dei dati offline sulle piattaforme mobili. Le marche temporali personalizzate sono generalmente disattivate, a meno che non raccogliiate sia dati app Web che offline nella stessa suite di rapporti.
* I dati vengono contrassegnati con marca temporale quando i dati offline sono abilitati nell’SDK per dispositivi mobili (impostazione predefinita) o quando una suite di rapporti è configurata per accettare dati con marca temporale. I dati raccolti offline sui dispositivi mobili possono essere inviati ore o settimane dopo la data dell'avvenimento. Questi hit possono essere messi in coda nella piattaforma Analytics per minuti o ore più a lungo degli hit senza marca temporale:

   * Per i dati con marca temporale inviati in prossimità dell'ora corrente, il probabile ritardo è di 10-15 minuti.
   * Per i dati con marca temporale inviati da ieri, il probabile ritardo è di circa 2 ore.
   * Per i dati con marca temporale inviati prima di ieri, ogni giorno aggiunge circa 1 ora di ritardo, fino a 15 giorni prima, quando il ritardo smette di aumentare.

* I dati delle sessioni con marca temporale abilitata vengono conservati fino a 92 giorni.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

La variabile viene utilizzata per l’implementazione dei cookie di prime parti per specificare il dominio in cui vengono scritti la richiesta immagine e il cookie.

<!-- 

trackingServer.xml

 -->

Utilizzato per pagine non sicure. Se *`trackingServer`* è definito, non viene inviato nulla a 2o7.net. Se non *`trackingServer`* è definito (e dc non è definito), i dati vanno a 112.2o7.net.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Un elenco dei centri dati Adobe è disponibile [qui](https://helpx.adobe.com/analytics/kb/determining-data-center.html).

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

La variabile viene utilizzata per l’implementazione dei cookie di prime parti per specificare il dominio in cui vengono scritti la richiesta immagine e il cookie.

<!-- 

trackingServerSecure.xml

 -->

Utilizzato per pagine sicure. Se non *`trackingServerSecure`* è definito, i dati SSL vanno a *`trackingServer`*.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL Integration Data Sources] utilizzare [!UICONTROL transaction ID] per collegare i dati offline a una transazione online (come un lead o un acquisto generato online).

<!-- 

transactionID.xml

 -->

Ogni singolo *`transactionID`* inviato ad Adobe viene registrato in preparazione del [!UICONTROL Data Sources] caricamento di informazioni offline sulla transazione. Vedere [Origini](https://marketing.adobe.com/resources/help/en_US/sc/datasources/)dati.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 100 byte | esatto | n/d | "" |

**Abilita archiviazione** ID transazione {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Prima di registrare *`transactionID`* i valori, [!UICONTROL Transaction ID Storage] è necessario abilitare la suite di rapporti selezionata in Report Suite Manager. Questa impostazione si trova in

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Per verificare se *`transactionID Storage`* è abilitata per una suite di rapporti, vai a

```
Analytics > Admin > Data Sources > Manage
```

**Sintassi e valori** possibili {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

I caratteri *`transactionID`* devono contenere solo caratteri alfanumerici. Se più [!UICONTROL transactionIDs] devono essere registrati in un singolo hit, è possibile utilizzare una virgola per delimitare più valori.

**Esempi** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Insidie, domande e suggerimenti**{#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Se *`transactionID`* la registrazione non è abilitata, *`transactionID`* i valori verranno scartati e non saranno utilizzabili con [!UICONTROL Integration Data Sources]. Assicurarsi di impostare una variabile di conversione o un evento (una eVar o la variabile eventi) sulla pagina in cui *`transactionID`* è impostata. In caso contrario, non viene registrato alcun dato per il *`transactionID`*.

* Se state registrando [!UICONTROL transactionIDs] per più sistemi, ad esempio acquisti e lead, accertatevi che il valore in *`transactionID`* sia sempre univoco. Questo può essere ottenuto aggiungendo un prefisso all’ID, ad esempio lead_1234 e purchase_1234. [!UICONTROL Integration Data Sources] non funzionano come previsto ( [!UICONTROL Data Source] i dati si collegano ai dati errati) se una univoca *`transactionID`* viene vista due volte.

* Per impostazione predefinita, *`transactionID`* i valori vengono conservati per 90 giorni. Se il processo di interazione offline supera i 90 giorni, contatta l'Assistenza clienti per richiedere la proroga del limite.

>[!NOTE]
>
>La *`transactionID`* variabile può contenere caratteri diversi da una virgola. Deve trovarsi nella stessa posizione in cui è specificato il limite di caratteri (100 byte). Se si utilizzano caratteri multibyte, è necessario abilitare il supporto dei caratteri multibyte per evitare problemi con i caratteri imprevisti nel *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

I visitatori possono essere identificati dalla variabile o dall'indirizzo IP/Agente utente.

<!-- 

visitorID.xml

 -->

I caratteri alfanumerici possono *`visitorID`* essere fino a 100 e non devono contenere un trattino.

Se imposti esplicitamente un ID personalizzato, verrà sempre utilizzato prima degli altri metodi ID.

Ordine di utilizzo: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Dimensione massima* | ** Parametro debugger** | ** Report compilati** | ** Valore predefinito** |
|---|---|---|---|
| 100 byte | vid | n/d | "" |

**Sintassi e valori** possibili {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>La *`visitorID`* variabile non deve contenere un trattino.

**Esempi** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Impostazioni** di configurazione {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Nessuno

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

La variabile viene utilizzata per identificare il dominio con cui sono impostati i cookie.

<!-- 

visitorNamespace.xml

 -->

Se *`visitorNamespace`* viene utilizzato nel file JavaScript, non eliminarlo o modificarlo. Se *`visitorNamespace`* vengono apportate modifiche, tutti i visitatori segnalati in Analytics possono diventare nuovi visitatori. La cronologia del visitatore viene disconnessa dal traffico corrente e futuro. Non modificate questa variabile senza l'approvazione di un rappresentante Adobe.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | ns | N/D | "" |

Analytics utilizza un cookie per identificare in modo univoco i visitatori del sito. Se non *`visitorNamespace`* viene utilizzato, il cookie è associato a 2o7.net. Se *`visitorNamespace`* viene utilizzato, il cookie è associato a un sottodominio di 2o7.net. Tutti i visitatori del sito devono avere i loro cookie associati allo stesso dominio o sottodominio.

Il motivo per utilizzare la *`visitorNamespace`* variabile è di evitare il sovraccarico del limite di cookie di un browser. Internet Explorer impone un limite di 20 cookie per dominio. Utilizzando la *`visitorNamespace`* variabile, i cookie di Analytics di altre società non entrano in conflitto con i cookie dei visitatori.

**Sintassi e valori** possibili {#section_EE247FE371784CA4B6058182181F3EA1}

Il valore di *`visitorNamespace`* deve essere fornito da Adobe ed è una stringa di caratteri ASCII che non contengono virgole, punti, spazi o caratteri speciali.

```js
s.visitorNamespace="company_specific_value"
```

**Identificazione dei visitatori tra le suite** di rapporti {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Se non specificate un `visitorNamespace`, ogni suite di rapporti della società riceve il cookie dell’ID visitatore personalizzato scritto come `s_vi_[random string]`. Se specifichi `visitorNamespace`, lo stesso `s_vi` cookie verrà utilizzato per tutte le suite di rapporti che inviano i dati a quelle specificate `trackingServer`. Se avete implementato i tag per più suite, accertatevi di specificare lo spazio nomi visitatore in modo che lo stesso cookie venga utilizzato da ogni suite di rapporti.

**Esempi** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Impostazioni** di configurazione {#section_1128A2531ECC43DFA6749ECC21F050A2}

Nessuno

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

Le variabili e sono variabili di conversione.

<!-- 

zip.xml

 -->

Sono come eVar in quanto catturano eventi, ma a differenza delle eVar, non persistono. Le variabili *`zip`* e *`state`* sono come eVar che scadono immediatamente.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| 50 byte | zip | Conversione &gt; Profilo visitatore &gt; Codici postali | "" |

Poiché le *`state`* variabili e le *`zip`* variabili scadono immediatamente, gli unici eventi associati sono gli eventi attivati sulla stessa pagina e compilati. Ad esempio, se si utilizza *`zip`* per confrontare i tassi di conversione per CAP, è consigliabile compilare *`zip`* in ogni pagina del processo di estrazione. Adobe consiglia di utilizzare l'indirizzo di fatturazione come origine per il CAP. È possibile scegliere di utilizzare l'indirizzo di spedizione invece (supponendo che vi sia un solo indirizzo di spedizione per l'ordine). Un sito multimediale può scegliere di utilizzare *`zip`* e *`state`* per la registrazione o il tracciamento del click-through degli annunci.

**Sintassi e valori** possibili {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

La *`zip`* variabile non impone alcuna limitazione di valore o formato. Non esistono limitazioni *`zip`* al di fuori delle limitazioni standard delle variabili.

**Esempi** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Impostazioni** di configurazione {#section_7987084EECC34DD38B643B94F82385CA}

Nessuno

**Insidie, domande e suggerimenti**{#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Compilate [!UICONTROL zip] su ogni pagina in cui viene attivato un evento rilevante (ad esempio ogni pagina del processo di estrazione).
* Le *`zip`* variabili e *`state`* le variabili si comportano come eVar che scadono nella visualizzazione pagina.

