---
description: Descrive come Report Builder supporta i report di percorsi e fallout e come l'implementazione differisce da Reports & Analytics.
title: Rapporti di percorso e fallout percorso in Report Builder
uuid: 9ca6cb97-8f31-46f6-977a-e81a89a176d1
feature: Report Builder
role: User, Admin
exl-id: 211b0e76-2895-401d-a5a5-73e459a486e2
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 9%

---

# Rapporti di percorso e fallout percorso in Report Builder

Descrive come Report Builder supporta i report di percorsi e fallout e come l&#39;implementazione differisce da Reports &amp; Analytics.

| Nome del rapporto di percorso in Reports &amp; Analytics (Percorsi > dimensione >) | Supportato nel Report Builder? |
|--- |--- |
| Flusso della dimensione successiva/precedente | Non fornito come rapporto indipendente. Può essere riprodotto con diverse richieste con la dimensione Percorso e utilizzando un filtro. |
| Dimensione successiva/precedente | Non fornito come rapporto indipendente. Può essere riprodotto con un rapporto Percorso e utilizzando un filtro. |
| Abbandono | Supportato e fornito come rapporto indipendente ( Percorsi > dimensione > Abbandono dimensione). |
| Percorsi completi | Non supportati. |
| PathFinder | Non fornito come rapporto indipendente. Può essere riprodotto come rapporto di percorso utilizzando un filtro. |
| Lunghezza percorso | Supportato solo per la dimensione Pagina. |
| Analisi pagina > Riepilogo dimensioni | Non fornito come rapporto indipendente. Può essere riprodotto con diverse richieste con la dimensione Percorso e utilizzando un filtro. |
| Analisi pagina > Ricarica | Non fornito come rapporto indipendente. Può essere riprodotto con un rapporto di dimensione utilizzando la metrica Ricarica. |
| Analisi pagina > Profondità dimensione | Supportato solo per la dimensione Pagina. |
| Analisi pagina > Tempo trascorso sulla dimensione | Non supportati. |
| Entrate e uscite > Pagine di ingresso | Non fornito come rapporto indipendente. Può essere riprodotto come rapporto Percorso utilizzando il filtro predefinito Sito inserito. |
| Entrate e uscite > Pagine di ingresso originali | Supportato solo per la dimensione Pagina. |
| Entrate e uscite > Visite a pagina singola | Non fornito come rapporto indipendente. Può essere riprodotto come rapporto di percorso utilizzando un filtro predefinito. |
| Entrate e uscite > Dimensione di uscita | Non fornito come rapporto indipendente. Può essere riprodotto come rapporto di percorso utilizzando il filtro predefinito Exited Site. |
