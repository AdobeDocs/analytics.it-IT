---
description: L’abilitazione della gestione delle app attiva le variabili della soluzione mobile che catturano il ciclo di vita e altre metriche dalle applicazioni mobili.
title: Gestione app
feature: Strumenti di amministrazione
exl-id: ec19695a-2961-45e4-bf44-434f0ff9e3c9
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 32%

---

# Gestione app

L’abilitazione della gestione delle app attiva le variabili della soluzione mobile che catturano il ciclo di vita e altre metriche dalle applicazioni mobili.

Questa integrazione tra Adobe Analytics e Mobile Services:

* Consente di condividere i dati KPI (Key Performance Indicator) da Mobile Services ad Adobe Analytics.
* Consente di abilitare il tracciamento della posizione.
* Aggiunge nuovi rapporti in Analytics > Rapporti > App mobile.
* Aggiunge 25 nuove classificazioni mobili di Adobe.
* Aggiunge 5 nuove metriche Adobe Mobile.
* Aggiunge un nuovo Adobe di dimensioni di Mobile.
* Sincronizza i dati con Analytics ogni 15 minuti

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

## Passaggio 1: Abilitare i rapporti app {#section_FBADF80AED2B4978A904ABB770B3B931}

Abilita App Reports v3.0 per misurare le metriche seguenti:

* **Acquisizione** : tieni traccia degli URL di riferimento per le campagne di download delle app.
* **Ciclo di vita** : livello base di reporting fornito dalla misurazione inviata a ogni avvio dell&#39;app.
* **Azioni app** : rapporti e percorsi basati sulle azioni in-app.
* **Valore del ciclo di vita** : scopri come cresce nel tempo il valore degli utenti utilizzando KPI per le app (come acquisti, visualizzazioni di annunci, visualizzazioni di video completate, condivisioni social, caricamenti di foto).
* **Eventi temporizzati** : misura quanto tempo (in-app e totale) intercorre tra le azioni chiave dell’app (ad esempio il tempo che trascorre prima del primo acquisto).

## Passaggio 2: Abilita tracciamento posizione {#section_2CCBD205191C4CA3B7B71A6F11FF97EC}

L’abilitazione del tracciamento della posizione consente di:

* Tieni traccia dei dati di latitudine e longitudine e crea rapporti su di essi in Analysis Workspace e Mobile Services.
* Identifica, crea e visualizza punti di interesse specifici in Mobile Services. I POI devono essere definiti nel file di configurazione dell’SDK per dispositivi mobili.
* Tracciare i beacon Bluetooth (UUID, principale, secondario e prossimità).

## Passaggio 3: (Facoltativo) Attivare/disattivare rapporti legacy e attribuzione per hit in background {#section_1708BCAA87AA4884986F7532759C5DD4}

Gli hit in background abilitati (gli hit generati quando l’app è in background) indicano che sono trattati come hit in primo piano regolari. Ora vengono visualizzati con rapporti regolari e questo influisce anche sull’attribuzione. Questa configurazione è in genere utile solo per mantenere la coerenza con le implementazioni legacy.

È invece consigliabile &quot;includere hit di background&quot; in una [suite di rapporti virtuali](/help/components/vrs/vrs-about.md). Questo ti consente di visualizzare gli hit ma questi non influiranno negativamente sul numero di visite e visitatori.
Le classificazioni mobili sono abilitate dopo l’abilitazione di **[!UICONTROL App Management]** > **[!UICONTROL App Reporting]**.

Le classificazioni vengono utilizzate per classificare i valori in gruppi e generare rapporti a livello di gruppo. Ad esempio, puoi classificare tutte le campagne di ricerca a pagamento in una categoria come &quot;termini musicali pop&quot; e generare rapporti sul successo di tale categoria in relazione a metriche quali Istanze (ad esempio, click-through) e conversione in eventi di successo.

| Classificazione | Definizione |
|--- |--- |
| Data primo avvio | Data del primo avvio dopo l&#39;installazione o reinstallazione.   DD/MM/YYYY |
| ID app | Memorizza il nome e la versione dell&#39;applicazione nel seguente formato:   `[AppName] [BundleVersion]`  Ad esempio, `myapp 1.1.` |
| Numero di avvii | Numero di volte per cui l’applicazione è stata avviata o portata in primo piano. |
| Giorni dal primo utilizzo | Numero di giorni dalla prima esecuzione. |
| Giorni dall’ultimo utilizzo | Numero di giorni dall’ultimo utilizzo. |
| Ora del giorno | Misura l’ora in cui è stata avviata l’app (nel formato numerico a 24 ore). Utilizzato per la suddivisione del tempo per determinare le ore di utilizzo di picco. |
| Giorno della settimana | Numero del giorno della settimana in cui è stata avviata l’app. |
| Nome del dispositivo | Memorizza il nome del dispositivo.  Stringa di due cifre separate da virgola che identifica il dispositivo Di norma il primo numero rappresenta la generazione del dispositivo e il secondo numero indica membri diversi della famiglia di dispositivi. |
| Versione sistema operativo | Versione del sistema operativo. |
| Risoluzione | Larghezza x altezza in pixel reali. |
| Valore del ciclo di vita (eVar) | Viene compilata dai metodi trackLifetimeValue. |
| Origine acquisizione |  |
| Canale di acquisizione |  |
| Termine di acquisizione |  |
| Contenuto acquisizione |  |
| Nome acquisizione |  |
| Posizione (fino a 10 km) | Viene compilata dai metodi trackLocation. |
| Posizione (fino a 100 m) | Viene compilata dai metodi trackLocation. |
| Posizione (fino a 1 m) | Viene compilata dai metodi trackLocation. |
| Nome del punto di interesse | Viene compilata dai metodi trackLocation quando il dispositivo si trova entro un POI definito. |
| Distanza dal centro del punto di interesse | Viene compilata dai metodi trackLocation quando il dispositivo si trova entro un POI definito. |
| ID messaggio in-app |  |
| Messaggi in-app online |  |
| Consenso push |  |
| ID payload |  |
