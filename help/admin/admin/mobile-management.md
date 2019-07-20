---
description: Abilitando la gestione mobile vengono attivate le variabili della soluzione mobile che acquisiscono il ciclo di vita e altre metriche dalle applicazioni mobili.
seo-description: Abilitando la gestione mobile vengono attivate le variabili della soluzione mobile che acquisiscono il ciclo di vita e altre metriche dalle applicazioni mobili.
seo-title: Gestione mobile
solution: Analytics
title: Gestione mobile
topic: Strumenti di amministrazione
uuid: d 09 edf 72-bb 91-422 d-b 22 c -7 b 6971 f 228 de
translation-type: tm+mt
source-git-commit: 6184104b5a46242c5973552298964e96ff671d7c

---


# Gestione mobile

Abilitando la gestione mobile vengono attivate le variabili della soluzione mobile che acquisiscono il ciclo di vita e altre metriche dalle applicazioni mobili.

Questa integrazione tra Adobe Analytics e Mobile Services

* Consente di condividere i dati KPI (Key Performance Indicator) da Mobile Services ad Adobe Analytics.
* Consente di abilitare il tracciamento della posizione.
* Aggiunge nuovi rapporti in Analytics &gt; Rapporti &gt; App mobile.
* Aggiunge nuove 25 classificazioni Adobe Mobile.
* Aggiunge altre 5 metriche di Adobe Mobile.
* Aggiunge nuove dimensioni di Adobe Mobile.
* Sincronizza i dati ad Analytics ogni 15 minuti

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Mobile Management]** &gt; **[!UICONTROL Mobile Application Reporting]**.

## Passaggio 1: Enable App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

Abilita Report App v 3.0 per misurare le metriche seguenti:

* **Acquisizione** - tieni traccia degli URL di provenienza per le campagne di download delle app.
* **Ciclo di vita** : livello di base del reporting fornito dalla misurazione inviata per ogni lancio dell'app.
* **Azioni** app: rapporti e percorsi basati sulle azioni in-app.
* **Valore** del ciclo di vita: comprendere il valore degli utenti nel tempo utilizzando i KPI delle app (come acquisti, visualizzazioni di annunci pubblicitari, completamenti video, condivisioni social, caricamenti di foto).
* **Eventi** temporizzati: misura il tempo trascorso (tempo in-app e totale) tra le azioni app chiave (ad esempio, l'ora prima del primo acquisto).

## Passaggio 2: Enable Location Tracking {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

Abilitazione tracciamento posizione consente di:

* Tieni traccia dei dati di latitudine e longitudine e report su di esso in Analysis Workspace e Mobile Services.
* Identifica, crea e visualizza specifici punti di interesse (POI) all'interno di Mobile Services. I POI devono essere definiti nel file di configurazione SDK di Mobile.
* Tieni traccia dei beacon Bluetooth (UUID, principale, secondario e prossimità).

## Passaggio 3: (Optional) Enable/Disable Legacy Reporting and Attribution for Background Hits {#section_1708BCAA87AA4884986F7532759C5DD4}

Gli hit in background abilitati (hit generati quando l'app è in background) indicano che sono stati trattati come hit di primo piano regolari. Adesso vengono visualizzati nei rapporti regolari e ciò influisce sull'attribuzione. In genere, questa configurazione è utile solo per mantenere la coerenza con le implementazioni legacy.

Instead, we recommend that you “include background hits” in a [virtual report suite](../../components/vrs/vrs-about.md). Questo consente di visualizzare gli hit, ma non influirà negativamente sulla visita e sui conteggi dei visitatori.
Mobile classifications are enabled after you enable **[!UICONTROL Mobile Management]** &gt; **[!UICONTROL Mobile Application Reporting]**.

Le classificazioni vengono utilizzate per suddividere i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, potete classificare tutte le campagne Search Search in una categoria come «Condizioni musicali pop» e segnalare il successo della categoria relativo a metriche come Istanze (a. k. a. Click-through) e conversione in eventi di successo.

| Classificazione | Definizione |
|--- |--- |
| Data primo avvio | Data del primo avvio dopo l'installazione o la reinstallazione. DD/MM/YYYY |
| ID app | Memorizza il nome e la versione dell'applicazione nel seguente formato:   `[AppName] [BundleVersion]`  Ad esempio, `myapp 1.1.` |
| Numero di avvii | Numero di volte per cui l'applicazione è stata avviata o portata in primo piano. |
| Giorni dal primo utilizzo | Numero di giorni dalla prima esecuzione.   |
| Giorni dall'ultimo utilizzo | Numero di giorni dall'ultimo utilizzo. |
| Ora del giorno | Calcola l'ora di avvio dell'app e utilizza il formato numerico 24 ore. Utilizzato per la suddivisione del tempo per determinare le ore di utilizzo di picco. |
| Giorno della settimana | Numero del giorno della settimana in cui è stata avviata l'app. |
| Nome del dispositivo | Memorizza il nome del dispositivo.  Stringa di due cifre separate da virgola che identifica il dispositivo Di norma il primo numero rappresenta la generazione del dispositivo e il secondo numero indica membri diversi della famiglia di dispositivi. |
| Versione sistema operativo | Versione del sistema operativo. |
| Risoluzione | Larghezza x altezza in pixel reali. |
| Valore del ciclo di vita (evar) | Viene compilata dai metodi trackLifetimeValue. |
| Sorgente di acquisizione |  |
| Media di acquisizione |  |
| Termine acquisizione |  |
| Contenuto di acquisizione |  |
| Nome acquisizione |  |
| Posizione (fino a 10 chilometri) | Viene compilata dai metodi trackLocation. |
| Posizione (fino a 100 m) | Viene compilata dai metodi trackLocation. |
| Posizione (fino a 1 m) | Viene compilata dai metodi trackLocation. |
| Nome del punto di interesse | Viene compilata dai metodi trackLocation quando il dispositivo si trova entro un POI definito. |
| Distanza dal centro del punto di interesse | Viene compilata dai metodi trackLocation quando il dispositivo si trova entro un POI definito. |
| ID messaggio in-app |  |
| Messaggio in-app online |  |
| Consenso push |  |
| ID payload |  |

