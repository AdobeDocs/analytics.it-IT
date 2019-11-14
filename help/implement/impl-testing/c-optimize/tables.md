---
description: Molti browser Web non iniziano a visualizzare il contenuto di una tabella finché il browser non ha compilato l'intera tabella.
keywords: Analytics Implementation
solution: Analytics
subtopic: Troubleshooting
title: Tabelle
topic: Developer and implementation
uuid: f72d7894-38bd-4926-bce4-0c6af7278c63
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Tabelle

Molti browser Web non iniziano a visualizzare il contenuto di una tabella finché il browser non ha compilato l'intera tabella.

Se l’intero contenuto della pagina si trova all’interno di un unico grande sommario, il browser deve compilare l’intero contenuto della pagina prima di visualizzare qualsiasi elemento.

L'inserimento della chiamata al file di libreria JavaScript all'esterno dei tag della tabella garantisce che la chiamata ai server Analytics non influisca sulla visualizzazione del contenuto della pagina.

> [!NOTE] Il file deve essere collocato in una posizione giuridica per le immagini e deve essere visualizzato tra l'apertura <body> e la chiusura </body> tag .

