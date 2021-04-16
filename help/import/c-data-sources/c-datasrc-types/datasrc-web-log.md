---
description: Le origini dati Registro web ti consentono di importare file di registro del server Web standard.
subtopic: Data sources
title: Registro web
topic-fix: Developer and implementation
uuid: a0efed57-6d1b-43d8-97ce-dc31009805e0
exl-id: 11c4f21a-de07-436e-a05e-ab6769cb3e21
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 100%

---

# Registro web

Le origini dati Registro web ti consentono di importare file di registro del server web standard.

Sono supportati i tipi di registri server web comuni seguenti:

| Nome colonna | Descrizione |
|--- |--- |
| Registro comune NCSA | Apache predefinito |
| NCSA esteso (Combinato) | Apache |
| Registro esteso W3C | Usato da IIS 4.0 e versioni successive |
| Registro Microsoft IIS | Usato da IIS 3.0 e versioni precedenti |

I campi del file di registro principali elaborati da Origini dati includono Indirizzo IP, Data/Ora della richiesta e URL. In alcuni casi, come per il formato NCSA esteso, Origini dati elabora anche i campi Referente e Agente utente.

Puoi visualizzare i dati del registro web utilizzando i report di marketing standard per Visualizzazioni pagina, Visite e Visitatori. Poiché le metriche dei rapporti si basano principalmente sui cookie e i registri dei server web si basano sull&#39;indirizzo IP, Adobe consiglia di importare i registri del server web in una suite di rapporti separata creata appositamente per tale scopo.

Per ulteriori informazioni sui file di registro del server web, consulta la documentazione del server web.
