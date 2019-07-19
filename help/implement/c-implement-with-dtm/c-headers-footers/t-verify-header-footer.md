---
description: Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.
keywords: Implementazione di Analytics; metodo di implementazione; gestione tag dinamica; dtm; code; codice della pagina; codice di intestazione; codice piè di pagina; codice da incorporare; verify code; verificare il codice dell'intestazione; verificare il codice piè di pagina; scheda embed; embed
seo-description: Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.
seo-title: Verificare il codice di intestazione e piè di pagina
solution: Analytics
title: Verificare il codice di intestazione e piè di pagina
topic: Sviluppatore e implementazione
uuid: d 395 a 417-0 c 61-41 a 6-a 124-d 2 f 400 f 4626 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Verificare il codice di intestazione e piè di pagina

Verifica che la libreria Gestione tag dinamica sia caricata correttamente sul sito.

1. Aprite il sito nel browser.
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   Se il codice non è stato installato correttamente, viene visualizzato l'errore di riferimento:

   `_satellite is not defined`

   Se ricevi questo errore, assicurati che:

* You have included the full header code on every page of the site in the [!DNL HEAD] section, as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] possibile.
* Non sono presenti caratteri imprevisti che compaiono nello snippet di codice, possibile a causa di copia e incolla da un documento formattato.

