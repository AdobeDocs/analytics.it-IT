---
description: Domande frequenti sui feed di dati
keywords: Feed di dati;processo;colonna pre;colonna post;sensibilità maiuscole/minuscole
title: Domande frequenti sui feed di dati
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '1450'
ht-degree: 100%

---

# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## I nomi dei feed devono essere univoci? {#unique}

I nomi dei file di feed dati sono costituiti dall‘ID della suite di rapporti (RSID) e dalla data. Due feed configurati per lo stesso RSID e la stessa data hanno lo stesso nome file. Se tali feed vengono inviati alla stessa posizione, un file sovrascrive l‘altro. Per evitare la sovrascrittura di un file, non è possibile creare un feed che possa sovrascrivere un feed esistente nella stessa posizione.

Se si tenta di creare un feed quando ne esiste già un altro con lo stesso nome di file, viene visualizzato un messaggio di errore. Prendi in considerazione le seguenti soluzioni:

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

I feed di dati non includono bot filtrati dalle [regole bot di Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html?lang=it).

## Perché trovo più valori `000` nella colonna `event_list` o `post_event_list` dei feed dati? {#values}

Alcuni editor di fogli di calcolo, in particolare Microsoft Excel, arrotondano automaticamente i numeri elevati. La colonna `event_list` contiene molti numeri delimitati da virgole, che a volte possono essere considerati da Excel come numeri elevati. In tal caso, le ultime cifre vengono arrotondate a `000`.

Adobe consiglia di non aprire automaticamente i file `hit_data.tsv` in Microsoft Excel. Piuttosto, utilizza la finestra di dialogo Importa dati di Excel e assicurati che tutti i campi siano trattati come testo.

## Le colonne come `hitid_high`, `hitid_low`, `visid_high` e `visid_low` sono garantite come univoche per l‘hit o la visita? {#hitid}

Nella maggior parte dei casi, la concatenazione di `hitid_high` e `hitid_low` identifica in modo univoco un hit. Lo stesso concetto si applica alla concatenazione di `visid_high` e `visid_low` per le visite. Tuttavia, in alcuni rari casi, a causa di anomalie di elaborazione si può verificare che due hit condividano entrambi lo stesso ID. Adobe consiglia di non creare flussi di lavoro per feed di dati che si basano in modo inflessibile sull‘univocità di ogni hit.

## Perché mancano informazioni nella colonna del dominio per alcuni gestori? {#domain}

Alcuni gestori di dispositivi mobili (come T-Mobile e O1) non forniscono più informazioni di dominio per le ricerche DNS inverse. Pertanto, tali dati non sono disponibili nei rapporti con dati sul dominio.

## Perché non posso estrarre file “Orari” da dati che hanno più di 7 giorni? {#hourly}

Per i dati che hanno più di 7 giorni, i file “Orari” di un giorno vengono combinati in un unico file “Giornaliero”.

Esempio: il 9 marzo 2021 è stato creato un nuovo feed di dati e i dati dal 1° gennaio 2021 al 9 marzo vengono consegnati come “Orari”. Tuttavia, i file “Orari” prima del 2 marzo 2021 sono combinati in un unico file “Giornaliero”. Puoi estrarre i file “Orari” solo dai dati che hanno meno di 7 giorni dalla data di creazione. In questo caso, dal 2 marzo al 9 marzo.

## Qual è l’impatto dell’ora legale sui feed di dati orari? {#dst}

In alcuni fusi orari, l’ora cambia due volte all&#39;anno a causa dell’introduzione dell’ora legale. I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario della suite di rapporti non utilizza l’ora legale, la consegna dei file continua normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è quello che utilizza l’ora legale, la consegna dei file viene modificata per l’ora in cui si verifica il passaggio all’ora legale o solare (di solito alle 2:00).

Quando si passa dall’ora solare all’ora legale (un’ora in avanti), il cliente riceve solo 23 file. L’ora saltata nel passaggio all’ora legale viene omessa. Ad esempio, se il passaggio si verifica alle 2 del mattino, si ottiene un file per l’ora 01:00 e un file per l’ora 03:00. Non c&#39;è alcun file relativo alle 02:00 perché, le 02:00 ora solare diventano le 03:00 ora legale.

Quando si passa dall’ora legale all’ora solare (un’ora indietro), il cliente ottiene 24 file. Tuttavia, l’ora in cui avviene il passaggio all’ora solare include in realtà due ore di dati. Ad esempio, se il passaggio si verifica alle 02:00, il file dell’ora 01:00 viene ritardato di un’ora, ma contiene i dati relativi a due ore. Contiene dati da 01:00 ora legale a 02:00 ora solare (che corrisponde alle 03:00 ora legale). Il file successivo inizia alle 02:00 ora solare.

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

