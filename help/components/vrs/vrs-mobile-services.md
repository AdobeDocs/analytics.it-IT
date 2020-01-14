---
description: L'interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.
title: Supporto VRS in Mobile Services
uuid: 1b11279e-d0d8-48c5-a5b5-8020d5ed39da
translation-type: tm+mt
source-git-commit: 9193a520b13a0717a3383a32b39936f278c49d49

---


# Supporto VRS in Mobile Services

L&#39;interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.

## Supporto VRS in Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

L&#39;interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.

Adobe Mobile Services supporta le suite di rapporti virtuali. Tuttavia, se pianificate di creare una suite di rapporti virtuale con più app e pianificate di eseguire un&#39;attività di messaggistica, dovete specificare il singolo App-ID come parametro. Se stai creando un messaggio push, l&#39;App-ID deve essere uno dei parametri del segmento utilizzato. Se stai creando un messaggio in-app, l&#39;App-ID deve essere uno dei parametri delle caratteristiche stabilite per il messaggio. In caso contrario, il messaggio verrà inviato/attivato a tutti gli utenti di tutte le app che soddisfano i criteri di attivazione/segmento.

Per ulteriori dettagli, consulta Suite di rapporti [virtuali](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/c-mob-vrs.html) nella documentazione di Adobe Mobile Services.
