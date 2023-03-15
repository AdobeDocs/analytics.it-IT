---
description: L’interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.
title: Supporto VRS in Mobile Services
feature: VRS
exl-id: 3082333a-514d-45c6-9432-da32bd27a2eb
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 6%

---

# Supporto VRS in Mobile Services

L’interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.

## Supporto VRS in Mobile Services {#topic_1D0BABFA64EF42DE9C09B7AA37CACEC5}

L’interfaccia utente di Adobe Mobile Services combina i dati delle app mobili dalle suite di rapporti di Adobe Analytics con la possibilità di inviare notifiche push e generare messaggi in-app.

Adobe Mobile Services supporta suite di rapporti virtuali. Tuttavia, se prevedi di creare una suite di rapporti virtuale con più app e di eseguire un’attività di messaggistica, devi specificare il singolo App-ID come parametro. Se stai creando un messaggio push, l’App-ID deve essere uno dei parametri del segmento che stai utilizzando. Se stai creando un messaggio in-app, l’App-ID deve essere uno dei parametri delle caratteristiche stabilite per il messaggio. In caso contrario, il messaggio verrà inviato/attivato a tutti gli utenti in tutte le app che soddisfano i criteri di segmento/attivazione.

Per ulteriori dettagli, consulta [Suite di rapporti virtuali](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/c-mob-vrs.html) nella documentazione di Adobe Mobile Services.
