---
description: La verifica di eventuali modifiche al file. JS o HTML è responsabilità del cliente. Deve essere completato prima di pubblicare le modifiche ai siti Web di produzione.
keywords: Implementazione di Analytics
seo-description: La verifica di eventuali modifiche al file. JS o HTML è responsabilità del cliente. Deve essere completato prima di pubblicare le modifiche ai siti Web di produzione.
seo-title: Modifiche al codice
solution: Analytics
title: Modifiche al codice
topic: Sviluppatore e implementazione
uuid: efac 045 e -15 f 5-45 f 6-a 21 a-de 6 c 4 b 0 a 8185
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Modifiche al codice

La verifica di eventuali modifiche al file. JS o HTML è responsabilità del cliente. Deve essere completato prima di pubblicare le modifiche ai siti Web di produzione.

Ensure that the linefeeds/return characters are not stripped or altered from the code that is placed within the HTML, or from within the [!DNL .JS] file. Assicurarsi che javascript venga eseguito senza un errore su tutte le pagine e i modelli delle pagine (in Opzioni Internet Explorer, selezionate la scheda Avanzate e fate clic su Visualizza una notifica su ogni errore di script.

Durante la verifica di errori, incollate il codice in una pagina HTML predefinita per determinare se l'errore si verifica a causa di altri elementi/oggetti della pagina.

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

