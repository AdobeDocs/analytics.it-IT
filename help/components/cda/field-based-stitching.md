---
title: Cuciture basate sul campo
description: Comprendere i prerequisiti e i limiti dell'unione dei dati mediante l'unione basata sui campi.
translation-type: tm+mt
source-git-commit: 2e7ec3b2e4401b02005b3099dae2bb34c64a6846
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 0%

---


# Cuciture basate sul campo

Tra dispositivi  Analytics fornisce due metodi distinti per unire i dati. Questo metodo si basa su una  variabile Analytics, ad esempio [prop](/help/implement/vars/page-vars/prop.md) o [eVar](/help/implement/vars/page-vars/evar.md), per contenere un identificatore di persona. Questa variabile viene utilizzata come base per collegare tra loro i dispositivi.

## Prerequisiti specifici per l&#39;unione basata sul campo

Se intendete implementare  Analytics cross-Device utilizzando l&#39;unione basata sul campo, sono necessari i seguenti requisiti. Collaborate con i team all&#39;interno dell&#39;organizzazione e con l&#39;Account Manager Adobe per assicurarvi di soddisfare tutti i requisiti indicati di seguito.

>[!IMPORTANT] Se non vengono soddisfatti tutti i prerequisiti, potrebbe non essere possibile abilitare l&#39; di Analytics tra dispositivi diversi o risultati negativi durante l&#39;unione dei dati.

* Tutti i prerequisiti elencati nella pagina [](overview.md)della panoramica.
* L&#39;implementazione deve impostare una prop o eVar che identifichi in modo univoco un individuo quando possibile, ad esempio quando un utente accede o apre un&#39;e-mail. Questo requisito si applica a tutte le piattaforme, comprese le app mobili se utilizzate. Comunicate la variabile di identificazione desiderata al vostro Account Manager quando viene eseguito il provisioning per l&#39;unione basata su campo.

## Limitazioni specifiche per la cucitura basata sul campo

* Le cuciture basate sui campi funzionano meglio sulle suite di rapporti con un elevato tasso di identificazione dell&#39;utente. Se la suite di rapporti ha una bassa percentuale di identificazione o di accesso, puoi usare il grafico [](device-graph.md)Co-op.

## Passaggi successivi

Una volta che l&#39;organizzazione soddisfa tutti i requisiti e ha compreso i limiti, puoi avviare la [configurazione di cross-device  Analytics](setup.md).