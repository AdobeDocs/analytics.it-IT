---
description: Domande frequenti sui feed di dati
keywords: Feed di dati;processo;pre colonna;post colonna;sensibilità maiuscole/minuscole
title: Domande frequenti sui feed di dati
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: e9969fbcc2adb58fba8d2bd293580181a05d1bac
workflow-type: tm+mt
source-wordcount: '1369'
ht-degree: 0%

---

# Domande frequenti sui feed di dati

Domande frequenti sui feed di dati.

## I nomi dei feed devono essere univoci?{#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

I nomi dei file di feed dati sono costituiti dall’ID suite di rapporti e dalla data. I due feed configurati per lo stesso RSID e la stessa data avranno lo stesso nome file. Se tali feed vengono inviati nella stessa posizione, un file sovrascrive l’altro. Per evitare la sovrascrittura di un file, non è possibile creare un feed che possa sovrascrivere un feed esistente nella stessa posizione.

Se si tenta di creare un feed quando ne esiste un altro con lo stesso nome di file, viene visualizzato il seguente messaggio:

Se ricevi questo errore, considera le seguenti soluzioni alternative:

* Modificare il percorso di consegna
* Se possibile, modifica le date
* Se possibile, modifica la suite di rapporti

## Quando vengono elaborati i dati? {#section_6346328F8D8848A7B81474229481D404}

Prima di elaborare i dati su base oraria o giornaliera, i feed di dati attendono che tutti gli hit che hanno inserito la raccolta dati entro l’intervallo di tempo (giorno o ora) siano stati scritti in data warehouse. In seguito, i feed di dati raccolgono i dati con marche temporali che rientrano nell’intervallo temporale, li comprime e li invia tramite FTP. Per i feed orari, in genere i file vengono scritti in data warehouse entro 15-30 minuti dopo l&#39;ora, ma non esiste un periodo di tempo impostato. Se non vi erano dati con marche temporali che rientrano nell’intervallo temporale, il processo prova nuovamente l’intervallo temporale successivo. Il processo di feed dati corrente utilizza il campo `date_time` per determinare quali hit appartengono all’ora. Questo campo è basato sul fuso orario della suite di rapporti.

## Qual è la differenza tra le colonne con un prefisso `post_` e le colonne senza un prefisso `post_`?

Le colonne senza il prefisso `post_` contengono i dati esattamente come sono stati inviati alla raccolta dati. Le colonne con un prefisso `post_` contengono il valore dopo l’elaborazione. Esempi che possono modificare un valore sono la persistenza delle variabili, le regole di elaborazione, le regole VISTA, la conversione di valuta o altri Adobi logici lato server. Se possibile, Adobe consiglia di utilizzare la versione `post_` di una colonna.

Se una colonna non contiene una versione `post_` (ad esempio, `visit_num`), può essere considerata una colonna post.

## Come vengono gestiti i feed di dati per la distinzione tra maiuscole e minuscole?

In Adobe Analytics, la maggior parte delle variabili viene considerata senza distinzione tra maiuscole e minuscole a scopo di reporting. Ad esempio, &quot;neve&quot;, &quot;neve&quot;, &quot;NEVE&quot; e &quot;sNow&quot; sono tutti considerati allo stesso valore. La distinzione tra maiuscole e minuscole viene mantenuta nei feed di dati.

Se vedi diverse varianti di maiuscole e minuscole dello stesso valore tra colonne non post e post (ad esempio, &quot;neve&quot; nella colonna precedente e &quot;neve&quot; nella colonna post), l’implementazione utilizza valori sia in maiuscolo che in minuscolo nel sito. La variazione di maiuscole e minuscole nella colonna post è stata precedentemente passata e memorizzata nel cookie virtuale o è stata elaborata più o meno nello stesso momento per quella suite di rapporti.

## I bot vengono filtrati dalle regole bot di Admin Console incluse nei feed di dati?

I feed di dati non includono bot filtrati da [regole bot della console di amministrazione](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/bot-removal/bot-removal.html).

## Perché visualizzo più valori `000` nella colonna dei feed di dati `event_list` o `post_event_list`?

Alcuni editor di fogli di calcolo, in particolare Microsoft Excel, arrotondano automaticamente numeri grandi. La colonna `event_list` contiene molti numeri delimitati da virgole e a volte Excel ne considera un numero elevato. Arrotonda le ultime diverse cifre a `000`.

Adobe consiglia di non aprire automaticamente i file `hit_data.tsv` in Microsoft Excel. Utilizzare invece la finestra di dialogo Importa dati di Excel e assicurarsi che tutti i campi siano trattati come testo.

## Perché mancano informazioni nella colonna del dominio per alcuni gestori? {#section_B7508D65370442C7A314EAED711A2C75}

Alcuni gestori di dispositivi mobili (come T-Mobile e O1) non forniscono più informazioni di dominio per le ricerche DNS inverse. Pertanto, tali dati non sono disponibili per la generazione di rapporti sul dominio.

## Perché non posso estrarre file &quot;Orari&quot; da dati che hanno più di 7 giorni?

Per i dati che hanno più di 7 giorni, i file &quot;Ogni ora&quot; di un giorno vengono combinati in un unico file &quot;Giornaliero&quot;.

Esempio: Il 9 marzo 2021 è stato creato un nuovo feed di dati e i dati dal 1° gennaio 2021 al 9 marzo vengono consegnati come &quot;Orario&quot;. Tuttavia, i file &quot;Ogni ora&quot; prima del 2 marzo 2021 sono combinati in un unico file &quot;Giornaliero&quot;. Puoi estrarre i file &quot;Ogni ora&quot; solo dai dati che hanno meno di 7 giorni dalla data di creazione. In questo caso, dal 2 marzo al 9 marzo.

## Qual è l’impatto del risparmio giornaliero sui feed di dati orari? {#section_70E867D942054DD09048E027A9474FFD}

Per alcuni fusi orari, l&#39;ora cambia due volte all&#39;anno a causa delle definizioni dell&#39;ora legale (DST). I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario per la suite di rapporti non utilizza DST, la consegna dei file continua normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è quello che utilizza DST, la consegna dei file viene modificata per l’ora in cui si verifica la modifica dell’ora (di solito 2:00).

Quando si eseguono transizioni di tempo STD -> DST (&quot;Primavera avanti&quot;), il cliente riceve solo 23 file. L’ora saltata nella transizione DST viene omessa. Ad esempio, se la transizione si verifica alle 2 del mattino, ottengono un file per l’ora 1:00 e un file per l’ora 3:00. Non c&#39;è alcun file 2:00 perché, alle 2:00 STD, diventa 3:00 DST.

Quando si eseguono transizioni DST -> STD, (&quot;Fall Back&quot;), il cliente ottiene 24 file. Tuttavia, l&#39;ora della transizione include in realtà due ore di dati. Ad esempio, se la transizione si verifica alle 2:00, il file per 1:00 viene ritardato di un&#39;ora, ma contiene dati per due ore. Contiene dati da 1:00 DST a 2:00 STD (che sarebbe stato 3:00 DST). Il file successivo inizia alle 2:00 STD.

## Riceverò i file manifest quando non vengono raccolti dati? {#section_72510794694D42A9A75C966B812AEB0F}

Facoltativamente, puoi configurare un feed di dati per consegnare un file manifesto se non vengono raccolti dati per un periodo specifico. Se abiliti questa opzione, riceverai un file manifesto simile al seguente:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## In che modo Analytics gestisce gli errori di trasferimento FTP? {#section_4BD44E9167F0494FB2B379D2BA132AD8}

In caso di errore di trasferimento FTP (accesso negato, connessione persa, fuori quota, ecc.), Adobe tenta di connettersi e inviare automaticamente i dati fino a tre volte separate. Se gli errori persistono, il feed viene contrassegnato come non riuscito e viene inviata una notifica e-mail.

Se un trasferimento ha esito negativo, è possibile eseguire nuovamente un processo fino a quando non ha esito positivo.

In caso di problemi durante il recupero del feed di dati dal sito FTP, consulta [Risoluzione dei problemi relativi ai processi](jobs-troubleshooting.md).

## Come faccio a rimandare un lavoro? {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Dopo aver verificato/corretto il problema di consegna, esegui nuovamente il processo per ottenere i file.

## Qual è l’impostazione BucketOwnerFullControl per i feed di dati Amazon S3? {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Il caso d&#39;uso comune per Amazon S3 è che il proprietario dell&#39;account Amazon Web Services (AWS) crea un bucket, quindi crea un utente che dispone dell&#39;autorizzazione per creare oggetti in quel bucket e quindi fornisce le credenziali per tale utente. In questo caso, gli oggetti di un utente appartengono allo stesso account e il proprietario dell&#39;account ha implicitamente il pieno controllo dell&#39;oggetto (lettura, eliminazione, ecc.). Questo processo è simile al funzionamento della consegna FTP.

AWS consente inoltre a un utente di creare oggetti in un bucket che appartiene a un account utente diverso. Ad esempio, se due utenti AWS, userA e userB, non appartengono allo stesso account AWS ma desiderano creare oggetti in altri bucket. Se l’utente A crea un bucket, ad esempio bucketA, può creare un criterio di bucket che consente esplicitamente all’utente B di creare oggetti in bucketA anche se l’utente non possiede il bucket. Questo criterio può essere vantaggioso perché non richiede che l&#39;utente A e l&#39;utente B scambino credenziali. Al contrario, userB fornisce a userA il loro numero di account, e userA crea una policy di bucket che sostanzialmente dice &quot;lascia che l&#39;utente B crei oggetti in bucketA&quot;.

**** BucketOwnerFullControlfornisce diritti tra account diversi per creare oggetti in altri bucket. Se userB carica un oggetto nel bucket dell&#39;utente A, userB &quot;possiede&quot; ancora tale oggetto e, per impostazione predefinita, a userA non vengono concesse autorizzazioni per tale oggetto anche se l&#39;utente A è proprietario del bucket. Questo perché gli oggetti non ereditano le autorizzazioni dal bucket principale. UserB deve concedere esplicitamente le autorizzazioni userA perché userB è ancora il proprietario dell&#39;oggetto. Per concedere questa autorizzazione, userB deve caricare l&#39;oggetto con un ACL BucketOwnerFullControl, che specifica che al proprietario del bucket (userA) sono concesse autorizzazioni complete per l&#39;oggetto (lettura, scrittura, eliminazione, ecc.), anche se l&#39;oggetto è &quot;posseduto&quot; da userB.

>[!MORELIKETHIS]
>
>* [Risoluzione dei problemi dei processi](jobs-troubleshooting.md)

