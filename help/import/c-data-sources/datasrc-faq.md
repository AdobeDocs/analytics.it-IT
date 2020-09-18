---
description: In questo argomento sono fornite risposte alle domande comuni.
subtopic: Data sources
title: Domande frequenti su Origini dati
topic: Developer and implementation
uuid: 394a627f-093c-400a-bfb3-c2aa24568deb
translation-type: tm+mt
source-git-commit: dbcdabdfd53b9d65d72e6269fcd25ac7118586e7
workflow-type: tm+mt
source-wordcount: '1494'
ht-degree: 95%

---


# Domande frequenti su Origini dati

In questo argomento sono fornite risposte alle domande comuni.

## Come posso collegare dati offline a eventi online? {#section_F48A9474A70D4CB8B449DE305F199AD6}

Affinché le origini dati ID transazione possano collegare dati offline a eventi online, devi abilitare la Registrazione ID transazione. Consulta [Registrazione ID transazione](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) per ulteriori informazioni.

## Quanto costa utilizzare la funzione Origine dati? {#section_0B84E3E8891B45E8970EA9D8AAD1ADEC}

Origini dati non ha costi aggiuntivi oltre la chiamata al server standard. I costi di chiamata al server si applicano solo ai tipi di origine dati a elaborazione completa, in cui vengono inviati hit singoli come righe di dati. Le origini dati a livello aggregato e di traffico non generano costi aggiuntivi.

## Come si includono i commenti nei file Origini dati? {#section_AA42152C7B30425EA541A7BA274E78ED}

Ogni riga in un file Origini dati che inizia con un simbolo cancelletto (#) viene trattata come commento.

## È necessario includere una colonna data nei dati del foglio di calcolo? {#section_EA37F5FFB13446C497B3C64943F7084E}

Sì. Poiché molti rapporti di marketing sono codificati dalla colonna data, Origini dati richiede una colonna data.

## Posso archiviare dati in variabili esistenti già in uso? {#section_AB557C2997D04EAFBDC61398B13D13C6}

Adobe consiglia di selezionare variabili nuove e non utilizzate per importare i dati con Origini dati. Se non sei sicuro della configurazione del file di dati o vuoi capire meglio i rischi legati al riutilizzo delle variabili, contatta l’Assistenza clienti.

## Posso eliminare i dati importati con Origini dati? {#section_DB73BC06BD774738BF019B347D9DED96}

No. Una volta importati, i dati caricati nei rapporti con Origini dati non possono essere rimossi, neanche dai tecnici Adobe. Vengono inseriti permanentemente nei dati esistenti e diventano indistinguibili dai dati inseriti tramite metodi di raccolta dati tradizionali (ovvero JavaScript, ActionSource, API di inserimento dati, ecc.). Pertanto, Adobe consiglia vivamente di caricare i dati di Origini dati in una suite di rapporti di prova prima di caricarli in una suite di produzione.

## Quanti dati posso importare alla volta? {#section_7A76D59E2C5B434D9BDBD2ABD2873168}

L’elaborazione viene messa in pausa se la dimensione supera i 50 MB e non riprende finché il totale non è inferiore a 50 MB. Per limitare i ritardi di generazione dei rapporti, non caricare più di 90 giorni di dati al giorno.

## Quando importo i dati tramite Origine dati, i dati esistenti vengono sovrascritti? {#section_BDBD16D0AFD54D55AFDB8AC77D35FE77}

I dati di Origini dati non sovrascrivono mai i dati dei rapporti esistenti. I dati caricati tramite Origini dati vengono aggiunti ai dati esistenti.

## Quando carico i dati tramite Origini dati, perché non ottengo anche le metriche? {#section_33176B39744F4F5A861E69AD87B99B78}

Quando carichi dati di Origini dati, carichi le metriche che saranno disponibili nell’interfaccia del rapporto.

Ad esempio, se carichi Ricavi da call center per prodotti venduti sul sito, puoi avere i Ricavi da call center nello stesso rapporto di Ricavi online. Tuttavia non puoi utilizzarli insieme a Visite, dato che non ne hai caricato il numero. Adobe può creare rapporti solo di metriche ed elementi caricati tramite Origine dati (oltre alle metriche di rapporti di marketing standard).

## Cosa succede se trasferisco valori negativi nel reporting tramite Origini dati? {#section_77E5F37F3CFB4407BA32A91E6F3132B2}

Il valore diminuisce di conseguenza.

## Qual è la differenza tra Origine dati Traffico e Origine dati Conversione (Generica)? {#section_A34C952490814D4FB802F22D9FB3E9F8}

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

## Origini dati prende in considerazione sub-relazioni, correlazioni e percorsi? {#section_7ABAE2F3C4DD48E18FB8CB20AE8AFD14}

Poiché il processo di Origine dati (“per DS generico, non Traffico”) crea hit singoli elaborati dalla cache, viene utilizzato il processo di sub-relazione, ma non il processo di correlazione. I percorsi hanno il potenziale per l’elaborazione, ma ogni hit ne costituirebbe la visita, pertanto non vengono generati percorsi. I dati dei percorsi vengono generati per le importazioni Registro web.

## Sussiste la distinzione maiuscole/minuscole per le estensioni dei file di caricamento Origine dati o di classificazione? {#section_710787BA4D8C403D8326D666807832B8}

Se le estensioni di un file di caricamento Origine dati o un file di classificazione sono maiuscole, i file non vengono elaborati. Le estensioni dei file di caricamento Origine dati devono essere minuscole. Ad esempio, [!DNL file.TXT] e [!DNL file.FIN] non vengono elaborati. Analogamente, [!DNL .TAB] e [!DNL .FIN] non vengono elaborati. Tuttavia, [!DNL .txt] e [!DNL .fin] vengono elaborati.

## Posso aggiungere altri eventi al modello generato o il limite massimo è tre? {#section_F184913926DD43B1872956CED308ADB5}

Puoi aggiungere quanti eventi desideri. Tuttavia, la procedura guidata consente solo tre eventi. Una volta creato il file modello, puoi aggiungere altri eventi secondo necessità.

## Cosa succede a un file Origine dati in cui uno o più record non hanno lo stesso numero di colonne del record intestazione? {#section_2666949CB11B49768774C904C93A16D4}

Se hai un file Origine dati in cui uno o più record non hanno lo stesso numero di colonne del record intestazione, si verificherà quanto segue.

* Viene inviata un’e-mail al creatore dell’origine dati con una notifica dell’errore.
* Il file non viene elaborato a causa della mancata corrispondenza delle colonne.

## Viene eseguito il rollup delle informazioni di Origini dati? {#section_E0E44C55A84245918E7CF5A4232F5C88}

È possibile eseguire il rollup delle informazioni di Origini dati; tuttavia, l’Assistenza clienti di Adobe deve rielaborare il rollup dalla data dello storico per includere i dati storici. Ad esempio, se la data corrente è 31 ottobre 2015 e vuoi caricare dati per il periodo 1°-15 agosto 2015 tramite Origini dati, devi impostare il rollup per la rielaborazione a partire dal 1° agosto 2015, in modo da includere i dati appena importati.

Inoltre i dati non devono mai essere caricati direttamente in una suite di rapporti rollup utilizzando Origini dati. Se devi includere i dati in un rollup, questi devono essere importati in una suite di rapporti standard, denominata anche *`child suite`* per il rollup. Contatta l’Assistenza clienti di Adobe per ulteriori informazioni.

## Perché il rapporto Visualizzazioni pagina non mostra dati di Origini dati per un singolo giorno, ma mostra i dati corretti per una settimana? {#section_E361A93AFDE1487989B4B0C4438EEDF7}

Origini dati non crea rapporti di dati su base oraria. Quando tenti di eseguire un rapporto per un giorno specifico, i dati possono essere suddivisi solo per ora, pertanto non viene visualizzato nulla nel rapporto. Puoi visualizzare i dati solo quando sono suddivisi per un livello di granularità giornaliero o superiore, eseguendo un rapporto settimanale o mensile.

## Come vengono calcolati i Visitatori unici in un caricamento Origine dati di un registro server web? {#section_477FEDFD1DBE45278E7D09AFBD59CDAC}

Il numero di Visitatori unici in un registro server web viene calcolato come combinazioni distinte diverse di *`IP Address`* e *`User Agent`* nel registro web. Ogni combinazione unica di questi due elementi viene calcolata come Visitatore unico. Se la colonna [!UICONTROL User Agent] è vuota (o non è inclusa nel registro web), non è possibile identificare il numero di Visitatori unici e l’intero caricamento sarà conteggiato come un solo Visitatore unico (anche se sono presenti più indirizzi IP).

## In Origini dati, come posso sapere quali login appartengono a quale suite di rapporti? {#section_8EF9D22D5BE14C218724B06E78EF7DF4}

In Origini dati, l’ID suite di rapporti è la prima parte del login a cui viene aggiunto un numero casuale che identifica l’origine dati specifica configurata. Ad esempio, `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## In che modo la versione 15 e la segmentazione influiscono sulle origini dati? {#section_7E9E541DB73C49CDAADC031B678F8678}

Nella versione 15 Origini dati ha un comportamento diverso in base al tipo di origine:

* le origini dati Elaborazione completa, Registro web e ID transazione appaiono come normali. Quando sono applicati segmenti, i dati vengono filtrati in base alle regole dei segmenti.
* Le origini dati standard o conversione (campagne pubblicitarie, gestione delle relazioni con i clienti, soddisfazione cliente, prestazioni del sito, dati di riepilogo generici, acquisti online, lead e preventivi e dati di canale offline) appaiono nella versione 15. Tuttavia, poiché tali origini dati non sono collegate a visite o visitatori, vengono filtrate quando sono applicati segmenti.

## Le metriche importate tramite ID transazione sono disponibili nei feed di dati di click-stream e in data warehouse? {#section_01CD14CA3E11490CB2CBA433C649029E}

Il feed di dati contiene qualsiasi metrica ID transazione ricevuta. Tuttavia, se carichi i dati ID transazione per una data passata, l’unico modo per ottenere i dati è scaricare di nuovo il feed di dati per tale giorno.

## Le eVar attualmente persistenti nel Profilo visitatore sono allocate a metriche caricate utilizzando origini dati? {#section_1748BD5C6A12467F8082E07D6A9CD595}

No per elaborazione completa, sì per ID transazione. Le origini dati a elaborazione completa vengono elaborate utilizzando profili visitatore separati, pertanto anche se gli ID visitatore corrispondono, non potranno essere collegate da una prospettiva di allocazione eVar. Le origini dati ID transazione sono collegate al profilo visitatore principale, pertanto le eVar persistenti sono allocate a eventi caricati tramite ID transazione.

## Le eVar caricate tramite origini dati persistono a comportamenti online successivi? {#section_0B490CEAAB604826AFD3E8B2531C8F2D}

No. Le eVar caricate tramite origini dati ID transazione vengono lette solo dalle informazioni profilo memorizzate e non aggiornano il profilo.
No. Le eVar sono le uniche variabili salvate nello snapshot del profilo visitatore.

## Come funzionano gli eventi numerici e valutari con le origini dati?

L&#39;elaborazione completa supporta solo i formati legacy dell&#39;elenco eventi, escludendo il valore numerico/valutario (più di 1) dell&#39;evento direttamente nell&#39;elenco eventi, `"eventNN,eventKK"` non `"eventNN=#.##"`. Significa che supporta un evento contatore solo se viene passato nella colonna eventi nel file dell&#39;origine dati e incrementa di 1.

Se sono richiesti eventi numerici, valutari o contatore (più di 1), utilizzare l&#39;elenco dei prodotti:

```js
s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";
```
