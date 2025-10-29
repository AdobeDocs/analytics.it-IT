---
title: Regole di elaborazione per i canali di marketing
description: Utilizza le regole per determinare a quale canale di marketing appartiene un hit.
feature: Marketing Channels
exl-id: 825f70a5-cce3-4b1c-bb42-828388348216
role: Admin
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 3%

---

# Regole di elaborazione per il canale di marketing

_Questa pagina fa riferimento alle regole di elaborazione che assegnano un canale di marketing a un hit. Vedi [Regole di elaborazione](../general/processing-rules/pr-overview.md) per la funzione che ti consente di regolare la modalità di raccolta dei dati._

Le regole di elaborazione per il canale di marketing ti consentono di creare una logica che determina il valore per le dimensioni [Canale di marketing](/help/components/dimensions/marketing-channel.md) e [Dettaglio canale di marketing](/help/components/dimensions/marketing-detail.md). Utilizza [Marketing Channel Manager](c-channels.md) per determinare quali canali di marketing utilizzi, quindi utilizza le regole di elaborazione per determinare come viene impostato ogni canale.

![Bucket canale di marketing](assets/buckets_2.png)

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Marketing Channels]** > **[!UICONTROL Marketing Channel Processing Rules]**

Una volta eseguita l&#39;[installazione automatica](/help/components/c-marketing-channels/c-getting-started-mchannel.md), viene creata una regola per ogni canale generato durante l&#39;installazione.

![Regole predefinite](assets/marketing_channel_rules.png)

Puoi utilizzare più regole per definire un singolo canale di marketing. L’utilizzo di più regole per un singolo canale può essere utile se desideri impostare i dettagli del canale in modo diverso a seconda delle condizioni della regola. Puoi anche utilizzare più condizioni per definire una singola regola.

## Definizioni delle regole

Ogni regola contiene una condizione e un’assegnazione:

* **[!UICONTROL If any/all of the following are true]**: se si aggiungono più condizioni a una singola regola, è possibile determinare se tutte le condizioni devono essere soddisfatte o una qualsiasi delle condizioni deve essere soddisfatta per impostare il canale e il valore associato.
* **Condizioni regola**: specificare una o più condizioni regola che devono essere soddisfatte. In genere si specifica una dimensione a cui un hit deve corrispondere per qualificarsi per il canale di marketing.
* **[!UICONTROL Then do the following]**: quando le condizioni della regola corrispondono, impostare [Canale marketing](/help/components/dimensions/marketing-channel.md) ([!UICONTROL Identify the channel as]) e [Dettagli canale marketing](/help/components/dimensions/marketing-detail.md) ([!UICONTROL Set the channel's value]).

## Condizioni di regola

Quando si impostano le condizioni della regola, sono disponibili le seguenti opzioni.

>[!NOTE]
>
>Tutti i campi di testo vengono valutati come **senza distinzione tra maiuscole e minuscole**. Ad esempio, se utilizzi una condizione di regola in cui il parametro della stringa di query `cmp` è uguale a `abc123`, sia il parametro che il valore della stringa di query possono utilizzare qualsiasi combinazione di lettere maiuscole e minuscole.

**Le condizioni rilevate da Adobe** non contengono opzioni o campi per l&#39;immissione di testo.

| Condizione rilevata da Adobe | Descrizione |
|---|---|
| **[!UICONTROL Matches Paid Search Detection Rules]** | L&#39;hit proviene da un motore di ricerca riconosciuto e corrisponde a [Regole di rilevamento ricerca a pagamento](../general/paid-search-detection/paid-search-detection.md). |
| **[!UICONTROL Matches Natural Search Detection Rules]** | L’hit proviene da un motore di ricerca riconosciuto e non corrisponde alle regole di rilevamento di ricerche a pagamento. |
| **[!UICONTROL Referrer Matches Internal URL Filters]** | L&#39;hit conteneva un [Referrer](/help/components/dimensions/referrer.md) corrispondente a [Filtri per URL interni](../general/internal-url-filter-admin.md). |
| **[!UICONTROL Referrer Does Not Match Internal URL Filters]** | L’hit conteneva un referente che non corrispondeva ai filtri URL interni. |
| **[!UICONTROL Is First Hit of Visit]** | Il risultato è stato il primo di una visita. |
| **[!UICONTROL Referrer Is Social Network]** | Il tipo [Referrer](/help/components/dimensions/referrer-type.md) è &quot;Social network&quot;. |
| **[!UICONTROL Referrer Is Not Social Network]** | Il tipo di referente non è &quot;Social network&quot;. |
| **[!UICONTROL Referrer Is Conversational AI]** | Il tipo di referente è &quot;IA per la conversazione&quot;. |
| **[!UICONTROL Referrer Is Not Conversational AI]** | Il tipo di referente non è &quot;IA per la conversazione&quot;. |

**Gli attributi Hit** consentono di specificare una dimensione, un operatore corrispondente e un valore da cercare.

| Condizione attributo hit | Descrizione |
|---|---|
| **[!UICONTROL Page]** | La dimensione [Pagina](/help/components/dimensions/page.md). |
| **[!UICONTROL Page Domain]** | Dominio dell’URL. Ad esempio: `products.example.com`. |
| **[!UICONTROL Page Domain And Path]** | Il dominio e il percorso dell’URL. Ad esempio: `products.example.com/mens/pants/overview.html`. |
| **[!UICONTROL Page Root Domain]** | Dominio principale dell’URL. Ad esempio: `example.co.uk`. |
| **[!UICONTROL Page URL]** | L’URL dell’intera pagina. |
| **[!UICONTROL Query String Parameter]** | Un singolo parametro della stringa di query nell’URL della pagina. Utilizza un parametro di stringa di query per condizione di regola. Se si desidera includere più parametri della stringa di query in una regola, utilizzare più condizioni della regola. |
| **[!UICONTROL Referrer]** | La dimensione [Referrer](/help/components/dimensions/referrer.md). |
| **[!UICONTROL Referring Domain]** | La dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md). |
| **[!UICONTROL Referring Domain And Path]** | Una concatenazione del dominio di riferimento e del percorso URL del referente. Ad esempio, `www.example.com/products/id/12345` o `ad.example.com/foo`. |
| **[!UICONTROL Referring Parameter]** | Un parametro di stringa di query all’interno del referente. |
| **[!UICONTROL Referring Root Domain]** | Dominio principale di riferimento. |
| **[!UICONTROL Search Engine]** | La dimensione [Motore di ricerca](/help/components/dimensions/search-engine.md). |
| **[!UICONTROL Search Keyword(s)]** | La dimensione [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md). |
| **[!UICONTROL Search Engine + Search Keyword(s)]** | Una concatenazione di motore di ricerca e parola chiave di ricerca. |
| **[!UICONTROL AMO ID]** | Il codice di tracciamento principale utilizzato dalle integrazioni Adobe Advertising e Advertising Analytics. Quando una di queste integrazioni è abilitata, è possibile utilizzare il prefisso del codice di tracciamento per identificare i canali specifici di Advertising. I valori che iniziano con &quot;AL&quot; sono per Ricerca e Social. I valori che iniziano con &quot;AC&quot; sono per Display. Quando l’AMO ID viene utilizzato nei canali di marketing, le metriche di clic/costo/impression possono essere attribuite al canale corretto. |
| **[!UICONTROL AMO EF ID]** | Il codice di tracciamento secondario utilizzato da Adobe Advertising. Funge da chiave per l’invio di dati ad Advertising. Può essere utilizzato per identificare i click-through di visualizzazione e i view-through di visualizzazione come due canali di marketing separati. A questo scopo, imposta la logica del canale di marketing per &quot;AMO EF ID&quot; termina con `:d` per i click-through di visualizzazione, oppure &quot;AMO EF ID&quot; termina con `:i` per i click-through di visualizzazione. Se non desideri dividere la visualizzazione in due canali, utilizza la dimensione AMO ID. |

**Le variabili di conversione** consentono di specificare un eVar personalizzato, un operatore corrispondente e un valore da cercare.

| Condizione della variabile di conversione | Descrizione |
|---|---|
| **eVar 1-250** | La dimensione [eVar](/help/components/dimensions/evar.md) associata. |
