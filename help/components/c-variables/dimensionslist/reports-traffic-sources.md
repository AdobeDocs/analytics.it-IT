---
description: Visualizza informazioni sui luoghi sul Web che determinano il traffico verso il sito. Puoi vedere quali motori di ricerca e siti Web esterni al tuo dominio inviano i visitatori.
seo-description: Visualizza informazioni sui luoghi sul Web che determinano il traffico verso il sito. Puoi vedere quali motori di ricerca e siti Web esterni al tuo dominio inviano i visitatori.
seo-title: Origini del traffico
solution: Analytics
title: Origini del traffico
topic: Rapporti
uuid: 34ab8797-7a3e-43fd-afb2-4335869661b8
translation-type: tm+mt
source-git-commit: debfeb513ec40de9323485006e9ed8459f75a586

---


# Origini del traffico

Visualizza informazioni sui luoghi sul Web che determinano il traffico verso il sito. Puoi vedere quali motori di ricerca e siti Web esterni al tuo dominio inviano i visitatori.

## Origini del traffico {#topic_6718F8EFD5984DC5839B9E8F6CC45EDA}

Visualizza informazioni sui luoghi sul Web che determinano il traffico verso il sito. Puoi vedere quali motori di ricerca e siti Web esterni al tuo dominio inviano i visitatori.

I report in questo menu sono suddivisi in tre categorie di base:

* Cerca parole chiave
* Motori di ricerca
* Referenti e domini di provenienza

### Cerca parole chiave - Tutto, Pagato o Naturale

Visualizza una suddivisione di ogni parola chiave di ricerca utilizzata per trovare il sito. Potete ordinare l’elenco per visualizzazioni di pagina o per parole chiave di ricerca facendo clic sul titolo della colonna sopra l’elenco. Fai clic sulla lente di ingrandimento accanto a una parola chiave di ricerca per visualizzare i risultati della ricerca per il tuo sito.

### Motori di ricerca - Tutti, Pagati o Naturali

Visualizza i motori di ricerca utilizzati dagli utenti per trovare la pagina Web. Il grafico mostra la suddivisione percentuale dei motori di ricerca utilizzati per trovare il sito.

**Tutte le classificazioni delle pagine di ricerca**

Visualizza il livello del sito tra tutte le voci delle ricerche del visitatore, inclusi i dati per la classificazione delle pagine di ricerca a pagamento e naturale.

Ad esempio, un utente che accede al sito da un motore di ricerca potrebbe avervi visto al terzo di cento pagine di risultati. Questo consente di visualizzare e ottimizzare rapidamente le attività dei motori di ricerca. I dati per questo rapporto possono essere visualizzati per tutto il periodo di tempo tranne l'ora.

### Domini di riferimento e referenti

**Domini di riferimento**

Mostra i domini che fanno riferimento ai clienti che hanno più inciso sulle metriche di successo del sito. I riferimenti sono suddivisi in due categorie principali: Domini e URL. I domini fanno riferimento al nome del dominio e vengono visualizzati come dominio di base senza la stringa di query o le sottodirectory associate. Gli URL includono il nome del dominio di base, nonché eventuali stringhe di query o sottodirectory.

**Domini di riferimento originali**

Visualizza i referenti originali che hanno prodotto i clienti sul sito. I clienti possono visitare il sito più volte e disporre di un referente diverso per ogni visita.

Questo rapporto è utile per vedere in che modo i visitatori sono stati rimandati la prima volta che sono arrivati sul sito. Questo può essere utile per verificare se hanno continuato a utilizzare lo stesso referente e per visualizzare i pattern in base al modo in cui i clienti vengono indirizzati al sito. Puoi visualizzare il numero di visitatori generati da un referente originale o scoprire il fatturato generato da ciascun referente originale. I rapporti del referente possono essere compilati ogni volta che un visitatore accede al sito, anche se il visitatore accede più volte al sito durante una sessione (prima della scadenza della visita).

**Riferimenti**

Visualizza il dominio o l’URL da cui i visitatori sono arrivati prima del loro arrivo sul sito, i metodi utilizzati dai visitatori per trovare il sito Web e il numero di visite al sito provenienti da queste posizioni di riferimento.

Ad esempio, se un visitatore fa clic su un collegamento dal sito A e arriva sul sito, il sito A è il referente se non è definito come parte del dominio. Durante l’implementazione, il consulente di implementazione può aiutarti a definire i domini e gli URL che fanno parte del tuo sito Web (anche questo può essere fatto dopo l’implementazione). Tutti i domini o gli URL che non fanno parte di tali domini e URL definiti sono considerati referenti.

Ad esempio, se al filtro URL interno vengono aggiunte le pagine Web A e B, ma non la pagina Web C, la pagina Web C viene considerata un referente.

See [Internal URL Filters](/help/admin/admin/internal-URL-filter-admin.md)

>[!NOTE]
>
>Analytics registra un dominio di riferimento come e-mail quando i visitatori fanno clic su un collegamento a un messaggio e-mail contenente il protocollo `imap://` o `mail://` e arrivano al sito.
>
>Ad esempio, qualsiasi cosa proveniente da https://mail.yahoo.com</code> non viene conteggiata come referente e-mail perché il protocollo è `https://`. Le e-mail di Outlook sono riportate nella `Typed/ Bookmarked` riga. Qualsiasi referente con un protocollo HTTP in cui il dominio è un motore di ricerca noto viene riportato nella `Search Engine` riga.

**Tipi di referente**

Tracciando e registrando i siti di provenienza dei visitatori per ogni visita, puoi determinare in che modo i visitatori hanno scoperto il sito per ogni visita. L'elenco seguente definisce i vari tipi di referenti.

* I riferimenti del disco rigido vengono registrati quando i visitatori fanno clic su un collegamento in un documento HTML situato sul proprio disco rigido e arrivano sul sito come risultato.
* Quando i visitatori fanno clic su un collegamento situato in una pagina di un altro sito Web (non definito come parte del sito) e arrivano al sito Web, vengono registrati altri riferimenti al sito Web.
* I referenti del motore di ricerca vengono registrati quando i visitatori accedono al sito tramite un motore di ricerca. * I riferimenti digitati/segnalibro vengono registrati quando i visitatori digitano l'URL del sito direttamente nel browser o se accedono al sito selezionando i segnalibri.
