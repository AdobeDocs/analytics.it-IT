---
description: Visualizza informazioni relative ai visitatori, quali il conteggio dei visitatori, la fedeltà dei clienti e le caratteristiche dei visitatori.
seo-description: Visualizza informazioni relative ai visitatori, quali il conteggio dei visitatori, la fedeltà dei clienti e le caratteristiche dei visitatori.
seo-title: Rapporti sui visitatori
solution: Analytics
title: Rapporti sui visitatori
topic: Analisi ad hoc
uuid: 3 e 9 b 41 d 1-d 6 ff -47 a 8-aa 6 b -829 df 1040 c 34
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rapporti sui visitatori

Visualizza informazioni relative ai visitatori, quali il conteggio dei visitatori, la fedeltà dei clienti e le caratteristiche dei visitatori.

## Return Frequency {#concept_447A99B71E484D27A7A02888CC51FD3D}

Mostra il tempo che trascorre tra visite dal ritorno dei visitatori e il numero di visite che rientrano in ciascuna categoria di lunghezza. Utilizzate il report per visualizzare il tempo medio di tempo in cui i visitatori vanno senza visitare il sito e le tendenze nei clienti ripetuti.

<!-- 

c_reports_return_freq.xml

 -->

Ad esempio, la visualizzazione della metrica Ordini in questo rapporto consente a un sito di vendita di comprendere il tempo più efficace tra le visite alla generazione della conversione. Utilizzate queste informazioni sul mercato in modo efficace ai visitatori che hanno compiuto un certo periodo di tempo senza visitare il sito.

Puoi:

* Identificare il numero di visitatori di ritorno e la frequenza delle visite di ritorno.
* Valuta il fascino e la rilevanza del tuo sito web per i visitatori nel tempo.
* Scopri in che modo il tuo sito è collegato ai visitatori e quanto spesso si sentono obbligati a restituire ulteriori interazioni o aggiornamenti.
* Identificazione dell'impatto del contenuto e promozioni del sito Web sui visitatori.

Per impostazione predefinita, il rapporto presenta le lunghezze temporali seguenti:

* Meno di un giorno
* Uno a tre giorni
* Da tre a sette giorni
* Da sette a quattro giorni
* Quattordici giorni a un mese
* Più di un mese

## Visit Number {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Mostra i numeri delle visite dei clienti sul tuo sito maggiormente influenzati dalle metriche di successo. Un visitatore che effettua una prima visita al sito viene conteggiato nell'elemento della riga Numero 1. I visitatori che ritornano al sito per una seconda visita vengono conteggiati nell'elemento della riga Numero 2 e così via.

<!-- 

c_reports_visit_number.xml

 -->

Puoi utilizzare questo rapporto come rapporto di abbandono per vedere se i visitatori stanno tornando. Puoi anche aggiungere una metrica ricavi per verificare se genera più entrate da visite iniziali o visite successive.

Ad esempio, questo rapporto potrebbe rispondere a domande quali: I clienti che hanno acquistato alla quarta visita generano più entrate rispetto a quelli che hanno acquistato la prima visita?

Puoi suddividere il rapporto in base a qualsiasi altro rapporto o variabile per determinare:

* Il numero di visite di cui dispone un utente che fa clic su XYZ della campagna per effettuare un acquisto.
* Se gli utenti a Tokyo, ad esempio, eseguono più visite prima di generare un lead rispetto agli utenti di Londra.

>[!NOTE]
>
>Se lo stesso visitatore visita più volte il sito Web nello stesso periodo, ogni numero di visita specificato viene incrementato per ogni visita.

Questo rapporto si basa sui dati ID visitatore passati ad Adobe su ogni hit eseguito dai visitatori. Quando vengono ricevuti questi dati, Adobe lo confronta con dati ID visitatore storici per determinare se l'hit è:

* Nuovo visitatore (Numero visita uguale a 1).
* Visitatore precedente che continua una visita (il numero visita non viene incrementato).
* Un visitatore precedente sta effettuando una nuova visita (Numero visita viene incrementato di uno).

>[!NOTE]
>
>Ogni ID visitatore di Analytics è associato a un profilo visitatore sui server Adobe. I profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, a prescindere dalla scadenza del cookie ID visitatore.

## Customer Loyalty {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Utilizzate questo report per verificare se le entrate sono più interessate dai nuovi clienti o dai clienti ripetuti.

<!-- 

c_reports_customerloyalty.xml

 -->

[!UICONTROL Customer Loyalty] Il rapporto mostra i pattern di acquisto dei clienti in base a quattro categorie di fedeltà:

* **Non è un cliente**: Visitatori che non hanno mai acquistato
* **Nuovo cliente**: Visitatori che hanno effettuato un acquisto unico
* **Return Customer**: Visitatori che hanno effettuato 2 acquisti
* **Cliente fidato**: Visitatori che hanno effettuato acquisti con 3 +

>[!NOTE]
>
>Quando utilizzi queste metriche, tutte le visite utente (o tutti i visitatori) sono rappresentate in questo rapporto, a prescindere dal fatto che la visita (o visitatore) includa un acquisto.

Lo stato di fedeltà cambia dopo la fine della visita in cui si verifica un evento di acquisto. Ad esempio, un nuovo cliente (acquisto 1) effettua un acquisto e si registra per una newsletter dopo l'acquisto nella stessa visita. L'evento di registrazione newsletter è ancora considerato una nuova interazione cliente, in quanto lo stato di fedeltà cliente del visitatore non cambierà fino alla visita successiva.

## Profilo visitatore {#concept_4D829198CD144DCDA667E0651F93AFC7}

Visualizza informazioni sul tipo di visitatore che accede al sito. Potete visualizzare le posizioni del visitatore, il tipo di browser e l'hardware del computer utilizzato, le lingue utilizzate e i dati del fornitore di servizi Internet per i visitatori.

<!-- 

c_reports_visitor_profile.xml

 -->

** [!UICONTROL Languages] **: Displays your visitors’ preferred languages, captures the default browser language, and displays the languages that visitors use most often on your site.

** [!UICONTROL Domains] **: Lists the organizations and ISPs your visitors use to access your site. This report differs from the [!UICONTROL Full Domains] report in that the Full Domains report registers the full ISP domain, whereas this report lists the secondary domain.

** [!UICONTROL Top Level Domains] **: Identifies world regions that visitors come from based on their originating domain extension, and shows how many visitors come from these countries. I domini che terminano con Commercial (.com), Network (. net), Education (.edu), Government (.gov) e Organization (.org) sono in genere basati negli Stati Uniti e sono elencati separatamente dagli altri domini.

** [!UICONTROL Visitor ZIP/Postal Code] **: Displays the zip and postal codes that produced the customers that had the greatest effect on purchase success metrics.

## Geosegmentazione {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Mostra la dinamica geografica dei visitatori in tempo reale, compresi i paesi, gli stati e le città da cui stanno cercando. Puoi anche ottenere informazioni importanti sulla tecnologia e sulle preferenze dell'audience del sito Web.
