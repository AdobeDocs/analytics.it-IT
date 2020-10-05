---
title: Configurare l'analisi tra dispositivi
description: Configurare una suite di rapporti virtuale per abilitare CDA.
translation-type: tm+mt
source-git-commit: 60fe85adaebee8ca390e59727dda949c12c1ee26
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---


# Configurare l&#39;analisi tra dispositivi

Una volta soddisfatti tutti i prerequisiti, attenetevi alla seguente procedura per abilitare l&#39;analisi tra dispositivi. Per seguire questa procedura, devi appartenere a un gruppo Amministratore profilo di prodotto o avere privilegi di amministratore in  Adobe Analytics.

>[!IMPORTANT]
>
>Tutti i prerequisiti devono essere soddisfatti prima di seguire questi passaggi. Se tutti i prerequisiti non sono soddisfatti, la funzione non è disponibile o non funziona. Per prerequisiti e limitazioni, consultate la pagina [della](overview.md) panoramica e il metodo di cucitura desiderato (rispettivamente cuciture[basate su](field-based-stitching.md) campo o grafico [](device-graph.md)Dispositivo).

## Scegliete la suite di rapporti per più dispositivi che verrà abilitata per CDA

Quando l’organizzazione dispone del provisioning per l’utilizzo di CDA, potete scegliere quale suite di rapporti utilizzare. Questa scelta può essere comunicata tramite l&#39;Account Manager  Adobe.  Adobe consente quindi la suite di rapporti selezionata per l&#39;elaborazione CDA.

## Creare una suite di rapporti virtuali per dispositivi diversi per visualizzare la visualizzazione su più dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Andate a [experience.adobe.com](https://experiencecloud.adobe.com) ed effettuate l&#39;accesso utilizzando le credenziali AdobeID.
2. Fate clic sull&#39;icona a 9 griglie nella parte superiore, quindi fate clic su Analytics.
3. Passa il cursore del mouse sui componenti in alto, quindi fai clic su Suite di rapporti virtuale.
4. Fai clic su Aggiungi.
5. Immettete un nome per la suite di rapporti virtuali e accertatevi che sia selezionata la suite di rapporti abilitata per CDA.
6. (Facoltativo) Applicare un segmento alla suite di rapporti virtuali. Ad esempio, puoi applicare un segmento che limita la suite di rapporti virtuali alle date successive all&#39;attivazione di CDA e all&#39;inizio della cucitura. Questo segmento consente agli utenti di visualizzare solo gli intervalli di date cuciti all&#39;interno della VRS.
7. Fate clic sulla casella di controllo &quot;Abilita elaborazione tempo rapporto&quot; per abilitare diverse opzioni, tra cui Analisi multi-dispositivo.
8. Fate clic sulla casella di controllo &quot;Stitch User Visits Between Devices&quot; (Stitch Visite utente tra dispositivi).
9. Fate clic su Continue (Continua), completate la configurazione della suite di rapporti virtuali, quindi fate clic su Save (Salva).

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali su più dispositivi

Quando Analytics cross-device è abilitato su una suite di rapporti virtuale, prendi nota delle seguenti modifiche:

* Accanto al nome della suite di rapporti virtuale viene visualizzata una nuova icona cross-device. Questa icona è esclusiva per le suite di rapporti virtuali su più dispositivi.
* È disponibile una nuova dimensione con etichetta Stato [](../dimensions/identified-state.md) identificato. Questa dimensione determina se l&#39;ID Experience Cloud  sull&#39;hit è noto dal grafico del dispositivo in quel momento.
* Sono disponibili nuove metriche con etichetta [Persone](../metrics/people.md) e Dispositivi [](../metrics/unique-devices.md) univoci.
* La metrica Visitatori [](../metrics/unique-visitors.md) unici non è disponibile, in quanto viene sostituita con &#39;Persone&#39; e &#39;Dispositivi univoci&#39;.
* Durante la creazione di segmenti, il contenitore del segmento &quot;Visitatore&quot; viene sostituito con un contenitore &quot;Persona&quot;.
