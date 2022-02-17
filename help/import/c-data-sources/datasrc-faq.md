---
description: In questo argomento sono fornite risposte alle domande comuni.
subtopic: Data sources
title: Domande frequenti su Origini dati
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 2a5d38fe-5c5b-4275-bc44-e9cb02ec2f5d
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 95%

---

# Domande frequenti su Origini dati

In questo argomento sono fornite risposte alle domande comuni.

## Come posso collegare dati offline a eventi online? {#offline}

Affinché le origini dati ID transazione possano collegare dati offline a eventi online, devi abilitare la Registrazione ID transazione. Consulta [Registrazione ID transazione](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) per ulteriori informazioni.

## Quanto costa utilizzare la funzione Origine dati? {#cost}

Origini dati non ha costi aggiuntivi oltre la chiamata al server standard. I costi di chiamata al server si applicano solo ai tipi di origine dati a elaborazione completa, in cui vengono inviati hit singoli come righe di dati. Le origini dati a livello aggregato e di traffico non generano costi aggiuntivi.

## Come si includono i commenti nei file Origini dati? {#comments}

Ogni riga in un file Origini dati che inizia con un simbolo cancelletto (#) viene trattata come commento.

## È necessario includere una colonna data nei dati del foglio di calcolo? {#date}

Sì. Poiché molti rapporti di marketing sono codificati dalla colonna data, Origini dati richiede una colonna data.

## Posso archiviare dati in variabili esistenti già in uso? {#variables}

Adobe consiglia di selezionare variabili nuove e non utilizzate per importare i dati con Origini dati. Se non sei sicuro della configurazione del file di dati o vuoi capire meglio i rischi legati al riutilizzo delle variabili, contatta l’Assistenza clienti.

## Posso eliminare i dati importati con Origini dati? {#imported}

No. Una volta importati, i dati caricati nei rapporti con Origini dati non possono essere rimossi, neanche dai tecnici Adobe. Vengono inseriti permanentemente nei dati esistenti e diventano indistinguibili dai dati inseriti tramite metodi di raccolta dati tradizionali (ovvero JavaScript, ActionSource, API di inserimento dati, ecc.). Pertanto, Adobe consiglia vivamente di caricare i dati di Origini dati in una suite di rapporti di prova prima di caricarli in una suite di produzione.

## Quanti dati posso importare alla volta? {#amount}

L’elaborazione viene messa in pausa se la dimensione supera i 50 MB e non riprende finché il totale non è inferiore a 50 MB. Per limitare i ritardi di generazione dei rapporti, non caricare più di 90 giorni di dati al giorno.

## Quando importo i dati tramite Origine dati, i dati esistenti vengono sovrascritti? {#overwrite}

I dati di Origini dati non sovrascrivono mai i dati dei rapporti esistenti. I dati caricati tramite Origini dati vengono aggiunti ai dati esistenti.

## Quando carico i dati tramite Origini dati, perché non ottengo anche le metriche? {#metrics}

Quando carichi dati di Origini dati, carichi le metriche che saranno disponibili nell’interfaccia del rapporto.

Ad esempio, se carichi Ricavi da call center per prodotti venduti sul sito, puoi avere i Ricavi da call center nello stesso rapporto di Ricavi online. Tuttavia non puoi utilizzarli insieme a Visite, dato che non ne hai caricato il numero. Adobe può creare rapporti solo di metriche ed elementi caricati tramite Origine dati (oltre alle metriche di rapporti di marketing standard).

## Cosa succede se trasferisco valori negativi nel reporting tramite Origini dati? {#negative}

Il valore diminuisce di conseguenza.

## Qual è la differenza tra Origine dati Traffico e Origine dati Conversione (Generica)?  {#traffic}

Origine dati Traffico carica molto più velocemente perché aggiorna semplicemente i valori di riepilogo nelle tabelle appropriate. Origine dati Generica con dati di conversione (eventi, ecc.) crea un hit per ogni valore nella colonna da elaborare.

File di esempio:

<table id="table_D5408E0BDB984229B4C60A66BB53CEBB"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Date </code> </p> </td> 
   <td colname="col2"> <p> <code> Event15 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 01/01/2013 </code> </p> </td> 
   <td colname="col2"> <p> <code> 553 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

Nell’esempio sopra vengono creati 553 hit da elaborare nel sistema cache.

## Origini dati prende in considerazione sub-relazioni, correlazioni e percorsi? {#breakdown}

Poiché il processo di Origine dati (“per DS generico, non Traffico”) crea hit singoli elaborati dalla cache, viene utilizzato il processo di sub-relazione, ma non il processo di correlazione. I percorsi hanno il potenziale per l’elaborazione, ma ogni hit ne costituirebbe la visita, pertanto non vengono generati percorsi. I dati dei percorsi vengono generati per le importazioni Registro web.

## Sussiste la distinzione maiuscole/minuscole per le estensioni dei file di caricamento Origine dati o di classificazione? {#case}

Se le estensioni di un file di caricamento Origine dati o un file di classificazione sono maiuscole, i file non vengono elaborati. Le estensioni dei file di caricamento Origine dati devono essere minuscole. Ad esempio, [!DNL file.TXT] e [!DNL file.FIN] non vengono elaborati. Analogamente, [!DNL .TAB] e [!DNL .FIN] non vengono elaborati. Tuttavia, [!DNL .txt] e [!DNL .fin] vengono elaborati.

## Posso aggiungere altri eventi al modello generato o il limite massimo è tre? {#template}

Puoi aggiungere quanti eventi desideri. Tuttavia, la procedura guidata consente solo tre eventi. Una volta creato il file modello, puoi aggiungere altri eventi secondo necessità.

## Cosa succede a un file Origine dati in cui uno o più record non hanno lo stesso numero di colonne del record intestazione? {#header}

Se hai un file Origine dati in cui uno o più record non hanno lo stesso numero di colonne del record intestazione, si verificherà quanto segue.

* Viene inviata un’e-mail al creatore dell’origine dati con una notifica dell’errore.
* Il file non viene elaborato a causa della mancata corrispondenza delle colonne.

## Viene eseguito il rollup delle informazioni di Origini dati? {#rollup}

È possibile eseguire il rollup delle informazioni di Origini dati; tuttavia, l’Assistenza clienti di Adobe deve rielaborare il rollup dalla data dello storico per includere i dati storici. Ad esempio, se la data corrente è 31 ottobre 2015 e vuoi caricare dati per il periodo 1°-15 agosto 2015 tramite Origini dati, devi impostare il rollup per la rielaborazione a partire dal 1° agosto 2015, in modo da includere i dati appena importati.

Inoltre i dati non devono mai essere caricati direttamente in una suite di rapporti rollup utilizzando Origini dati. Se devi includere i dati in un rollup, questi devono essere importati in una suite di rapporti standard, denominata anche *`child suite`* per il rollup. Contatta l’Assistenza clienti di Adobe per ulteriori informazioni.

## Perché il rapporto Visualizzazioni pagina non mostra dati di Origini dati per un singolo giorno, ma mostra i dati corretti per una settimana? {#week}

Origini dati non crea rapporti di dati su base oraria. Quando tenti di eseguire un rapporto per un giorno specifico, i dati possono essere suddivisi solo per ora, pertanto non viene visualizzato nulla nel rapporto. Puoi visualizzare i dati solo quando sono suddivisi per un livello di granularità giornaliero o superiore, eseguendo un rapporto settimanale o mensile.

## Come vengono calcolati i Visitatori univoci in un caricamento Origine dati di un registro server web? {#unique}

Il numero di Visitatori univoci in un registro server web viene calcolato come combinazioni distinte diverse di *`IP Address`* e *`User Agent`* nel registro web. Ogni combinazione univoca di questi due elementi viene calcolata come Visitatore univoco. Se la colonna [!UICONTROL User Agent] è vuota (o non è inclusa nel registro web), non è possibile identificare il numero di Visitatori univoci e l’intero caricamento sarà conteggiato come un solo Visitatore univoco (anche se sono presenti più indirizzi IP).

## In Origini dati, come posso sapere quali login appartengono a quale suite di rapporti? {#login}

In Origini dati, l’ID suite di rapporti è la prima parte del login a cui viene aggiunto un numero casuale che identifica l’origine dati specifica configurata. Ad esempio, `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## In che modo la versione 15 e la segmentazione influiscono sulle origini dati? {#segmentation}

Nella versione 15 Origini dati ha un comportamento diverso in base al tipo di origine:

* le origini dati Elaborazione completa, Registro web e ID transazione appaiono come normali. Quando sono applicati segmenti, i dati vengono filtrati in base alle regole dei segmenti.
* Le origini dati standard o conversione (campagne pubblicitarie, gestione delle relazioni con i clienti, soddisfazione cliente, prestazioni del sito, dati di riepilogo generici, acquisti online, lead e preventivi e dati di canale offline) appaiono nella versione 15. Tuttavia, poiché tali origini dati non sono collegate a visite o visitatori, vengono filtrate quando sono applicati segmenti.

## Le metriche importate tramite ID transazione sono disponibili nei feed di dati di click-stream e in data warehouse? {#clickstream}

Il feed di dati contiene qualsiasi metrica ID transazione ricevuta. Tuttavia, se carichi i dati ID transazione per una data passata, l’unico modo per ottenere i dati è scaricare di nuovo il feed di dati per tale giorno.

## Le eVar attualmente persistenti nel Profilo visitatore sono allocate a metriche caricate utilizzando origini dati? {#visitor}

No per elaborazione completa, sì per ID transazione. Le origini dati a elaborazione completa vengono elaborate utilizzando profili visitatore separati, pertanto anche se gli ID visitatore corrispondono, non potranno essere collegate da una prospettiva di allocazione eVar. Le origini dati ID transazione sono collegate al profilo visitatore principale, pertanto le eVar persistenti sono allocate a eventi caricati tramite ID transazione.

## Le eVar caricate tramite origini dati persistono a comportamenti online successivi? {#evars}

No. Le eVar caricate tramite origini dati ID transazione vengono lette solo dalle informazioni profilo memorizzate e non aggiornano il profilo.
No. Le eVar sono le uniche variabili salvate nello snapshot del profilo visitatore.

## Come funzionano gli eventi numerici e valutari con le origini dati? {#numeric}

L’elaborazione completa supporta solo i formati degli elenchi di eventi precedenti, escludendo il valore evento numerico/valuta/contatore (più di 1) direttamente nell’elenco degli eventi, ovvero `"eventNN,eventKK"` not `"eventNN=#.##"`. Significa che supporta un evento contatore solo se viene passato nella colonna eventi nel file di origine dati e incrementa di 1.

Se sono necessari eventi numerici, valutari o contatore (più di 1), utilizzare l’elenco dei prodotti:

```js
s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";
```
