---
description: L'interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.
seo-description: L'interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.
seo-title: Supporto VRS in Mobile Services
title: Supporto VRS in Mobile Services
uuid: 1 b 11279 e-d 0 d 8-48 c 5-a 5 b 5-8020 d 5 ed 39 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Supporto VRS in Mobile Services

L'interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.

## VRS support in Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

L'interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.

Adobe Mobile Services supporta suite di rapporti virtuali. Tuttavia, se pianificate di creare una suite di rapporti virtuale con più app e pianificate di eseguire un'attività di messaggistica, dovete specificare il singolo App-ID come parametro. Se stai creando un messaggio push, l'App-ID deve essere uno dei parametri del segmento in uso. Se state creando un messaggio in-app, l'App-ID deve essere uno dei parametri delle Caratteristiche stabilite per il messaggio. Se questo non viene fatto, il messaggio verrà inviato/attivato a tutti gli utenti in tutte le app che soddisfano i criteri di segmento/attivazione.

For more details, see [Virtual Report Suites](https://marketing.adobe.com/resources/help/en_US/mobile/c_mob_vrs.html)in the Adobe Mobile Services documentation.
