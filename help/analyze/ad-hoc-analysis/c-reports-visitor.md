---
description: Visualizza informazioni sui visitatori, quali conteggio dei visitatori, fedeltà dei clienti e caratteristiche dei visitatori.
title: Rapporti sui visitatori
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 3%

---


# Rapporti sui visitatori

Visualizza informazioni sui visitatori, quali conteggio dei visitatori, fedeltà dei clienti e caratteristiche dei visitatori.

## Frequenza di ritorno {#concept_447A99B71E484D27A7A02888CC51FD3D}

Mostra il tempo che trascorre tra le visite dei visitatori di ritorno e il numero di visite che rientrano in ogni categoria di lunghezza di tempo. Utilizzate il rapporto per visualizzare la quantità media di tempo che i visitatori ripetuti passano senza visitare il sito e le tendenze dei clienti ripetuti.

<!-- 

c_reports_return_freq.xml

 -->

Ad esempio, mostrare la metrica Ordini in questo rapporto aiuta un sito retail a comprendere il tempo più efficace tra le visite durante la generazione della conversione. Utilizzate queste informazioni per commercializzare efficacemente i visitatori che hanno trascorso un certo periodo di tempo senza visitare il sito.

È possibile:

* Identificare il numero di visitatori di ritorno e la frequenza delle visite di ritorno.
* Valuta l&#39;attrattiva e la rilevanza del tuo sito Web per i visitatori nel tempo.
* Scopri quanto è appiccicoso il tuo sito per i visitatori e quanto spesso si sentono obbligati a tornare per ulteriori interazioni o aggiornamenti.
* Identificazione dell&#39;impatto dei contenuti e delle promozioni del sito Web sui visitatori.

Per impostazione predefinita, il rapporto ha le seguenti lunghezze di tempo:

* Meno di un giorno
* Da uno a tre giorni
* Da tre a sette giorni
* Da 7 a 4 giorni
* Da quattordici giorni a un mese
* Più di un mese

## Numero visita {#concept_BBB614072FD74379B1A8520ACB75AE9A}

Mostra i numeri di visita del cliente sul sito che hanno influenzato maggiormente le metriche di successo. Un visitatore che effettua una prima visita al sito viene conteggiato nella voce Numero visita 1. I visitatori che tornano al sito per una seconda visita vengono conteggiati nell’elemento della riga Numero visita 2 e così via.

<!-- 

c_reports_visit_number.xml

 -->

Potete utilizzare questo rapporto come rapporto di abbandono per verificare se i visitatori ritornano. È inoltre possibile aggiungere una metrica relativa alle entrate per verificare se si generano più entrate dalle visite iniziali o successive.

Ad esempio, questo rapporto potrebbe rispondere a domande come: I clienti che hanno acquistato la quarta visita hanno generato più entrate rispetto a quelli che hanno acquistato la prima visita?

Puoi suddividere il rapporto con qualsiasi altro rapporto o variabile per determinare:

* In genere, per effettuare un acquisto è necessario che un utente abbia fatto clic sulla campagna XYZ.
* Se, ad esempio, gli utenti di Tokyo effettuino più visite prima di generare un lead rispetto agli utenti di Londra.

>[!NOTE]
>
>Se lo stesso visitatore visita il sito Web più volte nello stesso periodo, ogni numero di visita specificato viene incrementato per ogni visita.

Questo rapporto si basa sui dati ID visitatore passati ad Adobe per ogni hit effettuato dai visitatori. Man mano che questi dati vengono ricevuti, Adobe li confronta con i dati storici dell’ID visitatore per determinare se l’hit è:

* Un nuovo visitatore (Numero visita è uguale a 1).
* Un visitatore precedente che continua una visita (il numero della visita non viene incrementato).
* Un visitatore precedente che effettuava una nuova visita (il numero di visita viene incrementato di uno).

>[!NOTE]
>
>Ogni ID visitatore di Analytics è associato a un profilo visitatore sui server Adobe. I profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, indipendentemente dalla scadenza dei cookie dell’ID visitatore.

## Fedeltà cliente {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

Utilizzate questo rapporto per verificare se le entrate sono maggiormente influenzate dai nuovi clienti o dai clienti ripetuti.

<!-- 

c_reports_customerloyalty.xml

 -->

Il [!UICONTROL Customer Loyalty] rapporto mostra i pattern di acquisto dei clienti in base a quattro categorie di fedeltà:

* **Not a Customer**: Visitatori che non hanno mai acquistato
* **Nuovo cliente**: Visitatori che hanno effettuato un singolo acquisto
* **Restituisci cliente**: Visitatori che hanno effettuato 2 acquisti
* **Cliente** fedele:Visitatori che hanno effettuato 3+ acquisti

>[!NOTE]
>
>Quando utilizzi queste metriche, tutte le Visite utente (o tutti i Visitatori) sono rappresentate in questo rapporto, a prescindere dal fatto che la Visita (o il Visitatore) abbia incluso un acquisto.

Lo stato di fedeltà cambia dopo la fine della visita in cui si verifica un evento di acquisto. Ad esempio, un nuovo cliente (1 acquisto) effettua un acquisto e quindi si registra per una newsletter dopo tale acquisto all’interno della stessa visita. L’evento di registrazione della newsletter è ancora considerato un’interazione con il nuovo cliente, perché lo stato Fedeltà cliente del visitatore non subirà modifiche fino alla visita successiva.

## Profilo visitatore {#concept_4D829198CD144DCDA667E0651F93AFC7}

Visualizza informazioni sul tipo di visitatore che accede al sito. Puoi vedere la posizione del visitatore, il tipo di browser e hardware utilizzato per il computer, le lingue utilizzate e i dati del provider di servizi Internet per i visitatori.

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Languages]**: Visualizza le lingue preferite dai visitatori, acquisisce la lingua predefinita del browser e visualizza le lingue che i visitatori utilizzano più spesso sul sito.

**[!UICONTROL Domains]**: Elenca le organizzazioni e gli ISP utilizzati dai visitatori per accedere al sito. Questo rapporto è diverso dal [!UICONTROL Full Domains] rapporto in quanto il rapporto Domini completi registra l&#39;intero dominio ISP, mentre questo rapporto elenca il dominio secondario.

**[!UICONTROL Top Level Domains]**: Identifica le regioni del mondo da cui provengono i visitatori in base all’estensione del dominio di origine e mostra quanti visitatori provengono da tali paesi. I domini che terminano in Commercial (.com), Network (.net), Education (.edu), Government (.gov) e Organization (.org) sono generalmente residenti negli Stati Uniti e sono elencati separatamente dal resto dei domini.

**[!UICONTROL Visitor ZIP/Postal Code]**: Visualizza i codici postali e postali che hanno prodotto i clienti che hanno avuto il maggiore effetto sulle metriche di successo degli acquisti.

## Geosegmentazione {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

Mostra le dinamiche geografiche dei visitatori in tempo reale, compresi i paesi, gli stati e le città da cui stanno navigando. È inoltre possibile ottenere informazioni importanti sulla tecnologia e sulle preferenze del pubblico del sito Web.
