---
title: Tipo di referrer
description: Il tipo di referente, a seconda di dove proviene il visitatore.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: 24608d7058b8e7ddbf255c2a67dbdc2bf1bc9cca
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 2%

---

# Tipo di referrer

Il &quot;Tipo di referrer&quot; [dimensione](overview.md) segnala quali canali generici i visitatori hanno fatto clic per arrivare al sito. L’Adobe mantiene le regole per ogni elemento dimensione, a differenza di [Canali di marketing](marketing-channel.md), in cui l’organizzazione mantiene le regole per ogni canale.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne a Adobe. Ogni valore è basato su [referrer](referrer.md) dell’hit, che dipende da [Filtri URL interni](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi dimensionali

Gli elementi di Dimension includono il tipo di referrer dell’hit. I valori specifici includono:

* **Digitato/Contrassegnato con segnalibro**: non esistono dati di riferimento per l’hit.
* **Motori di ricerca**: il referente proviene da un motore di ricerca riconosciuto che include una stringa di query per parola chiave.
* **Social network:**: i dati del referente appartenevano a un social network riconosciuto dall’Adobe.
* **Altri siti web**: i dati del referente non appartengono a un motore di ricerca o a un social network riconosciuto da Adobe.
* **Disco rigido**: il referrer proviene da una copia locale di una pagina web sul disco rigido del visitatore.
* **E-mail**: referrer proviene da un URL con un protocollo di `imap://` o `mail://`. Non include i servizi e-mail online, in quanto in genere utilizzano `https://` protocollo.

### Social network

L’elenco seguente fa riferimento alla tabella di ricerca &quot;Social network&quot; utilizzata dall’Adobe. Questo elenco viene fornito come Adobe di cortesia ai clienti Adobe Analytics. Se desideri consigliare ad Adobe di aggiungere un dominio a questo elenco, rivolgiti a un delegato del supporto nella tua organizzazione e contatta l’Assistenza clienti.

>[!NOTE]
>
>Questo elenco è diverso da quello predefinito dei social network in [Regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md).

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `tiktok.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Motori di ricerca nell’elemento dimensione &quot;Altri siti web&quot;

Quando visualizzi domini specifici nella dimensione &quot;Tipo referrer&quot;, ci possono essere domini che ti aspetti in &quot;Motori di ricerca&quot; elencati invece in &quot;Altri siti web&quot;. Ad esempio, potresti vedere `'google.com'` in &#39;Altri siti Web&#39;.

* **Domini dei motori di ricerca nell’elemento dimensione &quot;Motori di ricerca&quot;**: il referente ha soddisfatto tutti i criteri per essere classificato come motore di ricerca per Adobe. Il dominio di riferimento è un motore di ricerca valido, *e* l’URL di riferimento contiene un parametro di stringa di query per parola chiave.
* **Domini del motore di ricerca nell’elemento dimensione &quot;Altri siti web&quot;**: l’URL di riferimento non soddisfa tutti i criteri per essere classificato come motore di ricerca. Esempi comuni includono i sottodomini dedicati ad altre funzioni oltre alla ricerca. Ad esempio: `mail.google.com` o `autos.yahoo.com` non sono motori di ricerca, ma risiedono in un dominio di primo livello comunemente associato alla ricerca. Questi sottodomini non includono una stringa di query con parole chiave, ed è per questo che sono inclusi in &quot;Altri siti web&quot; invece di &quot;Motori di ricerca&quot;.
