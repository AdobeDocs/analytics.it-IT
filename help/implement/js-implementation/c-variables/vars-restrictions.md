---
description: Caratteri e stringhe non consentiti nelle variabili JavaScript.
keywords: Implementazione di Analytics
seo-description: Caratteri e stringhe non consentiti nelle variabili JavaScript.
seo-title: Caratteri JavaScript non validi
solution: Analytics
subtopic: Variabili
title: Caratteri JavaScript non validi
topic: Sviluppatore e implementazione
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Caratteri JavaScript non validi

Caratteri e stringhe non consentiti nelle variabili JavaScript.

* Scheda (0x09)
* Ritorno a capo (0x0D)
* Newline (0x0A)
* caratteri ASCII con codici superiori a 127 (a meno che i caratteri multibyte non siano attivati e *`charSet`* siano compilati in modo appropriato)
* Tag HTML (ad esempio <b></b> &amp;#153)

Molte variabili, in particolare prodotti, gerarchia ed eventi, presentano limitazioni o requisiti di sintassi aggiuntivi. Per le limitazioni delle singole variabili e i requisiti di sintassi, consultare la sezione corrispondente ai parametri delle *`s_account`* variabili.
