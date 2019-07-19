---
description: 'Vi aiuta a rispondere alla domanda: «Dopo aver fatto clic sul mio sito da una campagna, l''utente dovrà passare al sito?»'
keywords: Implementazione di Analytics
seo-description: 'Vi aiuta a rispondere alla domanda: «Dopo aver fatto clic sul mio sito da una campagna, l''utente dovrà passare al sito?»'
seo-title: Percorsi per campagna o codice di tracciamento
solution: Analytics
title: Percorsi per campagna o codice di tracciamento
topic: Sviluppatore e implementazione
uuid: eb 6 e 3484-1 b 40-4 ec 6-8017-ac 1003 cdf 636
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Percorsi per campagna o codice di tracciamento

Vi aiuta a rispondere alla domanda: «Dopo aver fatto clic sul mio sito da una campagna, l'utente dovrà passare al sito?»

To answer this question, you need to set aside an [!UICONTROL sprop] to be used for this report. È quindi necessario strutturare i dati affinché siano inseriti nel prop in modo che sia sensato quando è abilitato il percorso.

For this example, you are going to use [!UICONTROL prop1] as your campaign pathing prop. Now you want to populate this [!UICONTROL sprop] with the same value you put in the [!UICONTROL page name] variable. Vedi di seguito:

```js
s.prop1=s.pageName;
```

Eseguite questa operazione su tutte le pagine, a meno che l'utente non abbia fatto clic su di essa. If they have clicked from a campaign and are on the landing page of the campaign, then you populate the prop with a concatenation of the campaign and the [!UICONTROL pagename]. Vedi di seguito:

```js
 s.prop1=s.campaign + ‘ : ’ + s.pageName;
```

Se la campagna su cui facevano clic era denominata "banner 1234" e la pagina su cui è stata rilasciata era denominata "Home Page", il valore in quel prop sarà "banner 1234: Home page. " On every subsequent page you put the [!UICONTROL pagename] in the prop as shown above.

Quando un utente fa clic su questa campagna e visualizza quattro pagine totali in quella visita, vengono visualizzati i seguenti valori nella sprop in questo ordine:

```js
“banner1234 : Home Page” > “Page 2” > “Page 3” > “Page 4”
```

With our data captured in [!UICONTROL prop1] in this way, with pathing enabled on this prop, you can now look at one of various pathing reports to understand how they path through the site after they click from a campaign.

Potete specificare la pagina iniziale da cui avviare il rapporto sul percorso. In questo caso, avete selezionato «banner 1234: Home Page», perché desiderate sapere dove gli utenti hanno fatto clic dopo aver fatto clic sulla campagna «banner 1234». Questo rapporto è solo un esempio di numerosi rapporti sul percorso.
