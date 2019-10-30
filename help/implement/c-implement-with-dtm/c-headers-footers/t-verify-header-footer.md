---
description: Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.
keywords: Analytics Implementation;metodo di implementazione;gestione tag dinamica;dtm;codice;codice pagina;codice intestazione;codice piè di pagina;codice incorporato;verifica codice intestazione;verifica codice intestazione;verifica codice piè di pagina;scheda incorpora;embed
seo-description: Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.
seo-title: Verificare il codice di intestazione e piè di pagina
solution: Analytics
title: Verificare il codice di intestazione e piè di pagina
topic: Sviluppatore e implementazione
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Verificare il codice di intestazione e piè di pagina

Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.

1. Aprite il sito nel browser.
1. Aprite il modulo [!UICONTROL Developer Console] facendo clic con il pulsante destro del mouse e scegliendo **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Premere **[!UICONTROL Enter]**.

   Se il codice è stato installato correttamente, verrà visualizzata *`true`* nella console.

   Se il codice non è stato installato correttamente, verrà visualizzato l'errore di riferimento:

   `_satellite is not defined`

   Se ricevi questo errore, assicurati che:

* Hai incluso il codice di intestazione completo in ogni pagina del sito nella [!DNL HEAD] sezione, accanto al [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] tag come possibile.
* Non sono presenti caratteri imprevisti nello snippet di codice, che possono essere generati dalla copia e dall'incolla di un documento formattato.

