---
title: Configurare Analytics tra dispositivi
description: Configura una suite di rapporti virtuale per abilitare CDA.
exl-id: e6d4e0c2-6b85-4f89-b51f-c0eed7a4e3da
source-git-commit: f7106ca52447988c90a3ccac6a1e1cc7514f1fc9
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 7%

---

# Configurare Analytics tra dispositivi

Una volta soddisfatti tutti i prerequisiti, utilizza i seguenti passaggi per abilitare Cross-Device Analytics. Devi appartenere a un gruppo di amministrazione del profilo di prodotto o disporre dei privilegi di amministratore in Adobe Analytics per seguire questi passaggi.

>[!IMPORTANT]
>
>Tutti i prerequisiti devono essere soddisfatti prima di seguire questi passaggi. Se non vengono soddisfatti tutti i prerequisiti, la funzione non è disponibile o non funzionerà. Consulta la sezione [pagina panoramica](overview.md) e il metodo di cucitura desiderato ([Unione basata sui campi](field-based-stitching.md) o [Grafico dei dispositivi](device-graph.md), rispettivamente) per prerequisiti e limitazioni.

## Apri un ticket con l’Assistenza clienti per effettuare il provisioning di CDA nella tua suite di rapporti per dispositivi diversi

Il provisioning di CDA nella suite di rapporti per più dispositivi è fornito dall’ingegneria Adobe. Per avviare questo processo, contatta l’Assistenza clienti e preparati a fornire le seguenti informazioni:

* Il tuo ID organizzazione Adobe Experience Cloud (una stringa alfanumerica che termina con @AdobeOrg)
* ID suite di rapporti per la suite di rapporti multi-dispositivo che desideri abilitare con CDA
* Quale metodo di CDA utilizzare (unione basata sui campi o grafico dei dispositivi Adobe)
* Se si intende utilizzare un&#39;unione basata sui campi, la proprietà o l&#39;eVar che contiene l&#39;ID utente
* Preferenza di ripetizione frequenza e lunghezza del lookback. Le opzioni includono una ripetizione una volta alla settimana con un intervallo di lookback di 7 giorni, o una ripetizione ogni giorno con un intervallo di lookback di 1 giorno.
Il valore predefinito è la riproduzione settimanale con un intervallo di lookback di 7 giorni. In questo caso, i dati nell’ultima settimana sono soggetti a modifiche (in quanto vengono progressivamente uniti e aggiornati).

Una volta che avrai fornito queste informazioni all’Assistenza clienti, questi collaboreranno con Adobe Engineering per abilitare la suite di rapporti selezionata per l’elaborazione CDA.

## Creare una suite di rapporti virtuali per più dispositivi per visualizzare la visualizzazione su più dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Passa a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) e accedi utilizzando le tue credenziali AdobeID.
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
* Una nuova dimensione etichettata [Stato identificato](../dimensions/identified-state.md) è disponibile.
* Nuove metriche etichettate [Persone](../metrics/people.md), [Dispositivi univoci](../metrics/unique-devices.md), [Persone identificate](../metrics/identified-people.md), [Persone non identificate](../metrics/unidentified-people.md)e [Persone con ID Experience Cloud](../metrics/people-with-exp-cloud-id.md) sono disponibili.
* La metrica [Visitatori unici](../metrics/unique-visitors.md) non è disponibile, in quanto viene sostituito con &quot;Persone&quot; e &quot;Dispositivi univoci&quot;.
* Quando crei segmenti, il contenitore del segmento &quot;Visitatore&quot; viene sostituito da un contenitore &quot;Persona&quot;.
