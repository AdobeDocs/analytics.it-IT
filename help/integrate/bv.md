---
title: Integrazione Brand Visibility
description: Integrare Brand Visibility con CAdobe Analytics
feature:
role: User
source-git-commit: 841b09d487fb965fb2a5fce4a39a7480a5b01012
workflow-type: tm+mt
source-wordcount: '2629'
ht-degree: 1%
---

# Integrazione con Adobe Brand Visibility

[Adobe Brand Visibility](https://experienceleague.adobe.com/it/docs/llm-optimizer/using/home) è un&#39;applicazione di intelligenza artificiale generativa per l&#39;ottimizzazione dei motori generativi, progettata per aiutare i brand a migliorare la visibilità, la precisione e l&#39;influenza negli ambienti di ricerca basati sull&#39;intelligenza artificiale. Brand Visibility fornisce informazioni approfondite sulla presenza dei brand nelle risposte generate dall’intelligenza artificiale, offre contenuti consigliati e automatizza le correzioni di ottimizzazione.

L’intelligenza artificiale è diventato un canale di rilevamento primario. Gli agenti LLM (Large Language Model), come ChatGPT, Claude, Copilot e Perplexity, scansionano i contenuti del brand.

>[!NOTE]
>
>Brand Visibility era precedentemente denominato **LLM Optimizer (LLMO)**. Alcuni documenti di Adobe potrebbero continuare a utilizzare la precedente terminologia LLMO durante la transizione.


>[!PREREQUISITES]
>
>È necessario disporre di un’offerta a pagamento Visibilità dei brand predisposta e connessa alla configurazione Experience Platform tramite il connettore gestito.


>[!IMPORTANT]
>
>Come parte di questa integrazione, alcuni trattamenti temporanei dei dati Brand Visibility avvengono negli Stati Uniti. I dati vengono infine memorizzati nell’area geografica designata, come configurato nel contratto Adobe Analytics.

Se utilizzi Customer Percorsi Analytics, un’integrazione in entrata separata e più ricca trasferisce gli stessi dati del traffico CDN sottostante in Customer Journey Analytics tramite Adobe Experience Platform. Tale integrazione è disponibile oggi. Vedere [Integrazione Brand Visibility con Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv). Se disponi di Customer Journey Analytics, rivedi prima tale integrazione, poiché espone più campi e supporta l’unione di dati Brand Visibility con altri set di dati. L’integrazione di Analytics descritta in questa guida è progettata per i clienti che utilizzano Adobe Analytics senza avere accesso a o una licenza per Customer Journey Analytics.


## Casi d’uso

L’integrazione tra Adobe Analytics e Brand Visibility offre i seguenti vantaggi:

* **Integrazione in entrata**: utilizza i dati Brand Visibility in Adobe Analytics per misurare il traffico basato su LLM (crawler bot, richieste RAG, attività agente) insieme ai dati web e mobili esistenti. Sarà possibile, ad esempio:

  * Misura il traffico guidato da LLM per origine agente insieme ai canali tradizionali.

  * Identifica i contenuti molto utilizzati dai moduli LLM, ma con prestazioni inferiori nella conversione umana.

  * Rilevare dove le richieste dell’agente LLM non vanno a buon fine nei percorsi critici.

  * Confronta la domanda di bot LLM per una pagina con le conversioni e i ricavi di tale pagina nei dati web, confrontati a livello di URL e host.

* **Integrazione in uscita**: invia i dati sulle prestazioni di Adobe Analytics a Brand Visibility in modo da ottimizzare la visibilità AI per le origini LLM che inviano traffico prezioso, ad esempio ChatGPT o Perplessity. Sarà possibile, ad esempio:

  * Scopri quali fonti LLM inviano visitatori umani che continuano a convertire o generare ricavi. Adobe Analytics misura questo dal traffico web di riferimento, non dal set di dati bot.
  * Classifica le origini LLM in base al valore a valle dei visitatori umani inviati, quindi concentra il tuo lavoro di visibilità AI sulle origini che ottengono i migliori risultati.


## Integrazione in entrata

Questa sezione descrive i prerequisiti e i passaggi di configurazione per l&#39;integrazione in entrata di **Adobe Brand Visibility → Adobe Analytics**.


Il connettore Adobe Analytics in entrata è configurato per suite di rapporti tramite **Report Suite Manager**, descritto nella sezione 6.

>[!PREREQUISITES]
>
>I registri di accesso CDN devono essere già inoltrati e ricevuti da Adobe Brand Visibility per ciascun sito Brand Visibility prima di poter abilitare il connettore Brand Visibility → Adobe Analytics.
>
>Questo requisito si applica a **per Visibilità dei brand**. Non si deve supporre che una configurazione CDN o un feed di registro per un sito, dominio o sottodominio copra un altro sito a meno che Adobe non confermi tale copertura.
>
>
>Prima di abilitare il connettore, confermare:
>
>1. La pipeline del registro o CDN pertinente è configurata per inoltrare i registri di accesso richiesti alla destinazione fornita da Adobe.
>1. Brand Visibility ha confermato che i registri vengono ricevuti e rilevati per il sito pertinente.
>1. I dati sono visibili nel dashboard Traffico agente Visibilità dei brand per quel sito.
>
>L’inoltro del registro BYOCDN fornisce i dati della richiesta CDN lato server utilizzati per l’analisi del traffico agente. I dati non dipendono dai tag di JavaScript in esecuzione in un browser. Senza il feed di registro CDN richiesto, il connettore non avrà dati sul traffico da inserire nella suite di rapporti.
>
>Per ulteriori informazioni, vedere [Riferimento inoltro log BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview).


>[!IMPORTANT]
>
>Come parte di questa integrazione, alcuni trattamenti temporanei dei dati Brand Visibility avvengono negli Stati Uniti. I dati vengono infine memorizzati nell’area geografica designata, come configurato nel contratto Adobe Analytics.


### Come funziona

La Visibilità dei brand in entrata → l&#39;integrazione di Adobe Analytics aggiunge un set di **variabili riservate** alla suite di rapporti. Queste variabili contengono dati di riepilogo sul traffico da bot e agenti automatizzati rilevato sul sito Web, incluso il traffico basato su LLM, proveniente dagli stessi registri di accesso CDN descritti in [prerequisiti](#inbound-integration).

Questo traffico generalmente non esegue i tag JavaScript del browser e non viene acquisito tramite l’implementazione Adobe Analytics esistente. Le variabili riservate consentono di visualizzare questo traffico all’interno della stessa suite di rapporti già utilizzata per il sito.

Quando il connettore è abilitato, vengono aggiunte le seguenti variabili riservate:

| Segnalato come | Tipo | Note |
|---|---|---|
| URL | Dimensione | URL della pagina associato alla richiesta. |
| Tipo di bot | Dimensione | Il tipo di bot o agente automatico che ha effettuato la richiesta (ad esempio, un crawler di IA con nome). |
| Agente utente | Dimensione | Stringa dell’agente utente segnalata dal bot o dall’agente. |
| Stato | Dimensione | Codice di stato HTTP restituito per la richiesta. |
| Referer | Dimensione | Il valore del referente HTTP per la richiesta, se presente. |
| Richieste | Metrica | Numero di richieste CDN bot e agente. |


#### Copertura rispetto a Customer Journey Analytics

L’integrazione in entrata di CJA è basata su un set di dati più ampio di Riepilogo richieste CDN e supporta campi aggiuntivi (ad esempio, host e provider CDN) oltre all’unione con altri set di dati in Customer Journey Analytics. L’integrazione di Adobe Analytics è un set di variabili riservate nativo della suite di rapporti progettato per funzionare all’interno del modello di dati esistente di Analytics. Se le tue esigenze di reporting vanno oltre i campi elencati sopra, valuta l’integrazione di CJA.

#### Limitazioni importanti

- Non sono inclusi ID visitatore, ECID, visite o dati utente univoci. Si tratta di dati di riepilogo aggregati, non legati ai visitatori.
- Le variabili riservate non supportano le impostazioni del tipo di allocazione o del tipo di scadenza, in quanto non sono collegate a un visitatore.
- I dati non possono essere uniti con altri set di dati o dimensioni di Analytics nello stesso modo in cui lo si può fare in Customer Journey Analytics.
- Utilizza la metrica **Richieste** per misurare il volume di traffico da bot e agenti. Non utilizzarla in modo intercambiabile con metriche basate su visite o hit in altre aree della suite di rapporti.

L’esatto set di campi disponibili deve essere confermato in base alla configurazione della variabile della suite di rapporti dopo l’abilitazione del connettore.

### Responsabilità

L&#39;installazione e la configurazione del connettore in entrata comportano responsabilità sia per [Adobe](#adobe-managed-responsibilities) che per [te come cliente](#customer-owned-responsibilities).

#### Responsabilità gestite da Adobe

1. Rileva e conferma l’inoltro del registro CDN per ogni sito Brand Visibility integrato.
2. Rende le variabili riservate disponibili per il provisioning una volta confermato l’inoltro del registro BYOCDN.
3. Esegue la retrocompilazione di 90 giorni e la sincronizzazione oraria in corso una volta che il connettore è abilitato per una suite di rapporti.

#### Responsabilità del cliente

1. Completamento dell’onboarding Brand Visibility e dell’inoltro del registro BYOCDN per ciascun sito.
2. La conferma dei dati è visibile nel dashboard Traffico agente Brand Visibility prima di abilitare il connettore.
3. Scelta della suite di rapporti a cui ogni sito Visibilità dei brand si connette (un sito per suite di rapporti).
4. Abilitazione del connettore tramite Report Suite Manager.
5. Creazione di report, segmenti o visualizzazioni dati (se applicabile) che utilizzano le variabili riservate elencate in [Funzionamento](#how-it-works).

### Prima di iniziare

Prima di abilitare il connettore, conferma quanto segue:

- Hai completato l’onboarding di Adobe Brand Visibility per il sito da connettere.
- L&#39;inoltro del registro BYOCDN è configurato e confermato per tale sito (vedi [prequisiti](#inbound-integration)).
- I dati vengono visualizzati nel dashboard Traffico agente di Adobe Brand Visibility per quel sito.
- Sai a quale suite di rapporti desideri connettere il sito.

Ogni sito Adobe Brand Visibility si connette esattamente a una suite di rapporti. Se desideri inserire dati per più di un sito di Visibilità dei brand, connetti ciascun sito a una suite di rapporti separata.


### Abilita il connettore

Il connettore è attivato e disattivato dal menu **Modifica impostazioni** della suite di rapporti.

Per aprire le impostazioni di Adobe Brand Visibility per la suite di rapporti:

1. Accedi ad Adobe Analytics.
1. Passa a **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Seleziona la suite di rapporti che desideri connettere.
1. Seleziona **[!UICONTROL Edit Settings]**.
1. Dal menu di scelta rapida, selezionare **[!UICONTROL Adobe Brand Visibility]**.

Per eseguire il provisioning del connettore:

1. Selezionare **Provisioning Connettore dati di Adobe Brand Visibility**.
1. Rivedi le dimensioni e la metrica che verranno aggiunte a questa suite di rapporti (elencate in [Come funziona](#how-it-works)).
1. In **Seleziona sito Adobe Brand Visibility** scegliere il sito da connettere a questa suite di rapporti. Una volta connesso, i dati di riepilogo del sito vengono sincronizzati con questa suite di rapporti ogni ora.
1. Selezionare **Abilita**.

   Una volta abilitate, queste variabili non possono essere rimosse da questa suite di rapporti. Abilitando il connettore si avvia una retrocompilazione di 90 giorni, importando gli ultimi 90 giorni di dati Adobe Brand Visibility in questa suite di rapporti.

   Prima di abilitare il connettore, verificare di aver completato i passaggi descritti in [Prima di avviare](#before-you-start), verifica che i dati siano già visualizzati nel dashboard Traffico agente di Adobe Brand Visibility.

Dopo aver attivato il connettore, attendi il tempo necessario per il completamento della retrocompilazione iniziale e della prima sincronizzazione oraria. Conferma quindi che le variabili riservate menzionate in [Come funziona](#how-it-works) siano popolate nella tua suite di rapporti. sezione 8, punto 3).

### Disattiva il connettore

>[!WARNING]
>
>La disattivazione del connettore è **non reversibile**. La disabilitazione interrompe la sincronizzazione oraria ed elimina i dati Adobe Brand Visibility storici per questa suite di rapporti.

Per disattivare il connettore:

1. Vai a **Suite di rapporti di → per amministratori → Modifica impostazioni → Adobe Brand Visibility**.
1. Selezionare **Deprovisioning Connettore Dati Adobe Brand Visibility**.
1. Conferma che il sito Adobe Brand Visibility elencato sia quello che intendi disconnettere.
1. Seleziona **Disattiva**.
1. Conferma l’avviso da confermare.

Se desideri solo sospendere temporaneamente la generazione dei rapporti, non disabilitare il connettore. Contatta il team del tuo account Adobe per discutere le opzioni per mettere in pausa il reporting prima di disabilitarlo.

### Imposta criteri di completamento

L’integrazione in entrata è pronta per la generazione di rapporti quando vengono confermate tutte le seguenti operazioni:

* I registri CDN vengono inoltrati a e ricevuti da Adobe Brand Visibility per il sito.
* I dati sono visibili nel dashboard Traffico agente di Adobe Brand Visibility per il sito.
* Il connettore è stato abilitato per la suite di rapporti prevista tramite Report Suite Manager.
* Il backfill iniziale e almeno una sincronizzazione oraria sono stati completati.
* Le variabili riservate nella sezione 4 restituiscono i valori previsti nella generazione rapporti.

### Procedura di verifica

La procedura di verifica si articola nelle seguenti fasi:

1. Conferma preparazione al sito di Visibilità dei brand e al registro CDN:

   * Conferma il sito o il dominio esatto che intendi connettere.
   * Conferma l’inoltro dei registri CDN per quel sito e la conferma di ricezione è stata confermata dalla Visibilità dei brand.
   * I dati di conferma sono visibili nel dashboard Traffico agente per quel sito.

1. Conferma l’attivazione del connettore:

   1. Vai a **Suite di rapporti Admin → → Modifica impostazioni → Adobe Brand Visibility** per la suite di rapporti di destinazione.
   1. Conferma che la pagina mostri il connettore come abilitato ed elenca il sito di Visibilità dei brand connesso.

1. Conferma i dati nel reporting:

   1. Apri Analysis Workspace (o il flusso di lavoro di reporting standard) rispetto alla suite di rapporti connessa.
   1. Crea una tabella o una visualizzazione utilizzando la metrica **Richieste** suddivisa per **Tipo bot**.
   1. Viene visualizzato il volume della richiesta di conferma per un intervallo di date recente.
   1. Confermare le dimensioni **URL**, **Agente utente**, **Stato** e **Referer** restituiscono i valori previsti.

   Il tempo esatto necessario per la visualizzazione dei dati dipende dalla pianificazione di backfill e sincronizzazione descritta in [Abilitare il connettore](#enable-the-connector).



### Risoluzione dei problemi

Consulta i seguenti problemi e come risolverli.

| Problema | Risoluzione dei problemi |
|---|---|
| Il connettore non verrà abilitato oppure l&#39;elenco dei siti è vuoto. | Verifica se:<ul><li>Onboarding di Adobe Brand Visibility completato per il sito.</li><li>L’inoltro del registro BYOCDN è configurato e confermato per il sito.</li><li>Stai lavorando nella suite di rapporti corretta.</li><ul> |
| Il connettore è attivato ma non vengono visualizzati dati. | Verifica se: <ul><li>I dati sono visibili nel dashboard Traffico agente per il sito connesso (in caso contrario, il problema è a monte di Analytics).</li><li>È trascorso abbastanza tempo per il backfill iniziale di 90 giorni e almeno una sincronizzazione oraria.</li><li>- L’intervallo di date selezionato nel rapporto include un periodo dopo l’attivazione del connettore.</li></ul> |
| I dati appaiono incompleti o imprevisti. | Verifica se: <ul><li>Non è previsto che la suite di rapporti riceva anche dati per un sito di Visibilità dei brand diverso (ogni suite di rapporti si connette esattamente a un sito).</li><li>Stai leggendo la metrica **Richieste** invece di contare righe o hit in altre parti della suite di rapporti.</li><li>Le dimensioni che stai visualizzando corrispondono all’elenco nella Sezione 4; evar o eventi non correlati nella stessa suite di rapporti non fanno parte di questa integrazione.</li></ul> |

>[!MORELIKETHIS]
>
>[Visibilità dei brand riferimento all&#39;integrazione /LLMO](https://experienceleague.adobe.com/en/docs/analytics-platform/using/integrations/bv)
>[Riferimento inoltro registro BYOCDN](https://experienceleague.adobe.com/en/docs/brand-visibility/using/log-forwarding/log-forwarding-overview)

---

## Note di bozza per la documentazione (non per la pubblicazione)

Questa sezione è per revisione interna e deve essere rimossa prima della pubblicazione.

- **Source di verità utilizzato:** i nomi dei campi, l&#39;elenco delle variabili riservate e il flusso di lavoro di Report Suite Manager provengono da [AN-468884](https://jira.corp.adobe.com/browse/AN-468884) (David Wardell, stato Nuovo al 28 agosto 2026), più attuale e più specifico della richiesta di documentazione originale [AN-449989](https://jira.corp.adobe.com/browse/AN-449989) (Rob In der Maur, stato Nuovo). La copia della pagina per le schermate di provisioning/deprovisioning incorpora i miglioramenti redazionali della revisione interna del 28 agosto 2026 (`2026-08-28-an468884-abv-report-suite-ui-review.md`), che ha sostituito l&#39;abbreviazione &quot;ABV&quot; del ticket non elaborato con &quot;Adobe Brand Visibility&quot; nel testo rivolto al cliente.
- **Discrepanza del set di campi da riconciliare prima della pubblicazione:** L&#39;elenco delle dimensioni originale di AN-449989 era Host, URL/percorso pagina, provider CDN, agente utente e tipo di bot LLM, con una singola metrica Conteggio richieste agente. L’elenco effettivo delle variabili riservate di AN-468884 è URL, Tipo di bot, Agente utente, Stato e Referente, con un singolo evento Richieste. Host e provider CDN non sono presenti come variabili riservate separate in AN-468884; lo stato è nuovo. Questa bozza segue l&#39;AN-468884 come autorevole per il ticket eng, ma i due devono essere riconciliati con Aaron Kern / David Wardell prima che questo venga finalizzato, dal momento che i nomi dei campi visualizzati dai clienti potrebbero non corrispondere a quelli descritti dai team dell&#39;account utilizzando il vecchio linguaggio AN-449989.
- **Non ancora confermato, non indicare come fatto nella versione pubblicata:**
  - Data esatta GA. AN-431416 porta FixVersion H2 2026 (finestra di rilascio 2026-11-30) ed è in stato di esecuzione al 2026-09-01; AN-468884 (implementazione con variabile riservata) e AN-449989 (questo documento) sono entrambi ancora nuovi. Non pubblicare fino alla spedizione di eng.
  - Indica se il tipo di allocazione o il tipo di scadenza sono completamente soppressi nelle eVar riservate in produzione. La revisione 2026-08-28 ha segnalato che una suite di rapporti di test mostra attualmente queste eVar con Allocazione impostata su &quot;Most Recent (Last)&quot; (Più recente, ultimo), che potrebbe essere un comportamento predefinito da cancellare, anziché confermare il comportamento finale.
  - L’endpoint API LLMO per l’inserimento di siti ABV da parte dell’organizzazione IMS (popola il menu a discesa Site Selection ) e l’API di deprovisioning/disabilitazione erano ancora in sospeso da Joe Bass a partire dal commento del ticket 2026-08-26.
  - Confronto esatto del conteggio dei campi di CJA. Il ticket originale di AN-449989 afferma che CJA ha &quot;9 dimensioni aggiuntive&quot; e &quot;5 metriche aggiuntive&quot;, ma diverse di queste (LLM Session Bucket, LLM Unique Session Count, LLM Request Duplication Count) non sono state confermate per esistere nel gruppo di campi `cdn-requests-summary` consegnato a partire dalla revisione 2026-06-18. Questa bozza evita intenzionalmente di citare conteggi specifici nel confronto CJA per tale motivo.
  - La cadenza di sincronizzazione per questo percorso AA è indicata qui come oraria, corrispondente alla lingua del ticket di AN-468884 (&quot;esegui sincronizzazioni orarie&quot; / &quot;processo di sincronizzazione oraria&quot;). Questo non è stato convalidato in modo indipendente rispetto al comportamento di produzione di Origini dati AA come era la cadenza di CJA.


## Integrazione in uscita

Questa guida descrive solo l’integrazione Brand Visibility in entrata, che aggiunge dati sul traffico da bot e agenti automatizzati a una suite di rapporti Analytics. La documentazione sull’integrazione pubblicata descrive anche una direzione in uscita, in cui i dati sulle prestazioni di Analytics vengono resi disponibili per Brand Visibility all’interno del prodotto Brand Visibility. Tale direzione esula dall&#39;ambito della presente guida. Per ulteriori informazioni sull&#39;integrazione in uscita, vedere la [documentazione Brand Visibility](https://experienceleague.adobe.com/en/docs/brand-visibility/using/resources/adobe-analytics-integration).