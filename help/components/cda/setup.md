---
title: Configurare Analytics tra dispositivi
description: Configura una suite di rapporti virtuale per abilitare CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
feature: CDA
role: Admin
source-git-commit: cfa5cc02ba3a7349b51a904f29bab533c0f1c603
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 1%

---

# Configurare Analytics tra dispositivi

{{available-existing-customers}}

Una volta soddisfatti tutti i prerequisiti, procedi come segue per abilitare Cross-Device Analytics. Per seguire la procedura riportata di seguito, devi appartenere a un gruppo di amministrazione del profilo di prodotto o disporre dei privilegi di amministratore in Adobe Analytics.

>[!IMPORTANT]
>
>Prima di seguire questi passaggi, è necessario soddisfare tutti i prerequisiti. Se non vengono soddisfatti tutti i prerequisiti, la funzione non è disponibile o non funzionerà. Consulta la [pagina della panoramica](overview.md) e il metodo di unione desiderato ([Unione basata sui campi](field-based-stitching.md) o [Grafo di dispositivi](device-graph.md), rispettivamente) per conoscere i prerequisiti e le limitazioni.

## 1. Apri un ticket con l’Assistenza clienti per richiedere il provisioning di CDA per la suite di rapporti tra dispositivi

Il provisioning di CDA nella suite di rapporti per più dispositivi viene eseguito da tecnici Adobi. Per avviare questo processo, contatta l’Assistenza clienti e preparati a fornire le seguenti informazioni:

* ID organizzazione Adobe Experience Cloud (stringa alfanumerica che termina con @AdobeOrg)
* ID suite di rapporti per la suite di rapporti multi-dispositivo che desideri abilitare con CDA
* Metodo CDA da utilizzare (unione basata sui campi o grafico dei dispositivi di Adobe)
* Se intendi utilizzare l’unione basata sui campi, proprietà o eVar contenente l’ID utente
* Preferenza di ripetizione frequenza e lunghezza del lookback. Le opzioni includono una ripetizione una volta alla settimana con un intervallo di lookback di 7 giorni, oppure una ripetizione ogni giorno con un intervallo di lookback di 1 giorno.
L’impostazione predefinita è la riproduzione settimanale con intervallo di lookback di 7 giorni. In questo caso, i dati dell’ultima settimana sono soggetti a modifiche (in quanto vengono progressivamente uniti e aggiornati).

Una volta fornite all’Assistenza clienti queste informazioni, collaboreranno con il team di progettazione Adobe per abilitare la suite di rapporti scelta per l’elaborazione CDA.

## 2. Crea una suite di rapporti virtuali tra dispositivi per visualizzare la vista tra dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Passa a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e accedi con le credenziali Adobe ID.
2. Fai clic sull’icona della griglia a 9 celle in alto, quindi fai clic su Analytics.
3. Passa il puntatore del mouse su **[!UICONTROL Components]** nella parte superiore, quindi fai clic su **[!UICONTROL Virtual report suites]**.
4. Fai clic su Aggiungi.
5. Immetti un nome per la suite di rapporti virtuale e accertati che sia selezionata la suite di rapporti abilitata per CDA.
6. (Facoltativo) Applica un segmento alla suite di rapporti virtuali. Ad esempio, puoi applicare un segmento che limita la suite di rapporti virtuali alle date successive all’attivazione di CDA e all’inizio dell’unione. Questo segmento consente agli utenti di visualizzare solo intervalli di date uniti all’interno della suite di rapporti virtuale.
7. Fai clic sulla casella di controllo &quot;Abilita elaborazione dei tempi di report&quot;, che abilita diverse altre opzioni, tra cui Cross-Device Analytics.
8. Fai clic sulla casella di controllo &quot;Unisci le visite degli utenti tra i dispositivi&quot;.
9. Fai clic su Continua, completa la configurazione della suite di rapporti virtuali, quindi fai clic su Salva.

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali tra dispositivi

Quando Analytics tra dispositivi è abilitato in una suite di rapporti virtuale, tieni presente le seguenti modifiche:

* Accanto al nome della suite di rapporti virtuali viene visualizzata una nuova icona per più dispositivi. Questa icona è esclusiva per le suite di rapporti virtuali cross-device.
* È disponibile una nuova dimensione con etichetta [Stato identificato](../dimensions/identified-state.md).
* Sono disponibili nuove metriche con etichetta [Persone](../metrics/people.md), [Dispositivi univoci](../metrics/unique-devices.md), [Persone identificate](../metrics/identified-people.md), [Persone non identificate](../metrics/unidentified-people.md) e [Persone con ID Experience Cloud](../metrics/people-with-exp-cloud-id.md).
* La metrica [Visitatori univoci](../metrics/unique-visitors.md) non è disponibile in quanto è stata sostituita da &quot;Persone&quot; e &quot;Dispositivi univoci&quot;.
* Durante la creazione di segmenti, il contenitore di segmenti &quot;Visitatore&quot; viene sostituito da un contenitore &quot;Persona&quot;.
