---
description: nulle
keywords: Implementazione di Analytics; riferimento collegamento; redir
seo-description: nulle
seo-title: Misurazione dei collegamenti personalizzati sui protocolli mobili
solution: Analytics
title: Misurazione dei collegamenti personalizzati sui protocolli mobili
topic: Sviluppatore e implementazione
uuid: eb 82 de 26-da 2 e -41 c 2-8924-59 b 6 b 5 ccef 28
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Misurazione dei collegamenti personalizzati sui protocolli mobili

Molti utenti di dispositivi mobili scaricano i file sui propri dispositivi come podcast, suonerie e file simili. Poiché molti dispositivi mobili non supportano javascript, la misurazione dei collegamenti deve essere implementata tramite reindirizzamenti. Per utilizzare reindirizzamenti, dovete modificare i collegamenti href nel codice HTML per includere l'elemento REDIR. Il formato generale per un collegamento personalizzato è il seguente:

```
https://<your_Namespace>.112.2o7.net/b/ss/<RSID>/4/REDIR/
?url=<destination_URL>&pe=<link_type>&pev1=<current_URL>&pev2=<link_name>
```

Quando crei un riferimento collegamento, tieni presente quanto segue:

* Il valore dell'URL deve essere codificato in un URL.
* È necessario impostare un parametro pagename o URL pagina (g).
* Le variabili dinamiche possono leggere il parametro URL ma non impostarlo.
* Se non viene impostato alcun cookie, i server Adobe eseguono un handshake di cookie normale.
* Per tenere traccia dei collegamenti, dovete includere i parametri di tipo pe, pev 1 e pev 2.

Un URL di misurazione dei collegamenti personalizzato è simile a quello di seguito:

```
<a href=" https://johnny_appleseed.122.2o7.net/b/ss/appleseedpodcasts/4/REDIR/
?url=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pe=lnk_d
&pev1=http%3A%2F%2Fwww.johnny_appleseed.org%2Fmpegs%2Fplanting_apple_trees.mpeg&pev2=pl anting_apple_trees&">Planting an Apple Tree</a>
```

For more information, see the [Exit Link Tracking Redirects whitepaper](https://marketing.adobe.com/resources/help/en_US/whitepapers/redirects/).
