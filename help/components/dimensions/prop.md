---
title: Prop
description: Una dimensione personalizzata che potete utilizzare nel reporting.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---


# Prop

*Questa pagina della guida descrive il funzionamento dei prop come una dimensione. Per informazioni su come implementare i prop, vedete[prop](/help/implement/vars/page-vars/prop.md)nella guida per l&#39;utente Implementa.*

Le proprietà sono variabili personalizzate che potete utilizzare come desiderate. Non persistono oltre il risultato raggiunto.

> [!TIP] Nella maggior parte dei casi, Adobe consiglia di utilizzare [le eVar](evar.md) . Nelle versioni precedenti di Adobe Analytics, le proprietà e le eVar presentavano vantaggi e svantaggi l&#39;una per l&#39;altra. Tuttavia, Adobe ha migliorato le eVar dove soddisfano quasi tutti i casi di utilizzo per le prop.

Se disponete di un documento [di progettazione di una](/help/implement/prepare/solution-design.md)soluzione, potete allocare queste dimensioni personalizzate a valori specifici dell&#39;organizzazione. Il numero di proprietà disponibili dipende dal contratto con Adobe. Se il contratto con Adobe lo supporta, sono disponibili fino a 75 proprietà.

## Compilare prop con i dati

Ogni prop raccoglie i dati dalla stringa [`c1` - `c75` query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il parametro della stringa di `c1` query raccoglie i dati per prop1, mentre il parametro della stringa di `c68` query raccoglie i dati per prop68.

AppMeasurement, che compila le variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `prop1` - `prop75`. Per le linee guida per l’implementazione, consulta [le informazioni di base](/help/implement/vars/page-vars/prop.md) nella guida Implementa.

## Valori dimensione

Poiché i prop contengono stringhe personalizzate nella vostra implementazione, la vostra organizzazione determina quali valori di dimensione sono per ogni prop. Accertatevi di registrare lo scopo di ogni prop e i valori dimensionali tipici in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.

## Valore delle proprietà sulle eVar

Nella maggior parte dei casi, Adobe consiglia di utilizzare le eVar. Eccezioni a questa istruzione:

* Potete utilizzare le proprietà nei rapporti in tempo reale. Le eVar impiegano almeno 30 minuti per essere visualizzate nel reporting.
* Le proprietà possono diventare proprietà elenco, che accettano più valori nello stesso hit. Le variabili elenco sono separate e sono disponibili solo tre variabili elenco.
* Quando attivi il percorso su una prop, diventano immediatamente disponibili le dimensioni [Entry](entry-dimensions.md) ed [Exit](exit-dimensions.md) . Se desiderate dimensioni di entrata e uscita per le eVar, potete creare manualmente un segmento.

Consulta [eVar](evar.md) per ulteriori confronti tra prop ed eVar.
