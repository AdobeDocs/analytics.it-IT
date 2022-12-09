---
title: Risolvere i problemi relativi a picchi e perdite di dati
description: Scopri possibili motivi per cui è possibile visualizzare aumenti o diminuzioni drastici dei rapporti con tendenze.
exl-id: 1a91f95e-818f-423d-9247-e0bb96bd0018
source-git-commit: dc9cd6bb45af0c992c37ffe20ea22eab67789ec5
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 0%

---

# Risolvere i problemi relativi a picchi e perdite di dati

Quando il tuo sito raccoglie dati, ci sono molti fattori esterni che possono influenzare drasticamente la raccolta o il reporting di dati. Di seguito è riportato un elenco di possibili spiegazioni sul motivo per cui determinate variabili o il traffico complessivo aumentano o diminuiscono drasticamente.

Quando si determina la causa e si passa a una risoluzione, è possibile misurare l&#39;impatto dell&#39;evento sui dati e determinare come si desidera procedere. Consulta la sezione [pagina panoramica](overview.md) per ulteriori informazioni.

## Calo del traffico

Le gocce di traffico sono suddivise in due sezioni: dati parziali e dati zero.

### Cause potenziali di dati completamente mancanti (zeri di segnalazione)

* **Latenza suite di rapporti**: A volte, una suite di rapporti può sperimentare [latenza](../latency.md) a causa di una serie di fattori. Molti problemi di latenza vengono risolti in poche ore. Se hai a che fare con una suite di rapporti specifica, contatta l’Assistenza clienti Adobe con l’ID suite di rapporti interessato.
* **Rimozione dell&#39;implementazione**: A volte, quando un&#39;organizzazione apporta modifiche all&#39;implementazione o ristruttura il sito, la reimplementazione di Analytics viene ignorata. Collabora con gli sviluppatori della tua organizzazione per implementare nuovamente il codice sul tuo sito.
* **Problema di interfaccia/memorizzazione nella cache di Analytics**: In rare occasioni, la cache di un browser contiene dati non validi che fanno sì che tutti i rapporti restituiscano zeri. Cancella i cookie e la cache del browser per risolvere il problema. Se la cancellazione dei cookie/cache non funziona, contatta l’Assistenza clienti con il rapporto e l’intervallo di date mancanti; possono duplicare il problema e fornire informazioni aggiuntive.
* **Disponibilità di Analytics**: Controlla [status.adobe.com](https://status.adobe.com/products/1173/) per qualsiasi problema relativo alla raccolta o all’elaborazione dei dati.

### Cause potenziali di dati parzialmente mancanti o di traffico ridotto

* **Modifiche all&#39;implementazione**: Utilizza la [debugger](/help/implement/validate/debugger.md) per verificare che le dimensioni desiderate funzionino.
* **Traffico di riferimento ridotto**: Se viene rimosso un banner pubblicitario o un collegamento ipertestuale popolare in un altro sito, può causare una notevole diminuzione del traffico. Tendenza [Domini di riferimento](/help/components/dimensions/referring-domain.md) dimensione prima e dopo il calo per ulteriori ricerche.
* **Problemi di prestazioni del sito**: Una distribuzione errata del traffico tramite load balancer o problemi del server che ospitano il sito può contribuire a una diminuzione dei rapporti di Analytics. Collabora con il team all’interno dell’organizzazione che gestisce l’integrità e lo stato del sito per indagare eventuali problemi di prestazioni.
* **Modifiche nella classificazione della ricerca naturale**: Il traffico può potenzialmente diminuire se un altro sito supera la classifica di ricerca naturale per alcune delle tue parole chiave. Questa diminuzione può essere particolarmente evidente se il sito non è più sulla prima pagina dei risultati di ricerca. Tendenza [Motori di ricerca](/help/components/dimensions/search-engine.md) la dimensione della ricerca.
* **Modifiche alla pubblicità PPC**: La modifica dei titoli e delle descrizioni degli annunci per le campagne esistenti può influenzare il punteggio di qualità. In generale, un punteggio di alta qualità significa che la tua parola chiave attiva gli annunci in una posizione più alta e ad un costo più basso per clic. Tendenza [Parole chiave di ricerca - paid](/help/components/dimensions/search-keyword.md) la dimensione della ricerca.

## Picchi di traffico

I picchi di traffico sono suddivisi in due sezioni: dati quasi doppi e altre cause.

### Cause potenziali di avere dati prossimi o esattamente doppi dei dati previsti

* **Richieste di immagini multiple all&#39;interno di un&#39;implementazione**: Se l&#39;implementazione contiene più di un [`t()`](/help/implement/vars/functions/t-method.md) chiamata del metodo per pagina, raddoppia efficacemente tutti i dati raccolti. Usa il debugger sul tuo sito e cerca più richieste di immagini per acquisire duplicati.
* **File di origine dati duplicati caricati**: Se l&#39;organizzazione utilizza [Origini dati](/help/import/c-data-sources/datasrc-home.md), un utente dell’organizzazione può caricare lo stesso file due volte in Adobe Analytics. L’esecuzione di questo caricamento duplicato raddoppia efficacemente i dati nel reporting, causando il picco di traffico.

### Altre cause potenziali dell&#39;aumento del traffico

* **Ragni o robot**: Se vedete un forte aumento improvviso del traffico, la prima cosa da cercare è la possibilità di un ragno o un bot. A volte è difficile identificare i bot, in quanto ciascuno di essi dispone di un proprio modo di eseguire il codice sul sito. Crea un rapporto di Data Warehouse utilizzando l’IP come dimensione per vedere quali indirizzi causano il maggior traffico. Puoi quindi utilizzare [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md) o una regola VISTA per eliminare il traffico da bot dai rapporti futuri.
* **Campagne avviate**: Le attività di marketing come le campagne e-mail o l’ottimizzazione dei motori di ricerca possono potenzialmente causare un picco di traffico sul sito. Tendenza [Codice di tracciamento](/help/components/dimensions/tracking-code.md) la dimensione della ricerca. Può inoltre essere utile per contattare il team di marketing per assicurarsi che il picco sia intenzionale.
* **Cause ambientali o circostanziate**: Se si è verificato un evento festivo o circostanziale (un evento significativo in cui il sito è una risorsa nota o attività di marketing residue di altre organizzazioni), il traffico può aumentare sul sito. È difficile risolvere i problemi relativi alla causa esatta, in quanto il traffico può aumentare per un numero quasi illimitato di ragioni circostanziali. Queste cause, tuttavia, sono alcune delle più importanti da determinare in modo che la tua organizzazione possa sfruttarle e prendere le decisioni aziendali di conseguenza. Tendenza del [Pagina](/help/components/dimensions/page.md) o [Referrer](/help/components/dimensions/referrer.md) probabilmente è la posizione migliore per iniziare a determinare l’origine del traffico.

Se nessuna delle ragioni di cui sopra è una potenziale causa di aumento o diminuzione del traffico sul sito, contatta l’Assistenza clienti Adobe. Possono fornire assistenza nell’individuazione della fonte del picco o del calo di traffico. Quando crei l&#39;incidente, indica all&#39;agente come ricreare un report specifico che illustri chiaramente il picco o il calo.
