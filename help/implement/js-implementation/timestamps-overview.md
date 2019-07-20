---
description: Scopri i vantaggi e i vincoli relativi all'impostazione opzionale Marca temporale.
keywords: Implementazione di Analytics
seo-description: Scopri i vantaggi e i vincoli relativi all'impostazione opzionale Marca temporale.
seo-title: Utilizzo della marca temporale opzionale
solution: Analytics
title: Utilizzo della marca temporale opzionale
topic: Sviluppatore e implementazione
uuid: 956 aaa 16-6 ffa -4 b 63-b 022-a 659 f 5143 e 00
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizzo della marca temporale opzionale

Scopri i vantaggi e i vincoli relativi all'impostazione opzionale Marca temporale.

Marca temporale opzionale è l'impostazione predefinita per tutte le nuove suite di rapporti.

* Inserite sia i dati con marca temporale sia quelli privi di marca nella stessa suite per report globale.
* Inviate dati con marca temporale da un app per dispositivo mobile a una suite per report globale.
* Aggiorna le app per utilizzare le marche temporali senza dover creare una nuova suite di rapporti.

>[!NOTE]
>
>Marca temporale opzionale è l'impostazione predefinita per tutte le nuove suite per report generate da un modello Le nuove suite di rapporti copiate da una suite di rapporti esistente erediteranno le impostazioni dall'originale.

See [Timestamps Optional](https://marketing.adobe.com/resources/help/en_US/reference/timestamp-optional.html) for additional setup information.

## Timestamps Optional: Integrating Timestamped and Non-timestamped Data {#section_BF17CB593044462B993FD0D28EA56518}

Utilizzando la funzione opzionale Marca temporale, potete combinare dati non con marca temporale con dati con marca temporale senza la conseguente perdita di dati. I dati offline con marca temporale generata da un dispositivo mobile possono essere combinati con dati live e non con marca temporale da una pagina Web, oppure integrati con dati provenienti da qualsiasi piattaforma mediante una chiamata di marca temporale lato client.

* **Marca temporale.** Client-side timestamp data is captured and sent directly with the device data using client-side timestamp variables: Javascript on a web page, or using a Mobile SDK call ( [!DNL offlineEnabled=true]) in a mobile app.
* **Dati non marca temporale**. Adobe imposta una marca temporale su dati non con marca temporale in una suite di rapporti quando i dati raggiungono i server di raccolta.

![](assets/timestamp_v_non2.png)

Una suite di rapporti può avere una delle seguenti impostazioni di marca temporale:

* Marca temporale non consentita (impostazione di visitorid supportata)
* Marca temporale richiesta (impostazione visitorid non supportata)
* Marca temporale opzionale (impostazione visitorid supportato ma non sugli hit con marca temporale)

## About Timestamps Optional Features {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Marca temporale opzionale consente di integrare e generare report in più suite di rapporti con o senza marca temporale basata sul lato client. Con Marca temporale opzionale potete aggiornare l'app per utilizzare le marche temporali continuando a utilizzare dati senza marca temporale dall'app precedente.

| Nelle precedenti release… | Inoltre… |
|--- |--- |
| Non è stato possibile inviare dati con marca temporale a una suite di rapporti globale senza marca temporale. Di conseguenza, i dati inviati dai dispositivi offline venivano ignorati quando si aggiungeva a una suite di rapporti senza marca temporale. <br/><br/>Di conseguenza, i dati inviati dai dati offline venivano ignorati quando si aggiungeva a una suite di rapporti senza marca temporale. | Quando si aggiornava un'app per raccogliere e utilizzare le marche temporali, si utilizzava una nuova suite di rapporti. <br/>Non è stato possibile salvare nella suite di rapporti esistente o integrare dati esistenti quando si aggiorna l'app per utilizzare le marche temporali. |

**Con Marca temporale opzionale**, potete integrare dati non con marca temporale da un sito Web attivo con dati offline provenienti da dispositivi mobili, oppure aggiornare l'app con marca temporale a un'app con marca temporale. ![](assets/timestamp_v_non6.png)

## Combining Data into a Global Report Suite {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

La combinazione di dati in una suite di rapporti globale può essere eseguita in vari modi, inclusi i tag per più suite, le regole Vista e i file batch importati da fonti offline.

![](assets/timestamp_v_non9.png)

>[!IMPORTANT]
>
>Pianificate attentamente la progettazione per ciascun set di dati componente, in modo che la combinazione abbia senso in una suite di rapporti globale.

## Best Practices when Employing Timestamps {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

Di seguito sono descritte le procedure ottimali e alcuni requisiti e limitazioni di cui tenere a mente l'integrazione con i dati non con marca temporale.

* In generale, le marche temporali per un visitatore o una visita particolare devono essere visualizzate su Adobe nell'ordine cronologico corretto.

   I dati out-of-order possono includere dati in arrivo dall'inizio della raccolta dati offline e hit in arrivo o cali out-of-sync su dispositivi mobili offline. I dati out-of-order possono influenzare in modo negativo i calcoli temporali (ad esempio i valori passati), l'attribuzione (persistenza evar), il numero di visite/visite e i rapporti sui percorsi.

   ![](assets/timestamp_v_non8.png)

* Using timestamps when setting a [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) is not recommended. Può portare a dati out-of-order.

* Le app ibride costituite da un'app (dati con marca temporale e offline) che aprono un browser Web (dati dal vivo senza marca) non devono utilizzare le marche temporali. La generazione di rapporti non è accurata.

   ![](assets/timestamp_v_non.png)

   Inoltre, le app ibride non devono impostare un ID visitatore.
