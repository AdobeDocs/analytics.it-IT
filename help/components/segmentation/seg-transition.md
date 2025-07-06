---
description: Scopri come gestire i segmenti legacy.
title: Domande frequenti sui segmenti legacy
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
source-git-commit: c44bffa45ab8ed29ea28b91b2b3dc51811ab25fe
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 57%

---

# Segmenti legacy

Questo articolo risponde alle domande frequenti sulle best practice per la gestione dei segmenti legacy. I segmenti precedenti sono segmenti creati prima del 2014.

## Gestione dei segmenti legacy {#legacy}

+++ **Cos’è successo ai segmenti esistenti?**

I segmenti esistenti continuano a funzionare come prima. Tutti i rapporti a cui sono applicati questi segmenti continuano a funzionare correttamente.

La maggior parte dei segmenti predefiniti e dei segmenti delle suite precedenti viene migrata e convertita in modelli di segmenti nel Generatore di segmenti. I modelli di segmenti vengono utilizzati per creare rapidamente segmenti personalizzati con tipi di pubblico comuni. I modelli di segmenti non possono essere applicati direttamente a un rapporto, ma possono essere salvati con facilità in un segmento personalizzato.

I modelli di segmenti sono contrassegnati da un&#39;icona speciale ![AdobeLogoSmall](/help/assets/icons/AdobeLogoSmall.svg) nel Generatore di segmenti.



+++

+++ **Cos’è successo ai rapporti programmati con segmenti applicati?**

I rapporti programmati continuano a essere eseguiti correttamente con i segmenti definiti.

Quando elimini un segmento, i rapporti e le dashboard programmati a cui è applicato il segmento continuano a funzionare normalmente, ovvero il segmento o la dashboard continua a utilizzare il segmento eliminato.

I rapporti programmati non vengono aggiornati quando si modifica un segmento con lo stesso nome. Ad esempio, supponiamo che tu abbia 2 segmenti con lo stesso nome in suite di rapporti diverse:

![](assets/duplicate_seg_names.png)

Si dispone di una visualizzazione che fa riferimento al segmento per la suite di rapporti **[!UICONTROL mainprod]**. Quel segmento viene quindi eliminato in quanto si tratta di un duplicato. La visualizzazione continua a essere eseguita, facendo riferimento alla definizione del segmento eliminato. Se modifichi la definizione del segmento per il segmento maindev in modo da includere Isola di Catalina e Tijuana, Messico, il segmento applicato alla visualizzazione non cambia e utilizza la vecchia definizione. Per utilizzare la nuova definizione, aggiorna la visualizzazione in modo che faccia riferimento alla nuova definizione. Se non sei sicuro se una visualizzazione, un progetto o un rapporto programmato utilizzano un segmento eliminato, modifica il nome del segmento rimanente per mostrare se la visualizzazione utilizza il segmento rimanente.

+++

+++ **Cos’è successo ai segmenti di Data Warehouse?**

Tutti i segmenti esistenti di Data Warehouse continueranno a funzionare in Data Warehouse. La maggior parte dei segmenti di Data Warehouse funziona anche in altri componenti come Analysis Workspace.

Puoi creare o modificare nuovi segmenti di Data Warehouse in Gestione/Generatore di segmenti. Il meccanismo di compatibilità dei prodotti nel Generatore di segmenti determina automaticamente se un segmento è compatibile con Data Warehouse.

+++

+++ **Cos’è successo ai segmenti preconfigurati?**

* **Visite a pagina singola**
* **Visite da dispositivi mobili**
* **Visite da ricerca naturale**
* **Visite da ricerca a pagamento**
* **Visite con il cookie ID visitatore**

Verrà effettuata la migrazione di questi segmenti e diventeranno modelli di segmenti nel Generatore di segmenti. I rapporti esistenti a cui sono applicati questi segmenti continueranno a funzionare correttamente.

+++

+++ **Cos’è successo ai segmenti Experience Cloud (Suite):**

* Non acquirenti
* Acquirenti
* Prime visite
* Visite dai siti social
* Visite di oltre 10 minuti*
* Visite con oltre 5 visite precedenti*
* Visite da Facebook*

La maggior parte di questi segmenti (tranne quelli contrassegnati con un asterisco *) sono stati migrati come modelli di segmento nel Generatore di segmenti. Sono stati inoltre aggiunti diversi nuovi modelli di segmenti.

I rapporti esistenti a cui sono applicati questi segmenti continueranno a funzionare correttamente.

+++

+++ **Cos’è successo ai segmenti di amministrazione (noti anche come segmenti “globali”)?**

I segmenti **Admin** sono stati migrati nella nuova interfaccia e visualizzati come segmenti condivisi con tutti.

Il proprietario di questi segmenti è impostato sull’amministratore con l’account più vecchio degli utenti amministratori. Tuttavia, tutti gli amministratori possono eliminare, modificare e condividere questi segmenti.

L’interfaccia di gestione dei segmenti in Admin Console, in cui gli amministratori potevano creare e gestire i segmenti globali, non è più disponibile. Ora gli amministratori devono usare il nuovo Generatore di segmenti per creare segmenti e condividerli con gruppi o singoli utenti specifici o con tutti.

I segmenti esistenti che utilizzano una logica che è stata modificata come descritto in questo documento continuano a funzionare correttamente, anche se i segmenti devono essere aggiornati prima di poter essere salvati nuovamente. Ad esempio, se hai un segmento esistente in cui **[!UICONTROL US States]** **[!UICONTROL contains]** `New York`, tale segmento continua a funzionare correttamente. La prossima volta che modifichi il segmento, dovrai aggiornare il segmento per utilizzare il tipo enumerato con una condizione **[!UICONTROL equals]**.

+++

+++ **Cosa conviene fare con i segmenti duplicati che hanno lo stesso nome ma definizioni diverse?**
Ora che i segmenti funzionano in più suite di rapporti, potresti avere più segmenti con lo stesso nome. Devi:

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

### Suggerimenti per la migrazione

I seguenti suggerimenti consentono di migrare dimensioni comuni:

* Geo-città/area geografica/paese: cerca e seleziona città, aree geografiche o paesi specifici invece di utilizzare una corrispondenza parziale.
* Browser: utilizza la dimensione Tipi di browser per ottenere tutti i browser in un tipo, ad esempio Google Chrome
* Sistemi operativi: utilizza le dimensioni Tipi di sistema operativo per ottenere tutti i sistemi operativi in un tipo, ad esempio Microsoft Windows.
* Consulta “Dimensioni nuove e rinominate” (vedi di seguito)

## Dimensioni nuove e rinominate {#renamed}

La tabella seguente contiene un elenco di dimensioni rinominate nel Generatore di segmenti.

| Nuovo nome della dimensione | Nome precedente | Note |
|--- |--- |--- |
| Tipi di sistemi operativi | Nuovo | Aggiunto nella primavera 2015. |
| Larghezza browser - Bucket | Larghezza browser | Questa dimensione è compatibile con tutte le interfacce ed è suddivisa in un elenco enumerato di intervalli invece di valori interi specifici. Se devi segmentare valori specifici, utilizza la versione granulare di questa dimensione in un segmento Data Warehouse. |
| Altezza browser - Bucket | Altezza browser | Questa dimensione è compatibile con tutte le interfacce ed è suddivisa in un elenco enumerato di intervalli invece di valori interi specifici. Se devi segmentare valori specifici, utilizza la versione granulare di questa dimensione in un segmento Data Warehouse. |
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

{style="table-layout:auto"}

## Modifiche alle dimensioni basate su stringhe con valori noti {#string-based-dims}

Le dimensioni basate su stringhe che hanno un set noto di valori sono state modificate in tipi enumerati. Quando crei un segmento utilizzando queste dimensioni, l&#39;elenco viene precompilato con tutti i valori noti e l&#39;unico operatore supportato è **[!UICONTROL equals]**. Questa popolazione di valori consente di segmentare rapidamente i valori esatti desiderati senza selezionare valori non desiderati quando si utilizza una corrispondenza meno restrittiva.

Le seguenti dimensioni sono state modificate in elenchi enumerati:

| Nome dimensione | Nome dimensione | Nome dimensione |
| --- | --- | --- |
| produttore di dispositivi mobili | lunghezza e-mail mobile | profondità colore |
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

Le dimensioni basate su numeri interi (come la larghezza del browser) con un set di valori noto vengono suddivise in intervalli enumerati, in modo da poter definire rapidamente i segmenti per un intervallo specifico. Gli elenchi enumerati sono seguiti da “ - Bucket” dopo il nome della dimensione. La schermata seguente mostra il modo in cui queste dimensioni vengono segmentate utilizzando l’interfaccia precedente del Generatore di segmenti e l’interfaccia nuova:

![](assets/seg_browser_dimension.png)

Gli operatori “minore di”, “maggiore di” e simili ora sono compatibili solo con i segmenti di Data Warehouse. I segmenti destinati a essere compatibili con tutte le interfacce di reporting devono utilizzare la versione &quot;Bucket&quot; della metrica con l&#39;operatore **[!UICONTROL equals]**.
