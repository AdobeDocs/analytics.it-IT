---
description: Caratteri e stringhe non consentiti nelle variabili JavaScript.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Caratteri JavaScript non validi
topic: Developer and implementation
uuid: 04e3b4b4-7ff5-4673-8060-34302b6ee545
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Caratteri JavaScript non validi

Caratteri e stringhe non consentiti nelle variabili JavaScript.

* Scheda (0x09)
* Ritorno a capo (0x0D)
* Newline (0x0A)
* caratteri ASCII con codici superiori a 127 (a meno che i caratteri multibyte non siano attivati e *`charSet`* siano compilati in modo appropriato)
* Tag HTML (ad esempio <b></b> &amp;#153)

Molte variabili, in particolare prodotti, gerarchia ed eventi, presentano limitazioni o requisiti di sintassi aggiuntivi. Per le limitazioni delle singole variabili e i requisiti di sintassi, consultare la sezione corrispondente ai parametri delle *`s_account`* variabili.
