---
description: nulle
keywords: Implementazione di Analytics;riferimento collegamento;redir
seo-description: nulle
seo-title: Misurazione dei collegamenti personalizzati sui protocolli mobile
solution: Analytics
title: Misurazione dei collegamenti personalizzati sui protocolli mobile
topic: Sviluppatore e implementazione
uuid: eb82de26-da2e-41c2-8924-59b6b5ccef28
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Misurazione dei collegamenti personalizzati sui protocolli mobile

Molti utenti di dispositivi mobili scaricano i file sui propri dispositivi, ad esempio podcast, suonerie e file simili. Poiché molti dispositivi mobili non supportano JavaScript, la misurazione dei collegamenti deve essere implementata tramite reindirizzamenti. Per utilizzare i reindirizzamenti, è necessario modificare i collegamenti href nel codice HTML per includere l'elemento REDIR. Il formato generale di un collegamento personalizzato è il seguente:

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

Quando crei un riferimento a un collegamento, tieni presente quanto segue:

* Il valore URL deve essere codificato nell’URL.
* È necessario impostare un parametro pageName o URL pagina (g).
* Le variabili dinamiche possono leggere il parametro URL ma non impostarlo.
* Se non è impostato alcun cookie, i server Adobe eseguono un normale cookie handshake.
* Per tenere traccia dei collegamenti, è necessario includere i parametri pe, pev1 e pev2.

Un URL personalizzato per la misurazione dei collegamenti è simile al seguente:

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

Per ulteriori informazioni, consulta il white paper [Exit Link Tracking Reindirizza (Esci dal tracciamento del collegamento)](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/).
