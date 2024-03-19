---
title: Percentuale mancati recapiti
description: Il rapporto di visite con esattamente un hit per le voci.
feature: Metrics
exl-id: 2d4929df-3843-4ad2-abe6-5c01d3eac557
source-git-commit: ff3e9059d41f6365b850839a1f01c5747dcb9112
workflow-type: ht
source-wordcount: '191'
ht-degree: 100%

---

# Percentuale mancati recapiti

La [metrica](overview.md) “Percentuale mancati recapiti” mostra il rapporto tra le visite che contenevano esattamente un hit e il numero di visite in quella pagina. Puoi utilizzare questa metrica per comprendere quali elementi dimensionali hanno la percentuale non recapitate più alta o per vederne una aggregata totale del sito nel tempo. Percentuali non recapitate elevate possono far luce su problemi del sito o dell’app, ad esempio: progettazione inadeguata, tempi di caricamento lenti, contenuto irrilevante o mancata corrispondenza tra l’intenzione del visitatore e il contenuto della pagina.

Ecco un esempio: supponiamo che la pagina Home di un sito web riceva 500 visitatori in un mese. Tuttavia, 250 di questi visitatori lasciano il sito dopo aver visualizzato la pagina Home e non passano ad altre pagine. Di conseguenza, la percentuale non recapitate della pagina Home sarebbe del 50%.

>[!TIP]
>
>Utilizza questa metrica insieme a un’altra metrica, ad esempio [Voci](entries.md), per ottenere informazioni migliori. Se utilizzi questa metrica da sola, potresti ottenere elementi dimensionali contenenti percentuali non recapitate anomale.

## Come è calcolata questa metrica

Questa metrica viene calcolata utilizzando la formula [Non recapitate](bounces.md) diviso per le [Voci](entries.md).
