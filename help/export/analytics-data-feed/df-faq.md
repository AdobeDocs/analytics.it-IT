---
description: Domande frequenti sui feed di dati
keywords: Feed di dati;processo;pre colonna;post colonna;sensibilità maiuscole/minuscole
title: Domande frequenti sui feed di dati
feature: Data Feeds
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
source-git-commit: a71db2fac9333b70a55da91fe9a94b0cc8434b42
workflow-type: tm+mt
source-wordcount: '1437'
ht-degree: 0%

---

# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## I nomi dei feed devono essere univoci?{#unique}

I nomi dei file di feed dati sono costituiti dall’ID suite di rapporti e dalla data. Tutti e due i feed configurati per lo stesso RSID e la stessa data hanno lo stesso nome file. Se tali feed vengono inviati nella stessa posizione, un file sovrascrive l’altro. Per evitare la sovrascrittura di un file, non è possibile creare un feed che possa sovrascrivere un feed esistente nella stessa posizione.

Se si tenta di creare un feed quando ne esiste un altro con lo stesso nome di file, viene visualizzato un messaggio di errore. Considera le seguenti soluzioni alternative:

* Modificare il percorso di consegna
* Se possibile, modifica le date
* Se possibile, modifica la suite di rapporti

## Quando vengono elaborati i dati? {#processed}

Prima di elaborare i dati su base oraria o giornaliera, i feed di dati attendono che tutti gli hit che hanno inserito la raccolta dati entro l’intervallo di tempo (giorno o ora) siano stati scritti in data warehouse. In seguito, i feed di dati raccolgono i dati con marche temporali che rientrano nell’intervallo temporale, li comprime e li invia tramite FTP. Per i feed orari, in genere i file vengono scritti in data warehouse entro 15-30 minuti dopo l&#39;ora, ma non esiste un periodo di tempo impostato. Se non vi erano dati con marche temporali che rientrano nell’intervallo temporale, il processo prova nuovamente l’intervallo temporale successivo. Il processo di feed dati corrente utilizza `date_time` per determinare quali hit appartengono all’ora. Questo campo è basato sul fuso orario della suite di rapporti.

## Qual è la differenza tra le colonne con un `post_` prefisso e colonne senza un `post_` prefisso? {#post}

Colonne senza `post_` Il prefisso contiene i dati esattamente come è stato inviato alla raccolta dati. Colonne con un `post_` Prefisso contiene il valore dopo l’elaborazione. Esempi che possono modificare un valore sono la persistenza delle variabili, le regole di elaborazione, le regole VISTA, la conversione di valuta o altri Adobi logici lato server. L&#39;Adobe consiglia di utilizzare `post_` se possibile, versione di una colonna.

Se una colonna non contiene `post_` version (ad esempio, `visit_num`), quindi la colonna può essere considerata una colonna post.

## Come vengono gestiti i feed di dati per la distinzione tra maiuscole e minuscole? {#case}

In Adobe Analytics, la maggior parte delle variabili viene considerata senza distinzione tra maiuscole e minuscole a scopo di reporting. Ad esempio, &quot;neve&quot;, &quot;neve&quot;, &quot;NEVE&quot; e &quot;sNow&quot; sono tutti considerati allo stesso valore. La distinzione tra maiuscole e minuscole viene mantenuta nei feed di dati.

Se vedi diverse varianti di maiuscole e minuscole dello stesso valore tra colonne non post e post (ad esempio, &quot;neve&quot; nella colonna pre e &quot;neve&quot; nella colonna post), l’implementazione utilizza sia valori maiuscoli che minuscoli nel sito. La variazione di maiuscole e minuscole nella colonna post è stata precedentemente passata e memorizzata nel cookie virtuale o è stata elaborata più o meno nello stesso momento per quella suite di rapporti.

## I bot vengono filtrati dalle regole bot di Admin Console incluse nei feed di dati? {#bots}

I feed di dati non includono bot filtrati da [Regole bot di Admin Console](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Perché visualizzo più `000` nei valori `event_list` o `post_event_list` colonna feed dati? {#values}

Alcuni editor di fogli di calcolo, in particolare Microsoft Excel, arrotondano automaticamente numeri grandi. La `event_list` La colonna contiene molti numeri delimitati da virgole, a volte causando il trattamento di Excel come un numero elevato. Arrotonda le ultime diverse cifre a `000`.

L&#39;Adobe raccomanda di non aprire automaticamente `hit_data.tsv` file in Microsoft Excel. Utilizzare invece la finestra di dialogo Importa dati di Excel e assicurarsi che tutti i campi siano trattati come testo.

## Sono colonne come `hitid_high`, `hitid_low`, `visid_high`e `visid_low` garantito di essere unico per l&#39;hit o la visita? {#hitid}

In quasi tutti i casi, la concatenazione di `hitid_high` e `hitid_low` identificare in modo univoco un hit. Lo stesso concetto si applica alla concatenazione di `visid_high` e `visid_low` per visite. Tuttavia, le anomalie di elaborazione raramente possono causare la condivisione dello stesso ID hit da parte di due hit. L’Adobe consiglia di non creare flussi di lavoro per feed di dati che si basano in modo flessibile sull’univocità di ogni hit.

## Perché mancano informazioni nella colonna del dominio per alcuni gestori? {#domain}

Alcuni gestori di dispositivi mobili (come T-Mobile e O1) non forniscono più informazioni di dominio per le ricerche DNS inverse. Pertanto, tali dati non sono disponibili per la generazione di rapporti sul dominio.

## Perché non posso estrarre file &quot;Orari&quot; da dati che hanno più di 7 giorni? {#hourly}

Per i dati che hanno più di 7 giorni, i file &quot;Ogni ora&quot; di un giorno vengono combinati in un unico file &quot;Giornaliero&quot;.

Esempio: Il 9 marzo 2021 è stato creato un nuovo feed di dati e i dati dal 1° gennaio 2021 al 9 marzo vengono consegnati come &quot;Orario&quot;. Tuttavia, i file &quot;Ogni ora&quot; prima del 2 marzo 2021 sono combinati in un unico file &quot;Giornaliero&quot;. Puoi estrarre i file &quot;Ogni ora&quot; solo dai dati che hanno meno di 7 giorni dalla data di creazione. In questo caso, dal 2 marzo al 9 marzo.

## Qual è l’impatto del risparmio giornaliero sui feed di dati orari? {#dst}

Per alcuni fusi orari, l&#39;ora cambia due volte all&#39;anno a causa delle definizioni dell&#39;ora legale (DST). I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario per la suite di rapporti non utilizza DST, la consegna dei file continua normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è quello che utilizza DST, la consegna dei file viene modificata per l’ora in cui si verifica la modifica dell’ora (di solito 2:00).

Quando si eseguono transizioni di tempo STD -> DST (&quot;Primavera avanti&quot;), il cliente riceve solo 23 file. L’ora saltata nella transizione DST viene omessa. Ad esempio, se la transizione si verifica alle 2 del mattino, ottengono un file per l’ora 1:00 e un file per l’ora 3:00. Non c&#39;è alcun file 2:00 perché, alle 2:00 STD, diventa 3:00 DST.

Quando si eseguono transizioni DST -> STD, (&quot;Fall Back&quot;), il cliente ottiene 24 file. Tuttavia, l&#39;ora della transizione include in realtà due ore di dati. Ad esempio, se la transizione si verifica alle 2:00, il file per 1:00 viene ritardato di un&#39;ora, ma contiene dati per due ore. Contiene dati da 1:00 DST a 2:00 STD (che sarebbe stato 3:00 DST). Il file successivo inizia alle 2:00 STD.

## In che modo Analytics gestisce gli errori di trasferimento FTP? {#ftp-failure}

Se un trasferimento FTP non riesce (a causa di un accesso negato, connessione persa, errore fuori quota o altro problema), Adobe tenta di connettersi e inviare automaticamente i dati fino a tre volte separate. Se gli errori persistono, il feed viene contrassegnato come non riuscito e viene inviata una notifica e-mail.

Se un trasferimento ha esito negativo, è possibile eseguire nuovamente un processo fino a quando non ha esito positivo.

In caso di problemi durante il recupero del feed di dati dal sito FTP, consulta [Risoluzione dei problemi dei feed dati](troubleshooting.md).

## Come faccio a rimandare un lavoro? {#resend}

Dopo aver verificato/corretto il problema di consegna, esegui nuovamente il processo per ottenere i file.

## Qual è l’impostazione BucketOwnerFullControl per i feed di dati Amazon S3? {#BucketOwnerFullControl}

**BucketOwnerFullControl** fornisce diritti tra account diversi per creare oggetti in altri bucket.

Il caso d’uso comune per Amazon S3 è che il proprietario dell’account Amazon Web Services (AWS) crea un bucket, quindi crea un utente che dispone dell’autorizzazione per creare oggetti in tale bucket e quindi fornisce le credenziali per tale utente. In questo caso, gli oggetti di un utente appartengono allo stesso account e il proprietario dell&#39;account ha implicitamente il pieno controllo dell&#39;oggetto (lettura, eliminazione e così via). Questo processo è simile al funzionamento della consegna FTP.

AWS consente inoltre a un utente di creare oggetti in un bucket che appartengono a un account utente diverso. Ad esempio, due utenti AWS, userA e userB, non appartengono allo stesso account AWS ma desiderano creare oggetti in altri bucket. Se l’utente A crea un bucket denominato &quot;bucketA&quot;, può creare un criterio per i bucket che consente esplicitamente all’utente B di creare oggetti in bucketA anche se l’utente non possiede il bucket. Questo criterio può essere vantaggioso perché non richiede agli utenti A e userB di scambiare le credenziali. Al contrario, userB fornisce a userA il loro numero di account, e userA crea una policy di bucket che sostanzialmente dice &quot;lascia che l&#39;utente B crei oggetti in bucketA&quot;.

Tuttavia, gli oggetti non ereditano le autorizzazioni dal bucket principale. Pertanto, se userB carica un oggetto nel bucket dell&#39;utente A, userB &quot;possiede&quot; ancora tale oggetto e, per impostazione predefinita, a userA non vengono concesse autorizzazioni per tale oggetto anche se l&#39;utente A è proprietario del bucket. UserB deve concedere esplicitamente le autorizzazioni userA perché userB è ancora il proprietario dell&#39;oggetto. Per concedere questa autorizzazione, userB deve caricare l&#39;oggetto con un ACL BucketOwnerFullControl, che specifica che al proprietario del bucket (userA) sono concesse autorizzazioni complete per l&#39;oggetto (lettura, scrittura, eliminazione e così via), anche se l&#39;oggetto è &quot;di proprietà&quot; di userB.

>[!NOTE]
>
>Adobe Analytics non determina se il bucket dispone di un criterio che richiede l’assegnazione al proprietario del bucket del controllo completo dei nuovi oggetti, o anche se il proprietario del bucket si trova in un account diverso da quello utilizzato dall’utente per scrivere i dati. Al contrario, Analytics aggiunge automaticamente il proprietario del bucket al `BucketOwnerFullControl` ACL con ogni caricamento di feed.

