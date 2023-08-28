---
title: Percentuale non recapitate
description: Il rapporto di visite con esattamente un hit per le voci.
feature: Metrics
exl-id: 2d4929df-3843-4ad2-abe6-5c01d3eac557
source-git-commit: 9185ef6c570dd2fb0e54ce89f9833001d3e71b60
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 5%

---

# Percentuale non recapitate

La metrica &quot;Percentuale non recapitate&quot; mostra il rapporto tra le visite che contenevano esattamente un hit e il numero di visite su quella pagina. Puoi utilizzare questa metrica per capire quali elementi dimensionali hanno il tasso di mancato recapito più alto o per vedere un tasso di mancato recapito totale aggregato del sito nel tempo. Percentuali elevate di mancati recapiti possono far luce su problemi del sito o dell’app, ad esempio: progettazione inadeguata, tempi di caricamento lenti, contenuto irrilevante o mancata corrispondenza tra l’intento del visitatore e il contenuto della pagina.

Ecco un esempio: Supponiamo che la homepage di un sito web riceva 500 visitatori in un mese. Tuttavia, 250 di questi visitatori lasciano il sito dopo aver visualizzato la pagina principale e non passano ad altre pagine. Di conseguenza, il tasso di mancato recapito della home page sarebbe del 50%.

## Come è calcolata questa metrica

Questa metrica viene calcolata utilizzando la formula [`Bounces`](bounces.md) `divided by` [`Entries`](entries.md).
