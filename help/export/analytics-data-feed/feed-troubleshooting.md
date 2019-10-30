---
description: Questa sezione contiene informazioni su problemi comuni.
keywords: Feed dati;risoluzione dei problemi
seo-description: Questa sezione contiene informazioni su problemi comuni.
seo-title: Risoluzione dei problemi dei feed dati
solution: Analytics
title: Risoluzione dei problemi dei feed dati
uuid: 4be981ab-3a61-4099-9b0d-785d2ac2492a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Risoluzione dei problemi dei feed dati

Questa sezione contiene informazioni su problemi comuni.

## Errore durante il salvataggio del feed {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

I nomi dei file dei feed di dati sono costituiti dall’ID suite di rapporti e dalla data. I due feed configurati per lo stesso RSID e le stesse date avranno lo stesso nome file. Se tali feed vengono inviati nella stessa posizione, un file ne sovrascrive l’altro. Per impedire la sovrascrittura di un file, non potete creare un feed che possa sovrascrivere un feed esistente nella stessa posizione.

Se si tenta di creare un feed quando ne esiste un altro con lo stesso nome file, viene visualizzato il messaggio seguente:

Se ricevete questo errore, considerate le seguenti soluzioni:

* Modificare il percorso di consegna
* Se possibile, modificare le date
* Se possibile, modificate la suite di rapporti

## Impostazione BucketOwnerFullControl per feed di dati Amazon S3 {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Il caso d'uso comune per Amazon S3 è che il proprietario dell'account Amazon Web Services (AWS) crea un bucket, quindi crea un utente che dispone dell'autorizzazione per creare oggetti in quel bucket e quindi fornisce le credenziali per quell'utente. In questo caso, gli oggetti di un utente appartengono allo stesso account e il proprietario dell'account ha implicitamente il controllo completo dell'oggetto (lettura, eliminazione, ecc.). È simile al funzionamento della consegna FTP.

AWS consente inoltre a un utente di creare oggetti in un bucket che appartengono a un account utente completamente diverso. Ad esempio, se due utenti AWS, userA e userB, non appartengono allo stesso account AWS ma desiderano creare oggetti in altri bucket. Se userA crea un bucket, ad esempio bucketA, può creare un criterio bucket che consente esplicitamente a userB di creare oggetti nel bucketA anche se l'utente non possiede il bucket. Ciò può essere vantaggioso perché non richiede che l'utente A e l'utente B scambiino le credenziali. Al contrario, userB fornisce all'utenteA il relativo numero di account, e userA crea un criterio fisso che sostanzialmente dice "lascia che userB crei oggetti nel bucketA".

**BucketOwnerFullControl** fornisce diritti a più account per creare oggetti in altri bucket. Se userB carica un oggetto nel bucket dell'utenteA, userB "possiede" tale oggetto e, per impostazione predefinita, all'utenteA non vengono concesse autorizzazioni per tale oggetto anche se l'utenteA possiede il bucket; gli oggetti non ereditano le autorizzazioni dal bucket principale. UserB deve concedere esplicitamente a userA autorizzazioni perché userB è ancora il proprietario dell'oggetto. Per questo caricamento tra account, AWS fornisce un ACL BucketOwnerFullControl specificando che l'utilizzo di questo ACL da parte del proprietario del bucket (userA) e gli viene concessa l'autorizzazione completa all'oggetto (lettura, scrittura, eliminazione, ecc.), anche se l'oggetto è "di proprietà" di userB.

## Errori di trasferimento {#section_4BD44E9167F0494FB2B379D2BA132AD8}

In caso di errore nel trasferimento FTP (accesso negato, connessione persa, fuori quota, ecc.), Adobe tenta di collegare e inviare automaticamente i dati fino a tre volte. Se gli errori persistono, il feed viene contrassegnato come non riuscito e viene inviata una notifica e-mail.

In caso di mancata riuscita del trasferimento, è possibile [ripetere un processo](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) finché non riesce.

## Ripeti opzioni {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Dopo aver verificato/corretto il problema di consegna, eseguite nuovamente il [processo](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) per ottenere i file.

## L'impatto del risparmio giornaliero sui feed di dati orari {#section_70E867D942054DD09048E027A9474FFD}

Per alcuni fusi orari l'ora cambierà due volte all'anno a causa delle definizioni DST (daylight save time, ora legale). I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario della suite di rapporti non utilizza DST, la consegna dei file continuerà normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è uno che utilizza DST, la consegna dei file verrà modificata per l'ora in cui si verifica la modifica dell'ora (in genere 2:00).

Quando si effettuano transizioni di tempo STD -&gt; DST ("Spring Forward"), il cliente riceve solo 23 file. L'ora saltata nella transizione DST viene semplicemente omessa. Ad esempio, se la transizione si verifica alle 2 del mattino, riceveranno un file per 1:00 ora e riceveranno un file per 3:00 ore. Non ci sarà un file 2:00, poiché alle 2:00 STD, diventa 3:00 DST.

Quando si creano transizioni DST -&gt; STD, ("Autunno Indietro"), il cliente riceve 24 file. Tuttavia, l'ora della transizione includerà in realtà due ore di dati. Ad esempio, se la transizione si verifica alle 2:00 del mattino, il file per 1:00 verrà ritardato di un'ora, ma conterrà dati per due ore. Conterrà dati da 1:00 DST a 2:00 STD (che sarebbe stato 3:00 DST). Il file successivo inizierà alle 2:00 STD.

## Nessun dato per un periodo di tempo {#section_72510794694D42A9A75C966B812AEB0F}

Facoltativamente, puoi configurare un feed di dati per la distribuzione di un file manifesto se non vengono raccolti dati per un periodo specifico. Se attivate questa opzione, riceverete un file manifesto simile al seguente:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## Nessuna informazione di dominio per il reporting del dominio {#section_B7508D65370442C7A314EAED711A2C75}

  Alcuni gestori di dispositivi mobili (come T-Mobile e O1) non forniscono più informazioni di dominio per le ricerche DNS inverse. Pertanto, tali dati non sono disponibili per la generazione di rapporti sul dominio.

## Panoramica sull'elaborazione dei dati {#section_6346328F8D8848A7B81474229481D404}

Prima di elaborare i dati su base oraria o giornaliera, i feed di dati attendono che tutti gli hit che hanno immesso la raccolta dati entro il periodo di tempo (giorno o ora) siano stati scritti in data warehouse. In seguito, i feed di dati raccolgono i dati con marche temporali che rientrano nel periodo di tempo, li comprime e li invia tramite FTP. Per i feed orari, i file vengono generalmente scritti in data warehouse entro 15-30 minuti dopo l'ora, ma non esiste un periodo di tempo impostato. Se non vi erano dati con marche temporali che rientrano nell’intervallo temporale, il processo tenta nuovamente l’intervallo temporale successivo. Il processo di feed di dati corrente utilizza il `date_time` campo per determinare quali hit appartengono all’ora. Questo campo è basato sul fuso orario della suite di rapporti.
