---
description: Le voci rappresentano il numero di volte in cui un dato valore viene acquisito come primo valore di una visita. Le voci possono verificarsi solo una volta per visita. Tuttavia, non è necessariamente il primo hit se la variabile non è definita.
title: Voci
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: e6aaf2754c6a5c33fbe3e093b4d7ca5a375c41e7

---


# Voci

&quot;Voci&quot; rappresenta il numero di volte in cui un dato valore viene acquisito come primo valore di una visita. Le voci possono verificarsi solo una volta per visita. Tuttavia, non è necessariamente il primo hit se la variabile non è definita.

In Analysis Workspace, a partire da marzo 2020, è stato modificato il modo in cui il valore &quot;None&quot; interagisce con le voci/uscite.  Poiché ora in Analysis Workspace è possibile attivare e disattivare &quot;Nones&quot;, dopo l’entrata o l’uscita viene applicato &quot;None&quot;, mentre (per le variabili evar) veniva applicato in precedenza.  Ad esempio, se il primo hit di una visita non ha alcun valore per, ad esempio, eVar21, ma il secondo hit sì. In Reporting e analisi verrà visualizzato come &quot;Non specificato&quot; per la voce, ma in Analysis Workspace verrà visualizzato come valore per il secondo hit.

Le pagine di entrata hanno un ambito di suddivisione della visita, il che significa che persistono in tutti gli hit per una visita. Per ulteriori informazioni, consulta Contenitori [di](https://marketing.adobe.com/resources/help/en_US/sc/user/c_Breakdown_and_segmentation_containers.html) suddivisione e segmentazione.
