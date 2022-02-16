---
title: Firme bot comuni
description: Riconoscere gli identificatori comuni dei bot.
feature: Admin Tools
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 1%

---

# Firme bot comuni

Mentre l&#39;identificazione dei bot in un set di dati è diversa a seconda dell&#39;ambiente, ci sono alcuni modi comuni per identificare i bot.

## Numero elevato di visualizzazioni di pagina per visita

Puoi richiamare un rapporto di Data Warehouse con indirizzo IP, visualizzazioni di pagina e visitatori univoci. Quindi crea un calcolo &#x200B; &#x200B; in Excel per le visualizzazioni di pagina per visita e ordina dal più alto al più basso. I bot solitamente hanno un numero molto alto di visualizzazioni di pagina per visita (diverse centinaia a migliaia). Vedrete un brusco declino mentre vi spostate nel traffico reale.

## Nessun referrer

I bot generalmente non hanno un URL di riferimento. Nella segmentazione questo può essere filtrato come `Referring Domain equals Typed/Bookmarked`.

## Strani agenti utente

I bot utilizzano spesso agenti utente personalizzati che non sono classificati nella dimensione Browser o vengono visualizzati come `unknown` versione di un browser standard. Safari sconosciuto e Opera sconosciuta hanno una probabilità estremamente alta di essere dei bot.

## Sistemi operativi Linux o &quot;Non specificato&quot;

Non intendiamo screditare il grande sistema operativo Linux open-source, ma apparentemente ai robot piace impostarlo come sistema operativo. Tuttavia, presta attenzione nell&#39;escludere il traffico legittimo dagli utenti Linux. Ai robot piace anche non impostare un sistema operativo, che può essere segmentato su come `Operating System &#x200B;equals Not Specified`.

## Visualizzazioni di pagina = Visite = Visitatori unici

Ciò si applica in particolare al rapporto dell’agente utente. Come puoi vedere nella schermata seguente, la &quot;versione sconosciuta&quot; di questi browser ha quasi lo stesso numero di visitatori unici (e quasi lo stesso numero di visualizzazioni di pagina). Questo può essere isolato nella segmentazione creando un [!UICONTROL Include] contenitore per `Single Page Visits equals Enabled` o `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Numero di visite 1

I bot generalmente ottengono un nuovo ID visitatore ogni volta che vengono eseguiti, quindi subiscono una sola visita in assoluto e tutto il loro traffico consisterà in una visita numero di 1.

## Risoluzione monitor inferiore

Gli utenti moderni hanno monitor a risoluzione molto più elevata rispetto agli anni passati. Gli hit con le seguenti risoluzioni sembrano essere molto popolari per i bot:

* &#x200B; 1024 x 768 &#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* Non specificato
* 1024 x 667

## Paese + fuso orario non corrispondente

Noterete una discrepanza tra il paese di origine e il fuso orario. Ad esempio, la posizione potrebbe essere Stati Uniti, ma il fuso orario potrebbe essere GMT.

![](assets/bots-country-time-zone.png)

## Accesso non effettuato

L’utente non effettua l’accesso in alcun punto della visita e le eVar di identificazione dell’utente non persistono dalle visite precedenti. Mentre alcuni bot possono essere impostati per l&#39;autenticazione, la maggior parte non sono così intelligenti.

## Nessun KPI in visita

I bot generalmente non aggiungono prodotti al carrello o al check-out. Nella maggior parte dei casi non inviano moduli lead o altri eventi di successo, ma alcuni bot inviano moduli semplici di HTML. &#x200B;

## Stringa query specifica presente

A volte i bot tentano di bloccare la cache o di interrompere in altro modo i siti colpendo URL o URL malformati che non esistono (come le pagine di amministrazione LAMP o Wordpress tipiche) o aggiungendo stringhe di query specifiche.

## Indirizzi IP provenienti da piattaforme informatiche distribuite

I servizi di hosting web come Amazon Web Services o Google Cloud possono essere abusati come farm bot. Questi indirizzi IP corrono un rischio elevato di essere bot: &#x200B;
* [Google Cloud](https://cloud.google.com/compute/): L&#39;indirizzo IP inizia con `&#x200B;35.199` o `35.194&#x200B;`
