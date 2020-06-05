---
description: Leggi le best practice ed esempi di come compilare varie regole che puoi impostare per i tuoi canali di marketing.
title: Domande frequenti su Marketing Channels
translation-type: tm+mt
source-git-commit: d26edeed2f8d2c78c6e8cddaf8973870372a8b3d
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 0%

---


# Domande frequenti su Marketing Channels

Consultate [Creare regole](/help/components/c-marketing-channels/c-rules.md) di elaborazione del canale di marketing per le definizioni dei campi visualizzati sulla [!UICONTROL Marketing Channel Processing Rules] pagina.

## Domande frequenti {#faq}

Ogni implementazione delle regole di elaborazione del canale di marketing può variare a seconda dei codici di monitoraggio. La configurazione di regole che forniscono i risultati che state cercando può richiedere alcune riflessioni creative per risolvere i problemi.

**Domanda**: I miei codici di monitoraggio non seguono un pattern, e ho migliaia che devono essere specificati per il mio canale Affiliates.

* Utilizzate il processo di eliminazione. Se i canali E-mail e Affiliati utilizzano lo stesso parametro della stringa di query, ma disponete solo di alcuni codici di tracciamento e-mail, potete specificare i codici di tracciamento e-mail in un set di regole che definisce l&#39;e-mail. Quindi, puoi classificare tutti gli altri codici di tracciamento con *`affiliates.`*
* Nel sistema e-mail, aggiungete un parametro di stringa di query a tutti gli URL della pagina di destinazione, ad esempio *`&ch=eml`*. Create un set di regole per rilevare se il parametro query ch è uguale a *`eml`*. Se non contiene *`eml`*, è una filiale.

**Domanda**: I domini di riferimento contengono più dati di quanto mi aspetto.

* I domini di riferimento potrebbero essere troppo alti nell&#39;elenco delle regole di elaborazione. Deve essere uno degli ultimi set di regole (o l&#39;ultimo), perché l&#39;ordine di elaborazione è importante.

**Domanda**: Ho creato una regola che corrisponde a un parametro della stringa di query e non funziona.

* Accertatevi che il nome del parametro sia specificato nei campi del parametro della stringa di query (in genere un valore alfanumerico). Inoltre, accertatevi che il valore del parametro sia specificato dopo l&#39;operatore, come illustrato nell&#39;esempio seguente di una regola e-mail.

   ![](assets/example_email.png)

**Domanda**: Perché tutto il mio ultimo traffico è attribuito a un dominio interno?

* È presente una regola che corrisponde al traffico interno. Tieni presente che queste regole vengono elaborate per ogni hit che un visitatore fa sul tuo sito, non solo per la prima visita. Se disponete di una regola come *`Page URL exists`* senza altri criteri, il canale corrisponde a ogni hit successivo sul sito, perché un URL di pagina esiste sempre.

**Domanda**: Come si esegue il debug del traffico visualizzato in Nessun canale identificato nel report?

* Le regole vengono elaborate in ordine. Se non è stato trovato alcun criterio specifico, gli hit rientrano in una delle tre categorie seguenti:

1. Nessun referente (visita diretta).

2. Referente interno nella prima pagina di una visita.

3. Problema di elaborazione sulla pagina.

Accertatevi di disporre di un canale per queste tre possibilità. Ad esempio, creare regole che dicano:

1. **[!UICONTROL Referrer]** e **[!UICONTROL Does Not Exist]** e **[!UICONTROL Is First Page of Visit]**. (Vedere [Diretta.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** ed **[!UICONTROL Is First page of Visit]**. (Vedere [Interno](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** e **[!UICONTROL Exists]** e **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Infine, create un canale *Altro* che acquisisca gli hit rimanenti, come descritto in [Nessun canale identificato](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Relazione tra il primo e l&#39;ultimo tocco

Per comprendere l’interazione tra le precedenti dimensioni del primo e dell’ultimo tocco e per confermare che le impostazioni locali funzionano come previsto, potete eseguire il pulling di un rapporto sui canali di primo tocco, relativo in parte a un rapporto sull’ultimo canale di tocco, con l’aggiunta della metrica di successo chiave (vedere l’esempio di seguito). L’esempio illustra l’interazione tra il primo e l’ultimo canale di tocco.

![](assets/int-channel3.png)

L&#39;intersezione in cui prima è uguale all&#39;ultimo tocco è la diagonale della tabella. Sia l&#39;aggiornamento diretto che l&#39;aggiornamento della sessione ottengono il credito dell&#39;ultimo tocco solo se questi erano anche il primo canale touch, perché non possono ottenere credito da altri canali persistenti (righe evidenziate).

## Motivi per nessun canale identificato {#no-channel-identified}

Se le regole non acquisiscono dati o se le regole non sono configurate correttamente, il rapporto visualizza i dati nella [!UICONTROL No Channel Identified] riga del rapporto. Potete creare un set di regole denominato *Altro*, ad esempio, al termine dell&#39;ordine di elaborazione, che identifichi anche il traffico interno.

![](assets/example_other.png)

Questo tipo di regola funge da clausola catch-all per garantire che il traffico dei canali corrisponda sempre al traffico esterno, e in genere non finisca in **[!UICONTROL No Channel Identified]**. Fare attenzione a non creare una regola che identifichi anche il traffico interno. L&#39;impostazione del valore del canale su **[!UICONTROL Referring Domain]** o su **[!UICONTROL Page URL]** sono i modi più comuni e utili per creare un&#39;altra regola efficace.

>[!NOTE] Potrebbe ancora esserci del traffico di canale che può rientrare nella categoria Nessun canale identificato. Ad esempio: Un visitatore accede al sito e annota una pagina e, nella stessa visita, torna alla pagina tramite il segnalibro. Poiché questa non è la prima pagina della visita, non andrà né nel canale diretto né nell&#39;altro canale perché non c&#39;è un dominio di riferimento.

## Motivi per interni (aggiornamento sessione) {#internal}

L&#39;aggiornamento dell&#39;ultima sessione può avvenire solo se si è trattato anche del primo tocco. Consulta &quot;Relazione tra il primo e l&#39;ultimo tocco&quot; sopra. Gli scenari seguenti illustrano come l&#39;aggiornamento della sessione potrebbe essere un canale di primo tocco.

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

