---
title: Regole di elaborazione per i canali di marketing
description: Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul tuo sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l'hit a Nessun canale identificato.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Regole di elaborazione per i canali di marketing

Le regole di elaborazione del canale di marketing determinano se un hit di visitatore soddisfa i criteri assegnati a un canale. Le regole elaborano ogni hit che un visitatore fa sul tuo sito. Quando una regola non soddisfa i criteri per un canale, o se le regole non sono configurate correttamente, il sistema assegna l&#39;hit a Nessun canale identificato.

Di seguito sono riportate importanti linee guida per la creazione di regole:

* Ordinare le regole nell&#39;ordine desiderato.
* Alla fine dell’elenco, includete una regola catch-all, ad esempio Altro. Questa regola identifica il traffico esterno ma non il traffico interno.

   Vedere [Nessun canale identificato.](/help/components/c-marketing-channels/c-faq.md)

>[!NOTE] Sebbene queste regole non influenzino i rapporti al di fuori dei canali di marketing, influiscono sulla raccolta dei dati dei canali di marketing. I dati raccolti con queste regole sono permanenti al 100% e le regole modificate dopo la raccolta dei dati non sono retroattive. È vivamente consigliato rivedere e considerare tutte le circostanze prima di salvare [!UICONTROL Marketing Channel Processing Rules] per attenuare la raccolta dei dati in canali non corretti.

## Prerequisiti

* Consultate le informazioni concettuali in [Guida introduttiva ai canali](/help/components/c-marketing-channels/c-getting-started-mchannel.md)di marketing.
* Create uno o più canali in modo da poter assegnare loro le regole. Consultate [Aggiunta di canali di marketing.](/help/components/c-marketing-channels/c-channels.md)

## Creare regole di elaborazione per il canale di marketing

Crea regole di elaborazione del canale di marketing, che determinano se un hit di visitatore soddisfa i criteri assegnati a un canale.

Questa procedura utilizza una regola e-mail come esempio. L&#39;esempio presuppone che sia stato aggiunto un canale e-mail all&#39;elenco dei canali nella pagina Marketing Channel Manager.

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona una suite di rapporti.

   Se nella suite di rapporti non sono definiti canali, viene visualizzata la [!UICONTROL Marketing Channels: Auto Setup] pagina.

   Consultate [Eseguire la configurazione](/help/components/c-marketing-channels/c-getting-started-mchannel.md)automatica.

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**.

   ![Risultato passaggio](assets/marketing_channel_rules.png)

1. Dal **[!UICONTROL Add New Rule Set]** menu, selezionare **[!UICONTROL Email]**.

   Qui non si seleziona il canale, ma un modello che completa la regola con alcuni dei parametri necessari.

   ![Risultato passaggio](assets/example_email.png)

   Utilizzare la logica booleana (istruzioni if / then) per configurare una regola. Ad esempio, in una regola del canale di posta elettronica, fornire le impostazioni o le informazioni enfatizzate nella seguente istruzione di regola:

   `"If **[!UICONTROL All]** or **[!UICONTROL Any]** of the following are true:  **[!UICONTROL Query String Parameter]** *<value>* **[!UICONTROL exists]**...`

   `"Then identify the channel as **[!UICONTROL Email]**...`

   `"Then set the channel's value to **[!UICONTROL Query String Parameter]** *<value>*."`

   In questo esempio *`<value>`* è il parametro della stringa di query utilizzato per la campagna e-mail, ad esempio *`eml`*.
1. Per continuare a creare le regole, fare clic su **[!UICONTROL Add Rule]**.
1. Per assegnare priorità alle regole, trascinatele fino alla posizione desiderata.
1. Fai clic su **[!UICONTROL Save.]**

>[!MORELIKETHIS]
>
>* [Domande frequenti ed esempi](/help/components/c-marketing-channels/c-faq.md)


## Criteri regola canale di marketing

Questa tabella di riferimento definisce i campi, le opzioni e gli attributi che potete selezionare nella pagina Regole di elaborazione del canale di marketing.

| Termine | Definizione |
|--- |--- |
| Tutto | Attiva questo canale solo quando tutte le regole della regola numerata sono vere. |
| Qualsiasi | Attiva questo canale quando una delle regole del set di regole è vera. Questa opzione è disponibile solo se nella regola numerata è presente più di una regola. |
| ID AMO | Il codice di tracciamento principale utilizzato dalle integrazioni Advertising Cloud e Advertising Analytics. Quando una di queste integrazioni è abilitata, il prefisso del codice di tracciamento può essere utilizzato per identificare canali specifici di Advertising Cloud. L&#39;utilizzo di &quot;AMO ID&quot; inizia con &quot;AL&quot; per la ricerca, &quot;AC&quot; per la visualizzazione o &quot;AO&quot; per Social. Quando l&#39;ID AMO viene utilizzato nei canali di marketing, le metriche click/cost/impression possono essere attribuite al canale corretto (se non configurate, queste metriche andranno a Direct o Nessuno). |
| ID AMO ED | Il codice di tracciamento secondario utilizzato da Advertising Cloud. Lo scopo principale di questo codice di tracciamento è quello di fungere da chiave per l&#39;invio di dati ad Ad Cloud. Tuttavia, può essere utilizzato anche per identificare la visualizzazione ClickThroughs rispetto a visualizzazione ViewThroughs se si desidera visualizzarli come due canali di marketing separati. A tale scopo, è possibile impostare la logica del canale di marketing per le estremità &quot;AMO EF ID&quot; con &quot;:d&quot; per le estremità Display ClickThrough o &quot;AMO EF ID&quot; con &quot;:i&quot; per Display ViewThrough. Se non desideri dividere la visualizzazione in due canali, utilizza invece la dimensione ID AMO. |
| Variabili di conversione | È costituito da eVar abilitate per questa suite di rapporti e si applica solo quando queste variabili sono impostate tramite il codice Adobe sulla pagina.  Consulta la Guida all’implementazione. |
| Exists | Sono disponibili diverse selezioni, tra cui:<ul><li>**Non Esiste**: Specifica che l&#39;attributo hit non esiste nella richiesta. Ad esempio, in un dominio di riferimento, se l&#39;utente digita un URL o fa clic su un segnalibro, l&#39;attributo di dominio di riferimento non esiste.</li><li>**Vuoto**: Specifica che esiste un attributo hit, in genere un parametro eVar o una stringa di query, ma non è associato alcun valore all&#39;attributo hit.</li><li>**Non Contiene**: Consente di specificare, ad esempio, che un dominio di riferimento non contiene un valore specifico (anziché utilizzare la selezione &quot;Contiene&quot;).</li></ul> |
| Identificare il canale come | Associa la regola a un canale di marketing aggiunto alla pagina Marketing Channel Manager.  Consultate Aggiunta di canali di marketing. |
| Corrisponde alle regole di rilevamento ricerche pagate | Ricerca a pagamento rilevata da Adobe. Le ricerche pagate sono quando le aziende pagano una tariffa per il motore di ricerca per elencare il loro sito. Le ricerche pagate vengono in genere visualizzate nella parte superiore o destra dei risultati della ricerca. |
| Corrisponde alle regole di rilevamento ricerche naturali | Una ricerca non a pagamento rilevata dai report Adobe. |
| Il Referente Corrisponde Ai Filtri URL Interni | Una visita il cui URL di pagina corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. |
| Il Referente Non Corrisponde Ai Filtri URL Interni | L&#39;URL di provenienza non corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. Potete utilizzare questa impostazione con URL pagina ed Esiste per impostare una regola catch-all, in modo che nessuna visita venga effettuata nella sezione Nessun canale identificato del rapporto. |
| Ignora gli hit corrispondenti ai filtri URL interni | (Per i referenti) Tiene traccia solo degli hit provenienti da siti esterni. In genere, lasciate questa impostazione attivata a meno che non desideriate includere il traffico interno. |
| Prima pagina della visita | La prima pagina di una visita rilevata dai report Adobe. |
| Page | Il nome della pagina Web del sito a cui è assegnato un tag mediante il Web beacon di Adobe. Questo valore è equivalente a s.pageName. Gli esempi includono `Home Page` e `About Us`. |
| Dominio pagina | Il dominio della pagina in cui il visitatore arriva, ad esempio `products.example.co.uk`. |
| Dominio pagina e percorso | Il dominio e il percorso, ad esempio `products.example.co.uk/mens/pants/overview.html` . |
| Dominio principale pagina (TLD+1) | Il dominio principale della pagina in cui il visitatore arriva, ad esempio example.co.uk . |
| URL della pagina | L’URL di una pagina Web sul sito. |
| Dominio di riferimento | Il dominio di provenienza dei visitatori prima che visitassero il sito, ad esempio, i referenti provenienti da `abcsite.com` e `xyzsite.com`. |
| Parametro stringa query | Se l’URL di una pagina sul sito è simile a quello di `https://example.com/?page=12345&cat=1`, la pagina e il gatto sono entrambi parametri di stringa di query. (Consulta `https://en.wikipedia.org/wiki/Query_string`.)  È possibile specificare un solo parametro di stringa di query per set di regole. Per aggiungere ulteriori parametri di stringa di query, utilizzare `ANY` come operatore, quindi aggiungere nuovi parametri di stringa di query alla regola. |
| Referrer | Posizione della pagina Web (URL completo) in cui si trovavano i visitatori prima di accedere al sito. Un referente esiste al di fuori del dominio definito. |
| Dominio e percorso di riferimento | Una concatenazione del dominio di riferimento e del percorso dell&#39;URL. Alcuni esempi:    `www.example.com/products/id/12345` o `ad.example.com/foo` |
| Parametro di riferimento | Un parametro della stringa di query sull’URL del referente. Ad esempio, se i visitatori provengono da `example.com/?page=12345&cat=1`, i parametri di riferimento sono pagina e gatto. |
| Riferimento a dominio radice | Il dominio radice del referente. Un referente esiste al di fuori del dominio definito. |
| Motore di ricerca | Un motore di ricerca come Google o Yahoo! che ha portato i visitatori al tuo sito. |
| Parole chiave di ricerca | Una parola utilizzata per eseguire una ricerca utilizzando un motore di ricerca. |
| Motore di ricerca + Parole chiave | Una concatenazione della parola chiave di ricerca e del motore di ricerca per identificare in modo univoco il motore di ricerca. Ad esempio, se cercate la parola computer, il motore di ricerca e la parola chiave sono identificati come segue: `Search Tracking Code = "<search_type>:<search engine>:<search keyword>" where    search_type = "n" or "p", search_engine = "Google", and search_keyword = "computer"`**Nota:**n = naturale; p = paid |
| Imposta il valore del canale su | Oltre a sapere quale canale di marketing porta un visitatore sul sito, puoi sapere quale banner pubblicitario, parola chiave di ricerca o campagna e-mail all&#39;interno del canale riceve credito per l&#39;attività del sito di un visitatore. Questo ID è un valore di canale memorizzato insieme al canale. Spesso questo valore è un ID campagna incorporato nella pagina di destinazione o nell’URL di provenienza; in altri casi è la combinazione di motori di ricerca e parole chiave di ricerca, o l&#39;URL di provenienza a identificare il visitatore in modo più corretto da un determinato canale. |

## Canale interno (aggiornamento sessione)

Il canale interno (spesso rinominato come Aggiornamento sessione) consiste in visite al sito in cui l’URL di provenienza corrisponde alla configurazione dei filtri URL interni nell’Admin Console, il che significa che il visitatore è venuto dall’interno del sito per avviare la visita.

![](assets/int-channel1.png)

### Escludere le best practice

È consigliabile deselezionare l’opzione Ignora ultimo tocco per i canali Direct e Internal, in modo che non possano ricevere credito da altri canali touch persistenti (o da altri canali reciproci).

>[!NOTE]Questo documento presuppone che l&#39;opzione Aggiornamento diretto e Aggiornamento sessione non siano selezionate.

![](assets/int-channel2.png)

### Periodo di coinvolgimento

Sia il primo che l’ultimo canale touch per un visitatore vengono reimpostati dopo 30 giorni di inattività in quel browser.

>[!NOTE] Il valore predefinito è 30 giorni e può essere modificato in base alle esigenze tramite le impostazioni Amministratore.

Se il visitatore utilizza il sito frequentemente, la finestra di coinvolgimento si espanderà con loro. Devono essere inattivi per 30 giorni affinché il periodo scada e i canali vengano reimpostati.
Esempio:

* Giorno 1: L&#39;utente accede al sito sul display. I canali Primo e Ultimo tocco verranno impostati su Display.

* Giorno 2: L&#39;utente viene al sito su Natural Search. Il primo tocco rimane Display e l&#39;ultimo tocco è impostato su Natural Search.

* Giorno 35: L&#39;utente non è stato sul sito in 33 giorni e torna utilizzando la scheda che aveva aperto nel browser. Presupponendo una finestra di coinvolgimento di 30 giorni, la finestra si sarebbe chiusa e i cookie di Marketing Channel sarebbero scaduti. Il primo canale touch e l’ultimo touch vengono reimpostati e impostati su Aggiornamento sessione, dal momento che l’utente proviene da un URL interno.

### Relazione tra il primo e l&#39;ultimo tocco

Per comprendere l’interazione tra il primo e l’ultimo tocco e per confermare che le impostazioni locali funzionano come previsto, potete eseguire il pulling di un rapporto sui canali di primo tocco, relativo in parte a un rapporto sull’ultimo canale, con l’aggiunta della metrica di successo chiave (vedere l’esempio di seguito). L’esempio illustra l’interazione tra il primo e l’ultimo canale di tocco.

![](assets/int-channel3.png)

L&#39;intersezione in cui prima corrisponde all&#39;ultimo tocco è evidenziata in arancione. Sia l&#39;aggiornamento diretto che l&#39;aggiornamento della sessione ottengono solo l&#39;ultimo tocco di credito se erano anche il primo canale touch, perché non possono ottenere credito da altri canali persistenti (righe evidenziate in grigio).

### Perché si verifica l&#39;aggiornamento della sessione?

Poiché sappiamo che l’ultimo aggiornamento della sessione può avvenire solo se si tratta anche del primo tocco, gli scenari seguenti spiegano come l’aggiornamento della sessione potrebbe essere un canale di primo tocco.

**Scenario 1: Timeout sessione**

Un visitatore accede al sito Web e quindi lascia la scheda aperta nel browser per utilizzarla in un secondo momento. Il periodo di coinvolgimento del visitatore scade (o elimina volontariamente i cookie) e utilizza la scheda aperta per visitare nuovamente il sito Web. Poiché l’URL di provenienza è un dominio interno, la visita verrà classificata come Aggiornamento sessione.

**Scenario 2: Non tutte le pagine del sito dispongono di tag**

Un visitatore arriva sulla pagina A senza tag, quindi passa alla pagina B con tag. La pagina A viene visualizzata come referente interno e la visita viene classificata come Aggiornamento sessione.

**Scenario 3: Reindirizza**

Se un reindirizzamento non è impostato per trasmettere i dati del referente alla nuova pagina di destinazione, i dati del referente di immissione vera andranno persi e ora la pagina di reindirizzamento (probabilmente una pagina interna) verrà visualizzata come dominio di riferimento. La visita verrà classificata come Aggiornamento sessione.

**Scenario 4: Traffico tra domini**

Un visitatore passa da un dominio che viene attivato alla Suite A a un altro dominio che viene attivato alla Suite B. Se nella Suite B i filtri URL interni includono il primo dominio, la visita nella Suite B verrà registrata come Interno, poiché Marketing Channels la vede come una nuova visita nella seconda suite. La visita verrà classificata come Aggiornamento sessione.

**Scenario 5: Lunghi tempi di caricamento delle pagine**

Un visitatore arriva sulla pagina A, che pesa sul contenuto, e il codice Adobe Analytics si trova nella parte inferiore della pagina. Prima che tutto il contenuto (inclusa la richiesta di immagini di Adobe Analytics) possa essere caricato, il visitatore fa clic sulla pagina B. La pagina B avvia la richiesta di immagine di Adobe Analytics. Poiché la richiesta di immagine della pagina A non è mai stata caricata, la seconda pagina viene visualizzata come il primo hit della visita in Adobe Analytics, con la pagina A come referente. La visita viene classificata come Aggiornamento sessione.

**Scenario 6: Cancellazione dei cookie nel mid-site**

Un visitatore accede al sito e a metà sessione cancella i cookie. Entrambi i canali First e Last-touch venivano reimpostati e la visita veniva classificata come Aggiornamento sessione (perché il referente era interno).
