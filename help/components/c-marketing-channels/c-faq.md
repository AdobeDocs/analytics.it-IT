---
description: Leggi le best practice ed esempi di come compilare varie regole che puoi impostare per i tuoi canali di marketing.
seo-description: Leggi le best practice ed esempi di come compilare varie regole che puoi impostare per i tuoi canali di marketing.
seo-title: Domande frequenti ed esempi
solution: Analytics
subtopic: Canali di marketing
title: Domande frequenti ed esempi
topic: Reports and Analytics
uuid: 1c63a1b5-a191-4855-aa65-face19ab1037a
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Domande frequenti ed esempi

Leggi le best practice ed esempi di come compilare varie regole che puoi impostare per i tuoi canali di marketing.

* [Domande frequenti](../../components/c-marketing-channels/c-faq.md#section_E490CEAF0E76422C91D34D8A80A0C573)
* [Nessun canale identificato](../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7)
* [Ricerca pagata](../../components/c-marketing-channels/c-faq.md#section_E934BFE182E4404A93FE07AFEAE64DC1)
* [Ricerca naturale](../../components/c-marketing-channels/c-faq.md#section_A4C6B8F0360449BE94F0128FF7C71386)
* [Affiliati](../../components/c-marketing-channels/c-faq.md#section_8D142C7074CD4DEC87DF55B691107622)
* [Social Network](../../components/c-marketing-channels/c-faq.md#section_492B72A3B261479D9C84F631E90C03D8)
* [Visualizzazione](../../components/c-marketing-channels/c-faq.md#section_4FD846B89FCE4ECFB7781BD02874A1AB)
* [Interno](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947)
* [E-mail](../../components/c-marketing-channels/c-faq.md#section_4A927BE947B748E39595F4525B7280DE)
* [Direct](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A)

Consultate [Creare regole](../../components/c-marketing-channels/t-rules.md#task_84EDE9F46F404CB9B7CA0537328CEE08) di elaborazione del canale di marketing per le definizioni dei campi visualizzati sulla [!UICONTROL Marketing Channel Processing Rules] pagina.

## Domande frequenti {#section_E490CEAF0E76422C91D34D8A80A0C573}

Ogni implementazione delle regole di elaborazione del canale di marketing può variare a seconda dei codici di monitoraggio. La configurazione di regole che forniscono i risultati che state cercando può richiedere alcune riflessioni creative per risolvere i problemi.

**Domanda**: I miei codici di monitoraggio non seguono un pattern, e ho migliaia che devono essere specificati per il mio canale Affiliates.

* Utilizzate il processo di eliminazione. Se i canali E-mail e Affiliati utilizzano lo stesso parametro della stringa di query, ma disponete solo di alcuni codici di tracciamento e-mail, potete specificare i codici di tracciamento e-mail in un set di regole che definisce l'e-mail. Quindi puoi classificare tutti gli altri codici di tracciamento con *`affiliates.`*
* Nel sistema e-mail, aggiungete un parametro di stringa di query a tutti gli URL della pagina di destinazione, ad esempio *`&ch=eml`*. Create un set di regole per rilevare se il parametro query ch è uguale a *`eml`*. Se non contiene *`eml`*, è una filiale.

**Domanda**: I domini di riferimento contengono più dati di quanto mi aspetto.

* I domini di riferimento potrebbero essere troppo alti nell'elenco delle regole di elaborazione. Deve essere uno degli ultimi set di regole (o l'ultimo), perché l'ordine di elaborazione è importante.

**Domanda**: Ho creato una regola che corrisponde a un parametro della stringa di query e non funziona.

* Accertatevi che il nome del parametro sia specificato nei campi del parametro della stringa di query (in genere un valore alfanumerico). Inoltre, accertatevi che il valore del parametro sia specificato dopo l'operatore, come illustrato nell'esempio seguente di una regola e-mail.

   ![](assets/example_email.png)

**Domanda**: Perché tutto il mio ultimo traffico è attribuito a un dominio interno?

* È presente una regola che corrisponde al traffico interno. Tieni presente che queste regole vengono elaborate per ogni hit che un visitatore fa sul tuo sito, non solo per la prima visita. Se disponete di una regola come *`Page URL exists`* senza altri criteri, il canale corrisponde a ogni hit successivo sul sito, perché un URL di pagina esiste sempre.

**Domanda**: Come si esegue il debug del traffico visualizzato in Nessun canale identificato nel report?

* Le regole vengono elaborate in ordine. Se non è stato trovato alcun criterio specifico, gli hit rientrano in una delle tre categorie seguenti:

1. Nessun referente (visita diretta).

2. Referente interno nella prima pagina di una visita.

3. Problema di elaborazione sulla pagina.

Accertatevi di disporre di un canale per queste tre possibilità. Ad esempio, creare regole che dicano:

1. **[!UICONTROL Referrer]** e **[!UICONTROL Does Not Exist]** e **[!UICONTROL Is First Page of Visit]**. (Vedere [Diretta](../../components/c-marketing-channels/c-faq.md#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A).)

2. **[!UICONTROL Referrer Matches Internal URL Filters]** ed **[!UICONTROL Is First page of Visit]**. (Vedere [Interno](../../components/c-marketing-channels/c-faq.md#section_179A2BE5C8E24719A9E5C0DC09AF0947).)

3. **[!UICONTROL Referrer]** e **[!UICONTROL Exists]** e **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Infine, create un canale *Altro* che acquisisca gli hit rimanenti, come descritto in [Nessun canale identificato](../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7).

## Nessun canale identificato {#section_451E42994DA247A8A7B8559C715A5EE7}

Se le regole non acquisiscono dati o se le regole non sono configurate correttamente, il rapporto visualizza i dati nella [!UICONTROL No Channel Identified] riga del rapporto. Potete creare un set di regole denominato *Altro*, ad esempio, al termine dell'ordine di elaborazione, che identifichi anche il traffico interno.

![](assets/example_other.png)

Questo tipo di regola funge da clausola catch-all per garantire che il traffico dei canali corrisponda sempre al traffico esterno, e in genere non finisca in **[!UICONTROL No Channel Identified]**. Fare attenzione a non creare una regola che identifichi anche il traffico interno. L'impostazione del valore del canale su **[!UICONTROL Referring Domain]** o su **[!UICONTROL Page URL]** sono i modi più comuni e utili per creare un'altra regola efficace.

>[!NOTE]
>
>Potrebbe ancora esserci del traffico di canale che può rientrare nella categoria Nessun canale identificato. Ad esempio: Un visitatore accede al sito e annota una pagina e, nella stessa visita, torna alla pagina tramite il segnalibro. Poiché questa non è la prima pagina della visita, non andrà né nel canale diretto né nell'altro canale perché non c'è un dominio di riferimento.

## Ricerca pagata {#section_E934BFE182E4404A93FE07AFEAE64DC1}

Una ricerca a pagamento è una parola o una frase che viene pagata con un motore di ricerca per essere inserita nei risultati della ricerca. Per rispettare le regole di rilevamento delle ricerche pagate, il canale di marketing utilizza le impostazioni configurate sulla [!UICONTROL Paid Search Detection] pagina. ( **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Paid Search Detection]**). L'URL di destinazione corrisponde alla regola di rilevamento della ricerca a pagamento esistente per quel motore di ricerca.

Per la regola del canale di marketing, le [!UICONTROL Paid Search] impostazioni sono le seguenti:

![](assets/example_paid_search.png)

Per ulteriori informazioni, consulta [Rilevamento](https://marketing.adobe.com/resources/help/en_US/reference/paid_search_detection.html) ricerca a pagamento in Amministratore.

## Ricerca naturale {#section_A4C6B8F0360449BE94F0128FF7C71386}

Una ricerca naturale si verifica quando i visitatori trovano il sito Web tramite una ricerca Web, dove il motore di ricerca ha classificare il sito senza pagare per l'elenco. Potete controllare l’URL di destinazione che il motore di ricerca utilizza per collegarsi al sito. Questo URL consente ad Analytics di identificare se una ricerca è naturale.

In Analytics non è disponibile il rilevamento della ricerca naturale. Dopo aver impostato il rilevamento della ricerca a pagamento, il sistema sa che se un referente di ricerca non era un referente di ricerca a pagamento, deve essere un referente di ricerca naturale. Per una ricerca naturale, l'URL di destinazione non corrisponde alla regola di rilevamento della ricerca a pagamento esistente per quel motore di ricerca.

Per la regola del canale di marketing, le impostazioni di Ricerca naturale sono le seguenti:

![](assets/example_natural_search.png)

Per ulteriori informazioni, consulta Rilevamento [ricerca a](https://marketing.adobe.com/resources/help/en_US/reference/paid_search_detection.html) pagamento nell’amministratore.

## Affiliati {#section_8D142C7074CD4DEC87DF55B691107622}

Una regola di affiliazione identifica i visitatori che provengono da un set specificato di domini di provenienza. Nella regola, puoi elencare i domini delle filiali che desideri monitorare, come segue:

![](assets/example_affiliates.png)

## Social Network {#section_492B72A3B261479D9C84F631E90C03D8}

Questa regola identifica i visitatori provenienti da un social network, come Facebook*. Le impostazioni possono essere le seguenti:

![](assets/example_social.png)

## Visualizzazione {#section_4FD846B89FCE4ECFB7781BD02874A1AB}

Questa regola identifica i visitatori provenienti da annunci pubblicitari per banner. È identificato da un parametro di stringa di query nell'URL di destinazione, in questo caso *`Ad_01`*.

![](assets/example_display.png)

## Interno {#section_179A2BE5C8E24719A9E5C0DC09AF0947}

Questa regola identifica i visitatori provenienti da un referente che corrisponde ai filtri URL interni per la suite di rapporti.

![](assets/example_internal.png)

## E-mail {#section_4A927BE947B748E39595F4525B7280DE}

Per impostare questa regola, dovete fornire il parametro della stringa di query per la campagna e-mail. In questo esempio, il parametro è *`eml`*:

![](assets/example_email.png)

Se la regola contiene codici di tracciamento, immettete un valore per riga, come illustrato di seguito:

![](assets/tracking_code.png)

## Direct {#section_D0A1DD9D5EEF4A05A1CC81F9EADC074A}

Questa regola identifica i visitatori che non dispongono di un dominio di riferimento. Questa regola include i visitatori che arrivano direttamente al sito, ad esempio da un collegamento Preferiti o incollando un collegamento nel browser.

![](assets/example_direct.png)

