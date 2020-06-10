---
description: Abilitando la gestione delle app vengono attivate le variabili della soluzione mobile che acquisiscono lo stile di vita e altre metriche dalle applicazioni mobili.
title: Gestione app
topic: Admin tools
translation-type: tm+mt
source-git-commit: a28a05047e95d12343fd94f7b11e5cabf7fac070
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 31%

---


# Gestione app

Abilitando la gestione delle app vengono attivate le variabili della soluzione mobile che acquisiscono lo stile di vita e altre metriche dalle applicazioni mobili.

Questa integrazione tra Adobe Analytics e Mobile Services:

* Consente di condividere i dati KPI (Key Performance Indicator) da Mobile Services ad Adobe Analytics.
* Consente di abilitare il tracciamento della posizione.
* Aggiunge nuovi report in Analytics > Report > App mobile.
* Aggiunge 25 nuove classificazioni Adobe Mobile.
* Aggiunge 5 nuove metriche di Adobe Mobile.
* Aggiunge nuove dimensioni di Adobe Mobile.
* Sincronizza i dati con Analytics ogni 15 minuti

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

## Passaggio 1: Abilita rapporti app {#section_FBADF80AED2B4978A904ABB770B3B931}

Abilita App Reports v3.0 per misurare le metriche seguenti:

* **Acquisizione** - tieni traccia degli URL di provenienza per le campagne di download delle app.
* **Ciclo di vita** : livello base di reporting fornito dalle misurazioni inviate a ogni avvio dell&#39;app.
* **Azioni** app - rapporti e percorsi basati sulle azioni in-app.
* **Valore** del ciclo di vita: scopri in che modo gli utenti maturano valore nel tempo utilizzando KPI per le app (come acquisti, visualizzazioni di annunci pubblicitari, completamenti di video, condivisioni social, caricamenti di foto).
* **Eventi** temporizzati: misura il tempo (in-app e totale) che trascorre tra le azioni app chiave (ad esempio il tempo prima del primo acquisto).

## Passaggio 2: Abilita tracciamento posizione {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

L’attivazione del tracciamento della posizione consente di:

* Tieni traccia dei dati di latitudine e longitudine e genera un rapporto su di essi in Analysis Workspace e Mobile Services.
* Identifica, crea e visualizza punti di interesse specifici (POI) in Mobile Services. I POI devono essere definiti nel file di configurazione dell’SDK per dispositivi mobili.
* Tracciare i beacon Bluetooth (UUID, principale, secondario e prossimità).

## Passaggio 3: (Facoltativo) Attivare/disattivare rapporti legacy e attribuzione per hit in background {#section_1708BCAA87AA4884986F7532759C5DD4}

Gli hit in background abilitati (hit generati quando l’app è in background) indicano che sono trattati come normali hit in primo piano. Ora vengono visualizzati nei rapporti regolari e questo incide anche sull&#39;attribuzione. Questa configurazione è in genere desiderabile solo per mantenere la coerenza con le implementazioni precedenti.

È invece consigliabile &quot;includere hit di background&quot; in una suite [di rapporti](/help/components/vrs/vrs-about.md)virtuale. Questo consente di visualizzare gli hit ma non influiscono negativamente sul conteggio delle visite e dei visitatori.
Le classificazioni per dispositivi mobili sono abilitate dopo aver attivato **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

Le classificazioni vengono utilizzate per classificare i valori in gruppi e per creare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come &quot;termini musicali pop&quot; e generare rapporti sul successo di quella categoria in relazione a metriche come Istanze (alias Click-through) e conversione in eventi di successo.

| Classificazione | Definizione |
|--- |--- |
| Data primo avvio | Data del primo avvio dopo l’installazione o reinstallazione.   DD/MM/YYYY |
| ID app | Memorizza il nome e la versione dell&#39;applicazione nel seguente formato:   `[AppName] [BundleVersion]`  Ad esempio, `myapp 1.1.` |
| Numero di avvii | Numero di volte per cui l&#39;applicazione è stata avviata o portata in primo piano. |
| Giorni dal primo utilizzo | Numero di giorni dalla prima esecuzione. |
| Giorni dall’ultimo utilizzo | Numero di giorni dall&#39;ultimo utilizzo. |
| Ora del giorno | Calcola l&#39;ora di avvio dell&#39;app e utilizza il formato numerico 24 ore. Utilizzato per la suddivisione del tempo per determinare le ore di utilizzo di picco. |
| Giorno della settimana | Numero del giorno della settimana in cui è stata avviata l&#39;app. |
| Nome del dispositivo | Memorizza il nome del dispositivo.  Stringa di due cifre separate da virgola che identifica il dispositivo Di norma il primo numero rappresenta la generazione del dispositivo e il secondo numero indica membri diversi della famiglia di dispositivi. |
| Versione sistema operativo | Versione del sistema operativo. |
| Risoluzione | Larghezza x altezza in pixel reali. |
| Valore &quot;lifetime&quot; del ciclo di vita (eVar) | Viene compilata dai metodi trackLifetimeValue. |
| Origine acquisizione |  |
| Supporto di acquisizione |  |
| Termine acquisizione |  |
| Contenuto acquisizione |  |
| Nome acquisizione |  |
| Posizione (fino a 10 km) | Viene compilata dai metodi trackLocation. |
| Posizione (fino a 100 m) | Viene compilata dai metodi trackLocation. |
| Posizione (fino a 1 m) | Viene compilata dai metodi trackLocation. |
| Nome del punto di interesse | Viene compilata dai metodi trackLocation quando il dispositivo si trova entro un POI definito. |
| Distanza dal centro del punto di interesse | Viene compilata dai metodi trackLocation quando il dispositivo si trova entro un POI definito. |
| ID messaggio in-app |  |
| Messaggio in-app online |  |
| Consenso push |  |
| ID payload |  |

