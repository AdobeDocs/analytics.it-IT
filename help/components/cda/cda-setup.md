---
title: Configurazione di Analisi cross-device
description: Scopri come configurare Analytics Cross-Device dopo aver soddisfatto i prerequisiti.
translation-type: tm+mt
source-git-commit: 1ab4c27d6635167be475b6669ff6ed1913adc455

---


# Configurazione di Analisi cross-device

> [!IMPORTANT] Tutti i prerequisiti devono essere soddisfatti prima di seguire questi passaggi. Se tutti i prerequisiti non sono soddisfatti, la funzione non è disponibile o non funzionerà. Consultate [Analisi cross-device](cda-home.md) per prerequisiti e limitazioni.

Una volta soddisfatti tutti i prerequisiti, utilizza i passaggi seguenti per abilitare Analytics tra dispositivi. Per seguire questi passaggi, devi appartenere a un gruppo Amministratore di profilo di prodotto o avere privilegi di amministratore in Adobe Analytics.

## Scegli la suite di rapporti cross-device che sarà abilitata per CDA

Quando l'organizzazione ha il provisioning di utilizzare CDA, scegli quale suite di rapporti utilizzare. Questa scelta può essere comunicata tramite il tuo Adobe Account Manager. Adobe quindi abilita la suite di rapporti selezionata per l'elaborazione CDA.

## Creare una suite di rapporti virtuali per dispositivi diversi per visualizzare la vista cross-device

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come indicato di seguito:

1. Passa a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) ed effettua l'accesso utilizzando le credenziali adobeid.
2. Fate clic sull'icona a 9 griglia nella parte superiore, quindi fate clic su Analytics.
3. Passa il cursore sopra Componenti nella parte superiore, quindi fai clic su Suite di rapporti virtuali.
4. Fai clic su Aggiungi.
5. Immetti un nome per la suite di rapporti virtuali e assicurati che sia selezionata la suite di rapporti abilitata per CDA.
6. Fai clic sulla casella «Abilita elaborazione tempo rapporto», che abilita diverse opzioni tra cui Analisi cross-device.
7. Fai clic sulla casella "Stitch User Visits tra dispositivi".
8. Fate clic su Continue (Continua), terminate la configurazione della suite di rapporti virtuali, quindi fate clic su Save (Salva).

![CDA, casella di selezione](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite per rapporti virtuali su più dispositivi

Quando Analytics cross-device è abilitato in una suite di rapporti virtuale, prendi nota delle seguenti modifiche:

* Accanto al nome della suite di rapporti virtuale viene visualizzata una nuova icona cross-device. Questa icona è esclusiva delle suite per rapporti virtuali cross-device.
* Sono disponibili nuove metriche denominate "Persone" e "Dispositivi univoci".
* La metrica "Visitatori unici" non è disponibile, poiché viene sostituita con Persone e Dispositivi univoci.
* Quando si creano segmenti, il contenitore del segmento «Visitatore» viene sostituito da un contenitore «Persona».

## Metrica calcolata Compressione

La capacità di utilizzare simultaneamente Analytics per i dispositivi stitch dipende da un'ampia gamma di fattori. L'efficacia della capacità di determinare i dati può essere misurata con una metrica calcolata denominata compression. Fattori che contribuiscono alla compressione includono:

* Utilizzo del grafico Co-op o del grafico privato: In generale, le organizzazioni che utilizzano il device co-op tendono a visualizzare tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico privato.
* Tasso di login: Più utenti accedono al sito, più Adobe può identificare e unire i visitatori tra i dispositivi. Anche i siti con una frequenza di login ridotta dispongono di tassi di compressione bassi.
* Copertura Experience Cloud ID: Solo i visitatori con un ECID possono essere cucito. Una percentuale inferiore di visitatori sul sito utilizzando un ECID correlazioni a tassi di compressione più bassi.
* Utilizzo più dispositivi: Se i visitatori del sito non utilizzano più dispositivi, potete visualizzare tassi di compressione inferiori.
* Granularità di reporting: La compressione per giorno è in genere inferiore alla compressione per mese o anno. Le possibilità che un utente utilizzi più dispositivi si riducono in un singolo giorno rispetto a un mese intero. Anche la segmentazione, il filtro o l'uso delle dimensioni di suddivisione può presentare un tasso di compressione inferiore.

Per visualizzare la compressione dell'organizzazione per un determinato periodo di tempo:

1. Fate clic su Area di lavoro nella parte superiore, quindi fate clic su Crea nuovo progetto.
2. Inizia con un progetto vuoto, quindi fai clic su Crea.
3. Trascina la metrica Dispositivi unici nell'area «Goccia una metrica qui».
4. Trascina la metrica Persone sul quadro direttamente a destra dell'intestazione della metrica Dispositivi unici, in modo che le due metriche siano affiancate.
5. Fai clic sul simbolo + accanto alle metriche disponibili a sinistra per aprire il generatore di metriche calcolate.
6. Assegna a questa metrica calcolata le seguenti impostazioni:
   * Nome: Compressione cross-device
   * Formato: Percentuale
   * Posizioni decimali: 2
   * Definizione: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!NOTE] Fate clic su «Aggiungi» nell'angolo in alto a destra dell'area di definizione per aggiungere un numero statico. Trascina Persone e dispositivi univoci dall'elenco delle metriche disponibili a sinistra.
7. Fate clic su Salva.
8. Trascina la nuova metrica calcolata sul quadro direttamente a destra dell'intestazione della metrica Persone, in modo che tutte e tre le metriche siano affiancate.
9. Facoltativo: Per impostazione predefinita, l'area di lavoro carica la dimensione Giorno. Trascina una dimensione di data alternativa, ad esempio settimana o mese, sopra la dimensione Giorno se desideri una granularità temporale diversa.
