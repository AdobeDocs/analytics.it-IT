---
description: Istruzioni su come eseguire Analisi ad hoc con Java 11.
seo-description: Istruzioni su come eseguire Analisi ad hoc con Java 11.
seo-title: Analisi ad hoc e Java 11
title: Eseguire Analisi ad hoc con Java 11
translation-type: tm+mt
source-git-commit: 23bdb0c24416c376ec1df7b609a5794dbf8886f2

---


# Eseguire Analisi ad hoc con Java 11

Durante l'esecuzione di Analisi ad hoc con Java 11, è necessario seguire ulteriori passaggi rispetto a Java 8.

## Prerequisiti

Collabora con il team IT per assicurarti che sia presente quanto segue:

* Java 11 must be installed, with *JAVA_HOME* environment variable set
* JavaFX must be installed, with the *PATH_TO_FX_SDK* environment variable pointed to the JavaFX SDK directory. For example, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* on a Mac, or *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* on a PC.

## Installazione di Analisi ad hoc per Java 11

1. **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]** Vai a.
1. Fai clic su **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Viene scaricato un file zip.
1. Estraete il file scaricato.
1. **Selezionate il file. bat (PC) o. sh (Mac)**. Selezionate il file datacenter appropriato guardando il numero «sc» nell'URL di Adobe Analytics. (3 = LON, 4 = SIN, 5 = PNW) Se utilizzate un PC, verificate che stiate eseguendo un sistema operativo Windows a 32 bit o a 64 bit scegliendo «About your PC» (Informazioni sul PC). Quindi selezionate il file. bat appropriato.
1. **Eseguite il file selezionato**. Per PC: Doubleclick the. bat file. For Mac: Right-click the .sh file, then select **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Accedi ad Analisi ad hoc.

>[!Note]
>
> I metodi di autenticazione Federated ed Enterprise ID non sono compatibili con la versione Java 11 di Analisi ad hoc.

## Funzioni non supportate in Analisi ad hoc (Java 11)

Nella versione Java 11 sono disponibili alcune limitazioni conosciute compatibili con Analisi ad hoc:

* I metodi di autenticazione Federated &amp; Enterprise ID non sono supportati.
* I sistemi operativi Linux non sono supportati.
* When using a Mac, do not use the Mac application menu (including *cmd + Q*). Ciò potrebbe causare la chiusura di Analisi ad hoc senza un avviso. Utilizzate invece il menu all'interno di Analisi ad hoc.
* La visualizzazione Analisi sito non è supportata quando si esegue Analisi ad hoc su macos.

## Domande frequenti

**Q: Ottengo un errore "Impossibile trovare\ bin\ javaw" (esempio di seguito): cosa devo fare?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A: If you get this error, work with your IT team to set the *JAVA_HOME* environment variable which is required to run Ad Hoc Analysis in Java 11.