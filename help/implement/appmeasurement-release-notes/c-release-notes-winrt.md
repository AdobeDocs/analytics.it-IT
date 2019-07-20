---
description: nulle
seo-description: nulle
seo-title: Winrt per Windows 8
solution: Analytics, Marketing Cloud
subtopic: Note sulla versione
title: Winrt per Windows 8
topic: Sviluppatore e implementazione
uuid: cec 19 d 63-114 c -4 ef 6-a 55 e-db 6 aad 4 e 948 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# WinRT for Windows 8{#winrt-for-windows}

>[!NOTE]
>
>Per trovare la versione corrente della libreria, attivare la registrazione di debug.

[I download](https://marketing.adobe.com/developer/get-started/mobile/c-measuring-mobile-applications) delle librerie mobili [!DNL Developer Connection]sono disponibili.

>[!NOTE]
>
>The [!DNL WinRT] for [!DNL Windows] 8 SDK is replaced by the [Windows 8.1 Universal App Store](../appmeasurement-release-notes/c-release-notes-winu.md#concept_79EEB87B0FEC4F6DB11BE8ED417A970E) SDK. Nell'SDK non si verifica alcun ulteriore sviluppo.

## Versione 4.0 {#section_248BF5A38F1843A5BCF6DBD62A5D3D59}

Data di rilascio: **17 giugno 2014**

Nuova versione con nuove funzioni, tra cui geolocalità, valore del ciclo di vita, azioni temporizzate e supporto di consenso.

## Version 3.1.1 {#section_6E925545B72240BB816DA2333CA93E46}

Release Date: **May 22, 2014**

Correzioni di bug e miglioramenti delle prestazioni.

## Versione 3.1.0 {#section_F9059928B6FE43C99322A0DA35EB85C3}

Data di rilascio: **17 ottobre 2013**

* [!DNL Windows] Compatibilità 8.1

## Version 3.0.5 {#section_8F163FF1E88142F180091A88C9FD9D12}

Data di rilascio:**18 aprile 2013**

* È stato corretto un problema a causa del quale talvolta era possibile calcolare erroneamente la durata della sessione precedente.

## Version 3.0.4 {#section_FD242F9BA3D1481090E45998883E4CDD}

Release Date: **March 21, 2013**

* `ADMS_Measurement.visitorID` viene ora precompilato con il valore predefinito.
* È stato risolto un problema relativo al recupero delle informazioni sul dispositivo.

## Version 3.0.3 {#section_5865E881249441ADBB03A9637548650F}

Data di rilascio:**21 febbraio 2013**

* Deprecated `offlineThrottleDelay` as the setting is no longer necessary due to thread optimization. L'impostazione esiste ancora per mantenere compatibilità con versioni precedenti, ma non ha più effetti.
* `DayOfWeek` è ora basato su 1 a partire da Domenica per corrispondere ai valori raccolti su altre piattaforme.
* Aggiunta automatica di sottoscrizione ai listener di eventi in trackinghelper. js per semplificare il tracciamento del ciclo di vita.

## Version 3.0.2 {#section_CCFAE5A29FB14DAD9A9F14FE8EE09B75}

Release Date: **November 2012**

* La risoluzione dello schermo viene ora raccolta con precisione per le piattaforme C #, C + + e HTML 5/winjs.
* `ADMS_Churn` è ora interna. Per utilizzare le best practice per il tracciamento del ciclo di vita dell'applicazione, usa le chiamate seguenti:

   ```
   public void ADMS_Measurement.StartSession(); 
   public void ADMS_Measurement.StopSession();
   ```

* Added `public double maxSessionLength` variable to `ADMS_Measurement` to allow you to set a maximum session length for the previous user session. Se la lunghezza della sessione registrata supera il massimo, verrà inviata la lunghezza massima della sessione. Default `maxSessionLength` is 3600 (seconds).
* Added a `lifecycleSessionTimeout` configuration variable that lets you specify the length of time, in seconds, that must elapse between app launches before the launch is considered a new session.
* Aggiunta della nuova metrica Durata sessione precedente alle metriche del ciclo di vita.
* Trackinghelper aggiornato per motivi di chiarezza.
* Bug del modulo multimediale fisso.

## Version 3.0.1 {#section_EA2E5F8550C348BDB948A9236BD35619}

**Ottobre 2012**

Versione iniziale.
