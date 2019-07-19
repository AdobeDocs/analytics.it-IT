---
description: Le origini dati Registro web ti consentono di importare file di registro del server web standard.
seo-description: Le origini dati Registro web ti consentono di importare file di registro del server web standard.
seo-title: Registro web
solution: Analytics
subtopic: Origini dati
title: Registro web
topic: Sviluppatore e implementazione
uuid: a 0 efed 57-6 d 1 b -43 d 8-97 ce-dc 31009805 e 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

Puoi visualizzare i dati del registro web utilizzando i report di marketing standard per Visualizzazioni pagina, Visite e Visitatori. Poiché le metriche dei rapporti si basano principalmente sui cookie e i registri dei server web si basano sull'indirizzo IP, Adobe consiglia di importare i registri del server web in una suite di rapporti separata creata appositamente per tale scopo.

Per ulteriori informazioni sui file di registro del server web, consulta la documentazione del server web.