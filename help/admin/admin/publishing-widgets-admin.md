---
description: Un Widget di pubblicazione è un contenitore che consente di incorporare rapporti di marketing (segnalibri e dashboard) in una pagina web. Le persone della tua organizzazione che non hanno accesso ai rapporti di marketing possono visualizzare dati pertinenti.
title: Pubblicazione Widget
feature: Strumenti di amministrazione
uuid: 4ecf6a5a-8a4e-4707-b282-39890eba3c5d
exl-id: 97ec07d8-29ad-4ef3-9227-bfdc14a59b97
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 2%

---

# Pubblicazione Widget

Un Widget di pubblicazione è un contenitore che consente di incorporare i rapporti di Analytics (segnalibri e dashboard) in una pagina web. Le persone nella tua organizzazione che non hanno accesso ai rapporti di Analytics possono visualizzare dati pertinenti.

Ad esempio, puoi fornire un dashboard in modo che i dirigenti aziendali possano visualizzare il numero di visitatori della pagina, il numero di visitatori unici della pagina e così via.

>[!CAUTION]
>
>Per visualizzare i dati pubblicati tramite Publishing Widget non è necessaria alcuna autenticazione. Per questo motivo, è consigliabile considerare i dati pubblicati non più sicuri dei dati inviati a un gruppo di e-mail o a un server di elenco. Utilizza il widget solo in conformità agli standard di sicurezza della tua organizzazione, ai requisiti contrattuali esistenti e alla legge applicabile. Il widget di pubblicazione consente di limitare, in base all’indirizzo IP o al percorso del dominio, le aree in cui è possibile pubblicare i dati. Tuttavia, tali meccanismi sono intesi unicamente a prevenire la distribuzione non intenzionale dei dati e non costituiscono un modo efficace per garantire l’accesso ai dati distribuiti tramite il Widget di pubblicazione.
>
> L&#39;Adobe non assume alcuna responsabilità per i dati esposti tramite Publishing Widget.

Poiché Publishing Widget può potenzialmente determinare volumi di traffico elevati, Adobe si riserva il diritto, a sua discrezione, di disabilitare i widget Editoria di un&#39;azienda per uso improprio o traffico eccessivo che sta causando un impatto sulle prestazioni complessive.

## Risoluzione dei problemi - Pubblicazione della cache dei widget

La prima volta che un utente visualizza il widget di pubblicazione distribuito, il widget esegue il rapporto. Dopo l’esecuzione del rapporto, i risultati vengono aggiunti a una cache e sono validi per 1 ora. Qualsiasi utente successivo che visualizza il widget di pubblicazione entro l’ora successiva vedrà la versione in cache (tornerà istantaneamente). Trascorsa un&#39;ora, tutti gli utenti successivi che visualizzano il widget di pubblicazione lo forzeranno ad eseguire nuovamente il rapporto, e questi risultati saranno memorizzati nella cache e così via. In questo modo, i dati hanno un&#39;età massima di un&#39;ora.

Se osservi differenze di dati tra Publishing Widget e l’interfaccia di reporting, potrebbe essere necessario cancellare la cache di Publishing Widget.

1. Fai clic su nel widget di pubblicazione (in modo che il widget sia attivo).
1. Fai clic su **[!UICONTROL Save]** nel widget.
1. Esegui nuovamente il widget. La modalità Anteprima non utilizza la cache del widget.

>[!NOTE]
>
>I widget di pubblicazione mostrano solo la prima colonna di dati in un rapporto.

## Pubblicazione delle descrizioni dei Widget {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descrizione |
|--- |--- |
| Nome | Nome del widget. |
| Descrizione | (Facoltativo) Specifica una descrizione del widget. |
| Rapporto | Dall’elenco a discesa Rapporto in alto, seleziona una cartella o un dashboard. Dall’elenco a discesa Rapporto in basso, seleziona un minirapporti o un segnalibro.  Questi rapporti non richiedono l’autenticazione dei visitatori. <br>Quando un visitatore carica una pagina web che include un Widget di pubblicazione, il widget visualizza automaticamente il rapporto associato utilizzando i dati di reporting correnti. Le modifiche apportate a un widget di pubblicazione, ad esempio la modifica del report associato, aggiornano automaticamente l&#39;output del report per tutte le pagine web che utilizzano quel widget, senza dover ridistribuire le pagine web.</br> |
| Destinazione | Specifica la destinazione del widget.   Le destinazioni devono essere in un formato URL valido, incluso il prefisso https:// o https:// . Le destinazioni dei widget di pubblicazione sono inclusive, il che significa che il widget di pubblicazione funziona su tutti gli URL che includono la destinazione specificata. <br>Ad esempio, una destinazione https://www.corp1.com/sales/ consente la pubblicazione di widget su tutte le pagine Web all&#39;interno o al di sotto della pagina vendite sul sito Web www.corp1.com.</br> |
