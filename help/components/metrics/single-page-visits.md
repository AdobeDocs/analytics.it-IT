---
title: Visite a pagina singola (metriche)
description: Il numero di volte in cui l’elemento dimensione "Pagina" non è cambiato in una visita.
feature: Metrics
exl-id: 086235d0-4542-4e82-96ab-28c47c842ecf
TQID: https://experienceleague.adobe.com/iDXuwf-Ls1N7VzmtZiMRISLbSEtHOtDTeoddfDEiAwA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 219
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
