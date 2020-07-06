---
description: Un widget di pubblicazione è un contenitore che consente di incorporare rapporti di marketing (segnalibri e dashboard) in una pagina Web. Le persone nell'organizzazione che non hanno accesso ai rapporti di marketing possono visualizzare i dati pertinenti.
title: Pubblicazione Widget
topic: Admin tools
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 1%

---


# Pubblicazione Widget

Un widget di pubblicazione è un contenitore che consente di incorporare  rapporti Analytics (segnalibri e dashboard) in una pagina Web. Gli utenti dell&#39;organizzazione che non hanno accesso  rapporti Analytics possono visualizzare i dati pertinenti.

Ad esempio, potete fornire una dashboard in modo che i dirigenti aziendali possano visualizzare il numero di visitatori della pagina, il numero di visitatori unici della pagina e così via.

>[!CAUTION]
>
>Per visualizzare i dati pubblicati tramite il widget di pubblicazione non è richiesta alcuna autenticazione. Per questo motivo, è consigliabile considerare i dati pubblicati non più sicuri dei dati inviati a un gruppo e-mail o a un server di elenco. Utilizza il widget solo in conformità con gli standard di sicurezza della tua organizzazione, i requisiti contrattuali esistenti e la legge applicabile. Il widget di pubblicazione consente di limitare, in base all’indirizzo IP o al percorso del dominio, la pubblicazione dei dati. Tuttavia, questi meccanismi sono destinati esclusivamente a prevenire la distribuzione non intenzionale dei dati e non rappresentano un modo efficace per garantire l’accesso ai dati distribuiti tramite il Widget di pubblicazione.
>
> Adobe non si assume alcuna responsabilità per i dati esposti tramite il widget di pubblicazione.

Dato che Publishing Widget può generare volumi di traffico elevati, Adobe si riserva il diritto, a propria discrezione, di disattivare i widget di pubblicazione di una società per un uso improprio o per un traffico eccessivo che sta causando un impatto sulle prestazioni complessive.

## Risoluzione dei problemi - Pubblicazione della cache dei widget

La prima volta che un utente visualizza il widget di pubblicazione distribuito, il widget esegue il rapporto. Dopo l&#39;esecuzione del rapporto, i risultati vengono aggiunti a una cache e sono validi per 1 ora. Ogni utente successivo che visualizza il widget di pubblicazione entro l’ora successiva vedrà la versione memorizzata nella cache (tornerà immediatamente). Dopo un&#39;ora, tutti gli utenti successivi che visualizzano il widget di pubblicazione lo forzeranno a eseguire nuovamente il rapporto, e questi risultati saranno memorizzati nella cache e così via. In questo modo, i dati hanno un&#39;età massima di un&#39;ora.

Se vengono visualizzate differenze di dati tra il widget di pubblicazione e l’interfaccia di reporting, potrebbe essere necessario cancellare la cache del widget di pubblicazione.

1. Fate clic su nel widget di pubblicazione (in modo che il widget sia attivo).
1. Fate clic **[!UICONTROL Save]** sul widget.
1. Eseguire nuovamente il widget. La modalità Anteprima non utilizza la cache del widget.

>[!NOTE]
>
>I widget di pubblicazione mostrano solo la prima colonna di dati in un rapporto.

## Pubblicazione delle descrizioni dei widget {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descrizione |
|--- |--- |
| Nome | Nome del widget. |
| Descrizione | (Facoltativo) Specificate una descrizione per il widget. |
| Rapporto | Dall’elenco a discesa Rapporto superiore, selezionate una cartella o una dashboard. Dall&#39;elenco a discesa Rapporto in basso, selezionate un rapporto o un segnalibro.  Questi rapporti non richiedono l’autenticazione del visitatore. <br>Quando un visitatore carica una pagina Web che include un widget di pubblicazione, il widget visualizza automaticamente il rapporto associato utilizzando i dati di reporting correnti. Le modifiche apportate a un widget di pubblicazione, come la modifica del rapporto associato, aggiornano automaticamente l’output del rapporto per tutte le pagine Web che utilizzano tale widget, senza dover ridistribuire le pagine Web.</br> |
| Destinazione | Specificate la destinazione per il widget.   Le destinazioni devono essere in un formato URL valido, incluso il prefisso https:// o https://. Le destinazioni dei widget di pubblicazione sono incluse, il che significa che il widget di pubblicazione funziona su tutti gli URL che includono la destinazione specificata. <br>Ad esempio, una destinazione di https://www.corp1.com/sales/ consente la pubblicazione di widget su tutte le pagine Web all’interno o al di sotto della pagina di vendita del www.corp1.com Web di Adobe.</br> |
