---
description: Mostra le metriche in base al fatto che javascript sia abilitato, disabilitato o che venga conteggiato come "non identificato".
seo-description: Mostra le metriche in base al fatto che javascript sia abilitato, disabilitato o che venga conteggiato come "non identificato".
seo-title: Supporto javascript
solution: Analytics
title: Supporto javascript
topic: Rapporti
uuid: 7 b 95001 a-cd 35-478 a -8 b 24-54 d 30666110 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Supporto javascript

Mostra le metriche in base al fatto che javascript sia abilitato, disabilitato o che venga conteggiato come "non identificato".

>[!NOTE]
>
>In early November 2016, we plan to remove the restriction where JavaScript is always listed as *`disabled / unidentified`* for Mobile devices.

Il rapporto javascript corrisponde alla colonna javascript nei dati grezzi.

javascript è un campo a livello di visita, quindi il valore viene mantenuto dal primo hit della visita. La colonna javascript si basa sul primo valore presente nella colonna j_ jscript (come a una visita_ referrer che mantiene il primo referente della visita).

j_ jscript viene popolato dal parametro j della richiesta di immagine di Adobe Analytics.

Ecco un esempio:

| Hit | j_ jscript | javascript |
|---|---|---|
| 1 |  | 0 |
| 2 | 1.6 | 0 |
| 3 | 1.6 | 0 |

Di conseguenza, non è importante se una versione javascript specificata in un certo momento nella visita non viene visualizzata in Javascript perché il primo hit non contiene alcun valore per j_ jscript.
