---
description: Puoi copiare il valore di un eVar in una prop per abilitare il percorso.
subtopic: Processing rules
title: Determinare un percorso copiando un valore eVar in un prop
feature: Admin Tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: ht
source-wordcount: '128'
ht-degree: 100%

---

# Determinare un percorso copiando un valore eVar in un prop

Puoi copiare il valore di un eVar in una prop per abilitare il percorso.

Quando si impostano i valori, la variabile a sinistra riceve il valore (anche se è vuoto) dalla variabile a destra.

| Set di regole | Valore |
|---|---|
| Condizione | Nessuno (eseguire sempre) |
| Azione | Sovrascrivere il valore di Prop1 con eVar1 |

Puoi modificare questa regola per impostare il valore di Prop1 solo se non contiene già un valore simile al seguente:

| Set di regole | Valore |
|---|---|
| Condizione | Se Prop1 non è impostato |
| Azione | Sovrascrivere il valore di Prop1 con eVar1 |

Esempio:

![](assets/overwrite-empty-prop.png)
