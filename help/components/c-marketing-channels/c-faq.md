---
description: Leggi le best practice ed esempi di come compilare varie regole che puoi impostare per i tuoi canali di marketing.
title: Domande frequenti e esempi su Marketing Channels
translation-type: tm+mt
source-git-commit: 21f4b9df688776f7a1db96f76e258031ae3abb3d

---


# Domande frequenti e esempi su Marketing Channels

Consultate [Creare regole](/help/components/c-marketing-channels/c-rules.md) di elaborazione del canale di marketing per le definizioni dei campi visualizzati sulla [!UICONTROL Marketing Channel Processing Rules] pagina.

## Domande frequenti {#faq}

Ogni implementazione delle regole di elaborazione del canale di marketing può variare a seconda dei codici di monitoraggio. La configurazione di regole che forniscono i risultati che state cercando può richiedere alcune riflessioni creative per risolvere i problemi.

**Domanda**: I miei codici di monitoraggio non seguono un pattern, e ho migliaia che devono essere specificati per il mio canale Affiliates.

* Utilizzate il processo di eliminazione. Se i canali E-mail e Affiliati utilizzano lo stesso parametro della stringa di query, ma disponete solo di alcuni codici di tracciamento e-mail, potete specificare i codici di tracciamento e-mail in un set di regole che definisce l&#39;e-mail. Quindi puoi classificare tutti gli altri codici di tracciamento con *`affiliates.`*
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

2. **[!UICONTROL Referrer Matches Internal URL Filters]** e **[!UICONTROL Is First page of Visit]**. (Vedere [Interno](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** e **[!UICONTROL Exists]** e **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Infine, create un canale *Altro* che acquisisca gli hit rimanenti, come descritto in [Nessun canale identificato](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Nessun canale identificato {#no-channel-identified}

Se le regole non acquisiscono dati o se le regole non sono configurate correttamente, il rapporto visualizza i dati nella [!UICONTROL No Channel Identified] riga del rapporto. Potete creare un set di regole denominato *Altro*, ad esempio, al termine dell&#39;ordine di elaborazione, che identifichi anche il traffico interno.

![](assets/example_other.png)

Questo tipo di regola funge da clausola catch-all per garantire che il traffico dei canali corrisponda sempre al traffico esterno, e in genere non finisca in **[!UICONTROL No Channel Identified]**. Fare attenzione a non creare una regola che identifichi anche il traffico interno. L&#39;impostazione del valore del canale su **[!UICONTROL Referring Domain]** o su **[!UICONTROL Page URL]** sono i modi più comuni e utili per creare un&#39;altra regola efficace.

> [!NOTE] Potrebbe ancora esserci del traffico di canale che può rientrare nella categoria Nessun canale identificato. Ad esempio: Un visitatore accede al sito e annota una pagina e, nella stessa visita, torna alla pagina tramite il segnalibro. Poiché questa non è la prima pagina della visita, non andrà né nel canale diretto né nell&#39;altro canale perché non c&#39;è un dominio di riferimento.

## Ricerca pagata {#paid-search}

Una ricerca a pagamento è una parola o una frase che viene pagata con un motore di ricerca per essere inserita nei risultati della ricerca. Per rispettare le regole di rilevamento delle ricerche pagate, il canale di marketing utilizza le impostazioni configurate sulla [!UICONTROL Paid Search Detection] pagina. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). L&#39;URL di destinazione corrisponde alla regola di rilevamento della ricerca a pagamento esistente per quel motore di ricerca.

Per la regola del canale di marketing, le [!UICONTROL Paid Search] impostazioni sono le seguenti:

![](assets/example_paid_search.png)

Per ulteriori informazioni, consulta [Rilevamento](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) ricerca a pagamento in Amministratore.

## Ricerca naturale {#natural-search}

Una ricerca naturale si verifica quando i visitatori trovano il sito Web tramite una ricerca Web, dove il motore di ricerca ha classificare il sito senza pagare per l&#39;elenco. Potete controllare l’URL di destinazione che il motore di ricerca utilizza per collegarsi al sito. Questo URL consente ad Analytics di identificare se una ricerca è naturale.

In Analytics non è disponibile il rilevamento della ricerca naturale. Dopo aver impostato il rilevamento della ricerca a pagamento, il sistema sa che se un referente di ricerca non era un referente di ricerca a pagamento, deve essere un referente di ricerca naturale. Per una ricerca naturale, l&#39;URL di destinazione non corrisponde alla regola di rilevamento della ricerca a pagamento esistente per quel motore di ricerca.

Per la regola del canale di marketing, le impostazioni di Ricerca naturale sono le seguenti:

![](assets/example_natural_search.png)

Per ulteriori informazioni, consulta Rilevamento [ricerca a](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) pagamento nell’amministratore.

## Affiliati {#afilliates}

Una regola di affiliazione identifica i visitatori che provengono da un set specificato di domini di provenienza. Nella regola, puoi elencare i domini delle filiali che desideri monitorare, come segue:

![](assets/example_affiliates.png)

## Social Network {#social-networks}

Questa regola identifica i visitatori provenienti da un social network, come Facebook*. Le impostazioni possono essere le seguenti:

![](assets/example_social.png)

## Visualizzazione {#display}

Questa regola identifica i visitatori provenienti da annunci pubblicitari per banner. È identificato da un parametro di stringa di query nell&#39;URL di destinazione, in questo caso *`Ad_01`*.

![](assets/example_display.png)

## Interno {#internal}

Questa regola identifica i visitatori provenienti da un referente che corrisponde ai filtri URL interni per la suite di rapporti.

![](assets/example_internal.png)

## E-mail {#email}

Per impostare questa regola, dovete fornire il parametro della stringa di query per la campagna e-mail. In questo esempio, il parametro è *`eml`*:

![](assets/example_email.png)

Se la regola contiene codici di tracciamento, immettete un valore per riga, come illustrato di seguito:

![](assets/tracking_code.png)

## Direct {#direct}

Questa regola identifica i visitatori che non dispongono di un dominio di riferimento. Questa regola include i visitatori che arrivano direttamente al sito, ad esempio da un collegamento Preferiti o incollando un collegamento nel browser.

![](assets/example_direct.png)

