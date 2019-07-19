---
description: Caratteri e stringhe non consentite nelle variabili javascript.
keywords: Implementazione di Analytics
seo-description: Caratteri e stringhe non consentite nelle variabili javascript.
seo-title: Caratteri javascript non validi
solution: Analytics
subtopic: Variabili
title: Caratteri javascript non validi
topic: Sviluppatore e implementazione
uuid: 04 e 3 b 4 b 4-7 ff 5-4673-8060-34302 b 6 ee 545
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Caratteri javascript non validi

Caratteri e stringhe non consentite nelle variabili javascript.

* Tab (0 x 09)
* Ritorno a capo (0 x 0 D)
* Newline (0 x 0 A)
* ASCII characters with codes above 127 (unless multi-byte characters are enabled and *`charSet`* is populated appropriately)
* HTML tags (e.g. <b></b> or &amp;#153)

Molte variabili, soprattutto prodotti, gerarchia ed eventi, presentano limitazioni aggiuntive o requisiti di sintassi. For individual variable limitations and syntax requirements, see the section corresponding to the *`s_account`* variable parameters.
