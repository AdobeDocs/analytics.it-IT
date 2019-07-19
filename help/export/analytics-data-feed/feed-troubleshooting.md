---
description: Questa sezione contiene informazioni sui problemi più comuni.
keywords: Feed dati; risoluzione dei problemi
seo-description: Questa sezione contiene informazioni sui problemi più comuni.
seo-title: Risoluzione dei problemi dei feed di dati
solution: Analytics
title: Risoluzione dei problemi dei feed di dati
uuid: 4 be 981 ab -3 a 61-4099-9 b 0 d -785 d 2 ac 2492 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Risoluzione dei problemi dei feed di dati

Questa sezione contiene informazioni sui problemi più comuni.

## Error When Saving Feed {#section_EF38BB51A7E240D69DAD4C07A34D9AD5}

I nomi dei file di feed dati sono composti dall'ID suite di rapporti e dalla data. Tutti i due feed configurati per lo stesso RSID e le date avranno lo stesso nome file. Se tali feed vengono consegnati alla stessa posizione, un file sovrascrive l'altro. Per evitare la sovrascrittura di un file, non potete creare un feed che abbia il rischio di sovrascrivere un feed esistente nella stessa posizione.

Se si tenta di creare un feed quando un altro esiste con lo stesso nome file, viene visualizzato il seguente messaggio:

Se ricevi questo errore, prendi in considerazione le seguenti soluzioni:

* Modifica del percorso di consegna
* Modifica delle date se possibile
* Se possibile, cambia la suite di rapporti

## BucketOwnerFullControl setting for Amazon S3 data feeds {#section_6797EBBB7E6D44D4B00C7AEDF4C2EE1D}

Il caso d'uso comune per Amazon S 3 è che il proprietario dell'account Amazon Web Services (AWS) crea un bucket, quindi crea un utente con autorizzazione per creare gli oggetti in quel bucket e quindi fornisce le credenziali per quell'utente. In questo caso, gli oggetti di un utente appartengono allo stesso account e il proprietario dell'account ha in modo implicito il controllo completo dell'oggetto (lettura, eliminazione, ecc.). Questo è simile a quello della distribuzione FTP.

AWS consente inoltre a un utente di creare oggetti in un bucket che appartiene a un account utente completamente diverso. Ad esempio, se due utenti AWS, usire e userb non appartengono allo stesso account AWS, ma vogliono creare oggetti in altri bucket. Se usircrea un bucket, ad esempio bucketa, può creare un criterio bucket che consente esplicitamente a userb di creare oggetti in bucketa anche se l'utente non possiede il bucket. Ciò può risultare vantaggioso perché non richiede che usire userb scambiare le credenziali. Userb fornisce usera con il proprio numero account, mentre usircrea una policy bucket che sostanzialmente dice "Abilitare gli oggetti in bucketa".

**Bucketownerfullcontrol** fornisce diritti incrociati per creare oggetti in altri bucket. Se userb carica un oggetto nel bucket di usir, userb continua a «proprietario» dell'oggetto e, per impostazione predefinita, uai non concede alcuna autorizzazione a quell'oggetto persino se uscratch possiede il bucket: gli oggetti non ereditano le autorizzazioni dal bucket principale. Userb deve concedere esplicitamente le autorizzazioni usira perché userb è ancora il proprietario dell'oggetto. Per questo caricamento tra account, AWS fornisce un ACL bucketownerfullcontrol specificando che l'uso di questo ACL è eseguito dal proprietario dell'intervallo (uscratch) e dispone di autorizzazioni complete per l'oggetto (lettura, scrittura, eliminazione ecc.), anche se l'oggetto è "owned" da userb.

## Transfer Failures {#section_4BD44E9167F0494FB2B379D2BA132AD8}

Nel caso di un errore di trasferimento FTP (accesso negato, perso, perdita di quota, ecc.), Adobe tenta di connettersi automaticamente e inviare i dati fino a tre orari separati. Se gli errori persistono, il feed viene contrassegnato come non riuscito e viene inviata una notifica e-mail.

In case of a transfer failure, you can [rerun a job](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) until it succeeds.

## Resend Options {#section_BFD4447B0B5946CAAEE4F0F03D42EDFD}

Once you have verified/corrected the delivery issue, just use [rerun the job](../../export/analytics-data-feed/c-df-jobs/t-job-rerun.md#task_FF9CD08685944E1EBB0CCA02F581C501) to get the files.

## Daylight Savings impact on Hourly Data Feeds {#section_70E867D942054DD09048E027A9474FFD}

Per determinate fusi orari l'ora cambia due volte all'anno a causa delle definizioni ora legale (DST). I feed di dati rispettano il fuso orario per il quale è configurata la suite di rapporti. Se il fuso orario per la suite di rapporti non utilizza DST, la consegna dei file continuerà normalmente come qualsiasi altro giorno. Se il fuso orario della suite di rapporti è uno che utilizza DST, la consegna dei file verrà modificata per l'ora in cui si verifica la modifica temporale (in genere 2:00 am).

Quando si effettuano transizioni STD -&gt; transizioni ora DST («Spring Forward»), il cliente ottiene solo 23 file. L'ora saltata nella transizione DST viene semplicemente omessa. Ad esempio, se la transizione si verifica alle 1:00, verrà visualizzato un file per 3:00 ora e sarà possibile ottenere un file per ora. Non ci sarà alcun file 2:00, poiché alle 2:00 STD diventa 3:00 DST.

Quando si creano DST -&gt; transizioni STD ("Fall Back"), il cliente riceve 24 file. Tuttavia, l'ora della transizione includerà in realtà 2 ore di dati. Ad esempio, se la transizione avviene alle 2:00, il file per 1:00 verrà ritardato di un'ora, ma conterrà dati per due ore. Conterrà dati da 1:00 DST a 2:00 STD (che sarebbero state 3:00 DST). Il file successivo inizierà da 2:00 STD.

## No Data for a Time Period {#section_72510794694D42A9A75C966B812AEB0F}

Facoltativamente, puoi configurare un feed di dati per distribuire un file manifesto se non vengono raccolti dati per un periodo specifico. Se abilitate questa opzione, riceverete un file manifesto simile a quanto segue:

```
Datafeed-Manifest-Version: 1.0
 Lookup-Files: 0
 Data-Files: 0
 Total-Records: 0
```

## No Domain Info for Domain Reporting {#section_B7508D65370442C7A314EAED711A2C75}

Alcuni operatori mobili (come T-Mobile e O 1) non forniscono più informazioni di dominio per le ricerche inverso DNS. Pertanto, i dati non sono disponibili per i rapporti sul dominio.

## Data Processing Overview {#section_6346328F8D8848A7B81474229481D404}

Prima di elaborare dati orari o giornalieri, i feed di dati attendono che tutti gli hit che immettono la raccolta dati entro il periodo temporale (giorno o ora) siano stati scritti in data warehouse. Dopo che ciò si verifica, i feed dati raccolgono i dati con marca temporale che rientrano nell'intervallo temporale, lo comprime e lo invia tramite FTP. Per i feed orari, i file vengono generalmente scritti al data warehouse entro 15-30 minuti dopo l'ora, ma non è impostato alcun periodo di tempo. Se non sono presenti dati con marche temporali che rientrano nella cornice temporale, il processo ripete il periodo temporale successivo. The current data feed process uses the `date_time` field to determine which hits belong to the hour. Questo campo si basa sul fuso orario della suite di rapporti.
