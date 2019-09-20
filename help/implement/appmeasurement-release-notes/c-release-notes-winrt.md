---
description: nulle
seo-description: nulle
seo-title: WinRT per Windows 8
solution: Analytics,Experience Cloud
subtopic: Note sulla versione
title: WinRT per Windows 8
topic: Sviluppatore e implementazione
uuid: set19d63-114c-4ef6-a55e-db6aad4e948b
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# WinRT per Windows 8{#winrt-for-windows}

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivate la registrazione di debug.

I [download](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) della libreria mobile sono disponibili in [!DNL Developer Connection].

>[!NOTE]
>
>L’SDK [!DNL WinRT] per [!DNL Windows] 8 è sostituito dall’SDK [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E) . In questa SDK non si verificheranno ulteriori sviluppi.

## Versione 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Data di rilascio: **17 giugno 2014**

Nuova versione con nuove funzioni, tra cui geolocalità, valore del ciclo di vita, azioni temporizzate e supporto per l’iscrizione.

## Versione 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Release Date: **May 22, 2014**

Correzioni di bug e miglioramenti delle prestazioni.

## Versione 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Data di rilascio: **17 ottobre 2013**

* [!DNL Windows] Compatibilità 8.1

## Versione 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Data di rilascio:**18 aprile 2013**

* È stato risolto un problema che talvolta causava un calcolo errato della lunghezza della sessione precedente.

## Versione 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Release Date: **March 21, 2013**

* `ADMS_Measurement.visitorID` ora viene precompilato con il valore predefinito.
* È stato risolto un problema relativo al recupero delle informazioni sul dispositivo.

## Versione 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Data di rilascio:**21 febbraio 2013**

* Obsoleto `offlineThrottleDelay` perché l'impostazione non è più necessaria a causa dell'ottimizzazione del thread. L'impostazione esiste ancora per mantenere la compatibilità con le versioni precedenti, ma non ha più alcun effetto.
* `DayOfWeek` ora è basato su 1 a partire da domenica per corrispondere ai valori raccolti su altre piattaforme.
* Aggiunta della sottoscrizione automatica ai listener di eventi in TrackingHelper.js per semplificare il tracciamento del ciclo di vita.

## Versione 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Release Date: **November 2012**

* La risoluzione dello schermo viene ora raccolta con precisione per le piattaforme C#, C++ e HTML5/WinJS.
* `ADMS_Churn` la classe è ora interna. Per utilizzare le best practice per il tracciamento del ciclo di vita delle applicazioni, usa le seguenti chiamate:

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* È stata aggiunta `public double maxSessionLength` una variabile per `ADMS_Measurement` consentire di impostare una lunghezza massima di sessione per la sessione utente precedente. Se la lunghezza della sessione registrata supera il massimo, verrà inviata la lunghezza massima consentita. Il valore predefinito `maxSessionLength` è 3600 (secondi).
* Aggiunta una variabile di `lifecycleSessionTimeout` configurazione che consente di specificare il tempo, in secondi, che deve trascorrere tra gli avvii dell'app prima che l'avvio venga considerato una nuova sessione.
* Aggiunta della nuova metrica Durata sessione precedente alle metriche del ciclo di vita.
* TrackingHelper aggiornato per maggiore chiarezza.
* È stato corretto un bug del modulo multimediale.

## Versione 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**Ottobre 2012**

Versione iniziale.
