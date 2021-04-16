---
description: Utilizza Dynamic Tag Management per aggiungere codice di intestazione e piè di pagina che determina il caricamento di JavaScript e del contenuto della pagina sul sito. È necessario installare sia il codice intestazione che il codice piè di pagina in ogni pagina del sito, indipendentemente dall'opzione di hosting utilizzata.
keywords: Implementazione di Analytics;metodo di implementazione;gestione tag dinamica;dtm;codice;codice pagina;codice intestazione;codice piè di pagina;codice di incorporamento;scheda incorporamento;incorporamento
title: Aggiungere un codice intestazione e piè di pagina
topic-fix: Developer and implementation
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
exl-id: 170c28fb-8884-4c44-b586-f88a7583083e
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '493'
ht-degree: 2%

---

# Aggiungere un codice intestazione e piè di pagina

Utilizza Dynamic Tag Management per aggiungere codice di intestazione e piè di pagina che determina il caricamento di JavaScript e del contenuto della pagina sul sito. È necessario installare sia il codice intestazione che il codice piè di pagina in ogni pagina del sito, indipendentemente dall&#39;opzione di hosting utilizzata.

Poiché Dynamic Tag Management include uno snippet di codice sia nell’intestazione che nel piè di pagina, è possibile eseguire regole all’inizio o alla fine di una pagina. Questa funzionalità ti consente di implementare strumenti di test e altre tecnologie mantenendo il controllo sul tracciamento delle pagine.

Dynamic Tag Management crea codici di incorporamento di staging e produzione che puoi utilizzare per testare le modifiche nell’ambiente di staging prima di inviare le modifiche all’ambiente di produzione.

>[!IMPORTANT]
>
>Per una corretta implementazione, è fondamentale seguire queste istruzioni come visualizzate nell&#39;Aiuto di Adobe. In particolare, è necessario inserire il codice di intestazione nella sezione `<head>` dei modelli di documento. Inoltre, è necessario posizionare il codice a piè di pagina immediatamente prima del tag di chiusura `</body>` . Posizionare uno di questi codici da incorporare altrove nel markup, o utilizzare metodi asincroni per aggiungere i codici da incorporare, o racchiudere i codici da incorporare in qualsiasi modo, sono *non* implementazioni supportate di Dynamic Tag Management. I codici di incorporamento devono essere implementati esattamente come è stato fornito.
>
>Un’implementazione non supportata darà risultati imprevisti e impedirà all’assistenza clienti e al reparto tecnico di fornire assistenza nell’implementazione.

1. Nell’interfaccia Dynamic Tag Management, apri la scheda [!UICONTROL Embed] e seleziona l’opzione di hosting (ad esempio Akamai), quindi attiva il pulsante.

   Passaggio 1: Copia il codice di intestazione di produzione fornito nella scheda Incorpora di Dynamic Tag Management e inseriscilo nella sezione [!DNL HEAD] del sito HTML.

   ![](assets/dtm-embed.png)

   Posiziona il codice il più vicino possibile al tag `<head>` . Questo frammento di codice deve essere posizionato su ogni pagina del sito di produzione live.

   >[!NOTE]
   >
   >Il codice di incorporamento di produzione riflette solo gli elementi pubblicati in quella [proprietà](/help/implement/other/dtm/t-create-web-property.md). Tuttavia, il codice di incorporamento per la gestione temporanea riflette tutti gli elementi nella proprietà associata, indipendentemente dallo stato pubblicato o non pubblicato. Per testare gli elementi non pubblicati sul sito di produzione, abilita lo staging locale nella console seguendo le istruzioni in [Test delle regole non pubblicate per Akamai Hosting](/help/implement/other/dtm/c-rules/t-test-rules-akamai.md).

1. Copia il codice a piè di pagina di produzione e inseriscilo nella sezione [!DNL BODY] del sito HTML.

   Posiziona il codice il più vicino possibile al tag `</body>` .
1. Copia il codice di intestazione e piè di pagina di staging, quindi ripeti i passaggi sopra descritti sul tuo sito di staging.

   >[!NOTE]
   >
   >La differenza tra snippet di codice di produzione e di staging è l’aggiunta di [!DNL -staging] al nome del file nella versione di staging. Il codice a piè di pagina rimane lo stesso in fase di staging e produzione.
