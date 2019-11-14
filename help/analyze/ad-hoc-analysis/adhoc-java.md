---
description: Istruzioni su come eseguire Analisi ad hoc con Java 11.
title: Eseguire Ad Hoc Analysis con Java 11
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Eseguire Ad Hoc Analysis con Java 11

Per eseguire Analisi ad hoc con Java 11 è necessario seguire ulteriori passaggi rispetto all'esecuzione con Java 8.

## Prerequisiti

Collaborate con il team IT per garantire che siano disponibili le seguenti soluzioni:

* È necessario installare Java 11 con la variabile di ambiente *JAVA_HOME* impostata
* È necessario installare JavaFX, con la variabile di ambiente *PATH_TO_FX_SDK* indicata nella directory JavaFX SDK. Ad esempio, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* su un Mac oppure *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* su un PC.

## Installazione di Analisi ad hoc per Java 11

1. Vai a **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Fai clic su **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Questo scarica un file zip.
1. Decomprimete il file scaricato.
1. **Selezionate il file**.bat (PC) o .sh (Mac). Selezionate il file del centro dati appropriato guardando il numero seguente "sc" nell'URL di Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Se si utilizza un PC, verificare se si sta eseguendo un sistema operativo Windows a 32 bit o a 64 bit andando su 'Informazioni sul PC'. Quindi selezionate il file .bat appropriato.
1. **Eseguire il file** selezionato. Per PC: Fate doppio clic sul file .bat. Per Mac: Fate clic con il pulsante destro del mouse sul file .sh, quindi selezionate **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Accedi ad Analisi ad hoc.

> [!NOTE] I metodi di autenticazione Federated ID e Enterprise ID non sono compatibili con la versione Java 11 di Ad Hoc Analysis.

## Funzioni non supportate in Analisi ad hoc (Java 11)

Esistono alcune limitazioni note nella versione Java 11 compatibile con Analisi ad hoc:

* I metodi di autenticazione Federated e Enterprise ID non sono supportati.
* I sistemi operativi Linux non sono supportati.
* Quando utilizzate un Mac, non utilizzate il menu dell'applicazione Mac (incluso *cmd + Q*). Ciò potrebbe causare la chiusura dell'analisi ad hoc senza alcun avviso. Utilizzate invece il menu in Analisi ad hoc.
* La visualizzazione Analisi del sito non è supportata quando si esegue Analisi ad hoc in Mac OS.

## Domande frequenti

**D: Ricevo un errore "Impossibile trovare \bin\javaw" (esempio di seguito) - cosa devo fare?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A: Se ricevi questo errore, chiedi al team IT di impostare la variabile di ambiente *JAVA_HOME* necessaria per eseguire Analisi ad hoc in Java 11.
