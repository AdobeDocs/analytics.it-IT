---
title: Configurare Analytics tra dispositivi
description: Configura una suite di rapporti virtuale per abilitare CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
feature: CDA
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 7%

---

# Configurare Analytics tra dispositivi

Una volta soddisfatti tutti i prerequisiti, procedi come segue per abilitare Cross-Device Analytics. Per seguire la procedura riportata di seguito, devi appartenere a un gruppo di amministrazione del profilo di prodotto o disporre dei privilegi di amministratore in Adobe Analytics.

>[!IMPORTANT]
>
>Prima di seguire questi passaggi, è necessario soddisfare tutti i prerequisiti. Se non vengono soddisfatti tutti i prerequisiti, la funzione non è disponibile o non funzionerà. Consulta la [pagina panoramica](overview.md) e il metodo di unione desiderato ([Unione basata sui campi](field-based-stitching.md) o [Device Graph](device-graph.md), rispettivamente) per prerequisiti e limitazioni.

## Apri un ticket con l’Assistenza clienti per richiedere il provisioning di CDA per la suite di rapporti tra dispositivi

Il provisioning di CDA nella suite di rapporti per più dispositivi viene eseguito da tecnici Adobi. Per avviare questo processo, contatta l’Assistenza clienti e preparati a fornire le seguenti informazioni:

* ID organizzazione Adobe Experience Cloud (stringa alfanumerica che termina con @AdobeOrg)
* ID suite di rapporti per la suite di rapporti multi-dispositivo che desideri abilitare con CDA
* Metodo CDA da utilizzare (unione basata sui campi o grafico dei dispositivi di Adobe)
* Se intendi utilizzare l’unione basata sui campi, proprietà o eVar contenente l’ID utente
* Preferenza di ripetizione frequenza e lunghezza del lookback. Le opzioni includono una ripetizione una volta alla settimana con un intervallo di lookback di 7 giorni, o una ripetizione ogni giorno con un intervallo di lookback di 1 giorno.
L’impostazione predefinita è la riproduzione settimanale con intervallo di lookback di 7 giorni. In questo caso, i dati dell’ultima settimana sono soggetti a modifiche (in quanto vengono progressivamente uniti e aggiornati).

Una volta fornite all’Assistenza clienti queste informazioni, collaboreranno con il team di progettazione Adobe per abilitare la suite di rapporti scelta per l’elaborazione CDA.

## Creare una suite di rapporti virtuale per più dispositivi per visualizzare la vista cross-device

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e accedi utilizzando le credenziali Adobe ID.
2. Fai clic sull’icona della griglia a 9 celle in alto, quindi fai clic su Analytics.
3. Passa il puntatore del mouse su Componenti nella parte superiore, quindi fai clic su Suite di rapporti virtuali.
4. Fai clic su Aggiungi.
5. Immetti un nome per la suite di rapporti virtuale e accertati che sia selezionata la suite di rapporti abilitata per CDA.
6. (Facoltativo) Applica un segmento alla suite di rapporti virtuali. Ad esempio, puoi applicare un segmento che limita la suite di rapporti virtuali alle date successive all’attivazione di CDA e all’inizio dell’unione. Questo segmento consente agli utenti di visualizzare solo intervalli di date uniti all’interno della VRS.
7. Fai clic sulla casella di controllo &quot;Abilita elaborazione dei tempi di report&quot;, che abilita diverse altre opzioni, tra cui Cross-Device Analytics.
8. Fai clic sulla casella di controllo &quot;Unisci le visite degli utenti tra i dispositivi&quot;.
9. Fai clic su Continua, completa la configurazione della suite di rapporti virtuali, quindi fai clic su Salva.

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali tra dispositivi

Quando Analytics tra dispositivi è abilitato in una suite di rapporti virtuale, tieni presente le seguenti modifiche:

* Accanto al nome della suite di rapporti virtuali viene visualizzata una nuova icona per più dispositivi. Questa icona è esclusiva per le suite di rapporti virtuali cross-device.
* Una nuova dimensione etichettata [Stato identificato](../dimensions/identified-state.md) è disponibile.
* Nuove metriche etichettate [Persone](../metrics/people.md), [Dispositivi univoci](../metrics/unique-devices.md), [Persone identificate](../metrics/identified-people.md), [Persone non identificate](../metrics/unidentified-people.md), e [Persone con ID Experience Cloud](../metrics/people-with-exp-cloud-id.md) sono disponibili.
* La metrica [Visitatori univoci](../metrics/unique-visitors.md) non è disponibile, in quanto viene sostituito con &quot;Persone&quot; e &quot;Dispositivi univoci&quot;.
* Durante la creazione di segmenti, il contenitore di segmenti &quot;Visitatore&quot; viene sostituito da un contenitore &quot;Persona&quot;.
