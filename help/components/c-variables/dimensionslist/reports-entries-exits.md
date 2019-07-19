---
description: Il rapporto Pagina di partecipazione mostra in percentuale e in base a visite totali le pagine sul sito per i primi visitatori visti dalle nuove visite.
seo-description: Il rapporto Pagina di partecipazione mostra in percentuale e in base a visite totali le pagine sul sito per i primi visitatori visti dalle nuove visite.
seo-title: Entrata ed uscita
solution: Analytics
title: Entrata ed uscita
topic: Rapporti
uuid: 756 de 55 b -136 b -427 b-a 80 c-f 822260131 b 1
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Entrata ed uscita

>[!NOTE]
>Per gli hit con più valori nella variabile prodotti, le Voci e le uscite si applicano a tutti i valori di prodotto in un hit anziché solo alla prima.

Il rapporto Pagina di partecipazione mostra in percentuale e in base a visite totali le pagine sul sito per i primi visitatori visti dalle nuove visite.

Potete visualizzare:

* **Pagine di immissione** (o sezioni): Visualizza, per percentuale e per visita totale le pagine sul sito sono le prime pagine visualizzate da una nuova visita. Potete usare questo rapporto per identificare quali delle pagine Web sono i punti di ingresso più frequenti, ottimizzare i punti di ingresso principali sul sito e indirizzare il traffico verso i messaggi chiave.

   A useful way to use the Page View metric is to run a **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Pages Entry]** report, sort by it, and see which entry pages drive the most page views.

* **Pagine di immissione originali**: Mostra la prima pagina visualizzata per i visitatori della prima volta sul sito. Ogni utente viene conteggiato solo una volta, a meno che non eliminino i cookie o non venga tracciato con i cookie.
* **Visite singole pagina**: Mostra le pagine più spesso sia di entrata che di uscita per le sessioni di esplorazione dei visitatori.
* **Esci da pagine**: Visualizza, per percentuale e per visite totali, le pagine sul sito che erano le ultime pagine visualizzate prima di uscire dal sito. Le pagine di uscita presentano un ambito delle suddivisioni visite, che significa che restano in tutti gli hit per una visita.

**Metriche in un rapporto sulle pagine di immissione**

* **Voci**: come istanze o occorrenze, quante volte la pagina specificata è la pagina di immissione per una visita.
* **Visite**: quante visite erano presenti nella pagina di immissione, questa metrica deve corrispondere alle voci.
* **Uscite**: Numero di volte in cui si è verificato un'uscita nella pagina di immissione specificata. Se desiderate vedere quante volte la pagina di immissione era anche la pagina di uscita, utilizzate la metrica Bounce (Rimbalzi) invece di uscire.

**Segmentazione in un rapporto sulle pagine di immissione**

Running an [!UICONTROL Entry Pages Report] only reports on entry pages, even if you apply segment to a non-entry page.

Ad esempio, si supponga che una sequenza visita sia la seguente:

[!DNL Page A] &gt; [!DNL Page B] &gt; [!DNL Page C]

If Page B and Page C are used in a segment, only Page A is reported in an [!UICONTROL Entry Pages Report], because Page A is the entry page.
