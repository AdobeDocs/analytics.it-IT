---
title: Tipo di referrer
description: Il tipo di referente, a seconda di da dove proviene il visitatore.
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: 14f0ca66fdbd0468ef6b6eef41fcc020b43cddc9
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---

# Tipo di referrer

La dimensione &quot;Referrer type&quot; (Tipo referente) indica i canali generici che i visitatori hanno fatto clic per arrivare al tuo sito. Adobe mantiene le regole per ogni elemento dimensione, a differenza di [Canali di marketing](marketing-channel.md), in cui l’organizzazione gestisce le regole per ogni canale.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne all’Adobe. Ogni valore è basato sul [referrer](referrer.md) dell’hit, che dipende da [Filtri URL interni](/help/admin/admin/internal-url-filter-admin.md). Assicurati che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Elementi Dimension

Gli elementi di Dimension includono il tipo di referente dell&#39;hit. I valori specifici includono quanto segue:

* **Digitato/Segnalibro**: Non esistono dati di riferimento per l&#39;hit.
* **Motori di ricerca**: Il referente proviene da un motore di ricerca riconosciuto che include una stringa di interrogazione per parola chiave.
* **Reti sociali:**: I dati di riferimento appartenevano a un social network riconosciuto da un Adobe.
* **Altri siti web**: I dati del referente non appartenevano a un motore di ricerca o a un social network riconosciuto da Adobe.
* **Disco rigido**: Referrer proviene da una copia locale di una pagina web sul disco rigido del visitatore.
* **E-mail**: Referrer originato da un URL con un protocollo di `imap://` o `mail://`. Non include i servizi e-mail online, in quanto in genere utilizzano `https://` protocollo.

### Social network

L&#39;elenco seguente fa riferimento alla tabella di ricerca &quot;Social network&quot; utilizzata da Adobe. L’Adobe fornisce questo elenco come cortesia ai clienti Adobe Analytics. Se desideri che l’Adobe aggiunga un dominio a questo elenco, rivolgiti all’Assistenza clienti per avere un delegato di supporto nella tua organizzazione.

>[!NOTE]
>
>Questo elenco è diverso dall&#39;elenco predefinito dei social network nel [Regole di elaborazione per i canali di marketing](../c-marketing-channels/c-rules.md).

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
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
* `yozm.daum.net`
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
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
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
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
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
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### Motori di ricerca nell’elemento dimensione &quot;Altri siti web&quot;

Quando visualizzi domini specifici nella dimensione &quot;Tipo referente&quot;, possono esserci domini che ti aspetteresti sotto &quot;Motori di ricerca&quot; elencati invece in &quot;Altri siti web&quot;. Ad esempio, potresti vedere `'google.com'` alla voce &quot;Altri siti web&quot;.

* **Domini del motore di ricerca nell’elemento dimensione &quot;Motori di ricerca&quot;**: Il referente ha soddisfatto tutti i criteri per classificare come motore di ricerca per Adobe. Il dominio di riferimento è un motore di ricerca valido, *e* l&#39;URL di riferimento contiene un parametro della stringa di query per parole chiave.
* **Domini del motore di ricerca nell’elemento dimensione &quot;Altri siti web&quot;**: L’URL di riferimento non soddisfa tutti i criteri per la classificazione come motore di ricerca. Esempi comuni includono sottodomini dedicati ad altre funzioni oltre alla ricerca. Ad esempio: `mail.google.com` o `autos.yahoo.com` non sono motori di ricerca, ma risiedono in un dominio di primo livello comunemente associato alla ricerca. Questi sottodomini non includono una stringa di query per parole chiave, per cui sono inclusi in &quot;Altri siti web&quot; invece di &quot;motori di ricerca&quot;.
