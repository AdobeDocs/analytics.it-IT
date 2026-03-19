---
title: Visite a pagina singola (metriche)
description: Il numero di volte in cui l’elemento dimensione "Pagina" non è cambiato in una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
source-git-commit: 6d2c278c5525c89b73c39bbfcedbe644806bf989
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 3%

---

# Visite a pagina singola

*Questa pagina della guida descrive il funzionamento di &quot;Visite a pagina singola&quot; come metrica. Per ulteriori informazioni, consulta la dimensione [Visite a pagina singola](../dimensions/single-page-visits.md).*

La **[!UICONTROL Single page visits]** [metrica](overview.md) mostra il numero di visite in cui l&#39;elemento dimensione [Pagina](../dimensions/page.md) conteneva un solo valore per l&#39;intera visita. Questa metrica è utile nel contesto di dimensioni in cui desideri visualizzare visite brevi, ma non ha la stessa severità di una regola di [[!UICONTROL Bounces]](bounces.md).

## Come è calcolata questa metrica

La definizione di questa metrica dipende dall&#39;impostazione del progetto di [[!UICONTROL Count repeat instances]](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md#project-info-settings):

* **[!UICONTROL Count repeat instances]abilitato**: conta il numero di visite in cui la dimensione [!UICONTROL Page] conteneva un singolo valore per la visita. Se un visitatore ricarica la pagina, si qualifica come visita di una singola pagina.
* **[!UICONTROL Count repeat instances]disabilitato**: conta il numero di visite in cui la dimensione [!UICONTROL Page] conteneva un singolo valore univoco per l&#39;intera visita.

Indipendentemente dall&#39;impostazione del progetto &#39;[!UICONTROL Count repeat instances]&#39;, questa metrica è conforme alle regole seguenti:

* Una visita è comunque considerata una visita a pagina singola se un visitatore genera chiamate di tracciamento dei collegamenti (la dimensione [!UICONTROL Page] viene rimossa da tutte le chiamate di tracciamento dei collegamenti).
* Non appena la dimensione [!UICONTROL Page] diventa un secondo valore univoco, la visita non si qualifica più come visita a pagina singola.

Vedi [Accesso singolo](single-access.md) per un confronto tra metriche.
