---
description: Domande frequenti sulla gestione dei segmenti legacy.
title: Domande frequenti sui segmenti legacy
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
source-git-commit: e1ba6e93bcea4ece6e06941a97227a54116e2c25
workflow-type: tm+mt
source-wordcount: '1448'
ht-degree: 93%

---

# Domande frequenti sui segmenti legacy

Risposte alle domande frequenti sulle best practice per la gestione dei segmenti legacy - segmenti creati prima del 2014.

## Best practice {#best-practices}

+++ **Cosa conviene fare con i segmenti duplicati che hanno lo stesso nome ma definizioni diverse?**
Ora che i segmenti funzionano in più suite di rapporti, potresti avere più segmenti con lo stesso nome. Consigliamo di svolgere una delle seguenti azioni:

* Rinominare i segmenti che hanno lo stesso nome ma definizioni diverse, oppure
* Eliminare i segmenti non più necessari.

+++

+++ **Cosa consiglia Adobe per quanto riguarda la pulizia dei segmenti?**

* Assegna a tutti i segmenti un tag legacy.
* Esamina i tuoi segmenti.
* Aggiungili alla libreria dei segmenti, se applicabile.
* Approva i segmenti canonici.
* Assegna tag ai segmenti seguendo le [best practice](/help/components/segmentation/segmentation-workflow/seg-workflow.md).

+++

## Gestione dei segmenti legacy {#legacy}

+++ **Cos’è successo ai segmenti esistenti?**

I segmenti esistenti continueranno a funzionare come prima. Tutti i rapporti a cui sono applicati questi segmenti continueranno a funzionare correttamente. [Altro...](/help/components/segmentation/seg-transition.md)

La maggior parte dei segmenti predefiniti e dei segmenti delle suite precedenti migreranno e diventeranno modelli nel Generatore di segmenti. I modelli di segmenti sono utilizzati per creare rapidamente segmenti personalizzati con audience comuni. I modelli di segmenti non possono essere applicati direttamente a un rapporto, ma possono essere salvati con facilità in un segmento personalizzato.

I modelli di segmenti sono contrassegnati da un’icona specifica nel Generatore di segmenti:

![](assets/seg_templates.png)

+++

+++ **Cos’è successo ai rapporti programmati con segmenti applicati?**

I rapporti programmati continuano a essere eseguiti correttamente con i segmenti definiti.

Quando elimini un segmento, i rapporti e le dashboard programmati a cui è applicato il segmento continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.

I rapporti programmati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Ad esempio, supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

![](assets/duplicate_seg_names.png)

È presente un segnalibro che fa riferimento al segmento per la suite di rapporti principale. Quel segmento viene quindi eliminato in quanto si tratta di un duplicato. Il segnalibro continuerà a essere eseguito e farà riferimento alla definizione del segmento eliminato. Se modifichi la definizione del segmento per il segmento maindev in modo da includere Isola di Catalina e Tijuana Messico, il segmento applicato al segnalibro non subirà modifiche e utilizzerà la vecchia definizione. Per risolvere il problema, aggiorna il segnalibro in modo che faccia riferimento alla nuova definizione. Se hai dubbi sul fatto che un segnalibro, una dashboard o un rapporto programmato utilizzino un segmento eliminato, modifica il nome del segmento rimanente in modo che risulti più chiaro se il segnalibro lo sta utilizzando.

+++

+++ **Cos’è successo ai segmenti di Data Warehouse?**

Tutti i segmenti esistenti di Data Warehouse continueranno a funzionare in Data Warehouse. La maggior parte dei segmenti di Data Warehouse funzionerà anche in altri componenti come Analysis Workspace e Reports &amp; Analytics.

Puoi creare o modificare nuovi segmenti di Data Warehouse nel Generatore/Gestore segmenti. Il meccanismo di compatibilità dei prodotti nel Generatore di segmenti determina automaticamente la compatibilità di un segmento con Data Warehouse.

+++

**Cos’è successo ai segmenti preconfigurati?**

* **Visite a pagina singola**
* **Visite da dispositivi mobili**
* **Visite da ricerca naturale**
* **Visite da ricerca a pagamento**
* **Visite con il cookie ID visitatore**

Verrà eseguita la migrazione di questi segmenti e diventeranno modelli di segmenti nel Generatore di segmenti. I rapporti esistenti a cui sono applicati questi segmenti continueranno a funzionare correttamente.

+++

+++ **Cos’è successo ai segmenti di Experience Cloud (Suite):**

* Non acquirenti
* Acquirenti
* Prime visite
* Visite dai siti social
* Visite di oltre 10 minuti*
* Visite con oltre 5 visite precedenti*
* Visite da Facebook*

La maggior parte di questi segmenti (tranne quelli contrassegnati con un asterisco *) sono stati migrati e i modelli di segmenti sono stati inseriti nel generatore di segmenti. Sono stati inoltre aggiunti diversi nuovi modelli di segmenti.

I rapporti esistenti a cui sono applicati questi segmenti continuano a funzionare correttamente.

+++

+++ **Cosa succederà ai segmenti admin (noti anche come segmenti “globali”)?**

I segmenti **admin** verranno migrati nella nuova interfaccia dei segmenti e visualizzati come segmenti condivisi con tutti.

Il proprietario di questi segmenti è impostato sull’amministratore con l’account più vecchio nell’elenco degli utenti amministratori dell’azienda di accesso. Tuttavia, tutti gli amministratori possono eliminare, modificare e condividere questi segmenti.

L’interfaccia di gestione dei segmenti in Admin Console, in cui gli amministratori potevano creare e gestire i segmenti globali, non è più disponibile. Ora gli amministratori devono usare il nuovo Generatore di segmenti per creare segmenti e condividerli con gruppi o singoli utenti specifici o con tutti.

I segmenti esistenti che utilizzano una logica che ha subito modifiche nel modo descritto in questo documento continueranno a funzionare correttamente, ma dovranno essere aggiornati prima di poter essere salvati di nuovo. Ad esempio, se hai un segmento esistente in cui Stati degli Stati Uniti contiene “New York”, esso continuerà a funzionare correttamente, ma la prossima volta che modifichi il segmento dovrai aggiornarlo per utilizzare il tipo enumerato con una condizione “è uguale a”.

+++

### Suggerimenti per la migrazione

Di seguito sono riportati alcuni suggerimenti per la migrazione delle dimensioni comuni:

* Geo-città/area geografica/paese: cerca e seleziona città, aree geografiche o paesi specifici invece di utilizzare una corrispondenza parziale.
* Browser: utilizza la dimensione Tipi di browser per ottenere tutti i browser in un tipo, ad esempio Google Chrome
* Sistemi operativi: utilizza le dimensioni Tipi di sistema operativo per ottenere tutti i sistemi operativi in un tipo, ad esempio Microsoft Windows.

* [Dimensioni nuove e rinominate](/help/components/segmentation/seg-transition.md#section_73CF121B64A24DEF8E6499F3167BF742)
* [Modifiche a “contiene”](/help/components/segmentation/seg-transition.md#section_1A9EDEE5CBC44B5AA6262560052ABE77)
* [Modifiche a “minore di” e “maggiore di”](/help/components/segmentation/seg-transition.md#section_84A8AAD0344148AD9F9211D3EB271903)

## Dimensioni nuove e rinominate {#renamed}

La tabella seguente contiene un elenco di dimensioni rinominate nel Generatore di segmenti.

| Nuovo nome della dimensione | Nome precedente | Note |
|--- |--- |--- |
| Tipi di sistemi operativi | Nuovo | Aggiunto nella primavera 2015. |
| Larghezza browser - Bucket | Larghezza browser | Questa dimensione è compatibile con tutte le interfacce ed è suddivisa in un elenco enumerato di intervalli invece di valori interi specifici. Per segmentare valori specifici, utilizza la versione granulare di questa dimensione in un segmento di Data Warehouse. |
| Altezza browser - Bucket | Altezza browser | Questa dimensione è compatibile con tutte le interfacce ed è suddivisa in un elenco enumerato di intervalli invece di valori interi specifici. Per segmentare valori specifici, utilizza la versione granulare di questa dimensione in un segmento di Data Warehouse. |
| Larghezza browser - Granulare | Larghezza browser | Questa dimensione è stata rinominata ed è ora compatibile solo con Data Warehouse. Quando definisci i segmenti compatibili con tutte le interfacce, utilizza il tipo enumerato, Larghezza browser - Bucket. |
| Altezza browser - Granulare | Altezza browser | Questa dimensione è stata rinominata ed è ora compatibile solo con Data Warehouse. Quando definisci i segmenti compatibili con tutte le interfacce, utilizza il tipo enumerato, Altezza browser - Bucket. |
| Supporto per cookie | Cookie | - |
| Profondità colore | Profondità colore del monitor | - |
| - | “App - *” | i prefissi “App -” sono stati rimossi da diversi tipi di dimensioni. Poiché i dati delle app mobile vengono generalmente acquisiti in una suite di rapporti che non contiene dati web, questi prefissi non erano necessari. |
| Pagina di ingresso originale | Pagina di ingresso originale | - |
| Java abilitato | Java | - |
| Lunghezza massima URL browser mobile | Lunghezza URL browser mobile | - |
| Decoration Mail mobile | Supporto per Decoration Mail mobile | - |
| Dispositivo mobile | Nome dispositivo mobile | - |
| Lunghezza massima segnalibro mobile | Lunghezza massima URL segnalibro mobile | - |
| Lunghezza massima e-mail mobile | Lunghezza massima URL e-mail mobile | - |
| Sistema operativo mobile (obsoleto) | Sistema operativo mobile | Utilizza la dimensione Sistema operativo e applica le visite dai segmenti dei dispositivi mobili. |
| Push-to-talk per dispositivi mobili | PTT mobile | - |
| Visualizzazioni sondaggio | Totale visualizzazioni sondaggio | - |
| Risposte sondaggio | Totale risposte sondaggio | - |
| Profondità della visita | Lunghezza percorso | - |
| Codice postale | CAP | - |

{style=&quot;table-layout:auto&quot;}

## Modifiche alle dimensioni basate su stringhe con valori noti {#string-based-dims}

Le dimensioni basate su stringhe che hanno un set noto di valori sono state modificate in tipi enumerati. Quando crei un segmento utilizzando queste dimensioni, l’elenco viene precompilato con tutti i valori noti e l’unico operatore supportato è “uguale a”. Ciò consente di segmentare rapidamente i valori esatti desiderati senza selezionare altri valori quando utilizzi una corrispondenza meno restrittiva.

Le seguenti dimensioni sono state modificate in elenchi enumerati:

| produttore di dispositivi mobili | lunghezza e-mail mobile | profondità colore |
|---|---|---|
| dimensioni schermo mobile | numero dispositivo mobile | risoluzione monitor |
| altezza schermo mobile | push-to-talk per dispositivi mobili | plug-in |
| supporto cookie per dispositivi mobile | decoration mail mobile | sistema operativo |
| supporto per immagini mobile | servizi di informazione mobile | tipo di referrer |
| profondità colore mobile | tipo di dispositivo mobile | motore di ricerca |
| supporto audio per dispositivi mobili | tipo di browser | stato |
| supporto video per dispositivi mobili | browser | paese |
| drm mobile | tipo di connessione | area geografica |
| protocolli di rete mobile | operatore di telefonia mobile | città |
| sistema operativo mobile | cookie | geo dma |
| vm java mobile | fedeltà del cliente | cookie persistente |
| lunghezza segnalibro mobile | java abilitato | ricerca a pagamento |
| lunghezza url mobile | lingua |  |

## Modifiche alle dimensioni basate su numeri interi con valori noti {#integer-based-dims}

Le dimensioni basate su numeri interi (come la larghezza del browser) con un set di valori noto sono state suddivise in intervalli enumerati, in modo da poter definire rapidamente i segmenti per un intervallo specifico. Gli elenchi enumerati sono seguiti da “ - Bucket” dopo il nome della dimensione. La schermata seguente illustra il modo in cui queste dimensioni vengono segmentate utilizzando l’interfaccia precedente del Generatore di segmenti e l’interfaccia nuova:

![](assets/seg_browser_dimension.png)

Gli operatori “minore di”, “maggiore di” e simili ora sono compatibili solo con i segmenti di Data Warehouse. I segmenti destinati ad essere compatibili con tutte le interfacce di reporting devono utilizzare la versione “Bucket” della metrica con l’operatore “uguale a”.
