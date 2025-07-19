---
title: Ricariche
description: Il numero di volte in cui la pagina è stata ricaricata.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 15%

---

# Ricariche

Il parametro &#39;Ricarica&#39; [metrica](overview.md) mostra il numero di volte in cui un elemento dimensione è stato presente durante un ricaricamento. In genere un ricaricamento si verifica quando un visitatore aggiorna la finestra del browser.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit in cui la dimensione [Pagina](../dimensions/page.md) contiene lo stesso valore dell&#39;hit precedente.

Il concetto di ricaricamento si applica alla dimensione Pagina indipendentemente dalla dimensione utilizzata nel reporting. Se ad esempio si utilizza [eVar1](../dimensions/evar.md) come dimensione e Ricarica come metrica, nella tabella viene visualizzato il numero di volte in cui ogni valore eVar è stato presente durante un ricaricamento (due valori di pagina consecutivi). Non mostra il numero di volte in cui sono stati presenti due valori eVar1 consecutivi.
