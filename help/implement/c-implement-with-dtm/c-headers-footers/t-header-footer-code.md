---
description: Utilizzate Gestione tag dinamica per aggiungere codice di intestazione e piè di pagina che determini il caricamento di JavaScript e del contenuto della pagina sul sito. È necessario installare sia il codice di intestazione che il codice di piè di pagina in ogni pagina del sito, indipendentemente dall'opzione di hosting utilizzata.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;embed tab;embed
solution: Analytics
title: Aggiungere un codice intestazione e piè di pagina
topic: Developer and implementation
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Aggiungere un codice intestazione e piè di pagina

Utilizzate Gestione tag dinamica per aggiungere codice di intestazione e piè di pagina che determini il caricamento di JavaScript e del contenuto della pagina sul sito. È necessario installare sia il codice di intestazione che il codice di piè di pagina in ogni pagina del sito, indipendentemente dall'opzione di hosting utilizzata.

Poiché Gestione tag dinamica include un frammento di codice sia nell’intestazione che nel piè di pagina, è possibile eseguire regole all’inizio o alla fine di una pagina. Questa capacità consente di implementare strumenti di test e altre tecnologie, mantenendo al contempo il controllo sul tracciamento delle pagine.

Gestione tag dinamica crea codici di incorporamento per l'area di produzione e l'area di produzione che consentono di verificare le modifiche apportate all'ambiente di staging prima di apportare modifiche all'ambiente di produzione.

>[!IMPORTANT]
>
>Per una corretta implementazione, è fondamentale che tu segua queste istruzioni come visualizzate nella Guida di Adobe. Nello specifico, è necessario inserire il codice di intestazione nella `<head>` sezione dei modelli di documento. Inoltre, è necessario posizionare il codice piè di pagina subito prima del `</body>` tag di chiusura. Posizionare uno di questi codici da incorporare altrove nel codice o utilizzare metodi asincroni per aggiungere i codici da incorporare o racchiudere i codici da incorporare in qualsiasi modo, *non* sono implementazioni supportate di Gestione tag dinamica. I codici da incorporare devono essere implementati esattamente come previsto.
>
>Un'implementazione non supportata darà risultati imprevisti e impedirà all'Assistenza clienti e all'Ingegneria di fornire assistenza nell'implementazione.

1. Nell'interfaccia Gestione tag dinamica, aprite la [!UICONTROL Embed] scheda e selezionate l'opzione di hosting (ad esempio Akamai), quindi passate a "On".

   Passaggio 1. Copiate il codice dell'intestazione di produzione fornito nella scheda Incorpora di Gestione tag dinamica e inseritelo nella [!DNL HEAD] sezione HTML del sito.

   ![](assets/dtm-embed.png)

   Posiziona il codice vicino al [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] tag come possibile. Questo frammento di codice deve essere inserito in ogni pagina del sito di produzione live.

   >[!NOTE]
   >
   >Il codice da incorporare produzione riflette solo gli elementi pubblicati in quella [proprietà](/help/implement/c-implement-with-dtm/t-create-web-property.md). Tuttavia, il codice da incorporare per l'staging riflette tutti gli elementi della proprietà associata, indipendentemente dallo stato Pubblicato o Non pubblicato. Per testare gli elementi non pubblicati sul sito di produzione, abilitate l'staging locale nella console seguendo le istruzioni riportate in [Test delle regole non pubblicate per l'hosting](/help/implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md)di Akamai.

1. Copiate il codice piè di pagina di produzione e inseritelo nella [!DNL BODY] sezione HTML del sito.

   Posiziona il codice vicino al [!DNL </body>] tag come possibile.
1. Copiate l'intestazione e il codice piè di pagina dell'area di gestione temporanea, quindi ripetete i passaggi descritti sopra nel sito dell'area di gestione temporanea.

   >[!NOTE]
   >
   >La differenza tra gli snippet di codice di produzione e di gestione temporanea è l'aggiunta del nome [!DNL -staging] di file nella versione di verifica. Il codice piè di pagina rimane invariato nell'area di gestione temporanea e nella produzione.

