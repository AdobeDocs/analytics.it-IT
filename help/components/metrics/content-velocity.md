---
title: Velocity contenuto
description: Content Velocity misura l’impatto dei contenuti sui contenuti a valle.
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
source-git-commit: 26e166e065df90cb327fe1106542e17831069141
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 2%

---

# Velocity contenuto

La metrica calcolata &quot;Content Velocity&quot; (Velocità del contenuto) consente di misurare il modo in cui una dimensione (in genere [[!UICONTROL Page]](/help/components/dimensions/page.md)) contribuisce a far sì che gli utenti trascorrano del tempo sul sito web o sull’app.

Questa metrica utilizza [Attribuzione della partecipazione](/help/analyze/analysis-workspace/attribution/models.md) il [Visualizzazioni pagina](page-views.md) metrica come parte del suo calcolo. Con la partecipazione Visita, ogni volta che viene visualizzata una pagina, anche tutte le pagine che sono state precedentemente visitate durante la stessa visita ricevono il merito per la visualizzazione della pagina. Questa formula in genere significa che più una pagina viene visitata durante una visita, maggiore è il credito ricevuto. (vedere [Visualizzazioni pagina (partecipazione) | Visita) o &quot;Partecipazione alla visita&quot;](#page-views-participation--visit-or-visit-participation) per ulteriori informazioni.)

## Calcolo

&quot;Velocità del contenuto&quot; è un valore predefinito calcolato [metrica](overview.md) e utilizza la formula `Page views (Visit participation)` diviso per `Visits`.

![](assets/cont-velo-1.png)

## Utilizzi comuni

[!UICONTROL Content Velocity] viene comunemente utilizzato nell’analisi dei contenuti insieme ad altre metriche chiave come [!UICONTROL Page Views], [!UICONTROL Visits], e [!UICONTROL Bounce Rate].

![](assets/cont-velo-3.png)

## Esempio

L’esempio seguente suddivide le 2 parti di Content Velocity (Velocità del contenuto): &quot;Page Views (Participation | Visita)&quot; e &quot;Visite&quot;.

### Visualizzazioni pagina (partecipazione) | Visita) o &quot;Partecipazione alla visita&quot;

Considera il seguente esempio di come la partecipazione alla visita influisce sull’attribuzione:

In un sito web, un utente visita le pagine seguenti in questo ordine:

* Pagina A
* Pagina B
* Pagina C
* Pagina D

Nell’esempio precedente, la pagina A riceverebbe il merito per 4 hit, la pagina B per 3 hit, la pagina C per 2 hit e la pagina D per 1 hit.

L’esempio seguente illustra lo stesso principio, ma con alcune pagine visitate più di una volta.

* Pagina A
* Pagina B
* Pagina C
* Pagina B
* Pagina D
* Pagina A

Nell’esempio precedente, alla pagina A verrebbero attribuiti 7 hit, alla pagina B 8 hit, alla pagina C 4 hit e alla pagina D 2 hit.

### Visite

Una volta calcolata la partecipazione alla visita, il risultato viene diviso per il numero di visite.
