---
description: La chiave per un'implementazione di tracciamento dei collegamenti corretta è la comprensione delle variabili s. linktrackvars e s. linktrackevents. Questo consente di trasmettere valori variabili personalizzati alle azioni dell'utente.
keywords: Implementazione di Analytics
seo-description: La chiave per un'implementazione di tracciamento dei collegamenti corretta è la comprensione delle variabili s. linktrackvars e s. linktrackevents. Questo consente di trasmettere valori variabili personalizzati alle azioni dell'utente.
seo-title: Utilizzo di s. linktrackvars e s. linktrackevents
solution: Analytics
title: Utilizzo di s. linktrackvars e s. linktrackevents
topic: Sviluppatore e implementazione
uuid: f 6 b 7019 b -987 b -4 b 7 d-a 446-80205 f 7 cc 36 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Utilizzo di s. linktrackvars e s. linktrackevents

La chiave per un'implementazione di tracciamento dei collegamenti corretta è la comprensione delle variabili s. linktrackvars e s. linktrackevents. Questo consente di trasmettere valori variabili personalizzati alle azioni dell'utente.

If you are implementing custom link tracking and are setting [!UICONTROL custom] variables and *`events`*, make sure that your [!UICONTROL s.linkTrackVars] variable contains a comma-separated list of all variables that you are passing, including the *`events`* variable. Make sure that [!UICONTROL s.linkTrackEvents] includes a comma-separated list of all events that you are passing.

Setting [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] does not actually set these variables/events, it only prepares the [!DNL Analytics] code to do so. Devi comunque impostare manualmente le variabili, come mostrato nell'esempio seguente:

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

Notice that events is listed in the [!UICONTROL s.linkTrackVars] variable. The individual events that may be passed are included in the [!UICONTROL s.linkTrackEvents] variable and are also included within [!UICONTROL s.events] later in the function. Each of the variables that are passed are listed in [!UICONTROL s.linkTrackVars] before they are populated later in the function. Also, "event9″ has been included in [!UICONTROL s.linkTrackEvents], but has not been included in [!UICONTROL s.events]. Non viene registrata, ma può essere registrata se l'utente aveva scelto di impostare s. events = "event 5, event 9."

Automatic file download and [!UICONTROL Exit] link tracking work differently. The [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] are included in the standard [!DNL s_code.js] file, and both are set to none. These variables are typically left set to none in the [!DNL s_code.js] file so that automatic link tracking, unlike [!UICONTROL custom link tracking], uses the [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] values that you set in the global JavaScript file. They also pass whatever the existing values of those variables are whenever a file download or [!UICONTROL Exit] link is recorded.

Consider the example where s.channel="Home" when the page loads, and where s.linkTrackVars="channel" in your [!DNL s_code.js] file. If a user clicks to download a file, automatic file download tracking passes data into [!DNL Analytics], including the value of [!UICONTROL s.channel] that was set on page load. "Home" is passed a second time, leading to inflation in page view data for this value in the [!UICONTROL Site Sections] report.

Adobe strongly recommends leaving the [!UICONTROL s.linkTrackVars] and [!UICONTROL s.linkTrackEvents] set to "none" in the global JavaScript file and setting them explicitly as necessary with your [!UICONTROL custom link tracking] implementation.
