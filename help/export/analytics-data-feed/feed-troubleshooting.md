---
description: Questa sezione contiene informazioni sui problemi comuni.
keywords: Feed di dati;risoluzione dei problemi
title: Risoluzione dei problemi dei feed dati
uuid: 4be981ab-3a61-4099-9b0d-785d2ac2492a
exl-id: 58531afe-5e0e-49b6-9c9f-9c857be8dc75
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '1026'
ht-degree: 0%

---

# Risoluzione dei problemi dei feed dati

Questa sezione contiene informazioni sui problemi comuni.

## Errore durante il salvataggio del feed {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

I nomi dei file di feed dati sono costituiti dall’ID suite di rapporti e dalla data. I due feed configurati per lo stesso RSID e la stessa data avranno lo stesso nome file. Se tali feed vengono inviati nella stessa posizione, un file sovrascrive l’altro. Per evitare la sovrascrittura di un file, non è possibile creare un feed che possa sovrascrivere un feed esistente nella stessa posizione.

Se si tenta di creare un feed quando ne esiste un altro con lo stesso nome di file, viene visualizzato il seguente messaggio:

Se ricevi questo errore, considera le seguenti soluzioni alternative:

* Modificare il percorso di consegna
* Se possibile, modifica le date
* Se possibile, modifica la suite di rapporti

## Impostazione BucketOwnerFullControl per i feed di dati Amazon S3 {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Il caso d&#39;uso comune per Amazon S3 è che il proprietario dell&#39;account Amazon Web Services (AWS) crea un bucket, quindi crea un utente che dispone dell&#39;autorizzazione per creare oggetti in quel bucket e quindi fornisce le credenziali per tale utente. In questo caso, gli oggetti di un utente appartengono allo stesso account e il proprietario dell&#39;account ha implicitamente il pieno controllo dell&#39;oggetto (lettura, eliminazione, ecc.). È simile al funzionamento della consegna FTP.

AWS consente inoltre a un utente di creare oggetti in un bucket che appartengono a un account utente completamente diverso. Ad esempio, se due utenti AWS, userA e userB, non appartengono allo stesso account AWS ma desiderano creare oggetti in altri bucket. Se l’utente A crea un bucket, ad esempio bucketA, può creare un criterio di bucket che consente esplicitamente all’utente B di creare oggetti in bucketA anche se l’utente non possiede il bucket. Questo può essere vantaggioso perché non richiede che l&#39;utente A e l&#39;utente B scambino credenziali. Al contrario, userB fornisce a userA il loro numero di account, e userA crea una policy di bucket che sostanzialmente dice &quot;lascia che l&#39;utente B crei oggetti in bucketA&quot;.

**** BucketOwnerFullControlfornisce diritti tra account diversi per creare oggetti in altri bucket. Se l&#39;utente B carica un oggetto nel bucket dell&#39;utente A, l&#39;utente B &quot;possiede&quot; ancora tale oggetto e, per impostazione predefinita, all&#39;utente A non vengono concesse autorizzazioni per tale oggetto anche se l&#39;utente A è proprietario del bucket. Gli oggetti non ereditano le autorizzazioni dal bucket principale. UserB deve concedere esplicitamente le autorizzazioni userA perché userB è ancora il proprietario dell&#39;oggetto. Per questo caricamento tra account diversi, AWS fornisce un ACL BucketOwnerFullControl specificando che l&#39;uso di questo ACL da parte del proprietario del bucket (userA) e dispone delle autorizzazioni complete per l&#39;oggetto (lettura, scrittura, eliminazione, ecc.), anche se l&#39;oggetto è &quot;posseduto&quot; da userB.

## Errori di trasferimento {#section_4BD44E9167F0494FB2B379D2BA132AD8}

In caso di errore di trasferimento FTP (accesso negato, connessione persa, fuori quota, ecc.), Adobe tenta di connettersi e inviare automaticamente i dati fino a tre volte separate. Se gli errori persistono, il feed viene contrassegnato come non riuscito e viene inviata una notifica e-mail.

In caso di errore di trasferimento, è possibile eseguire nuovamente un processo fino a quando non ha esito positivo.

## Opzioni di invio {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Dopo aver verificato/corretto il problema di consegna, esegui nuovamente il processo per ottenere i file.

## L’impatto del risparmio giornaliero sui feed di dati orari {#section_70E867D942054DD09048E027A9474FFD}

Per alcuni fusi orari l&#39;ora cambierà due volte all&#39;anno a causa delle definizioni dell&#39;ora legale (DST). I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario per la suite di rapporti non utilizza DST, la consegna dei file continuerà normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è quello che utilizza DST, la consegna dei file verrà modificata per l’ora in cui si verifica la modifica dell’ora (di solito 2:00).

Quando si eseguono transizioni di tempo STD -> DST (&quot;Primavera avanti&quot;), il cliente otterrà solo 23 file. L’ora saltata nella transizione DST viene semplicemente omessa. Ad esempio, se la transizione si verifica alle 2 del mattino, riceveranno un file per l’1:00 ore e riceveranno un file per le 3:00 ore. Non ci sarà alcun file 2:00, dato che alle 2:00 STD, diventa 3:00 DST.

Quando si eseguono transizioni DST -> STD, (&quot;Fall Back&quot;), il cliente riceverà 24 file. Tuttavia, l’ora della transizione includerà in realtà dati del valore di 2 ore. Ad esempio, se la transizione si verifica alle 2:00, il file per 1:00 verrà ritardato di un&#39;ora, ma conterrà dati per due ore. Conterrà dati da 1:00 DST a 2:00 STD (che sarebbe stato 3:00 DST). Il file successivo inizierà alle 2:00 STD.

## Nessun dato per un periodo di tempo {#section_72510794694D42A9A75C966B812AEB0F}

Facoltativamente, puoi configurare un feed di dati per consegnare un file manifesto se non vengono raccolti dati per un periodo specifico. Se abiliti questa opzione, riceverai un file manifesto simile al seguente:

```text
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## Nessuna informazione di dominio per la generazione di rapporti sul dominio {#section_B7508D65370442C7A314EAED711A2C75}

Alcuni gestori di dispositivi mobili (come T-Mobile e O1) non forniscono più informazioni di dominio per le ricerche DNS inverse. Pertanto, tali dati non sono disponibili per la generazione di rapporti sul dominio.

## Panoramica sull&#39;elaborazione dei dati {#section_6346328F8D8848A7B81474229481D404}

Prima di elaborare i dati su base oraria o giornaliera, i feed di dati attendono che tutti gli hit che hanno inserito la raccolta dati entro l’intervallo di tempo (giorno o ora) siano stati scritti in data warehouse. In seguito, i feed di dati raccolgono i dati con marche temporali che rientrano nell’intervallo temporale, li comprime e li invia tramite FTP. Per i feed orari, in genere i file vengono scritti in data warehouse entro 15-30 minuti dopo l&#39;ora, ma non esiste un periodo di tempo impostato. Se non vi erano dati con marche temporali che rientrano nell’intervallo temporale, il processo prova nuovamente l’intervallo temporale successivo. Il processo di feed dati corrente utilizza il campo `date_time` per determinare quali hit appartengono all’ora. Questo campo è basato sul fuso orario della suite di rapporti.

## Formati di feed di dati &quot;Ogni ora&quot; e &quot;Giornaliero&quot;

Per i dati che hanno più di 7 giorni, i file &quot;Ogni ora&quot; di un giorno vengono combinati in un unico file &quot;Giornaliero&quot;.

Esempio: Il 9 marzo 2021 è stato creato un nuovo feed di dati e i dati dal 1° gennaio 2021 al 9 marzo vengono consegnati come &quot;Orario&quot;. Tuttavia, i file &quot;Ogni ora&quot; prima del 2 marzo 2021 sono combinati in un unico file &quot;Giornaliero&quot;. Puoi estrarre i file &quot;Ogni ora&quot; solo dai dati che hanno meno di 7 giorni dalla data di creazione. In questo caso, dal 2 marzo al 9 marzo.