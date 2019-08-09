---
description: 'Adobe utilizza i termini seguenti quando si parla di metriche correlate all''integrazione DFA '
keywords: DFA
seo-description: 'Adobe utilizza i termini seguenti quando si parla di metriche correlate all''integrazione DFA '
seo-title: Definizione delle metriche
solution: Analytics
title: Definizione delle metriche
topic: Connettori dati
uuid: 062 f 6863-3 daa -4 e 8 a-b 6 ea -84279 d 49 c 388
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Definizione delle metriche{#metric-definitions}

Quando parla di metriche correlate all'integrazione DFA, Adobe utilizza i termini seguenti:

**Impression**: Le impression fanno riferimento al numero di volte in cui è stato visualizzato un annuncio. Le impression vengono riportate a livello di singolo annuncio, ma possono anche essere aggregate in gruppi di annunci o altri raggruppamenti multigruppo. La metrica impression in Analytics viene importata da DFA tramite un'importazione di origini dati notturne.

**Clic** su: I clic fanno riferimento al numero di volte su cui è stato fatto clic su un annuncio, come rapporto da DFA. I clic sono registrati nella pagina di reindirizzamento della DFA prima che il visitatore arrivi sul sito Web del cliente. Come per impression, la metrica di clic in Analytics viene importata da DFA tramite un'importazione di origini dati notturne.

**Click-through**: I click-through fanno riferimento al numero di volte in cui l'utente è entrato nella pagina di destinazione, dopo aver fatto clic su un annuncio. Questa metrica può essere leggermente diversa dai clic.

**View-Through: Le visualizzazioni di visualizzazione fanno riferimento al numero di volte in cui un visitatore è entrato nel sito Web del cliente dopo aver visualizzato un annuncio, ma NON ha fatto clic sull'annuncio.** Il visitatore deve passare al sito all'interno della finestra di visualizzazione, che per impostazione predefinita è impostata su 30 giorni. L'impression deve essere avvenuta più di recente rispetto all'ultimo clic. Le visualizzazioni delle visualizzazioni vengono registrate una volta per campagna, per visita e vengono conteggiate quando l'integrazione inserisce l'evar della visualizzazione con l'ID della campagna DFA e l'evento view-through.
