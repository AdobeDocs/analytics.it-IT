---
title: Configurazione di Analytics tra dispositivi
description: Scopri come configurare Analytics cross-Device dopo aver soddisfatto i prerequisiti.
translation-type: tm+mt
source-git-commit: 8c5e8d18ce4e09049d3fea07b8dd75ded6894313

---


# Configurazione di Analytics tra dispositivi

> [!NOTE] La documentazione di Analytics tra dispositivi è soggetta a modifiche man mano che la funzione viene ulteriormente sviluppata. Controllate regolarmente la disponibilità di aggiornamenti.

Una volta soddisfatti tutti i prerequisiti, attenetevi alla seguente procedura per abilitare l'analisi tra dispositivi. Per seguire questa procedura, devi appartenere a un gruppo Amministratore profilo di prodotto o avere privilegi di amministratore in Adobe Analytics.

> [!IMPORTANT] Tutti i prerequisiti devono essere soddisfatti prima di seguire questi passaggi. Se tutti i prerequisiti non sono soddisfatti, la funzione non è disponibile o non funziona. Consultate Analisi [](cda-home.md) multi-dispositivo per prerequisiti e limitazioni.

## Scegliete la suite di rapporti per più dispositivi che verrà abilitata per CDA

Quando l’organizzazione dispone del provisioning per l’utilizzo di CDA, potete scegliere quale suite di rapporti utilizzare. Questa scelta può essere comunicata tramite il tuo Adobe Account Manager. Adobe quindi abilita la suite di rapporti selezionata per l'elaborazione CDA.

## Creare una suite di rapporti virtuali per dispositivi diversi per visualizzare la visualizzazione su più dispositivi

Gli amministratori con accesso per creare suite di rapporti virtuali possono creare suite di rapporti virtuali CDA come segue:

1. Andate a [experience.adobe.com](https://experiencecloud.adobe.com) ed effettuate l'accesso utilizzando le credenziali AdobeID.
2. Fate clic sull'icona a 9 griglie nella parte superiore, quindi fate clic su Analytics.
3. Passa il cursore del mouse sui componenti in alto, quindi fai clic su Suite di rapporti virtuale.
4. Fai clic su Aggiungi.
5. Immettete un nome per la suite di rapporti virtuali e accertatevi che sia selezionata la suite di rapporti abilitata per CDA.
6. (Facoltativo) Applicare un segmento alla suite di rapporti virtuali. Ad esempio, puoi applicare un segmento che limita la suite di rapporti virtuali alle date successive all'attivazione di CDA e all'inizio della cucitura. Questo segmento consente agli utenti di visualizzare solo gli intervalli di date cuciti all'interno della VRS.
7. Fate clic sulla casella di controllo "Abilita elaborazione tempo rapporto" per abilitare diverse opzioni, tra cui Analisi multi-dispositivo.
8. Fate clic sulla casella di controllo "Stitch User Visits Between Devices" (Stitch Visite utente tra dispositivi).
9. Fate clic su Continue (Continua), completate la configurazione della suite di rapporti virtuali, quindi fate clic su Save (Salva).

![Casella di controllo CDA](assets/cda-checkbox.png)

## Aggiunte e modifiche alle suite di rapporti virtuali su più dispositivi

Quando Analytics cross-device è abilitato su una suite di rapporti virtuale, prendi nota delle seguenti modifiche:

* Accanto al nome della suite di rapporti virtuale viene visualizzata una nuova icona cross-device. Questa icona è esclusiva per le suite di rapporti virtuali su più dispositivi.
* Sono disponibili nuove metriche con etichetta 'Persone' e 'Dispositivi univoci'.
* La metrica "Visitatori unici" non è disponibile, in quanto viene sostituita con Persone e Dispositivi univoci.
* Durante la creazione di segmenti, il contenitore del segmento "Visitatore" viene sostituito con un contenitore "Persona".

## Metrica calcolata di compressione

La capacità di analisi multi-dispositivo di unire più dispositivi dipende da un'ampia gamma di fattori. L'efficacia della capacità della funzione di cucire i dati può essere misurata con una metrica calcolata denominata compressione. I fattori che contribuiscono alla compressione comprendono:

* Usando il grafico Co-op o il grafico Privato: In generale, le organizzazioni che utilizzano la cooperativa dispositivi tendono a visualizzare tassi di compressione migliori rispetto alle organizzazioni che utilizzano il grafico privato.
* Velocità di accesso: Più utenti accedono al sito, più Adobe è in grado di identificare e unire i visitatori tra i dispositivi. Anche i siti con un basso tasso di accesso hanno bassi tassi di compressione.
* Copertura Experience Cloud ID: È possibile unire solo i visitatori con un ECID. Una percentuale inferiore di visitatori del sito che utilizza un ECID è correlata a tassi di compressione più bassi.
* Utilizzo di più dispositivi: Se i visitatori del sito non utilizzano più dispositivi, è possibile visualizzare percentuali di compressione inferiori.
* Granularità del reporting: La compressione per giorno è generalmente inferiore alla compressione per mese o anno. Le possibilità di un singolo di utilizzare più dispositivi diventano più ridotte entro un singolo giorno rispetto a un intero mese. Segmentazione, filtraggio o utilizzo di dimensioni di suddivisione può anche mostrare una minore frequenza di compressione.

Per visualizzare la compressione aziendale per un determinato periodo di tempo:

1. Fai clic su Workspace in alto, quindi fai clic su 'Crea nuovo progetto'.
2. Inizia con un progetto vuoto, quindi fai clic su Crea.
3. Trascina la metrica Dispositivi univoci nell’area di quadro con l’etichetta "Rilascia qui una metrica".
4. Trascina la metrica Persone sul quadro direttamente a destra dell’intestazione della metrica Dispositivi univoci, in modo che le due metriche siano affiancate.
5. Fai clic sul simbolo '`+`' accanto alle metriche disponibili a sinistra per aprire il generatore Calculated Metric.
6. Assegna a questa metrica calcolata le seguenti impostazioni:
   * Nome: Compressione tra dispositivi
   * Formato: Percentuale
   * Posti decimali: 2
   * Definizione: `[Static Number: 1] minus [People] divided by [Unique Devices]`
      > [!TIP] Fare clic su 'Aggiungi' nell'angolo superiore destro dell'area di definizione per aggiungere un numero statico. Trascina Persone e Dispositivi univoci dall’elenco delle metriche disponibili a sinistra.
7. Fate clic su Salva.
8. Trascina la nuova metrica calcolata sul quadro direttamente a destra dell’intestazione della metrica Persone, in modo che tutte e tre le metriche siano affiancate.
9. Facoltativo: Per impostazione predefinita, l’area di lavoro carica la dimensione Giorno. Trascina una dimensione data alternativa, ad esempio una settimana o un mese, sopra la dimensione Giorno, se desideri una granularità ora diversa.
