---
description: È possibile scaricare i dati da  Analysis Workspace copiandoli oppure in formato PDF e CSV.
title: Scaricare file PDF o CSV
uuid: 8af5f3d7-5870-4ed6-8a9f-ef290a48ef5f
translation-type: tm+mt
source-git-commit: ab5d2be12100306410486fea31bacc6ee9756738
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 7%

---


# Scaricare file PDF o CSV da Workspace

Esistono diversi modi per esportare i dati da  Analysis Workspace a seconda del set di dati da analizzare all’esterno dello strumento e di chi deve ricevere le informazioni. I dati esportati possono essere sotto forma di dati copiati, file CSV o PDF. Un PDF è in genere la preferenza se si desidera includere le visualizzazioni nel file, mentre un file CSV (o i dati copiati) è preferito se si desidera semplicemente che i dati siano in testo normale.

>[!IMPORTANT]
>
> Alcune opzioni cui si fa riferimento in questa pagina, come **Scarica elementi come CSV**, al momento sono in test limitati. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/analytics/landing/an-releases.html)

## Scarica il progetto come CSV o PDF {#download-project}

Puoi scaricare un progetto completo da Progetto > **Scarica come PDF (o come CSV)**. Il file scaricato conterrà tutte le tabelle e le visualizzazioni visualizzate (visibili) nel progetto. Un PDF è in genere preferito se si desidera includere le visualizzazioni nel file, mentre un file CSV è preferito se si desidera semplicemente che i dati siano in testo normale.

Per i download dei progetti, tieni presente quanto segue:

* Il progetto può essere salvato o non salvato quando si richiede il download di un progetto. Tuttavia, solo i progetti salvati possono essere [pianificati](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/t-schedule-report.html).
* L&#39;esportazione dei PDF scaricati nel browser può richiedere alcuni minuti perché il progetto viene rieseguito  server di Adobe prima del rendering in formato PDF. È consigliabile non uscire dal progetto fino al completamento del download del PDF nel browser. Tuttavia, puoi continuare ad apportare modifiche al progetto mentre attendi. Se il rendering di un PDF richiede più di 5 minuti, verrà richiesto di inviarlo tramite e-mail.
* I download PDF vengono rappresentati come una singola pagina senza applicazione di impaginazione.
* Quando viene eseguito il rendering di un progetto in PDF, viene eseguito il rendering di ciò che si trova sulla pagina. Se un progetto contiene pannelli e visualizzazioni di dimensione personalizzata, dovrai impostarne ridimensionamento automatico (con il pulsante in alto a destra) in modo da evitare che alcuni contenuti vengano troncati.

## Copia dati negli Appunti (tasto di scelta rapida: Ctrl+C) {#copy-data}

Fai clic con il pulsante destro del mouse > Opzioni Copia negli Appunti per copiare rapidamente i dati da Workspace e incollarli altrove.

* Se si desidera copiare la tabella visualizzata, fare clic con il pulsante destro del mouse sull&#39;intestazione della tabella e scegliere **Copia dati visualizzati negli Appunti**.
* Se si desidera copiare un sottoinsieme di dati, effettuare una selezione nella tabella, quindi fare clic con il pulsante destro del mouse > **Copia selezione negli Appunti**.

Inoltre, il tasto di scelta rapida **Ctrl+C** consente di copiare la selezione negli Appunti. Una volta copiato, è possibile passare a un altro strumento e incollare le informazioni (o premere Ctrl+V).

## Download data as CSV {#download-data}

Fai clic con il pulsante destro del mouse > Scarica come CSV per scaricare una tabella di dati o l’origine dati di qualsiasi visualizzazione come CSV.

* Nell’intestazione di una tabella, fai clic con il pulsante destro del mouse > **Scarica i dati visualizzati come CSV**. I dati visualizzati nella tabella verranno scaricati come CSV.
* Se nella tabella è stata effettuata una selezione, l&#39;opzione **Scarica la selezione come CSV**&#x200B;è denominata. Solo la selezione verrà scaricata con questa opzione, al contrario della tabella visualizzata completa.
* Nell’intestazione di una visualizzazione, fai clic con il pulsante destro del mouse > **Scarica dati come CSV**. Questa opzione consente di scaricare la tabella dell’origine dati per una visualizzazione come CSV. Nota: la visualizzazione Mappa non supporta questa opzione.

## Download items as CSV {#download-items}

Per analizzare più righe di dati visibili di 400 righe in una tabella, fai clic con il pulsante destro del mouse sull’intestazione della tabella o su una riga qualsiasi e seleziona **Scarica elementi come CSV (nome Dimension)**. Questa opzione consente di esportare fino a 50.000 elementi dimensionali per la dimensione selezionata (in base all&#39;ordinamento della tabella), con l&#39;applicazione di filtri e segmenti. Se si sceglie questa opzione nella parte superiore della tabella, verrà esportata la prima dimensione della tabella. Sebbene non siano applicati limiti nella tabella a forma libera, si consiglia di utilizzare l&#39;opzione Download elementi nelle tabelle con meno di 20 colonne per garantire prestazioni ottimali.

>[!TIP]
>
> Se la dimensione supera i 50.000 elementi, scaricate il file con diverse metriche di ordinamento applicate o applicate un filtro. Ad esempio, ordina in base alle visite in un solo download e poi in ordine crescente per visite in un secondo download. Questo suggerimento può aiutare a recuperare gli elementi più lunghi di coda.

Puoi eseguire più attività all’interno del progetto e persino passare a un nuovo progetto Workspace nella stessa scheda mentre è in corso il download. Il download si interrompe se si apre una nuova scheda del browser. Il download viene annullato se si esce completamente da Workspace o si chiude la scheda del browser.

### File di elementi scaricati

Le funzionalità della tabella verranno applicate al file scaricato come segue:

* Tutti i segmenti di pannello saranno applicati come filtri.
* Le suddivisioni **sopra** la dimensione selezionata nella tabella vengono applicate come filtri sopra ogni colonna.
* Le suddivisioni **sotto** la dimensione selezionata nella tabella verranno rimosse.

Nell’esempio precedente, gli elementi Pagina verranno scaricati con il segmento del pannello (Nuovi clienti visitatori) e i componenti sopra (Canale marketing = E-mail) applicati come filtri, e i componenti sotto (Tipo dispositivo mobile) rimossi dal file CSV scaricato.

### Download delle notifiche

Quando il file viene scaricato, viene visualizzata una notifica informativa con l’avanzamento. In qualsiasi momento, puoi annullare il download facendo clic su &quot;Annulla download&quot;. La chiusura del toast non **annullerà** il download.

Una volta completato il file, verrà visualizzata una notifica di completamento e il file verrà scaricato nel browser.

Se richiedete più di un download alla volta, riceverete una notifica per informarvi che ogni download aggiuntivo sarà messo in coda fino al completamento del download precedente.

## Domande frequenti {#faq}

| Domanda | Risposta |
| --- | --- |
| Perché il mio PDF scaricato è una pagina? | Al momento, Workspace non impagina i PDF scaricati. |
| Posso esportare più di 50.000 elementi con l’opzione &quot;Scarica elementi come CSV&quot;? | Anche se ogni download può contenere fino a 50.000 elementi dimensionali, potete modificare l&#39;ordinamento della tabella per recuperare elementi finali più lunghi, oppure applicare un filtro per scaricare altri elementi specifici. |
| Cosa fa &quot;Copia visualizzazione&quot;? | La visualizzazione Copia non è un’opzione di esportazione. Consente di copiare una visualizzazione o un pannello da un’area di lavoro all’altra. Ad esempio, da un pannello all’altro nello stesso progetto, o da un progetto a un altro. [Guarda il video](https://www.youtube.com/watch?v=lvmAdKNfWQw) |

