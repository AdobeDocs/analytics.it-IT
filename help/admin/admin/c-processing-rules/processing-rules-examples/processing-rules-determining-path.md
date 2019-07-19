---
description: Puoi copiare il valore di un evar in un prop per abilitare i percorsi.
seo-description: Puoi copiare il valore di un evar in un prop per abilitare i percorsi.
seo-title: Determinare un percorso copiando un valore evar in un prop
solution: Analytics
subtopic: Regole di elaborazione
title: Determinare un percorso copiando un valore evar in un prop
topic: Strumenti di amministrazione
uuid: 8 d 7647 c 7-aa 91-466 b -8 d 31-fb 4 dce 83 f 04 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Determinare un percorso copiando un valore evar in un prop

Puoi copiare il valore di un evar in un prop per abilitare i percorsi.

Quando si impostano i valori, la variabile a sinistra riceve il valore (anche se è vuoto) dalla variabile a destra.

| Set di regole | Valore |
|---|---|
| Condizione | Nessuno (esegui sempre) |
| Azione | Sovrascrivi valore di prop 1 con evar 1 |

Potete modificare questa regola per impostare il valore di Prop 1 solo se non contiene già un valore, simile a quanto segue:

| Set di regole | Valore |
|---|---|
| Condizione | Se Prop 1 non è impostato |
| Azione | Sovrascrivi valore di prop 1 con evar 1 |

Ad esempio:

![](assets/overwrite-empty-prop.png)

