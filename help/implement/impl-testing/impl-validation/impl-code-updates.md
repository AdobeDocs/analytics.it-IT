---
description: La verifica di eventuali modifiche al file .JS o al codice HTML è responsabilità del cliente. Deve essere compilato prima di pubblicare le modifiche sui siti web di produzione.
keywords: Analytics Implementation
solution: Analytics
title: Modifiche al codice
topic: Developer and implementation
uuid: efac045e-15f5-45f6-a21a-de6c4b0a8185
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Modifiche al codice

La verifica di eventuali modifiche al file .JS o al codice HTML è responsabilità del cliente. Deve essere compilato prima di pubblicare le modifiche sui siti web di produzione.

Verificate che i caratteri linefeeds/return non vengano rimossi o modificati dal codice inserito all'interno dell'HTML o dall'interno del [!DNL .JS] file. Assicurarsi che il codice JavaScript venga eseguito senza errori su tutte le pagine e i modelli di pagina (in Opzioni Internet Explorer, selezionare la scheda Avanzate e fare clic su Visualizza una notifica su ogni errore di script in Internet Explorer).

Quando si verificano degli errori, incollare il codice in una pagina HTML predefinita per determinare se l'errore si verifica a causa di altri elementi/oggetti della pagina.

```js
<html><head></head><body>
...paste code here to debug...
</body></html>
```

