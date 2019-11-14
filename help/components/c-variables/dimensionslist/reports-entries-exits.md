---
description: Il rapporto Pagina di partecipazione mostra, in percentuale e per totale, quali pagine del sito sono le prime viste da nuove visite.
solution: Analytics
title: Entrate e uscite
topic: Reports
uuid: 756de55b-136b-427b-a80c-f822260131b1
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Entrate e uscite

>[!NOTE]
>Per gli hit con più valori nella variabile "products", le voci e le uscite si applicano a tutti i valori di prodotto in un hit anziché solo al primo.

Il rapporto Pagina di partecipazione mostra, in percentuale e per totale, quali pagine del sito sono le prime viste da nuove visite.

È possibile visualizzare:

* **Pagine** entrata (o sezioni): Visualizza, in percentuale e per visite totali, le pagine del sito sono le prime pagine visualizzate da una nuova visita. È possibile utilizzare questo rapporto per identificare quali pagine Web sono i punti di ingresso più frequenti, ottimizzare i punti di ingresso principali sul sito e indirizzare il traffico di immissione ai messaggi chiave.

   Un modo utile per utilizzare la metrica Visualizzazione pagina è eseguire un rapporto **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Entry]** , ordinarlo in base ad esso e vedere quali pagine di immissione generano il maggior numero di visualizzazioni di pagina.

* **Pagine** di immissione originali: Mostra la prima pagina visualizzata per i nuovi visitatori del sito. Ogni utente viene conteggiato solo una volta, a meno che non elimini i cookie o non venga monitorato con i cookie.
* **Visite** a pagina singola: Mostra le pagine che più spesso sono entrambe le pagine di entrata e uscita per le sessioni di navigazione dei visitatori.
* **Esci da pagine**: Visualizza, in percentuale e in totale, le pagine del sito che erano le ultime pagine visualizzate dai visitatori prima di lasciare il sito. Le pagine di uscita dispongono di un ambito di suddivisione per le visite, ossia persistono in tutti gli hit per una visita.

**Metriche su un rapporto Pagine di immissione**

* **Voci**: come istanze o occorrenze, quante volte la pagina specificata corrisponde alla pagina di immissione di una visita.
* **Visite**: quante visite è stata questa pagina la pagina di entrata, questa metrica dovrebbe essere uguale voci.
* **Uscite**: Numero di volte in cui si è verificata un'uscita, la pagina Entry (Entrata) era quella specificata. Se desiderate visualizzare il numero di volte in cui la pagina di immissione era anche la pagina di uscita, utilizzate la metrica Blocchi invece di uscire.

**Segmentazione in un rapporto Pagine di immissione**

Eseguire un [!UICONTROL Entry Pages Report] solo report sulle pagine di immissione, anche se si applica segmento a una pagina non di immissione.

Ad esempio, si supponga che una sequenza di visite sia la seguente:

[!DNL Page A] &gt; [!DNL Page B] &gt; [!DNL Page C]

Se in un segmento vengono utilizzate le pagine B e C, in un segmento viene segnalata solo la pagina A, in quanto la pagina A è la pagina iniziale. [!UICONTROL Entry Pages Report]
