---
description: Best practice per Power BI.
title: Best practice
feature: Report Builder
role: User, Admin
exl-id: 2d9447f4-77ac-465b-af93-206dc3ea80f7
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 2%

---

# Best practice

## Mantenere i riferimenti nelle visualizzazioni Power BI {#section_7ED14FE64D974681A57EB91EF1B47CB6}

Una volta creata una richiesta, tale richiesta avrà sempre lo stesso riferimento in Power BI. Tuttavia, se elimini una richiesta, il riferimento verrà utilizzato da una nuova richiesta creata per la stessa dimensione.

Se elimini una richiesta nella cartella di lavoro, accertati di non disporre di una visualizzazione che punti a tale richiesta in Power BI, in quanto in caso contrario la visualizzazione risulterà interrotta.

* Se possibile, non eliminare le richieste create nel Report Builder
* Assicurati di eliminare le richieste sul Report Builder anche la visualizzazione corrispondente in Power BI.
* Se non sei sicuro: elimina le richieste di cui non hai più bisogno, quindi ripubblica e passa a Power BI per vedere quali visualizzazioni sono state interrotte
