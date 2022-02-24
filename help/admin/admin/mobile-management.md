---
description: L’abilitazione della gestione delle app attiva le variabili della soluzione mobile che acquisiscono il ciclo di vita e altre metriche dalle applicazioni mobili.
title: Gestione delle app
feature: Admin Tools
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: ht
source-wordcount: '609'
ht-degree: 100%

---

# Gestione delle app

L’abilitazione della gestione delle app attiva le variabili della soluzione mobile che acquisiscono il ciclo di vita e altre metriche dalle applicazioni mobili.

Questa integrazione tra Adobe Analytics e Mobile Services:

* Consente di condividere i dati KPI (Key Performance Indicator, indicatore di prestazioni) da Mobile Services ad Adobe Analytics.
* Consente di abilitare il tracciamento della posizione.
* Aggiunge nuovi rapporti in Analytics > Rapporti > App mobile.
* Aggiunge 25 nuove classificazioni di Adobe Mobile.
* Aggiunge 5 nuove metriche di Adobe Mobile.
* Aggiunge nuove dimensioni di Adobe Mobile.
* Sincronizza i dati con Analytics ogni 15 minuti

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

## Passaggio 1. Abilitare App Reports {#section_FBADF80AED2B4978A904ABB770B3B931}

Abilita App Reports v3.0 per misurare le metriche seguenti:

* **Acquisizione**: tieni traccia degli URL di riferimento per le campagne di download di app.
* **Ciclo di vita**: livello base di reporting fornito dalla misurazione inviata a ogni avvio dell’app.
* **Azioni app**: rapporti e percorsi basati sulle azioni in-app.
* **Valore del ciclo di vita**: scopri come cresce nel tempo il valore degli utenti utilizzando i KPI per le app, ad esempio acquisti, visualizzazioni di annunci pubblicitari, riproduzioni video completate, condivisioni social, caricamenti di foto.
* **Eventi temporizzati**: misura quanto tempo (in-app e totale) intercorre tra le azioni in-app principali, ad esempio il tempo che precede il primo acquisto.

## Passaggio 2. Abilitare il tracciamento della posizione {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

L’abilitazione del tracciamento della posizione consente di:

* Tenere traccia dei dati di latitudine e longitudine e creare rapporti su di essi in Analysis Workspace e Mobile Services.
* Identificare, creare e visualizzare punti di interesse specifici in Mobile Services. I punti di interesse devono essere definiti nel file di configurazione dell’SDK per dispositivi mobili.
* Tracciare i beacon Bluetooth (UUID, principale, secondario e prossimità).

## Passaggio 3. (Facoltativo) Attivare/disattivare reportistica e attribuzione legacy per gli hit in background {#section_1708BCAA87AA4884986F7532759C5DD4}

Gli hit in background abilitati (hit generati quando l’app è in background) indicano che sono trattati come normali hit in primo piano. Ora vengono visualizzati nella reportistica normale e questo influisce anche sull’attribuzione. Questa configurazione in genere è utile solo per mantenere la coerenza con le implementazioni legacy.

Consigliamo invece di “includere hit in background” in una [suite di rapporti virtuale](/help/components/vrs/vrs-about.md). Questo consente di visualizzare gli hit che però non influiranno negativamente sul numero di visite e visitatori.
Le classificazioni mobili vengono abilitate dopo l’abilitazione di **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

Le classificazioni vengono utilizzate per categorizzare i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come “termini musicali pop” e generare rapporti sul successo di tale categoria in relazione a metriche quali istanze, o click-through, e conversione in eventi di successo.

| Classificazione | Definizione |
|--- |--- |
| Data primo avvio | Data del primo avvio dopo l’installazione o la reinstallazione.   GG/MM/AAAA |
| ID app | Memorizza il nome e la versione dell&#39;applicazione nel seguente formato:   `[AppName] [BundleVersion]`  Ad esempio, `myapp 1.1.` |
| Numero avvii | Numero di volte per cui l’applicazione è stata avviata o portata in primo piano. |
| Giorni dal primo utilizzo | Numero di giorni dalla prima esecuzione. |
| Giorni dall’ultimo utilizzo | Numero di giorni dall’ultimo utilizzo. |
| Ora del giorno | Misura l’ora in cui è stata avviata l’app (nel formato numerico a 24 ore). Utilizzato per la suddivisione del tempo per determinare le ore di utilizzo di picco. |
| Giorno della settimana | Numero del giorno della settimana in cui è stata avviata l’app. |
| Nome del dispositivo | Memorizza il nome del dispositivo.  Stringa di due cifre separate da virgola che identifica il dispositivo. Di norma il primo numero rappresenta la generazione del dispositivo e il secondo numero indica le versioni di diversi membri della famiglia di dispositivi. |
| Versione sistema operativo | Versione del sistema operativo. |
| Risoluzione | Larghezza x altezza in pixel reali. |
| Valore del ciclo di vita (eVar) | Compilato dai metodi trackLifetimeValue. |
| Origine acquisizione |  |
| Canale di acquisizione |  |
| Termine di acquisizione |  |
| Contenuto acquisizione |  |
| Nome acquisizione |  |
| Posizione (fino a 10 km) | Compilata dai metodi trackLocation. |
| Posizione (fino a 100 m) | Compilata dai metodi trackLocation. |
| Posizione (fino a 1 m) | Compilata dai metodi trackLocation. |
| Nome del punto di interesse | Compilato dai metodi trackLocation quando il dispositivo si trova entro un punto di interesse definito. |
| Distanza dal centro del punto di interesse | Compilata dai metodi trackLocation quando il dispositivo si trova in un punto di interesse definito. |
| ID messaggio in-app |  |
| Messaggio in-app online |  |
| Consenso push |  |
| ID payload |  |
