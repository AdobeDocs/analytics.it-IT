---
title: Regole di elaborazione per i canali di marketing
description: Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul tuo sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
translation-type: tm+mt
source-git-commit: 4b6107fe57787e639fb06ef957d6230d1bc45bd1
workflow-type: tm+mt
source-wordcount: '2004'
ht-degree: 3%

---


# Regole di elaborazione per i canali di marketing

Le regole di elaborazione del canale di marketing determinano se un hit visitatore soddisfa i criteri assegnati a un canale elaborando ogni hit che un visitatore compie sul sito. Le regole vengono elaborate nell&#39;ordine specificato e quando viene soddisfatta una regola, il sistema interrompe l&#39;elaborazione delle regole rimanenti.

![](assets/buckets_2.png)

Note aggiuntive sull&#39;elaborazione:
* I dati raccolti con queste regole sono permanenti al 100% e le regole modificate dopo la raccolta dei dati non sono retroattive. È vivamente consigliato rivedere e considerare tutte le circostanze prima di salvare [!UICONTROL Marketing Channel Processing Rules] per attenuare la raccolta dei dati in canali non corretti.
* Il rapporto può elaborare fino a 25 canali alla volta.
* Le regole possono accedere alle variabili che VISTA ha impostato, ma non ai dati che VISTA ha eliminato.
* Due canali di marketing non ricevono mai crediti per lo stesso evento (ad esempio acquisti o clic). In questo modo, i canali di marketing sono diversi dalle eVar (due eVar potrebbero ricevere credito per lo stesso evento).
* Se esiste una copertura delle regole, è possibile che [nessun canale identificato.](/help/components/c-marketing-channels/c-faq.md)

## Prerequisiti

* Consultate le informazioni concettuali in [Guida introduttiva ai canali](/help/components/c-marketing-channels/c-getting-started-mchannel.md)di marketing.
* Create uno o più canali in modo da poter assegnare loro le regole. Consultate [Aggiunta di canali di marketing.](/help/components/c-marketing-channels/c-channels.md)

## Creare regole di elaborazione per il canale di marketing

Crea regole di elaborazione del canale di marketing, che determinano se un hit di visitatore soddisfa i criteri assegnati a un canale.

Questa procedura utilizza una regola e-mail come esempio. L&#39;esempio presuppone che sia stato aggiunto un canale e-mail all&#39;elenco dei canali nella pagina Marketing Channel Manager.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
2. Seleziona una suite di rapporti.

   Se nella suite di rapporti non sono definiti canali, viene visualizzata la [!UICONTROL Marketing Channels: Auto Setup] pagina.

   Consultate [Eseguire la configurazione](/help/components/c-marketing-channels/c-getting-started-mchannel.md)automatica.

3. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Risultato passaggio](assets/marketing_channel_rules.png)

4. Dal **[!UICONTROL Add New Rule Set]** menu, selezionare **[!UICONTROL Email]**.

   Qui non si seleziona il canale, ma un modello che completa la regola con alcuni dei parametri necessari. Potete modificare il modello in base alle esigenze.

   ![Risultato passaggio](assets/example_email.png)

5. Per continuare a creare le regole, fare clic su **[!UICONTROL Add Rule]**.
6. Per assegnare priorità alle regole, trascinatele fino alla posizione desiderata.
7. Fai clic su **[!UICONTROL Save.]**

Continua verso il basso in questa pagina per visualizzare le raccomandazioni per l&#39;ordine delle regole di canale così come altri esempi di definizione.

### Imposta il valore del canale di marketing

**[!UICONTROL Add Rule]** **Impostate il valore** del canale per definire la dimensione di dettaglio del canale di marketing disponibile per quel canale. Questo consente di suddividere le dimensioni dei canali di marketing e visualizzare informazioni più dettagliate sul canale.

Si consiglia di impostare il valore del canale sugli stessi criteri utilizzati per definire il canale stesso. Ad esempio, se per definire il canale viene utilizzato il parametro della stringa di query, impostare anche il parametro della stringa di query come valore del canale.

### Criteri regola

Questa tabella di riferimento definisce i campi, le opzioni e gli attributi che potete utilizzare per definire le regole di elaborazione del canale di marketing.

| Termine | Definizione |
|--- |--- |
| Tutte | Attiva questo canale solo quando tutte le regole della regola numerata sono vere. |
| Any | Attiva questo canale quando una delle regole del set di regole è vera. Questa opzione è disponibile solo se nella regola numerata è presente più di una regola. |
| ID AMO | Il codice di tracciamento principale utilizzato dalle integrazioni  Advertising Cloud e  Advertising Analytics. Quando è abilitata una di queste integrazioni, il prefisso del codice di tracciamento può essere utilizzato per identificare  canali Advertising Cloud specifici. L&#39;utilizzo di &quot;AMO ID&quot; inizia con &quot;AL&quot; per la ricerca, &quot;AC&quot; per la visualizzazione o &quot;AO&quot; per Social. Quando l&#39;ID AMO viene utilizzato nei canali di marketing, le metriche click/cost/impression possono essere attribuite al canale corretto (se non configurate, queste metriche andranno a Direct o Nessuno). |
| ID AMO ED | Il codice di tracciamento secondario utilizzato da  Advertising Cloud. Lo scopo principale di questo codice di tracciamento è quello di fungere da chiave per l&#39;invio di dati a  Ad Cloud. Tuttavia, può essere utilizzato anche per identificare la visualizzazione ClickThroughs rispetto a visualizzazione ViewThroughs se si desidera visualizzarli come due canali di marketing separati. A tale scopo, è possibile impostare la logica del canale di marketing per le estremità &quot;AMO EF ID&quot; con &quot;:d&quot; per le estremità Display ClickThrough o &quot;AMO EF ID&quot; con &quot;:i&quot; per Display ViewThrough. Se non desideri dividere la visualizzazione in due canali, utilizza invece la dimensione ID AMO. |
| Variabili di conversione | È costituito da eVar abilitate per questa suite di rapporti e si applica solo quando queste variabili sono impostate tramite il codice di Adobe  sulla pagina.  Consulta la Guida all’implementazione. |
| Esiste | Sono disponibili diverse selezioni, tra cui:<ul><li>**Non Esiste**: Specifica che l&#39;attributo hit non esiste nella richiesta. Ad esempio, in un dominio di riferimento, se l&#39;utente digita un URL o fa clic su un segnalibro, l&#39;attributo di dominio di riferimento non esiste.</li><li>**Vuoto**: Specifica che esiste un attributo hit, in genere un parametro di stringa di eVar o di query , ma non è associato alcun valore all&#39;attributo hit.</li><li>**Non Contiene**: Consente di specificare, ad esempio, che un dominio di riferimento non contiene un valore specifico (anziché utilizzare la selezione &quot;Contiene&quot;).</li></ul> |
| Identificare il canale come | Associa la regola a un canale di marketing aggiunto alla pagina Marketing Channel Manager.  Consultate Aggiunta di canali di marketing. |
| Corrisponde alle regole di rilevamento ricerche pagate | Una ricerca a pagamento rilevata dal Adobe . Le ricerche pagate sono quando le aziende pagano una tariffa per il motore di ricerca per elencare il loro sito. Le ricerche pagate vengono in genere visualizzate nella parte superiore o destra dei risultati della ricerca. |
| Corrisponde alle regole di rilevamento ricerche naturali | Una ricerca non pagata rilevata dai report di  Adobe. |
| Il Referente Corrisponde Ai Filtri URL Interni | Una visita il cui URL di pagina corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. |
| Il Referente Non Corrisponde Ai Filtri URL Interni | L&#39;URL di provenienza non corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. Potete utilizzare questa impostazione con URL pagina ed Esiste per impostare una regola catch-all, in modo che nessuna visita venga effettuata nella sezione Nessun canale identificato del rapporto. |
| Ignora gli hit corrispondenti ai filtri URL interni | (Per i referenti) Tiene traccia solo degli hit provenienti da siti esterni. In genere, lasciate questa impostazione attivata a meno che non desideriate includere il traffico interno. |
| Prima pagina della visita | La prima pagina di una visita rilevata dai report di  Adobe. |
| Pagina | Il nome della pagina Web del sito a cui è assegnato un tag mediante  Adobe  Web beacon. Questo valore è equivalente a s.pageName. Gli esempi includono `Home Page` e `About Us`. |
| Dominio pagina | Il dominio della pagina in cui il visitatore arriva, ad esempio `products.example.co.uk`. |
| Dominio pagina e percorso | Il dominio e il percorso, ad esempio `products.example.co.uk/mens/pants/overview.html` . |
| Dominio principale pagina (TLD+1) | Il dominio principale della pagina in cui il visitatore arriva, ad esempio example.co.uk . |
| URL della pagina | L’URL di una pagina Web sul sito. |
| Dominio di riferimento | Il dominio di provenienza dei visitatori prima che visitassero il sito, ad esempio, i referenti provenienti da `abcsite.com` e `xyzsite.com`. |
| Query String Parameter | Se l’URL di una pagina sul sito è simile a quello di `https://example.com/?page=12345&cat=1`, la pagina e il gatto sono entrambi parametri di stringa di query. (Consulta `https://en.wikipedia.org/wiki/Query_string`.)  È possibile specificare un solo parametro di stringa di query per set di regole. Per aggiungere ulteriori parametri di stringa di query, utilizzare `ANY` come operatore, quindi aggiungere nuovi parametri di stringa di query alla regola. |
| Referrer | Posizione della pagina Web (URL completo) in cui si trovavano i visitatori prima di accedere al sito. Un referente esiste al di fuori del dominio definito. |
| Dominio e percorso di riferimento | Una concatenazione del dominio di riferimento e del percorso dell&#39;URL. Alcuni esempi:    `www.example.com/products/id/12345` o `ad.example.com/foo` |
| Parametro di riferimento | Un parametro della stringa di query sull’URL del referente. Ad esempio, se i visitatori provengono da `example.com/?page=12345&cat=1`, i parametri di riferimento sono pagina e gatto. |
| Riferimento a dominio radice | Il dominio radice del referente. Un referente esiste al di fuori del dominio definito. |
| Motore di ricerca | Un motore di ricerca come Google o Yahoo! che ha portato i visitatori al tuo sito. |
| Parole chiave di ricerca | Una parola utilizzata per eseguire una ricerca utilizzando un motore di ricerca. |
| Motore di ricerca + Parole chiave | Una concatenazione della parola chiave di ricerca e del motore di ricerca per identificare in modo univoco il motore di ricerca. Ad esempio, se cercate la parola computer, il motore di ricerca e la parola chiave sono identificati come segue: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Nota:** n = naturale; p = paid |
| Imposta il valore del canale su | Oltre a sapere quale canale di marketing porta un visitatore sul sito, puoi sapere quale banner pubblicitario, parola chiave di ricerca o campagna e-mail all&#39;interno del canale riceve credito per l&#39;attività del sito di un visitatore. Questo ID è un valore di canale memorizzato insieme al canale. Spesso questo valore è un ID campagna incorporato nella pagina di destinazione o nell’URL di provenienza; in altri casi è la combinazione di motori di ricerca e parole chiave di ricerca, o l&#39;URL di provenienza a identificare il visitatore in modo più corretto da un determinato canale. |

## Ordine e definizioni delle regole del canale di marketing {#channel-rules}

Le regole del canale vengono elaborate nell&#39;ordine specificato. Un approccio consigliato all&#39;ordine dei canali è quello di mettere i canali pagati o gestiti al primo posto (ad esempio, ricerca a pagamento, ricerca naturale, visualizzazione, e-mail) in modo che ricevano credito, seguito da canali organici (ad esempio, diretti, interni, domini di riferimento).

Di seguito è riportato l&#39;ordine consigliato per le regole di canale e per le definizioni di esempio:

### Ricerca pagata {#paid-search}

La ricerca a pagamento è una parola o una frase a cui si paga un motore di ricerca per la posizione nei risultati della ricerca. Questo canale viene generalmente definito in base al parametro della stringa di query (vedere Esempio di canale di visualizzazione) o alle regole di rilevamento della ricerca a pagamento. La decisione dipende dai dettagli del canale di marketing che desideri registrare.

#### Rilevamento di ricerca a pagamento

Per rispettare le regole di rilevamento delle ricerche pagate, il canale di marketing utilizza le impostazioni configurate sulla [!UICONTROL Paid Search Detection] pagina. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). L&#39;URL di destinazione corrisponde alla regola di rilevamento della ricerca a pagamento esistente per quel motore di ricerca.

Per la regola del canale di marketing, le [!UICONTROL Paid Search] impostazioni sono le seguenti:

![](assets/example_paid_search.png)

Per ulteriori informazioni, consulta [Rilevamento](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) ricerca a pagamento in Amministratore.

### Ricerca naturale {#natural-search}

Una ricerca naturale si verifica quando i visitatori trovano il sito Web tramite una ricerca Web, dove il motore di ricerca ha classificare il sito senza pagare per l&#39;elenco.

In Analytics non è disponibile il rilevamento della ricerca naturale. Dopo aver impostato il rilevamento della ricerca a pagamento, il sistema sa che se un referente di ricerca non era un referente di ricerca a pagamento, deve essere un referente di ricerca naturale. Per ulteriori informazioni, consulta Rilevamento [ricerca a](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) pagamento nell’amministratore.

Per la regola del canale di marketing, le impostazioni di Ricerca naturale sono le seguenti:

![](assets/example_natural_search.png)

### Visualizzazione {#display}

Questa regola identifica i visitatori provenienti da annunci pubblicitari per banner. È identificato da un parametro di stringa di query nell&#39;URL di destinazione, in questo caso *`Ad_01`*.

![](assets/example_display.png)

### E-mail {#email}

Questa regola identifica i visitatori provenienti da campagne e-mail. È identificato da un parametro della stringa di query nell’URL di destinazione, in questo caso *`eml`*:

![](assets/example_email.png)

### Affiliati {#afilliates}

Questa regola identifica i visitatori che provengono da uno specifico set di domini di provenienza. Nella regola, puoi elencare i domini delle filiali che desideri monitorare, come segue:

![](assets/example_affiliates.png)

### Altre campagne {#other-campaigns}

Una best practice consiste nell&#39;includere un canale &quot;Altre campagne&quot; che segua tutte le regole sui canali a pagamento. Questo canale funge da elemento catch-all per il traffico a pagamento non categorizzato.

![](assets/other-campaigns.png)

### Social Network {#social-networks}

Questa regola identifica i visitatori che provengono da un social network, come Facebook*. Il canale viene spesso rinominato come Organic Social. Le impostazioni possono essere le seguenti:

![](assets/example_social.png)

### Canale interno (aggiornamento sessione){#internal}

Questa regola prevede che i visitatori con il relativo URL di provenienza corrisponda all’impostazione Filtri URL interni nel Admin Console , il che significa che il visitatore è venuto dall’interno del sito per iniziare la visita. Questo canale viene spesso rinominato Aggiornamento sessione.

![](assets/int-channel1.png)

Per ulteriori informazioni sui motivi per cui si verifica questo canale, consulta [Motivi per l’interno (aggiornamento sessione)](https://docs.adobe.com/content/help/en/analytics/components/marketing-channels/c-faq.html) .

### Direct {#direct}

Questa regola identifica i visitatori che non dispongono di un dominio di riferimento, che include i visitatori che arrivano direttamente al sito, ad esempio da un collegamento Preferiti o incollando un collegamento nel loro browser. Questo canale viene spesso rinominato in Direct Typed/Segnalibro.

![](assets/example_direct.png)

### Canale Domains di riferimento {#referring-domains}

Il canale Domini di riferimento identifica i visitatori con un dominio di riferimento. Insieme, i canali di domini Interno, Diretto e Referente fungono da catch-all per tutti gli hit rimanenti che non sono ancora stati classificati in un canale.

![](assets/referring-domains.png)