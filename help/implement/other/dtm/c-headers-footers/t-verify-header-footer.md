---
description: Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;code;page code;header code;footer code;embed code;verify code;verify header code;verify footer code;embed tab;embed
title: Verificare il codice di intestazione e piè di pagina
topic: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: 82cf5ddfd4d18af09c2dbedba20514e4b643a94b
workflow-type: tm+mt
source-wordcount: '128'
ht-degree: 7%

---


# Verificare il codice di intestazione e piè di pagina

Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.

1. Aprite il sito nel browser.
1. Aprite il modulo [!UICONTROL Developer Console] facendo clic con il pulsante destro del mouse e scegliendo **[!UICONTROL Inspect Element]** > **[!UICONTROL Console]**.
1. Premere **[!UICONTROL Enter]**.

   Se il codice è stato installato correttamente, verrà visualizzata *`true`* nella console.

   Se il codice non è stato installato correttamente, verrà visualizzato l&#39;errore di riferimento:

   `_satellite is not defined`

   Se ricevi questo errore, accertati che:

* Avete incluso il codice di intestazione completo in ogni pagina del sito nella [!DNL HEAD] sezione, il più vicino possibile al `<head>` tag .
* Non sono presenti caratteri imprevisti nello snippet di codice, che possono essere generati dalla copia e dall&#39;incolla di un documento formattato.

