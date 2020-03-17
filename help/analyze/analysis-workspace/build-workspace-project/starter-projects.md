---
description: 'null'
title: Modelli
uuid: d6d1b745-a684-41c1-879b-9f9a9503fe00
translation-type: tm+mt
source-git-commit: 08d564f7fb06b94c2010515ea4a1dcbb2e6e2815

---


# Modelli

## Modelli {#topic_40932F09E18A467983AFBB29908E1CB8}

Puoi scegliere di creare un progetto in base a:

* **Progetto vuoto (predefinito)**: Per istruzioni, consulta [Creazione di un progetto](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md)di Analysis Workspace.
* **Modello** standard: Questi modelli vengono creati da Adobe e vengono forniti con il prodotto.
* **Modello** personalizzato: Questi modelli possono essere creati, condivisi o eliminati da utenti con diritti di amministratore o da non amministratori, a condizione che dispongano dell’ [!UICONTROL Analysis Workspace: Save as Template] autorizzazione in Admin Console. [Per saperne di più...](https://docs.adobe.com/content/help/en/analytics/admin/admin-console/permissions/product-profile.html)

![](assets/start_modal.png)

## Creare un modello personalizzato {#create-custom-template}

Gli utenti con diritti di amministratore possono trasformare qualunque progetto che creano in un modello personalizzato effettuando le seguenti operazioni:

1. Apri il progetto.
1. Vai a **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Save As Template]** (Salva come modello).

   ![](assets/save_project_template.png)

   Il progetto viene salvato con il nome corrente, seguito dalla parola (Modello) tra parentesi. Gli amministratori possono cambiare questo nome modificando il modello.

   >[!NOTE]
   >
   >Per impostazione predefinita, i modelli di progetto sono visibili a tutti gli utenti dell’organizzazione. Puoi utilizzare dei tag per organizzare i modelli. (Vai a **[!UICONTROL Project]** (Progetto) > **[!UICONTROL Project Info & Settings]** (Informazioni e impostazioni progetto) per modificare tag e descrizioni.)

### Azioni eseguibili sui modelli personalizzati

![](assets/custom_templates.png)

| Azione | Descrizione |
|--- |--- |
| Modificare  un modello | Consente a un amministratore di modificare il modello cambiandone l’origine dati e modificando componenti, visualizzazioni, intervalli di date ecc.  Sono disponibili due modi per modificare un modello personalizzato: <ul><li>Visualizza l’elenco dei modelli personalizzati in Analysis Workspace, selezionane uno e fai clic su Modifica modello, oppure</li><li>In Analytics, vai a Componenti > Progetti, quindi applica il filtro Modelli. Fai clic sul nome del modello da modificare.</li></ul>**Nota:** dopo aver modificato un modello, a seconda della situazione, puoi scegliere Salva o Salva con nome. Queste sono le differenze tra le due opzioni:<ul><li>**Salva:** Aggiorna il modello personalizzato per tutti gli utenti. Quando un altro utente crea un progetto basato su questo modello personalizzato, vedrà le modifiche che hai apportato.</li><li>**Salva con nome:** Crea una copia del modello personalizzato con le modifiche apportate. (Per verificare che sia attiva la modalità di modifica, controlla che la voce di menu Condividi > Condividi progetto sia disabilitata.)</li></ul> |
| Cercare nei modelli | Nella finestra di dialogo Modelli personalizzati, fai clic su Cerca modelli. |
| Ordinare i modelli | Puoi organizzare i modelli in ordine alfabetico, per rilevanza e per data di creazione.  Nella finestra di dialogo Modelli personalizzati, fai clic su Ordina:. |
| Applicare tag a un modello | Apri il modello e vai a Progetto > Informazioni e impostazioni progetto. Fai clic su Aggiungi tag. |
| Modificare la descrizione di un modello | Apri il modello e vai a Progetto > Informazioni e impostazioni progetto. Fai doppio clic sulla descrizione e modificala. |


## Modelli standard {#concept_4FE900FEEC894E849CB6C6A0E0ADA524}

La prima volta che si apre un’Workspace i modelli sono disponibili nella barra a sinistra. I modelli di Analysis Workspace coprono i casi d’uso più comuni. Sono raggruppati in base all’applicazione verticale a cui fanno riferimento e sono compilati con dimensioni, segmenti, metriche e visualizzazioni, a seconda della suite per rapporti selezionata.

Puoi usare questi modelli precompilati così come sono o adattarli alle tue esigenze (ad esempio, aggiungendo o sostituendo metriche o visualizzazioni) e salvarli con un nuovo nome.

[Modelli standard in Analysis Workspace su YouTube](https://www.youtube.com/watch?v=aRgYwPneVXg&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS&index=6) (2:46)

Di seguito sono riportati i modelli disponibili e le domande che ogni modello può rispondere.

* **Esercitazione** di formazione: Questo modello standard illustra la terminologia e i passaggi comuni per la creazione della prima analisi in Workspace. È disponibile come modello standard nel modale Nuovo progetto e sostituisce il progetto di esempio attuale per i nuovi utenti che non hanno altri progetti nel loro elenco.

### Pubblicità

>[!IMPORTANT]
>
>I modelli pubblicitari sono disponibili solo se la suite di rapporti è abilitata per Advertising Cloud.

* **Motori** di ricerca a pagamento: Questo modello suddivide tendenze pubblicitarie, piattaforme di annunci, parole chiave, account, campagne e altro ancora.

### Commercio

* **Magento: Marketing e Commercio**: questo modello suddivide la conversione e-commerce in base all’attribuzione del canale di marketing, oltre a fornire informazioni dettagliate in base a parole chiave di ricerca, pagina di destinazione, posizione geografica e altro ancora. Per visualizzare un video introduttivo, vedi >[!VIDEO](https://www.youtube.com/watch?v=AQOViVLEMHw)

### Media

* **Consumo audio**: quali contenuti vengono maggiormente consumati e coinvolgono maggiormente gli utenti?
* **Recency - Frequenza - Fedeltà**: Chi sono i miei lettori più fedeli?

### Mobile

>[!IMPORTANT]
>
>I modelli per dispositivi mobili sono disponibili solo se la suite per rapporti è abilitata per i dispositivi mobili.

* **Messaggistica:** si focalizza sulle prestazioni di messaggi in-app e push.
* **Posizione:** include una mappa che mostra i dati della posizione.
* **Metriche chiave:** controlla le metriche chiave della tua app.
* **Utilizzo app:** quanti utenti, avvii e primi avvii sono stati registrati per l’app, e quanto dura in media una sessione?
* **Acquisizione:** scopri le prestazioni dei collegamenti per acquisizione mobile.
* **Prestazioni:** quali sono le prestazioni dell’app e dove vengono riscontrati problemi dagli utenti?
* **Fidelizzazione:** chi sono i miei utenti più fedeli e cosa fanno?
* **Percorsi:** Quali sono i pattern di utilizzo principali per la l’app?

### Vendita al dettaglio

* **Prestazione campagna:** quali campagne generano maggior fatturato?
* **Prodotti:** quali prodotti hanno prestazioni migliori?

### Web

* **Acquisizione:** quali fattori generano maggior traffico verso il sito Web?
* **Consumo di contenuti:** quali sono le aree del sito più visitate?
* **Fidelizzazione:** che tipi di utenti hanno più probabilità di diventare utenti fedeli del sito?
* **Tecnologia:** quali tecnologie vengono usate per accedere al sito?

### Persone

> [!NOTE] Il modello Persone e la metrica Persone corrispondente sono disponibili per l’uso unicamente nell’ambito di [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-people.html).

Questo modello è basato sulla metrica Persone, che è una versione deduplicata della metrica Visitatori unici. La metrica Persone misura la frequenza con cui i consumatori che utilizzano più dispositivi interagiscono con il tuo marchio. Il modello consente di: 

* Segmentare i dati relativi a USA/Canada rispetto al resto del mondo. Device Co-op attualmente è disponibile solo nel Nord America.
* Affiancare e confrontare le metriche Persone e Visitatori unici.
* Visualizzare il “tasso di compressione”, una metrica calcolata che mostra lo scarto della metrica Persone come percentuale di Visitatori unici.
* Confrontare i totali dei diversi tipi di dispositivi utilizzati dalla clientela
* Verificare la media dei dispositivi pro capite.
* Scoprire come raggruppare i segmenti con la metrica Persone.
* Capire in che modo l’uso di Experience Cloud ID nel tuo ambiente riesca a ottimizzare l’efficacia della metrica Persone.

### IQ viaggio: Modello di analisi multi-dispositivo

<!-->This content is mirrored in the CDA doc.<-->

Questo modello consente di visualizzare dati di prestazioni cross-device vitali. È disponibile solo per i clienti che hanno accesso a [Cross-Device Analytics](https://docs.adobe.com/content/help/en/analytics/components/cda/cda-home.html) (CDA).

* **Nota speciale per i membri del Co-op Graph**: Mostra quale parte della suite di rapporti contiene i visitatori nelle aree in cui è supportato il grafico della cooperativa e nelle aree in cui non è supportato.
* **Identificazione degli utenti**: Mostra la frequenza con cui i visitatori del sito vengono identificati utilizzando metodi basati su Analisi cross-device.
* **Misurazione della dimensione** del pubblico: Mostra un confronto tra &quot;Dispositivi univoci&quot; e &quot;Persone&quot;. La proporzione di questi due numeri è nota come &#39;compressione tra dispositivi&#39;, una metrica calcolata visibile in questo pannello. Questa metrica di compressione dipende da un&#39;ampia gamma di fattori:
   * **Utilizzando il grafico Co-op o il grafico** Privato: In generale, le organizzazioni che utilizzano la cooperativa dispositivi tendono a visualizzare tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico privato.
   * **Velocità** di accesso: Più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. Anche i siti con un basso tasso di accesso hanno bassi tassi di compressione.
   * **Copertura** Experience Cloud ID: È possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
   * **Utilizzo** di più dispositivi: Se i visitatori del sito non utilizzano più dispositivi, è possibile visualizzare percentuali di compressione più basse.
   * **Granularità** del reporting: La compressione per giorno è generalmente inferiore alla compressione per mese o anno. Le possibilità di un singolo di utilizzare più dispositivi diventano più ridotte entro un singolo giorno rispetto a un intero mese. Segmentazione, filtraggio o utilizzo di dimensioni di suddivisione può anche mostrare una minore frequenza di compressione.
* **Segmenti** basati sulle persone: Contiene un elenco a discesa dei segmenti che consente di visualizzare dati specifici per il dispositivo. Questo pannello incoraggia la sperimentazione con i segmenti per vedere in che modo i report possono essere influenzati dall&#39;inclusione o esclusione di tipi di dispositivi.
* **Analisi del percorso** cross-device: Fornisce rapporti di flusso e di abbandono in base al tipo di dispositivo.
* **Attribuzione** tra dispositivi: Combinate le funzioni di IQ viaggio e IQ attribuzione.
* **Altri suggerimenti e trucchi**: Argomenti utili intorno a CDA che ti permettono di ottenere di più dall&#39;utilizzo.