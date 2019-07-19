---
description: Utilizzate Gestione tag dinamica per aggiungere un codice intestazione e piè di pagina che determini il caricamento di javascript e del contenuto della pagina sul sito. È necessario installare sia il codice header che il codice piè di pagina su ogni pagina del sito, indipendentemente dall'opzione di hosting utilizzata.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; code; codice della pagina; codice di intestazione; codice piè di pagina; codice da incorporare; scheda embed; embed
seo-description: Utilizzate Gestione tag dinamica per aggiungere un codice intestazione e piè di pagina che determini il caricamento di javascript e del contenuto della pagina sul sito. È necessario installare sia il codice header che il codice piè di pagina su ogni pagina del sito, indipendentemente dall'opzione di hosting utilizzata.
seo-title: Aggiungere un codice intestazione e piè di pagina
solution: Analytics
title: Aggiungere un codice intestazione e piè di pagina
topic: Sviluppatore e implementazione
uuid: 23 d 89 ae 0-340 a -4 b 12-91 d 1-953 b 4613 c 98 e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Aggiungere un codice intestazione e piè di pagina

Utilizzate Gestione tag dinamica per aggiungere un codice intestazione e piè di pagina che determini il caricamento di javascript e del contenuto della pagina sul sito. È necessario installare sia il codice header che il codice piè di pagina su ogni pagina del sito, indipendentemente dall'opzione di hosting utilizzata.

Dato che Gestione tag dinamica include uno snippet di codice sia nell'intestazione che nel piè di pagina, puoi eseguire regole all'inizio o alla fine di una pagina. Questa capacità consente di implementare strumenti di testing e altre tecnologie, mantenendo il controllo sul monitoraggio delle pagine.

Gestione tag dinamica crea codici da incorporare di produzione e produzione per testare le modifiche nell'ambiente di staging prima di inviare modifiche all'ambiente di produzione.

>[!IMPORTANT]
>
>Per un'implementazione corretta, è importante seguire queste istruzioni così come sono visualizzate nell'Aiuto di Adobe. Specifically, you must place the header code in the `<head>` section of your document templates. Also, you must place the footer code just before the closing `</body>` tag. Placing either of these embed codes elsewhere in your markup, or using asynchronous methods to append the embed codes, or wrapping the embed codes in any way, are *not* a supported implementations of Dynamic Tag Management. I codici da incorporare devono essere implementati esattamente come fornito.
>
>Un'implementazione non supportata darà risultati imprevisti e impedisce all'Assistenza clienti e all'ingegneria di essere assistiti con la tua implementazione.

1. In the Dynamic Tag Management interface, open the [!UICONTROL Embed] tab and select your hosting option (such as Akamai), then toggle the switch to "On."

   Risultato 1. Copy the production header code provided in the Embed tab of Dynamic Tag Management and place it within the [!DNL HEAD] section of your site HTML.

   ![](assets/dtm-embed.png)

   Place the code as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] possibile. Questo snippet di codice deve essere inserito in ogni pagina del sito di produzione live.

   >[!NOTE]
   >
   >Production embed code reflects only the published items in that [property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). Tuttavia, il codice da incorporare per la verifica riflette tutti gli elementi della proprietà associata, indipendentemente dallo stato pubblicato o non pubblicato. To test unpublished items on your production site, locally enable staging in the console by following the instructions in [Test Unpublished Rules for Akamai Hosting](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259).

1. Copy the production footer code and place it in the [!DNL BODY] section of your site HTML.

   Place the code as close to the [!DNL </body>] possibile.
1. Copiate l'intestazione di staging e il codice piè di pagina, quindi ripetete i passaggi riportati sopra sul sito di staging.

   >[!NOTE]
   >
   >The difference between production and staging code snippets is the addition of [!DNL -staging] to the filename in the staging version. Il codice piè di pagina resta invariato in staging e produzione.

