---
description: Per non sbagliare con la metrica Visite pagina singola in Analisi ad hoc, il rapporto Visite pagina singola mostra le pagine in cui i visitatori del tuo sito Web entrano e chiudono, senza intervenire per visualizzare altre pagine.
seo-description: Per non sbagliare con la metrica Visite pagina singola in Analisi ad hoc, il rapporto Visite pagina singola mostra le pagine in cui i visitatori del tuo sito Web entrano e chiudono, senza intervenire per visualizzare altre pagine.
seo-title: Visita singola pagina
solution: Analytics
title: Visita singola pagina
topic: Rapporti
uuid: 5 ca 52 be 8-c 7 f 5-464 a -8 a 06-55 e 8271760 b 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visita singola pagina

Per non sbagliare con la metrica Visite pagina singola in Analisi ad hoc, il rapporto Visite pagina singola mostra le pagine in cui i visitatori del tuo sito Web entrano e chiudono, senza intervenire per visualizzare altre pagine.

This report is most commonly used in the context of the [!UICONTROL Pages] report, however it can also be viewed in all traffic variables with [!UICONTROL pathing] enabled. Potete utilizzare questo rapporto per identificare le pagine di immissione che hanno meno probabilità di obbligare un visitatore a esplorare ulteriormente il sito, o per determinare il numero di visite che consiste in una singola pagina. Queste informazioni consentono di ottimizzare il contenuto per ridurre l'uscita da tali pagine.

## Properties of Report {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* An identical report can be retrieved by pulling a [!UICONTROL Pages] report, using [!UICONTROL Single Access] as a metric.

* Una visita a una singola pagina viene considerata una visita contenente un valore univoco, non una singola richiesta di immagine.

   * In the context of a [pages report](../../../components/c-variables/dimensionslist/reports-pages.md#concept_0219136EA25745B58434D0C7E751D7D5), only one unique page can fire within the visit.
   * In the context of a [site sections report](../../../components/c-variables/dimensionslist/reports-site-sections.md#concept_39E550D7A9E34C9580E81F5F9E12BDDD), a single unique site section fires within the visit.
   * In the context of a [traffic variable](/help/admin/admin/c-traffic-variables/traffic-var.md), a visit populates this report if a single unique value is fired.

* Le visite a una singola pagina possono essere costituite da molte richieste di immagini, purché la variabile nel contesto del rapporto contenga un unico valore univoco. Non appena viene compilato un secondo valore univoco, la visita non viene più considerata una visita a una singola pagina.
* Questo tipo di rapporto è considerato un tipo di rapporto. By default, the [!UICONTROL Pages] variable has pathing enabled. Tuttavia, anche le variabili di traffico hanno questa funzionalità. L'abilitazione dei percorsi su variabili di traffico aggiuntive dipende dal contratto. Per informazioni dettagliate, contattate l'Account Manager della vostra organizzazione.
* Questo rapporto può utilizzare un filtro di ricerca per individuare elementi di righe specifiche.
* This report can be viewed in both [trended](/help/components/c-variables/dimensionslist/reports-types.md) and [ranked](/help/components/c-variables/dimensionslist/reports-types.md) formats.

* In questo rapporto non sono disponibili suddivisioni.
* The only metric available within this report is [!UICONTROL Visits].

