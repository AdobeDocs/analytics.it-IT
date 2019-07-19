---
description: La convalida accurata dei dati è un processo di confronto dei dati del report con punti dati conosciuti e verificabili.
keywords: Implementazione di Analytics
seo-description: La convalida accurata dei dati è un processo di confronto dei dati del report con punti dati conosciuti e verificabili.
seo-title: Convalida accurata dei dati
solution: Analytics
title: Convalida accurata dei dati
topic: Sviluppatore e implementazione
uuid: 267 f 6 c 61-705 a -41 cf -9 e 09-4 e 2 ce 2331 f 32
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Convalida accurata dei dati

La convalida accurata dei dati è un processo di confronto dei dati del report con punti dati conosciuti e verificabili.

Il processo di convalida deve essere completato dal personale Adobe, preferibilmente da parte del consulente Adobe (la persona più familiare ai dettagli di implementazione tecnica).

I punti dati preferiti per questa convalida sono elencati come segue:

* (Siti Econversion) Confronto degli ordini di edizione per un giorno unico.
* Confronto degli eventi di successo noti, soprattutto quelli registrati in cui l'indirizzo IP e le altre informazioni sul browser memorizzate in genere nei registri del server Web possono essere confrontati con i dati raccolti.
* Confronto delle visualizzazioni di pagina.

>[!NOTE]
>
>Default pages, such as [!DNL index.html], often receive automated or monitoring traffic. Queste pagine rappresentano una differenza maggiore per la raccolta dati basata su browser rispetto ad altre pagine visitate.

Tutti e tre i tipi di convalida richiedono un registro di debug o un feed di dati per il periodo di tempo in questione. In genere si tratta di un giorno o meno.

È previsto che ordini o eventi di successo possano essere misurati entro il 2-3 % dei valori effettivi (a volte raggiungendo livelli di precisione più alti) utilizzando implementazioni basate su javascript standard. Si tratta di una pagina SSL, poiché le pagine SSL vengono memorizzate nella cache molto meno frequente e per definizione non devono essere memorizzate nella cache. Un'implementazione con richieste di immagini lato server su una pagina SSL deve essere compresa intorno al 0-1 % dei valori effettivi. Le pagine non sicure possono rilevare differenze più elevate, ma comunque entro il 5% dei valori effettivi.

Quando si confrontano le visualizzazioni di pagina per un singolo periodo di tempo, si prevede che le visualizzazioni delle pagine possono essere contate entro il 5% dei valori effettivi, senza includere monitoraggio (come Keynote o whatsupgold) o traffico automatizzato (spider, bot e script).

I confronti con precisione dati devono prendere in considerazione i seguenti elementi:

* QA o altri tipi di test interni che possono essere filtrati tramite indirizzi IP o regole VISTA.
* Tag intelligenti che generano tag solo per determinati tipi di ordini o traffico.
* Le query per il confronto devono prendere in considerazione ciò che viene misurato dal sito Web (non inclusi i ritorni, gli ordini dal personale del servizio di assistenza clienti o altre condizioni speciali).
* Verificate che le differenze di fuso orario tra query e suite di rapporti corrispondano.
* Traffico chiave personalizzato o traffico simile (transazione Keynote, ecc.) che misura il processo di ordinamento e che può essere riflesso nei tag, ma rimosso dai sistemi di ordinamento.
* Account per i processi di deduping del cliente.
* Reloads of the order page (Orders are de-duplicated based on *`purchaseID`*).

