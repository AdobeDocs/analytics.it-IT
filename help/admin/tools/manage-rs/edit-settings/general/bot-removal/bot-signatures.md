---
title: Firme bot comuni
description: Riconoscere gli identificatori comuni dei bot.
feature: Bot Removal
role: Admin
exl-id: 57622af6-c1d3-4ef1-b3e6-10c14f04a55c
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 100%

---

# Firme bot comuni

Anche se l’dentificazione dei bot in un set di dati è diversa a seconda dell’ambiente, esistono alcuni modi per identificare i bot.

## Numero elevato di visualizzazioni di pagina per visita

Puoi richiamare un rapporto di Data Warehouse con indirizzo IP, visualizzazioni di pagina e visitatori univoci. Quindi crea un calcolo in Excel per le visualizzazioni di pagina per visita e ordinale dal valore più alto a quello più basso. I bot solitamente hanno un numero molto alto di visualizzazioni di pagina per visita (diverse centinaia o migliaia). Il valore di visualizzazioni di pagina per visita si riduce bruscamente quando si arriva alle voci relative a traffico reale.

## Nessuna pagina di provenienza

I bot generalmente non hanno un URL di provenienza. Nella segmentazione questo può essere filtrato con `Referring Domain equals Typed/Bookmarked`.

## Agenti utente insoliti

I bot utilizzano spesso agenti utente personalizzati che non sono classificati nella dimensione Browser o vengono visualizzati come versione `unknown` di un browser standard. Safari sconosciuto e Opera sconosciuto segnalano molto probabilmente dei bot.

## Sistemi operativi Linux o “Non specificato”

Non intendiamo screditare il grande sistema operativo open source Linux, ma sembra che ai bot piaccia impostarlo come proprio sistema operativo. Tuttavia, fai attenzione a non escludere eventuale traffico legittimo da parte di utenti Linux. Ai bot piace anche non impostare un sistema operativo, che può essere segmentato con `Operating System &#x200B;equals Not Specified`.

## Visualizzazioni di pagina = Visite = Visitatori univoci

Ciò si applica in particolare al rapporto dell’agente utente. Come puoi vedere nella schermata seguente, la “versione sconosciuta” di questi browser ha quasi lo stesso numero di visitatori e visitatori univoci (e quasi lo stesso numero di visualizzazioni di pagina). Questo può essere isolato nella segmentazione creando un contenitore [!UICONTROL Include] per `Single Page Visits equals Enabled` o `Hit Depth is less than 2`.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-browsers-unknown.png)

## Numero di visite 1

I bot generalmente ottengono un nuovo ID visitatore ogni volta che vengono eseguiti, quindi si ha una sola visita in assoluto e tutto il loro traffico consisterà in numero di visite pari a 1.

## Risoluzioni monitor inferiori

Gli utenti moderni hanno monitor a risoluzione molto più elevata rispetto agli anni passati. Gli hit con le seguenti risoluzioni sembrano essere molto popolari per i bot:

* 1024 x 768
* 1366 x 768
* 1600 x 864
* 800 x 600
* 1600 x 1200
* Non specificato
* 1024 x 667

## Paese + fuso orario non corrispondenti

Noterai una discrepanza tra il paese di origine e il fuso orario. Ad esempio, la posizione potrebbe essere Stati Uniti, ma il fuso orario potrebbe essere GMT.

![](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/assets/bots-country-time-zone.png)

## Accesso non effettuato

L’utente non effettua l’accesso in alcun punto della visita e le eVar di identificazione dell’utente non persistono dalle visite precedenti. Mentre alcuni bot possono essere impostati per l’autenticazione, nella maggior parte dei casi non sono così intelligenti.

## Nessun KPI nella visita

I bot generalmente non aggiungono prodotti al carrello o non procedono al pagamento. Nella maggior parte dei casi non inviano moduli lead o altri eventi di successo, ma alcuni bot inviano moduli HTML semplici.

## Stringa query specifica presente

A volte i bot tentano di bloccare la cache o di interrompere in altro modo i siti selezionando URL non validi o che non esistono (come le tipiche pagine di amministrazione LAMP o Wordpress) o aggiungendo stringhe di query specifiche.

## Indirizzi IP provenienti da piattaforme di elaborazione distribuite

I servizi di hosting web come Amazon Web Services o Google Cloud possono essere usati impropriamente come bot farm. Questi indirizzi IP sono ad alto rischio come potenziali bot:

* [Google Cloud](https://cloud.google.com/compute/): l’indirizzo IP inizia con `&#x200B;35.199` o `35.194&#x200B;`
