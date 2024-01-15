---
description: Puoi copiare il valore di un eVar in una prop per abilitare il percorso.
subtopic: Processing rules
title: Determinare un percorso copiando un valore eVar in un prop
feature: Admin Tools
role: Admin
exl-id: 23c978b9-a159-4364-9214-561a255d23e4
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
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
