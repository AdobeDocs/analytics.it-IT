---
description: Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.
keywords: visit
seo-description: Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.
seo-title: Visita
solution: Analytics
title: Visita
topic: Metrics (Metriche)
uuid: 91317487-f 116-4546-8 cd 2-421418 c 49 a 7 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Visita

Una sequenza di pagine visualizzate in una sessione. La metrica visite viene comunemente utilizzata nei rapporti che presentano il numero di sessioni utente nel corso del periodo di tempo selezionato.

>[!NOTE]
>
>For information about how visits and mobile app launches are calculated, see [Compare Visits and Mobile App Launches](https://helpx.adobe.com/analytics/kb/compare-visits-and-mobile-app-launches.html) in the Knowledge Base.

La metrica visita è sempre associata a un periodo di tempo, quindi sai se conteggiare una nuova visita se lo stesso visitatore ritorna al sito. Una sessione inizia quando l'utente accede per la prima volta al sito e termina in uno dei seguenti scenari:

* **30 minuti di inattività:** Quasi tutte le sessioni finiscono in questo modo. Se tra richieste di immagini sono trascorsi più di 30 minuti, viene avviata una nuova visita.
* **12 ore di attività coerente:** Se un utente attiva le richieste di immagini senza un intervallo di 30 minuti per 12 ore, viene automaticamente avviata una nuova visita.
* **2500 hit:** Se un utente genera un numero elevato di hit senza avviare una nuova sessione, una nuova visita viene conteggiata dopo 2500 richieste di immagini.
* **100 hit in 100 secondi**: Se una visita è composta da più di 100 hit che si verificano entro meno di 100 secondi, la visita termina automaticamente. Questo comportamento indica in genere l'attività bot e questa limitazione viene applicata per evitare che le visite che richiedono l'elaborazione aumentino la latenza e aumentando il tempo necessario per generare i rapporti.

>[!NOTE]
>
>La definizione di una visita può essere ridotta per una suite di rapporti se richiesta in modo specifico, ma non può essere estesa. Chiedete a uno degli utenti supportati della vostra organizzazione di richiedere questa modifica.

I seguenti scenari non avviano una nuova visita:

* L'utente che chiude la scheda, la riapre e la pagina entro 30 minuti. L'utente può anche chiudere il browser o riavviare il computer e continuare a essere conteggiato come una singola visita (dato che il visitatore torna al sito entro il periodo di 30 minuti).
* Utenti che esplorano il sito in più schede. Anche se la navigazione con più schede non incrementa le visite o i visitatori, utilizza un browser separato. poiché le varie schede fanno riferimento agli stessi cookie, mentre i browser separati non sono disponibili.

Una visita non corrisponde necessariamente a una sessione del browser. Ad esempio, se un visitatore chiude il browser, riapre il browser e accede al sito cinque minuti dopo, viene riconosciuto come continuazione della stessa visita. Ciò significa anche che se un visitatore rimane in una pagina per 35 minuti, la visita sarà chiusa ed elaborata e verrà avviata una nuova visita se fa clic su un'altra pagina.

Al termine di una visita, tutte le variabili con scadenza visita sono scadute e non persistono più. La metrica numero visita verrà incrementata alla visita successiva per il visitatore.

>[!NOTE]
>
>If you are using Analytics as the reporting source for Adobe Target, refer to [Minimizing Inflated Visit and Visitor Counts in A4T](https://marketing.adobe.com/resources/help/en_US/target/a4t/minimizing-inflated-visit-and-visitor-counts-a4t.html) in the [!DNL Target] documentation.

For more information, refer to [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_overview.html) in the Adobe Analytics Implementation guide.

**Periodi di tempo**

Una visita viene segnalata in ogni periodo di tempo in cui si è verificato l'attività. Ad esempio, supponiamo che una visita inizi alle 11:45 di dicembre 1 e prosegua fino alle 12:30 di dicembre. La visita viene conteggiata il 1 dicembre e il 2 dicembre. Questo rapporto si applica ad altri periodi di tempo, inclusi settimanali, mensili, trimestrali e annuali.
