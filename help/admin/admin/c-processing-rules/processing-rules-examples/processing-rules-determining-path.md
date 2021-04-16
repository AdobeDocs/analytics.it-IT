---
description: Puoi copiare il valore di un eVar in un prop per abilitare il percorso.
subtopic: Processing rules
title: Determinare un percorso copiando un valore eVar in un prop
feature: Strumenti di amministrazione
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 24%

---

# Determinare un percorso copiando un valore eVar in un prop

Puoi copiare il valore di un eVar in un prop per abilitare il percorso.

Quando si impostano i valori, la variabile a sinistra riceve il valore (anche se è vuota) dalla variabile a destra.

| Set di regole | Valore |
|---|---|
| Condizione | Nessuno (esegui sempre) |
| Azione | Sovrascrivi valore di Prop1 con eVar1 |

Puoi modificare questa regola per impostare il valore di Prop1 solo se non contiene già un valore simile al seguente:

| Set di regole | Valore |
|---|---|
| Condizione | Se Prop1 non è impostato |
| Azione | Sovrascrivi valore di Prop1 con eVar1 |

Ad esempio:

![](assets/overwrite-empty-prop.png)
