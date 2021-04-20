---
description: Best practice per Power BI.
title: Best practice
uuid: 6d55a9aa-030e-4e4d-963c-ec9cc38e1731
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 4%

---


# Best practice

## Mantenere i riferimenti nelle visualizzazioni Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Una volta creata una richiesta, tale richiesta avrà sempre lo stesso riferimento in Power BI. Tuttavia, se elimini una richiesta, il riferimento verrà utilizzato da una nuova richiesta creata per la stessa dimensione.

Se elimini una richiesta nella cartella di lavoro, accertati di non avere una visualizzazione che punti a tale richiesta in Power BI, in quanto in caso contrario la visualizzazione risulterà interrotta.

* Se possibile, non eliminare le richieste create nel Report Builder
* Assicurati di eliminare le richieste sul Report Builder anche la visualizzazione corrispondente in Power BI.
* Se non sei sicuro: elimina le richieste di cui non hai più bisogno, quindi ripubblica e passa a Power BI per vedere quali visualizzazioni sono state interrotte

