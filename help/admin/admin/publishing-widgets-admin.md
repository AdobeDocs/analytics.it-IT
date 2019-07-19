---
description: Un widget Pubblicazione è un contenitore che consente di incorporare rapporti di marketing (segnalibri e dashboard) in una pagina Web. Le persone della tua organizzazione che non hanno accesso ai rapporti di marketing possono visualizzare i dati pertinenti.
seo-description: Un widget Pubblicazione è un contenitore che consente di incorporare rapporti di marketing (segnalibri e dashboard) in una pagina Web. Le persone della tua organizzazione che non hanno accesso ai rapporti di marketing possono visualizzare i dati pertinenti.
seo-title: Pubblicazione widget
solution: Analytics
title: Pubblicazione widget
topic: Strumenti di amministrazione
uuid: 4 ecf 6 a 5 a -8 a 4 e -4707-b 282-39890 eba 3 c 5 d
translation-type: tm+mt
source-git-commit: ad6ba22acf6996aa038c5a3252cae8bddbf0b36a

---


# Pubblicazione widget

Un widget Pubblicazione è un contenitore che consente di incorporare rapporti di Analytics (segnalibri e dashboard) in una pagina Web. Le persone della vostra organizzazione che non hanno accesso ai report di Analytics possono visualizzare i dati pertinenti.

Ad esempio, potete fornire una dashboard in modo che i dirigenti della società possano visualizzare il numero di visitatori della pagina, il numero di visitatori univoci della pagina e così via.

>[!CAUTION]
>
>Per visualizzare i dati pubblicati tramite il widget Pubblicazione non è richiesta alcuna autenticazione. Pertanto, i dati pubblicati devono essere considerati non più sicuri rispetto ai dati inviati a un gruppo e-mail o a un server di elenco. Utilizzate il widget solo in conformità con gli standard di protezione, i requisiti contrattuali esistenti e le leggi applicabili. Il widget Pubblicazione consente di limitare l'indirizzo IP o il percorso di dominio in cui è possibile pubblicare i dati. Tuttavia, tali meccanismi sono progettati esclusivamente per impedire la distribuzione non desiderata dei dati e non rappresentano un modo efficace per proteggere l'accesso ai dati distribuiti tramite il Publishing Widget.
>
>Adobe declina la responsabilità o la responsabilità dei dati esposti tramite il Publishing Widget.

Poiché la pubblicazione di widget può provocare volumi di traffico elevati, Adobe si riserva il diritto, a sua esclusiva discrezione, di disattivare i widget Pubblicazione di una società per un utilizzo errato o un traffico eccessivo che causa un impatto sulle prestazioni complessive.

## Risoluzione dei problemi - Caching widget

La prima volta che un utente visualizza il widget distribuito per la pubblicazione, il widget esegue il rapporto. Una volta eseguito il rapporto, i risultati vengono aggiunti a una cache e sono validi per 1 ora. Tutti gli utenti successivi che visualizzano il widget di pubblicazione entro l'ora successiva visualizzeranno la versione memorizzata nella cache (che verrà restituita istantanea). Dopo che è trascorsa un'ora, tutti gli utenti successivi che visualizzano il widget di pubblicazione la obbligheranno a eseguire nuovamente il rapporto, quindi questi risultati saranno memorizzati nella cache e così via. In tal modo, i dati sono garantiti al massimo di un'ora precedente.

Se visualizzate differenze di dati tra Pubblicazione widget e Interfaccia di reporting, potrebbe essere necessario cancellare la cache di Pubblicazione Widget.

1. Fate clic su Pubblicazione widget per rendere il widget attivo.
1. Click **[!UICONTROL Save]** on the widget.
1. Rieseguite il widget. (La modalità Anteprima non utilizza la cache del widget.)

>[!NOTE]
>
>La pubblicazione di widget mostra solo la prima colonna di dati di un rapporto.

## Publishing Widgets Descriptions {#section_D67478AECCA946B19A3E4C7071EB4871}

| Elemento | Descrizione |
|--- |--- |
| Nome | Nome del widget. |
| Descrizione | (Facoltativo) Specificate una descrizione per il widget. |
| Report | Dall'elenco a discesa Rapporto principale, selezionate una cartella o un dashboard. Dall'elenco a discesa Rapporto inferiore, selezionate un minirapporto o un segnalibro. Tali rapporti non richiedono l'autenticazione dei visitatori. <br>Quando un visitatore carica una pagina Web che include un widget di pubblicazione, il widget visualizza automaticamente il rapporto associato utilizzando i dati di reporting correnti. Changes to a Publishing Widget, such as changing the associated report, automatically updates the report output for all web pages that use that widget, without you having to redeploy the web pages.</br> |
| Destinazione | Specificate la destinazione per il widget. Le destinazioni devono essere in un formato URL valido, incluso il https:// o il prefisso https://. La pubblicazione di destinazioni di widget è inclusiva, ovvero la pubblicazione di funzioni widget su tutti gli URL che includono la destinazione specificata. <br>Ad esempio, una destinazione di https://www.corp1.com/sales/ consente di pubblicare i widget di pubblicazione su tutte le pagine Web nella pagina di vendita del www.corp1.com Web.</br> |