---
title: Domande frequenti sui canali di marketing
description: Domande frequenti per i canali di marketing.
translation-type: tm+mt
source-git-commit: 7202a49dda7c3ef4f4b535476d3cf637b9e9f7f6
workflow-type: tm+mt
source-wordcount: '1447'
ht-degree: 0%

---


# Domande frequenti sui canali di marketing

>[!NOTE]
>
>Per massimizzare l&#39;efficacia dei canali di marketing per Attribution IQ e Customer Journey Analytics, abbiamo pubblicato alcune [best practice riviste](/help/components/c-marketing-channels/mchannel-best-practices.md).

Domande frequenti per i canali di marketing.

## I miei codici di tracciamento non seguono un pattern, e ho migliaia che devono essere specificati per il mio canale Affiliates.

* Utilizza il processo di eliminazione. Se i canali e-mail e affiliate utilizzano lo stesso parametro della stringa query, ma disponi solo di alcuni codici di tracciamento e-mail, puoi specificare i codici di tracciamento e-mail in un set di regole che definiscono l’e-mail. Quindi, classifica tutti gli altri codici di tracciamento con *`affiliates.`*
* Nel sistema e-mail, aggiungi un parametro della stringa di query a tutti gli URL della pagina di destinazione, ad esempio *`&ch=eml`*. Crea un set di regole rilevando se il parametro di query ch è uguale a *`eml`*. Se non contiene *`eml`*, si tratta di una filiale.

## I domini di riferimento contengono più dati di quanto previsto.

* I domini di riferimento potrebbero essere troppo alti nell’elenco delle regole di elaborazione. Deve essere uno degli ultimi set di regole (o l&#39;ultimo), perché l&#39;ordine di elaborazione è importante.

## Ho creato una regola che corrisponde a un parametro di stringa query e non funziona.

* Assicurati che il nome del parametro sia specificato nei campi del parametro della stringa query (in genere un valore alfanumerico). Inoltre, assicurati che il valore del parametro sia specificato dopo l’operatore , come mostrato nell’esempio seguente di una regola e-mail.

   ![](assets/example_email.png)

## Perché tutto il traffico dell’ultimo contatto è attribuito a un dominio interno?

* Hai una regola che corrisponde al traffico interno. Tieni presente che queste regole elaborano per ogni hit che un visitatore fa sul tuo sito, non solo per la prima visita. Se disponi di una regola come *`Page URL exists`* senza altri criteri, tale canale corrisponde a ogni hit successivo sul sito, perché esiste sempre un URL di pagina.

## Come eseguo il debug del traffico visualizzato in Nessun canale identificato nel report?

* Le regole vengono elaborate in ordine. Se non è stato trovato alcun criterio specifico, gli hit rientrano in una delle tre categorie seguenti:

1. Nessun referente (una visita diretta).

2. Referente interno nella prima pagina di una visita.

3. Un problema di elaborazione sulla pagina.

Assicurati di avere un canale per queste tre possibilità. Ad esempio, crea regole che dicono:

1. **[!UICONTROL Referrer]** e  **[!UICONTROL Does Not Exist]** e  **[!UICONTROL Is First Page of Visit]**. (Vedere [Diretto.](/help/components/c-marketing-channels/c-faq.md))

2. **[!UICONTROL Referrer Matches Internal URL Filters]** e **[!UICONTROL Is First page of Visit]**. (Vedere [Interno](/help/components/c-marketing-channels/c-faq.md).)

3. **[!UICONTROL Referrer]** e  **[!UICONTROL Exists]** e  **[!UICONTROL Referrer Does Not Match Internal URL Filters]**.

Infine, crea un canale *Altro* che acquisisca gli hit rimanenti, come descritto in [Nessun canale identificato](/help/components/c-marketing-channels/c-faq.md#no-channel-identified).

## Relazione tra Primo e Ultimo contatto

Per comprendere l’interazione tra le dimensioni legacy di primo e ultimo contatto e confermare che le sostituzioni funzionano come previsto, puoi richiamare un rapporto di canale di primo contatto, relativo a un rapporto di canale di ultimo contatto, con la metrica di successo chiave aggiunta in (vedi l’esempio di seguito). L’esempio illustra l’interazione tra i canali di primo e ultimo contatto.

![](assets/int-channel3.png)

L’intersezione in cui primo è uguale all’ultimo contatto è la diagonale della tabella. Sia l’aggiornamento diretto che l’aggiornamento della sessione ottengono il credito dell’ultimo contatto solo se sono anche il canale di primo contatto, perché non possono ricevere credito da altri canali persistenti (righe evidenziate).

## Motivi per cui non è stato identificato alcun canale {#no-channel-identified}

Se le regole non acquisiscono dati o se non sono configurate correttamente, i dati vengono visualizzati nella riga [!UICONTROL No Channel Identified] del rapporto. Puoi creare un set di regole denominato *Altro*, ad esempio, al termine dell’ordine di elaborazione, che identifica anche il traffico interno.

![](assets/example_other.png)

Questo tipo di regola funge da elemento catch-all per garantire che il traffico del canale corrisponda sempre al traffico esterno e in genere non finisca in **[!UICONTROL No Channel Identified]**. Fai attenzione a non creare una regola che identifichi anche il traffico interno. L&#39;impostazione del valore del canale su **[!UICONTROL Referring Domain]** o su **[!UICONTROL Page URL]** sono i modi più comuni e utili per creare un&#39;altra regola efficace.

>[!NOTE]
>
>Potrebbe ancora esserci del traffico del canale che può rientrare nella categoria Nessun canale identificato. Ad esempio: Un visitatore accede al sito e annota una pagina e nella stessa visita torna alla pagina tramite il segnalibro. Poiché questa non è la prima pagina della visita, non andrà né nel canale Direct né nell&#39;altro canale perché non c&#39;è un dominio di riferimento.

## Motivi per interni (aggiornamento sessione) {#internal}

L’ultimo contatto interno (aggiornamento sessione) può verificarsi solo se si è trattato anche del primo contatto - vedi &quot;Relazione tra primo e ultimo contatto&quot; sopra. Gli scenari riportati di seguito spiegano come l’aggiornamento della sessione potrebbe essere un canale di primo contatto.

* **Timeout** sessione: Un visitatore accede al sito web e quindi lascia la scheda aperta nel browser per utilizzarla in un secondo momento. Il periodo di coinvolgimento del visitatore scade (o elimina volontariamente i cookie) e utilizza la scheda aperta per visitare nuovamente il sito web. Poiché l’URL di riferimento è un dominio interno, la visita verrà classificata come Aggiornamento sessione.

* **Non tutte le pagine del sito dispongono di tag**: Un visitatore arriva alla pagina A senza tag e quindi passa alla pagina B con tag. La pagina A viene visualizzata come referente interno e la visita viene classificata come aggiornamento della sessione.

* **Reindirizzamenti**: Se non è impostato un reindirizzamento per passare i dati del referente alla nuova pagina di destinazione, i dati del referente di ingresso effettivo vengono persi e ora la pagina di reindirizzamento (probabilmente una pagina interna) viene visualizzata come dominio di riferimento. La visita verrà classificata come Aggiornamento sessione.

* **Traffico** tra domini diversi: Un visitatore si sposta da un dominio che viene attivato nella suite A a un secondo dominio che viene attivato nella suite B. Se nella suite B i filtri URL interni includono il primo dominio, la visita nella suite B verrà registrata come interna, poiché i canali di marketing la vedono come una nuova visita nella seconda suite. La visita verrà classificata come Aggiornamento sessione.

* **Tempi** di caricamento delle pagine lunghi: Un visitatore arriva alla pagina A che è ricca di contenuti e il codice Adobe Analytics si trova nella parte inferiore della pagina. Prima che tutto il contenuto (inclusa la richiesta di immagine di Adobe Analytics) possa essere caricato, il visitatore fa clic sulla pagina B. La pagina B genera la richiesta di immagine di Adobe Analytics. Poiché la richiesta di immagine della pagina A non è mai stata caricata, la seconda pagina viene visualizzata come il primo hit della visita in Adobe Analytics, con la pagina A come referente. La visita viene classificata come Aggiornamento sessione.

* **Cancellazione dei cookie a metà sito**: Un visitatore accede al sito e a metà sessione cancella i cookie. I canali di primo e ultimo contatto venivano reimpostati e la visita veniva classificata come Aggiornamento sessione (perché il referente sarebbe interno).

Di seguito è riportato un esempio di impostazione di Interno (aggiornamento sessione) sia come canali di primo e ultimo contatto:

* Giorno 1: L&#39;utente accede al sito su Display. I canali di primo e ultimo contatto saranno impostati su Visualizzazione.
* Giorno 2: L&#39;utente viene al sito sulla ricerca naturale. Il primo contatto rimane Display e l’ultimo contatto è impostato su Ricerca naturale.
* Giorno 35: L&#39;utente non è stato sul sito in 33 giorni e torna utilizzando la scheda che aveva aperto nel loro browser. Supponendo che sia presente una finestra di coinvolgimento di 30 giorni, la finestra si sarebbe chiusa e i cookie del canale di marketing sarebbero scaduti. Il canale di primo contatto e ultimo contatto viene reimpostato su Aggiornamento sessione poiché l’utente proviene da un URL interno.

## Perché alcuni canali rimangono invariati dopo aver modificato le regole di elaborazione dei canali di marketing?

A volte le regole di elaborazione del canale di marketing sono configurate in modo errato, rendendo necessario modificare le regole di elaborazione. Dopo aver applicato le modifiche, puoi vedere alcune metriche ancora attribuire i dati a un canale errato. Ci sono diversi aspetti da considerare:

* **I dati del canale di marketing vengono raccolti in tempo** reale: I dati dei canali di marketing vengono elaborati al momento della raccolta dei dati ed è permanente al 100%. La modifica delle regole di elaborazione non influisce sui dati retroattivamente.
* **La modifica delle regole di elaborazione non influisce immediatamente sui dati** First Touch: Ad esempio:
   1. Un utente arriva attraverso il tuo canale e-mail perché è stato configurato in modo errato, quindi lascia il tuo sito.
   2. Il giorno successivo, modifichi la regola di elaborazione e-mail per correggerla.
   3. L&#39;utente ritorna diversi giorni dopo tramite ricerca naturale e fa un acquisto.
   4. Il canale e-mail ottiene credito First Touch e la ricerca naturale ottiene credito Last Touch.

   Anche diversi giorni dopo aver modificato le regole di elaborazione, i dati possono ancora essere raccolti nel canale Primo contatto sbagliato. I dati di primo contatto vengono raccolti continuamente nel canale errato fino alla scadenza del coinvolgimento di tutti gli utenti.

Il modo migliore per rimediare a queste discrepanze è quello di fare uno o entrambi i seguenti:

* **Scadono manualmente tutti i periodi** di coinvolgimento dei visitatori: Questa impostazione scade immediatamente tutti i canali di primo e ultimo contatto tra tutti i visitatori:
   1. Vai a Strumenti di amministrazione > Suite di rapporti .
   2. Passa il puntatore del mouse su Image Edit Settings (Impostazioni modifica immagine) > Marketing Channels (Canali di marketing) > Visitor Engagement Expiration (Scadenza coinvolgimento visitatore)
   3. Fare clic su Scade tutto.
   4. Fare clic su OK nella finestra a comparsa di avviso, per confermare che si è in grado di comprendere le operazioni da eseguire.

* **Visualizza le metriche Last Touch solo dal momento in cui hai corretto le regole in avanti**: Le metriche Last Touch seguono sempre il set di regole corrente. La visualizzazione del tempo da cui le regole di elaborazione sono state modificate riflette correttamente le regole di elaborazione più recenti.
