---
title: Risoluzione di picchi e perdite di dati
description: Scopri i possibili motivi per cui nei rapporti con tendenze possono verificarsi significativi incrementi o decrementi.
translation-type: tm+mt
source-git-commit: 178e372e63c436268a1f7028d986504983430b2f
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 0%

---


# Risoluzione di picchi e perdite di dati

Quando il sito raccoglie i dati, ci sono molti fattori esterni che possono influenzare drasticamente la raccolta di dati o il reporting. Di seguito è riportato un elenco di possibili spiegazioni sul motivo per cui determinate variabili o il traffico complessivo aumentano o diminuiscono notevolmente.

Man mano che si determina la causa e si passa a una risoluzione, è possibile misurare l&#39;impatto dell&#39;evento sui dati e determinare come si desidera procedere. Per ulteriori informazioni, consultate la pagina [](overview.md) della panoramica.

## Cadute di traffico

Le gocce di traffico sono suddivise in due sezioni: dati parziali e zero.

### Cause potenziali di dati completamente mancanti (zero di reporting)

* **Latenza** suite di rapporti: Talvolta, una suite di rapporti può rilevare una [latenza](../latency.md) dovuta a una serie di fattori. Molti problemi di latenza vengono risolti in poche ore. Se hai a che fare con una suite di rapporti specifica, contatta l&#39;Assistenza clienti  Adobe con l&#39;ID suite di rapporti interessato.
* **Rimozione** implementazione: A volte, quando un&#39;organizzazione apporta modifiche di implementazione o ristruttura il sito,  Analytics viene trascurata la reimplementazione. Collaborate con gli sviluppatori della vostra organizzazione per reimplementare il codice sul sito.
* **problema** di interfaccia/memorizzazione nella cache di Analytics: In rare occasioni, la cache di un browser contiene dati non validi che fanno sì che tutti i rapporti restituiscano zeri. Cancellate i cookie e la cache del browser per risolvere il problema. Se la cancellazione dei cookie/della cache non funziona, contatta l&#39;Assistenza clienti con il rapporto mancante e l&#39;intervallo di date; possono duplicare il problema e fornire ulteriori informazioni.
* **disponibilità** Analytics: Controlla [status.adobe.com](https://status.adobe.com/products/1173/) per eventuali problemi relativi alla raccolta o all&#39;elaborazione dei dati.

### Possibili cause di dati parzialmente mancanti o diminuzione del traffico

* **Modifiche** di implementazione: Utilizzate il [debugger](/help/implement/validate/debugger.md) per verificare il funzionamento delle dimensioni desiderate.
* **Traffico** di riferimento ridotto: Se viene rimosso un banner pubblicitario o un collegamento ipertestuale popolare in un altro sito, il traffico potrebbe subire una notevole diminuzione. Tendenza della dimensione dei domini [di](/help/components/dimensions/referring-domain.md) riferimento da prima e dopo il rilascio per proseguire la ricerca.
* **Problemi** di prestazioni del sito: Una distribuzione non corretta del traffico attraverso i bilanciatori del carico o problemi del server in cui è installato il sito può contribuire a una riduzione  rapporti Analytics. Collabora con il team all&#39;interno dell&#39;organizzazione che gestisce l&#39;integrità e lo stato del sito per indagare su eventuali problemi di prestazioni.
* **Modifiche nella classificazione** della ricerca naturale: Il traffico può diminuire se un altro sito supera la classifica di ricerca naturale per alcune delle parole chiave. Questa diminuzione può essere particolarmente evidente se il sito non si trova più nella prima pagina dei risultati della ricerca. Tendenza della dimensione motori [di](/help/components/dimensions/search-engine.md) ricerca per ulteriori ricerche.
* **Modifiche nella pubblicità** PPC: La modifica dei titoli e delle descrizioni degli annunci per le campagne esistenti può influenzare il punteggio di qualità. In generale, un punteggio di qualità elevata indica che la parola chiave attiva gli annunci in una posizione più alta e a un costo inferiore per clic. Tendenza delle parole chiave di [ricerca - dimensione pagata](/help/components/dimensions/search-keyword.md) per approfondire la ricerca.

## Picchi di traffico

I picchi di traffico sono organizzati in due sezioni: quasi doppi dati e altre cause.

### Possibili cause di avere quasi o esattamente il doppio dei dati previsti

* **Più richieste di immagini all&#39;interno di un&#39;implementazione**: Se l’implementazione contiene più di una chiamata [`t()`](/help/implement/vars/functions/t-method.md) metodo per pagina, raddoppia efficacemente tutti i dati raccolti. Utilizzate il debugger sul sito e cercate più richieste di immagini per acquisire duplicati.
* **File di origine dati duplicati caricati**: Se l&#39;azienda utilizza origini [](/help/import/c-data-sources/datasrc-home.md)dati, un utente dell&#39;azienda può caricare lo stesso file due volte in  Adobe Analytics. Se si esegue questo duplicato del caricamento, i dati nel reporting vengono raddoppiati, causando il picco di traffico.

### Altre potenziali cause dell&#39;aumento del traffico

* **Ragni o botti**: Se vedete un grande aumento improvviso del traffico, la prima cosa da cercare è la possibilità di un ragno o un bot. L&#39;identificazione dei bot può essere talvolta difficile, in quanto ognuno ha un proprio modo di eseguire il codice sul sito. Crea un rapporto di Data warehouse utilizzando l&#39;IP come dimensione per vedere quali indirizzi causano il maggior numero di traffico. Potete quindi utilizzare le regole [bot](/help/admin/admin/bot-removal/bot-rules.md) o una regola VISTA per eliminare il traffico bot dai rapporti futuri.
* **Campagne** avviate: Le attività di marketing, come campagne e-mail o ottimizzazione dei motori di ricerca, possono potenzialmente causare un picco del traffico sul sito. Tendenza della dimensione del codice [di](/help/components/dimensions/tracking-code.md) tracciamento per ulteriori ricerche. Può anche essere utile per contattare il team marketing per assicurarsi che il picco sia intenzionale.
* **Cause** ambientali o circostanziali: Se si è verificato un evento festivo o circostanziale (un evento significativo in cui il sito è una risorsa nota, o le attività di marketing residue di altre organizzazioni), il traffico può aumentare sul sito. Risolvere i problemi della causa esatta è difficile, in quanto ci sono un numero quasi illimitato di motivi circostanziali per cui il traffico può aumentare. Queste cause, tuttavia, sono alcune delle più importanti da determinare in modo che la tua organizzazione possa trarre vantaggio da tali cause e prendere le decisioni aziendali di conseguenza. La tendenza della dimensione [Pagina](/help/components/dimensions/page.md) o [Referente](/help/components/dimensions/referrer.md) è probabilmente il punto migliore per iniziare a determinare l’origine del traffico.

Se nessuno dei motivi di cui sopra è una potenziale causa di aumento o diminuzione del traffico sul sito, contatta  Assistenza clienti del Adobe. Possono fornire assistenza per individuare la fonte del picco di traffico o della caduta. Durante la creazione dell&#39;incidente, istruite l&#39;agente su come ricreare un rapporto specifico che illustri chiaramente il picco o la goccia.
