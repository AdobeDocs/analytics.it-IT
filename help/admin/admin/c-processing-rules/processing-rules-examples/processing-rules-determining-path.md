---
description: È possibile copiare il valore di un'eVar su una prop per abilitare il percorso.
subtopic: Processing rules
title: Determinare un percorso copiando un valore eVar in un prop
topic: Admin tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Determinare un percorso copiando un valore eVar in un prop

È possibile copiare il valore di un'eVar su una prop per abilitare il percorso.

Quando si impostano i valori, la variabile a sinistra riceve il valore (anche se vuoto) dalla variabile a destra.

| Set di regole | Valore |
|---|---|
| Condizione | None (execute always) |
| Azione | Sovrascrivi valore di Prop1 con eVar1 |

È possibile modificare questa regola per impostare il valore di Prop1 solo se non contiene già un valore, simile a quanto segue:

| Set di regole | Valore |
|---|---|
| Condizione | Se Prop1 Non È Impostato |
| Azione | Sovrascrivi valore di Prop1 con eVar1 |

Ad esempio:

![](assets/overwrite-empty-prop.png)

