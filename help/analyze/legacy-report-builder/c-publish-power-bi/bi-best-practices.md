---
description: Best practice per Power BI.
title: Best practice
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
TQID: https://experienceleague.adobe.com/WXvRDft1TRz5qM9R8Psz-Yp2qY-AL-SrrXgXWRx55N0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 100%

---

# Best practice

{{legacy-arb}}

## Mantenere i riferimenti nelle visualizzazioni Power BI

Una volta creata una richiesta, tale richiesta avrà sempre lo stesso riferimento in Power BI. Tuttavia, se elimini una richiesta, il riferimento verrà utilizzato da una nuova richiesta creata per la stessa dimensione.

Se elimini una richiesta nella cartella di lavoro, accertati di non disporre di una visualizzazione che punti a tale richiesta in Power BI, in quanto in caso contrario la visualizzazione risulterà interrotta.

* Se possibile, non eliminare le richieste create nel Report Builder
* Se elimini le richieste su Report Builder, assicurati di eliminare anche la visualizzazione corrispondente in Power BI.
* Se non sei sicuro: elimina le richieste di cui non hai più bisogno, quindi ripubblica e passa a Power BI per vedere quali visualizzazioni sono state interrotte
