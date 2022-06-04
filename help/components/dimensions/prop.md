---
title: Prop
description: Una dimensione personalizzata utilizzabile nel reporting.
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Prop

*Questa pagina di aiuto descrive il funzionamento delle proprietà come dimensione. Per informazioni su come implementare i prop, vedi [proprietà](/help/implement/vars/page-vars/prop.md) nella guida utente Implementa .*

Le proprietà sono variabili personalizzate che puoi utilizzare come desideri. Non persistono oltre il risultato impostato.

>[!TIP]
>
>Adobe consiglia di utilizzare [eVar](evar.md) nella maggior parte dei casi. Nelle versioni precedenti di Adobe Analytics, le proprietà e le eVar presentavano vantaggi e svantaggi l’una per l’altra. Tuttavia, Adobe ha migliorato le eVar in cui soddisfano quasi tutti i casi d’uso per le proprietà.

Se hai [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md), puoi allocare queste dimensioni personalizzate ai valori specifici dell’organizzazione. Il numero di proprietà disponibili dipende dal contratto con Adobe. Sono disponibili fino a 75 proprietà se il contratto con Adobe lo supporta.

## Popolare prop con i dati

Ogni prop raccoglie dati dal [`c1` - `c75` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. Ad esempio, il `c1` il parametro della stringa di query raccoglie i dati per prop1, mentre il `c68` il parametro della stringa query raccoglie i dati per prop68.

AppMeasurement, che compila variabili JavaScript in una richiesta di immagine per la raccolta dei dati, utilizza le variabili `prop1` - `prop75`. Vedi [prop](/help/implement/vars/page-vars/prop.md) nella guida utente Implementa per le linee guida di implementazione.

## Elementi Dimension

Poiché le proprietà contengono stringhe personalizzate nell’implementazione, l’organizzazione determina gli elementi dimensionali per ogni proprietà. Assicurati di registrare lo scopo di ogni prop e degli elementi dimensionali tipici in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

## Sensibilità delle maiuscole

Per impostazione predefinita, le proprietà non sono sensibili all’uso di maiuscole e minuscole. Se invii lo stesso valore in casi diversi (ad esempio, `"DOG"` e `"Dog"`), Analysis Workspace le raggruppa nello stesso elemento dimensione. Viene utilizzato il caso del primo valore rilevato all’inizio del mese di riferimento. Data Warehouse mostra il primo valore rilevato durante il periodo di richiesta.

È possibile fare la distinzione tra maiuscole e minuscole per qualsiasi proprietà. Puoi anche disabilitare la distinzione tra maiuscole e minuscole per qualsiasi proprietà una volta attivato. Contatta l’Assistenza clienti Adobe con l’ID suite di rapporti e le variabili desiderate per attivare o disattivare la distinzione tra maiuscole e minuscole.

>[!WARNING]
>
>L’attivazione della distinzione tra maiuscole e minuscole può causare uno scossone degli elementi dimensionali, risultati imprevisti con i segmenti e problemi con i filtri. L’Adobe consiglia vivamente di scegliere tra due periodi di tempo principali, ad esempio l’inizio di un mese o di un anno.

## Valore delle proprietà su eVar

Nella maggior parte dei casi, Adobe consiglia di utilizzare le eVar. Eccezioni a questa istruzione:

* Puoi utilizzare le proprietà nei rapporti in tempo reale. La visualizzazione delle eVar richiede almeno 30 minuti nel rapporto.
* Le proprietà possono diventare proprietà di elenco, che accettano più valori nello stesso hit. Le variabili elenco sono separate e sono disponibili solo tre variabili elenco.
* Quando si abilita il percorso su un prop, [Voce](entry-dimensions.md) e [Esci](exit-dimensions.md) le dimensioni diventano immediatamente disponibili. Se desideri dimensioni di entrata e uscita per eVar, puoi creare manualmente un segmento.

Vedi [eVar](evar.md) per ulteriori confronti tra prop ed eVar.
