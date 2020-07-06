---
description: Istruzioni su come eseguire  Ad hoc analysis con Java 11.
title: Eseguire Ad Hoc Analysis con Java 11
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 4%

---


# Eseguire Ad Hoc Analysis con Java 11

Per eseguire  Ad hoc analysis con Java 11, è necessario seguire i passaggi aggiuntivi rispetto all&#39;esecuzione con Java 8.

## Prerequisiti

Collaborate con il team IT per garantire che siano disponibili le seguenti soluzioni:

* È necessario installare Java 11 con la variabile di ambiente *JAVA_HOME* impostata
* È necessario installare JavaFX, con la variabile di ambiente *PATH_TO_FX_SDK* indicata nella directory JavaFX SDK. Ad esempio, *PATH_TO_FX_SDK=/homedir/javafx-sdk-11.0.2* su un Mac oppure *PATH_TO_FX_SDK=C:\Users\username\javafx-sdk-11.0.2* su un PC.

## Installare  Ad hoc analysis per Java 11

1. Vai a **[!UICONTROL Analytics > Tools > Ad Hoc Analysis]**.
1. Fai clic su **[!UICONTROL Ad Hoc Analysis (Java 11)]**. Questo scarica un file zip.
1. Decomprimete il file scaricato.
1. **Selezionate il file**.bat (PC) o .sh (Mac). Selezionate il file del centro dati appropriato guardando il numero che segue &quot;sc&quot; nell&#39;URL di Adobe  Analytics. (3 = LON, 4 = SIN, 5 = PNW) Se si utilizza un PC, verificare se si sta eseguendo un sistema operativo Windows a 32 bit o a 64 bit andando su &#39;Informazioni sul PC&#39;. Quindi selezionate il file .bat appropriato.
1. **Eseguire il file** selezionato. Per PC: Fate doppio clic sul file .bat. Per Mac: Fate clic con il pulsante destro del mouse sul file .sh, quindi selezionate **[!UICONTROL Open With > Other... > Utilities > (Enable all applications) > select Terminal > Open]**.
1. Accedete a  Ad hoc analysis.

>[!NOTE]
>
>I metodi di autenticazione federati e  Enterprise ID non sono compatibili con la versione Java 11 di  Ad hoc analysis.

## Funzioni non supportate in  Ad hoc analysis (Java 11)

Nella versione Java 11 sono presenti alcune limitazioni note compatibili con  Ad hoc analysis:

* I metodi di autenticazione delle Enterprise ID federate e  non sono supportati.
* I sistemi operativi Linux non sono supportati.
* Quando utilizzate un Mac, non utilizzate il menu dell&#39;applicazione Mac (incluso *cmd + Q*). Ciò potrebbe causare  Ad hoc analysis alla chiusura senza alcun avviso. Utilizzate invece il menu all&#39;interno  Ad hoc analysis.
* La visualizzazione Analisi del sito non è supportata se viene eseguita  Ad hoc analysis in Mac OS.

## Domande frequenti

**D: Ricevo un errore &quot;Impossibile trovare \bin\javaw&quot; (esempio di seguito) - cosa devo fare?**

![](/help/analyze/ad-hoc-analysis/assets/error-java.png)

A: Se si verifica questo errore, collaborare con il team IT per impostare la variabile di ambiente *JAVA_HOME* necessaria per eseguire  Ad hoc analysis in Java 11.
