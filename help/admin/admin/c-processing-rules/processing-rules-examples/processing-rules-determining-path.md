---
description: È possibile copiare il valore di un'eVar su una prop per abilitare il percorso.
seo-description: È possibile copiare il valore di un'eVar su una prop per abilitare il percorso.
seo-title: Determinare un percorso copiando un valore eVar in un prop
solution: Analytics
subtopic: Regole di elaborazione
title: Determinare un percorso copiando un valore eVar in un prop
topic: Strumenti di amministrazione
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

