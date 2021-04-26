---
title: Configurare Analytics tra dispositivi
description: Configura una suite di rapporti virtuale per abilitare CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
translation-type: tm+mt
source-git-commit: 005cb590f4f7d31d3de801437a0ba6fa25b2ea64
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 2%

---

# Configurare Analytics tra dispositivi

Una volta soddisfatti tutti i prerequisiti, utilizza i seguenti passaggi per abilitare Cross-Device Analytics. Devi appartenere a un gruppo di amministrazione del profilo di prodotto o disporre dei privilegi di amministratore in Adobe Analytics per seguire questi passaggi.

>[!IMPORTANT]
>
>Tutti i prerequisiti devono essere soddisfatti prima di seguire questi passaggi. Se non vengono soddisfatti tutti i prerequisiti, la funzione non è disponibile o non funzionerà. Per prerequisiti e limitazioni, consulta la [pagina di panoramica](overview.md) e il metodo di unione desiderato ([Unione basata sui campi](field-based-stitching.md) o [Grafico dispositivo](device-graph.md), rispettivamente.

## Apri un ticket con l’Assistenza clienti per effettuare il provisioning di CDA nella tua suite di rapporti per dispositivi diversi

Il provisioning di CDA nella suite di rapporti per più dispositivi è fornito dall’ingegneria Adobe. Per avviare questo processo, contatta l’Assistenza clienti e preparati a fornire le seguenti informazioni:

* Il tuo ID organizzazione Adobe Experience Cloud (una stringa alfanumerica che termina con @AdobeOrg)
* ID suite di rapporti per la suite di rapporti multi-dispositivo che desideri abilitare con CDA
* Quale metodo di CDA vuoi utilizzare (unione basata sul campo, grafico privato Adobe o grafico cooperativo Adobe)
* Se si intende utilizzare un&#39;unione basata sui campi, la proprietà o l&#39;eVar che contiene l&#39;ID utente
* Preferisci frequenza di riproduzione e lunghezza di lookback. Le opzioni includono una riproduzione una volta alla settimana con un intervallo di lookback di 7 giorni o una riproduzione giornaliera con un intervallo di lookback di 1 giorno.

Una volta che avrai fornito queste informazioni all’Assistenza clienti, questi collaboreranno con Adobe Engineering per abilitare la suite di rapporti selezionata per l’elaborazione CDA.

## Creare una suite di rapporti virtuali per più dispositivi per visualizzare la visualizzazione su più dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Passa a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e accedi utilizzando le credenziali AdobeID.
2. Fai clic sull’icona a 9 griglia in alto, quindi fai clic su Analytics.
3. Passa il puntatore del mouse su Componenti nella parte superiore, quindi fai clic su Suite di rapporti virtuali.
4. Fai clic su Aggiungi.
5. Immetti un nome per la suite di rapporti virtuali e accertati che la suite di rapporti abilitata per CDA sia selezionata.
6. (Facoltativo) Applica un segmento alla suite di rapporti virtuale. Ad esempio, puoi applicare un segmento che limita la suite di rapporti virtuali alle date successive all’attivazione di CDA e all’inizio della cucitura. Questo segmento consente agli utenti di visualizzare solo intervalli di date uniti all’interno della VRS.
7. Fai clic sulla casella di controllo &quot;Abilita elaborazione al momento del rapporto&quot;, che abilita diverse altre opzioni, tra cui Analisi multidispositivo.
8. Fai clic sulla casella di controllo &quot;Unisci visite utente tra dispositivi&quot;.
9. Fai clic su Continua, completa la configurazione della suite di rapporti virtuali, quindi fai clic su Salva.

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali su più dispositivi

Quando Analytics tra dispositivi è abilitato su una suite di rapporti virtuali, tieni presente le seguenti modifiche:

* Accanto al nome della suite di rapporti virtuali viene visualizzata una nuova icona per più dispositivi. Questa icona è esclusiva per le suite di rapporti virtuali su più dispositivi.
* È disponibile una nuova dimensione con etichetta [Stato identificato](../dimensions/identified-state.md). Questa dimensione determina se l&#39;ID Experience Cloud sull&#39;hit è noto dal grafico del dispositivo in quel momento.
* Sono disponibili nuove metriche etichettate [Persone](../metrics/people.md) e [Dispositivi univoci](../metrics/unique-devices.md) .
* La metrica [Visitatori unici](../metrics/unique-visitors.md) non è disponibile, in quanto viene sostituita con &quot;Persone&quot; e &quot;Dispositivi unici&quot;.
* Quando crei segmenti, il contenitore del segmento &quot;Visitatore&quot; viene sostituito da un contenitore &quot;Persona&quot;.
