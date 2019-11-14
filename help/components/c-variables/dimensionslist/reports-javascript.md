---
description: Mostra le metriche in base al fatto che il dispositivo abbia abilitato o meno JavaScript o che sia conteggiato come "non identificato".
solution: Analytics
title: Supporto JavaScript
topic: Reports
uuid: 7b95001a-cd35-478a-8b24-54d30666110d
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Supporto JavaScript

Mostra le metriche in base al fatto che il dispositivo abbia abilitato o meno JavaScript o che sia conteggiato come "non identificato".

> [!NOTE] All'inizio di novembre 2016, è prevista la rimozione della restrizione in cui JavaScript viene sempre elencato come *`disabled / unidentified`* per i dispositivi mobili.

Il rapporto JavaScript corrisponde al javascript delle colonne nei dati non elaborati.

javascript è un campo a livello di visita, quindi persiste il valore del primo hit della visita. La colonna javascript si basa sul primo valore presente nella colonna j_jscript (come un referrer visit_referrer persiste solo il primo referrer della visita).

j_jscript viene popolato dal parametro j dalla richiesta di immagine di Adobe Analytics.

Ecco un esempio:

| Hit | j_jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Di conseguenza, non importa se ad un certo punto della visita è stata specificata una versione javascript - sarà sempre visualizzata come non Javascript perché il primo hit non conteneva alcun valore per j_jscript.
