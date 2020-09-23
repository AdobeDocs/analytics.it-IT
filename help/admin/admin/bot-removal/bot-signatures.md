---
title: Firme bot comuni
description: Riconoscere gli identificatori comuni dei bot.
translation-type: tm+mt
source-git-commit: 2f4c54ec57eeddc03f0b0d12a0a7f391e36ab0fc
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---


# Firme bot comuni

Mentre identificare i bot in un set di dati è diverso a seconda dell&#39;ambiente, ci sono alcuni modi comuni per identificare i bot.

## Numero elevato di visualizzazioni di pagina per visita

Puoi eseguire il pulling di un rapporto di Data Warehouse con indirizzo IP, visualizzazioni di pagina e visitatori univoci. Quindi crea un &#x200B; di calcolo &#x200B; in Excel per le visualizzazioni di pagina per visita, e ordina dal più alto al più basso. I robot hanno generalmente un numero molto elevato di visualizzazioni di pagina per visita (diverse centinaia a migliaia). Vedrete un brusco declino mentre vi spostate nel traffico reale.

## Nessun referrer

I bot generalmente non hanno un URL di riferimento. Nella segmentazione questo può essere filtrato come `Referring Domain equals Typed/Bookmarked`.

## Strani Agenti Utente

I bot spesso utilizzano agenti utente personalizzati che non sono classificati nella dimensione Browser o vengono visualizzati come `unknown` versione di un browser standard. Safari sconosciuti e Opera sconosciuta hanno una probabilità estremamente alta di essere robot.

## Sistemi operativi Linux o &quot;Non specificati&quot;

Non vogliamo screditare il grande sistema operativo Linux open-source, ma a quanto pare ai robot piace impostarlo come sistema operativo. Tuttavia, state attenti ad escludere il traffico legittimo dagli utenti Linux. Ai robot piace anche non impostare un sistema operativo, che può essere segmentato come `Operating System &#x200B;equals Not Specified`.

## Visualizzazioni pagina = Visite = Visitatori univoci

Ciò vale soprattutto per il rapporto agente utente. Come si può vedere nella videata seguente, la &quot;versione sconosciuta&quot; di questi browser ha quasi lo stesso numero di visitatori unici (e quasi lo stesso numero di visualizzazioni di pagina). Può essere isolato nella segmentazione creando un [!UICONTROL Include] contenitore per `Single Page Visits equals Enabled` o `Hit Depth is less than 2`.

![](assets/bots-browsers-unknown.png)

## Numero visita di 1

Di solito i bot ottengono un nuovo ID visitatore ogni volta che vengono eseguiti, quindi subiscono una sola visita in assoluto e tutto il loro traffico sarà costituito da una visita numero 1.

## Risoluzione monitor inferiore

Gli utenti moderni hanno monitor a risoluzione molto più elevata rispetto agli anni passati. Gli hit con le seguenti risoluzioni sembrano essere molto popolari per i robot:

* &#x200B; 1024x768 &#x200B;
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* Non specificato
* 1024x667

## Paese + Fuso orario non corrispondente

Noterete una mancata corrispondenza tra il paese di origine e il fuso orario. Ad esempio, la posizione potrebbe essere Stati Uniti, ma il fuso orario potrebbe essere GMT.

![](assets/bots-country-time-zone.png)

## Accesso non effettuato

L&#39;utente non effettua l&#39;accesso in alcun punto della visita e le eVar di identificazione dell&#39;utente non persistono dalle visite precedenti. Mentre alcuni robot possono essere configurati per l&#39;autenticazione, la maggior parte non è così intelligente.

## Nessun indicatore KPI nella visita

I bot generalmente non aggiungono prodotti a un carrello o al check-out. Nella maggior parte dei casi non inviano moduli lead o altri eventi di successo, ma alcuni bot inviano moduli HTML semplici. &#x200B;

## Stringa query specifica presente

Talvolta i bot tentano di bloccare la cache o di interrompere in altro modo i siti colpendo URL o URL non esistenti in formato errato (come le tipiche pagine di amministrazione LAMP o Wordpress) o aggiungendo stringhe di query specifiche.

## Indirizzi IP che provengono da piattaforme informatiche distribuite

I servizi di hosting Web come  Amazon Web Services o Google Cloud possono essere abusati come bot farm. Questi indirizzi IP sono ad alto rischio di essere bot:
&#x200B;
* [Google Cloud](https://cloud.google.com/compute/): L&#39;indirizzo IP inizia con `&#x200B;35.199` o `35.194&#x200B;`
