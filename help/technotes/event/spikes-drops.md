---
title: Risolvere i problemi relativi a picchi e cadute nei dati
description: Scopri possibili motivi per cui puoi vedere aumenti o diminuzioni drastiche nei rapporti con tendenze.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
feature: Event, Data Configuration and Collection
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 0%

---

# Risolvere i problemi relativi a picchi e cadute nei dati

Quando il sito raccoglie i dati, esistono molti fattori esterni che possono influenzare drasticamente la raccolta dei dati o il reporting. Di seguito è riportato un elenco di potenziali spiegazioni sul perché alcune variabili o il traffico complessivo aumentino o diminuiscano notevolmente.

Quando si determina la causa e ci si sposta verso una risoluzione, è possibile misurare l&#39;impatto dell&#39;evento sui dati e determinare come procedere. Per ulteriori informazioni, vedere la [pagina della panoramica](overview.md).

## Cadute del traffico

Le riduzioni di traffico sono suddivise in due sezioni: dati parziali e dati nulli.

### Possibili cause di dati completamente mancanti (zero di segnalazione)

* **Latenza suite di rapporti**: occasionalmente, una suite di rapporti può riscontrare [latenza](../latency.md) a causa di una serie di fattori. Molti problemi di latenza vengono risolti in poche ore. Se hai dubbi su una suite di rapporti specifica, contatta l’Assistenza clienti di Adobe con l’ID suite di rapporti interessato.
* **Rimozione dell&#39;implementazione**: a volte, quando un&#39;organizzazione apporta modifiche all&#39;implementazione o ristruttura il proprio sito, la riimplementazione di Analytics viene ignorata. Collabora con gli sviluppatori della tua organizzazione per implementare nuovamente il codice sul tuo sito.
* **Problema di interfaccia/memorizzazione nella cache di Analytics**: in rari casi, la cache di un browser contiene dati non validi che fanno sì che tutti i rapporti restituiscano degli zeri. Per risolvere il problema, cancella i cookie e la cache del browser. Se la cancellazione dei cookie/cache non funziona, contatta l’Assistenza clienti per ottenere il rapporto mancante e l’intervallo di date; possono duplicare il problema e fornire ulteriori informazioni.
* **Disponibilità di Analytics**: controllare [status.adobe.com](https://status.adobe.com/products/1173/) per eventuali problemi relativi alla raccolta o all&#39;elaborazione dei dati.

### Possibili cause di dati parzialmente mancanti o traffico ridotto

* **Modifiche all&#39;implementazione**: utilizzare [debugger](/help/implement/validate/debugger.md) per verificare il funzionamento delle dimensioni desiderate.
* **Traffico di riferimento ridotto**: la rimozione di un banner pubblicitario o di un collegamento ipertestuale popolare in un altro sito può causare una notevole riduzione del traffico. Esegui la tendenza della dimensione [Domini di riferimento](/help/components/dimensions/referring-domain.md) da prima e dopo il rilascio per ulteriori ricerche.
* **Problemi relativi alle prestazioni del sito**: una distribuzione non corretta del traffico attraverso i load balancer o i problemi del server che ospitano il sito può contribuire a una riduzione del reporting di Analytics. Collabora con il team della tua organizzazione che gestisce l’integrità e lo stato del sito per indagare su eventuali problemi di prestazioni.
* **Modifiche nella classificazione di ricerca naturale**: il traffico può potenzialmente diminuire se un altro sito esclude la classificazione di ricerca naturale per alcune parole chiave. Questa riduzione può essere particolarmente evidente se il sito non si trova più nella prima pagina dei risultati di ricerca. Tendenza della dimensione [Motori di ricerca](/help/components/dimensions/search-engine.md) per ulteriori ricerche.
* **Modifiche nella pubblicità PPC**: la modifica dei titoli e delle descrizioni degli annunci per le campagne esistenti può influire sul punteggio di qualità. In generale, un punteggio di qualità elevato significa che la parola chiave attiva gli annunci in una posizione più alta e a un costo per clic inferiore. Tendenza della dimensione [Parole chiave di ricerca - a pagamento](/help/components/dimensions/search-keyword.md) per ulteriori ricerche.

## Picchi di traffico

I picchi di traffico sono suddivisi in due sezioni: dati doppi e altre cause.

### Possibili cause di avere quasi o esattamente il doppio dei dati previsti

* **Più richieste di immagini all&#39;interno di un&#39;implementazione**: se l&#39;implementazione contiene più di una chiamata al metodo [`t()`](/help/implement/vars/functions/t-method.md) per pagina, tutti i dati raccolti verranno raddoppiati. Utilizza il debugger sul tuo sito e osserva se sono presenti più richieste di immagini per acquisire duplicati.
* **File di origine dati duplicati caricati**: se la tua organizzazione utilizza [Origini dati](/help/import/data-sources/overview.md), un utente della tua organizzazione può caricare lo stesso file due volte in Adobe Analytics. L’esecuzione di questo caricamento duplicato raddoppia efficacemente i dati nel reporting, causando un picco di traffico.

### Altre possibili cause di aumento del traffico

* **Ragni o bot**: se vedi un forte aumento improvviso del traffico, la prima cosa da cercare è la possibilità di un ragno o di un bot. L’identificazione dei bot può a volte essere complessa, in quanto ciascuno di essi ha il proprio modo di eseguire il codice sul sito. Crea un rapporto di Data Warehouse utilizzando IP come dimensione per vedere quali indirizzi generano più traffico. Puoi quindi utilizzare [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) o una regola VISTA per eliminare il traffico da bot da rapporti futuri.
* **Campagne avviate**: le attività di marketing, come le campagne e-mail o l&#39;ottimizzazione dei motori di ricerca, possono causare un picco di traffico sul sito. Tendenza della dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md) per ulteriori ricerche. Può anche essere utile contattare il team di marketing per verificare che il picco sia stato intenzionale.
* **Cause ambientali o circostanziali**: se si è verificato un evento di vacanza o circostanziale (un evento significativo in cui il sito è una risorsa nota o le attività di marketing residue di altre organizzazioni), il traffico sul sito può aumentare. La risoluzione dei problemi relativi alla causa esatta è difficile, in quanto vi è un numero quasi illimitato di motivi circostanziali per cui il traffico può aumentare. Queste cause sono tuttavia tra le più importanti da determinare in modo che la tua organizzazione possa sfruttarle e prendere le decisioni aziendali di conseguenza. La tendenza della dimensione [Pagina](/help/components/dimensions/page.md) o [Referrer](/help/components/dimensions/referrer.md) è probabilmente il punto migliore da cui iniziare a determinare l&#39;origine del traffico.

Se nessuno dei motivi di cui sopra è una potenziale causa di aumento o riduzione del traffico sul sito, contatta l’Assistenza clienti di Adobe. Possono fornire assistenza nell’individuare l’origine del picco o del calo di traffico. Quando crei l’incidente, indica all’agente come ricreare un rapporto specifico che illustra chiaramente il picco o la caduta.
