---
description: Risposte alle domande frequenti sui feed di dati in Adobe Analytics.
keywords: Feed di dati;processo;colonna pre;colonna post;sensibilità maiuscole/minuscole
title: Domande frequenti sui feed dati
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: 470ab0dfa76681d73f847ba9c2aecaf64804540c
workflow-type: tm+mt
source-wordcount: '1488'
ht-degree: 73%

---

# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## I nomi dei feed devono essere univoci? {#unique}

Adobe Analytics non impedisce la sovrascrittura dei file di feed dati.

Per evitare che i file di feed dati vengano sovrascritti, si consiglia di assegnare nomi univoci a tutti i file di feed dati inviati alla stessa posizione.

I nomi dei file di feed dati sono costituiti dalle seguenti caratteristiche:

* ID suite di rapporti (RSID)

* Data di esportazione

Due feed configurati per lo stesso RSID e date hanno lo stesso nome file. Se tali feed vengono consegnati nella stessa posizione, un file sovrascrive l’altro.

Per evitare la sovrascrittura di un file, prendere in considerazione le seguenti soluzioni:

* Modifica il percorso di consegna.
* Se possibile, modifica le date.
* Se possibile, modifica la suite di rapporti.

## Quando vengono elaborati i dati? {#processed}

Prima di elaborare i dati su base oraria o giornaliera, i feed di dati attendono che tutti gli hit inseriti nella raccolta dati entro l‘arco temporale (giorno o ora) siano stati scritti nel data warehouse. In seguito, i feed di dati raccolgono i dati con le marche temporali che rientrano nell‘arco temporale in questione, li comprime e li invia tramite FTP. Per i feed orari, in genere i file vengono scritti nel data warehouse entro 15-30 minuti successivi all‘ora, ma non esiste un periodo di tempo specifico. Se non vi sono dati con marche temporali che rientrano nell’arco temporale, il processo viene nuovamente tentato nell’arco temporale successivo. Il processo di feed dati corrente utilizza il campo `date_time` per determinare quali hit appartengono a un‘ora. Questo campo è basato sul fuso orario della suite di rapporti.

## Qual è la differenza tra le colonne con prefisso `post_` e le colonne senza prefisso `post_`? {#post}

Le colonne senza prefisso `post_` contengono i dati esattamente come sono stati inviato alla raccolta dati. Le colonne con prefisso `post_` contengono il valore resultante dopo l‘elaborazione. Un valore può essere modificato, ad esempio, dalla persistenza delle variabili, da regole di elaborazione, da regole VISTA, dalla conversione di valuta o da altra logica applicata da Adobe lato server. Adobe consiglia di utilizzare la versione `post_` di una colonna, ove possibile.

Se una colonna non contiene una versione `post_` (ad esempio, `visit_num`), tale colonna può essere considerata una colonna Post.

## Come viene gestita la distinzione tra maiuscole e minuscole nei feed di dati? {#case}

In Adobe Analytics, la maggior parte delle variabili è considerata senza distinzione tra maiuscole e minuscole a scopo di reportistica. Ad esempio, “neve“, “Neve“, “NEVE“ e “nEve“ sono tutti considerati lo stesso valore. La distinzione tra maiuscole e minuscole viene invece mantenuta nei feed di dati.

Se vedi diverse varianti di maiuscole e minuscole dello stesso valore tra colonne Post e non-Post (ad esempio, “neve“ nella colonna Pre e “Neve“ nella colonna Post), l‘implementazione utilizza sia valori maiuscoli che minuscoli nel sito. La variazione di maiuscole e minuscole nella colonna Post è stata precedentemente trasmessa e memorizzata nel cookie virtuale oppure è stata elaborata più o meno nello stesso momento per quella suite di rapporti.

## I bot vengono filtrati dalle regole bot di Admin Console incluse nei feed di dati? {#bots}

I feed di dati non includono bot filtrati dalle [regole bot di Admin Console](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md).

## Perché trovo più valori `000` nella colonna `event_list` o `post_event_list` dei feed dati? {#values}

Alcuni editor di fogli di calcolo, in particolare Microsoft Excel, arrotondano automaticamente i numeri elevati. La colonna `event_list` contiene molti numeri delimitati da virgole, che a volte possono essere considerati da Excel come numeri elevati. In tal caso, le ultime cifre vengono arrotondate a `000`.

Adobe consiglia di non aprire automaticamente i file `hit_data.tsv` in Microsoft Excel. Piuttosto, utilizza la finestra di dialogo Importa dati di Excel e assicurati che tutti i campi siano trattati come testo.

## Le colonne come `hitid_high`, `hitid_low`, `visid_high` e `visid_low` sono garantite come univoche per l‘hit o la visita? {#hitid}

Nella maggior parte dei casi, la concatenazione di `hitid_high` e `hitid_low` identifica in modo univoco un hit. Lo stesso concetto si applica alla concatenazione di `visid_high` e `visid_low` per le visite. Tuttavia, in alcuni rari casi, a causa di anomalie di elaborazione si può verificare che due hit condividano entrambi lo stesso ID. Adobe consiglia di non creare flussi di lavoro per feed di dati che si basano in modo inflessibile sull‘univocità di ogni hit.

## Perché mancano informazioni nella colonna del dominio per alcuni gestori? {#domain}

Alcuni gestori di dispositivi mobili (come T-Mobile e O1) non forniscono più informazioni di dominio per le ricerche DNS inverse. Pertanto, tali dati non sono disponibili nei rapporti con dati sul dominio.

## Perché non posso estrarre in modo affidabile i file orari per le date precedenti? {#hourly}

Per ottimizzare lo storage e l&#39;elaborazione, Adobe consolida regolarmente le esportazioni orarie in file giornalieri. A causa di come e quando vengono eseguiti questi consolidamenti, l’output orario per le date più vecchie di 10 giorni non è prevedibile. Per una determinata data, è possibile visualizzare una combinazione di file orari per alcune ore e un file giornaliero consolidato per altri. I dati consolidati in un file giornaliero vengono in genere assegnati all&#39;ora `00`, che può lasciare vuote altre ore quando tali ore vengono richieste direttamente.

Per i backfill con più di 10 giorni, Adobe consiglia vivamente di utilizzare la granularità giornaliera per garantire risultati completi e prevedibili. Se devi richiedere la granularità oraria per i giorni precedenti, includi sempre l&#39;ora `00` nella richiesta per evitare di perdere dati orari consolidati.

## Qual è l’impatto dell’ora legale sui feed di dati orari? {#dst}

In alcuni fusi orari, l’ora cambia due volte all&#39;anno a causa dell’introduzione dell’ora legale. I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario della suite di rapporti non utilizza l’ora legale, la consegna dei file continua normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è quello che utilizza l’ora legale, la consegna dei file viene modificata per l’ora in cui si verifica il cambiamento (in genere alle 2:00).

Quando si passa dall’ora solare all’ora legale (primavera in avanti), si ricevono 23 file. L’ora saltata nel passaggio all’ora legale viene omessa. Ad esempio, se la transizione si verifica alle 2 del mattino, si ottiene un file per l&#39;ora 1:00 e un file per l&#39;ora 3:00. Nessun file 2:00 perché in 2:00 DST diventa 3:00 DST.

Quando si effettuano transizioni DST -> STD (fallback), si ricevono 24 file. Tuttavia, l’ora in cui avviene il passaggio all’ora solare include in realtà due ore di dati. Ad esempio, se la transizione si verifica alle 2:00 del mattino, il file per 1:00 viene ritardato di un&#39;ora, ma contiene dati per due ore. Contiene dati da 1:00 DST a 2:00 STD (che sarebbe stato 3:00 DST). Il file successivo inizia da 2:00 STD.

## In che modo Analytics gestisce gli errori di trasferimento FTP? {#ftp-failure}

Se un trasferimento FTP non riesce (a causa di un accesso negato, connessione persa, errore di limiti superati o altro problema), Adobe tenta di connettersi e inviare automaticamente i dati fino a tre volte. Se gli errori persistono, il feed viene contrassegnato come non riuscito e viene inviata una notifica e-mail.

Se un trasferimento non riesce, è possibile eseguire nuovamente il processo fino a quando non ha esito positivo.

In caso di problemi durante il recupero di un feed di dati dal sito FTP, consulta [Risoluzione dei problemi dei feed di dati](troubleshooting.md).

## Come faccio a eseguire nuovamente un processo? {#resend}

Dopo aver verificato/corretto il problema di consegna, esegui nuovamente il processo per ottenere i file.

## Qual è l’impostazione BucketOwnerFullControl per i feed di dati Amazon S3? {#BucketOwnerFullControl}

**BucketOwnerFullControl** fornisce diritti tra account diversi per creare oggetti in altri bucket.

Il caso d’uso comune per Amazon S3 è che il proprietario dell’account Amazon Web Services (AWS) crea un bucket, quindi crea un utente che dispone dell’autorizzazione per creare oggetti in tale bucket e quindi fornisce le credenziali per tale utente. In questo caso, gli oggetti di un utente appartengono allo stesso account e il proprietario dell’account ha implicitamente il pieno controllo dell’oggetto (lettura, eliminazione e così via). Questo processo è simile al funzionamento della consegna FTP.

AWS consente inoltre a un utente di creare oggetti in un bucket che appartengono a un account utente diverso. Ad esempio, due utenti AWS, userA e userB, non appartengono allo stesso account AWS ma desiderano creare oggetti in altri bucket. Se userA crea un bucket denominato “bucketA”, può creare un criterio di bucket che consenta esplicitamente a userB di creare oggetti in bucketA, anche se userB non ne è il propriatario. Questo criterio può essere vantaggioso perché non richiede a userA e userB di scambiarsi le credenziali. Al contrario, userB fornisce a userA il proprio numero di account, e userA crea un criterio di bucket di tipo “consenti a userB di creare oggetti in bucketA”.

Tuttavia, gli oggetti non ereditano le autorizzazioni dal bucket principale. Pertanto, se userB carica un oggetto nel bucket di userA, userB “possiede” ancora tale oggetto e, per impostazione predefinita, a userA non vengono concesse autorizzazioni per tale oggetto nonostante sia il proprietario del bucket. UserB deve concedere esplicitamente le autorizzazioni a userA, perché userB è ancora il proprietario dell’oggetto. Per concedere questa autorizzazione, userB deve caricare l’oggetto con un ACL BucketOwnerFullControl, che specifica che al proprietario del bucket (userA) sono concesse autorizzazioni complete per l’oggetto (lettura, scrittura, eliminazione e così via), anche se l’oggetto è “di proprietà” di userB.

>[!NOTE]
>
>Adobe Analytics non determina se il bucket dispone di un criterio che richiede l’assegnazione al proprietario del bucket del controllo completo dei nuovi oggetti; inoltre, non determina se il proprietario del bucket si trova in un account diverso da quello utilizzato dall’utente per scrivere i dati. Al contrario, Analytics aggiunge automaticamente il proprietario del bucket all’ACL `BucketOwnerFullControl` a ogni caricamento di feed.

