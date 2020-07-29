---
title: Prop
description: Una dimensione personalizzata che potete utilizzare nel reporting.
translation-type: tm+mt
source-git-commit: 7c722e361978a3d7517e95c23442b703e7e25270
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---


# Prop

*Questa pagina della guida descrive il funzionamento dei prop come una dimensione. Per informazioni su come implementare i prop, vedete[prop](/help/implement/vars/page-vars/prop.md)nella guida per l&#39;utente Implementa.*

Le proprietà sono variabili personalizzate che potete utilizzare come desiderate. Non persistono oltre il risultato raggiunto.

>[!TIP]
>
> Adobe consiglia di utilizzare [le eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di  Adobe Analytics, le proprietà eVar presentavano vantaggi e svantaggi l&#39;una per l&#39;altra. Tuttavia,  Adobe ha migliorato le eVar dove soddisfano quasi tutti i casi di utilizzo per le prop.

Se disponete di un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione, potete allocare queste dimensioni personalizzate a valori specifici dell&#39;organizzazione. Il numero di proprietà disponibili dipende dal contratto con  Adobe. Sono disponibili fino a 75 proprietà se il contratto con  Adobe lo supporta.

## Compilare prop con i dati

Ogni prop raccoglie i dati dalla stringa [`c1` - `c75` query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di `c1` query raccoglie i dati per prop1, mentre il parametro della stringa di `c68` query raccoglie i dati per prop68.

AppMeasurement, che compila le variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `prop1` - `prop75`. Per le linee guida per l’implementazione, consulta [le informazioni di base](/help/implement/vars/page-vars/prop.md) nella guida Implementa.

## Elementi Dimension

Poiché le proprietà contengono stringhe personalizzate nella vostra implementazione, la vostra organizzazione determina quali elementi dimensione sono per ogni proprietà. Accertatevi di registrare lo scopo di ogni prop ed elementi dimensionali tipici in un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione.

## Sensibilità delle maiuscole

Per impostazione predefinita, le proprietà non supportano la distinzione tra maiuscole e minuscole. Se inviate lo stesso valore in casi diversi (ad esempio `"DOG"` e `"Dog"`),  Analysis Workspace li raggruppa nello stesso elemento dimensione. Viene utilizzato il caso del primo valore visualizzato all&#39;inizio del mese di segnalazione. Data warehouse mostra il primo valore rilevato durante il periodo di richiesta.

Potete fare sì che qualsiasi proprietà faccia distinzione tra maiuscole e minuscole. È inoltre possibile disattivare la distinzione tra maiuscole e minuscole per qualsiasi proprietà una volta attivata. Contatta  Assistenza clienti di Adobe con l’ID suite di rapporti e le variabili desiderate per attivare o disattivare la distinzione tra maiuscole e minuscole.

>[!IMPORTANT]
>
>L&#39;attivazione della sensibilità alle maiuscole può determinare un calo delle dimensioni degli elementi, produrre risultati imprevisti con i segmenti e causare problemi con i filtri.  Adobe consiglia vivamente di alternare questa impostazione tra due periodi di tempo importanti, ad esempio l&#39;inizio di un mese o di un anno.

## Valore delle proprietà sulle eVar

 Adobe consiglia di utilizzare le eVar nella maggior parte dei casi. Eccezioni a questa istruzione:

* Potete utilizzare le proprietà nei rapporti in tempo reale. Le eVar impiegano almeno 30 minuti per essere visualizzate nel reporting.
* Le proprietà possono diventare proprietà elenco, che accettano più valori nello stesso hit. Le variabili elenco sono separate e sono disponibili solo tre variabili elenco.
* Quando attivi il percorso su una prop, diventano immediatamente disponibili le dimensioni [Entry](entry-dimensions.md) ed [Exit](exit-dimensions.md) . Se desiderate dimensioni di entrata e uscita per le eVar, potete creare manualmente un segmento.

Consultate [eVar](evar.md) per ulteriori confronti tra prop ed eVar.
