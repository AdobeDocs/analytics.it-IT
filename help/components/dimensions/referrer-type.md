---
title: Tipo referente
description: Il tipo di referente, a seconda della provenienza del visitatore.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# Tipo referente

La dimensione &#39;Tipo referente&#39; indica i canali generici sui quali i visitatori hanno fatto clic per arrivare al sito. Adobe mantiene le regole per ogni valore di dimensione, a differenza dei canali [](marketing-channel.md)Marketing, in cui l&#39;organizzazione mantiene le regole per ogni canale.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento a più tabelle di ricerca interne ad Adobe. Ogni valore è basato sul [referente](referrer.md) dell’hit, che dipende dai filtri [URL](/help/admin/admin/internal-url-filter-admin.md)interni. Accertatevi che la dimensione del referente e i filtri URL interni siano configurati correttamente.

## Valori dimensione

I valori delle dimensioni includono il tipo di referente dell’hit. I valori specifici includono quanto segue:

* **Digitato/Segnalibro**: Non esistono dati di referente per l’hit.
* **Motori** di ricerca: Il referente proviene da un motore di ricerca riconosciuto che include una stringa di query per parole chiave.
* **Social network:**: I dati del referente appartenevano a un social network riconosciuto da Adobe.
* **Altri siti** Web: I dati del referente non appartengono a un motore di ricerca o a un social network riconosciuto da Adobe.
* **Disco** rigido: Il referente ha avuto origine da una copia locale di una pagina Web sul disco rigido del visitatore.
* **E-mail**: Referente originato da un URL con un protocollo di `imap://` o `mail://`. Non include i servizi e-mail online, in quanto in genere utilizzano il `https://` protocollo.

### Social network

L&#39;elenco seguente fa riferimento alla tabella di ricerca &#39;Social network&#39; utilizzata da Adobe. Adobe fornisce questo elenco per cortesia ai clienti di Adobe Analytics. Se desiderate raccomandare ad Adobe di aggiungere un dominio a questo elenco, contattate l&#39;Assistenza clienti per richiedere un delegato di supporto nell&#39;organizzazione.

>[!NOTE] Questo elenco è diverso dall&#39;elenco predefinito dei social network nelle regole [di elaborazione dei canali di](../c-marketing-channels/c-rules.md)marketing.

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

### Motori di ricerca nel valore della dimensione &quot;Altri siti Web&quot;

Quando si visualizzano domini specifici nella dimensione &quot;Tipo referente&quot;, possono essere presenti domini che ci si aspetterebbe in &quot;Motori di ricerca&quot; elencati invece in &quot;Altri siti Web&quot;. Ad esempio, potete vedere `'google.com'` in &quot;Altri siti Web&quot;.

* **Domini del motore di ricerca nel valore** della dimensione &quot;Motori di ricerca&quot;: Il referente ha soddisfatto tutti i criteri per essere classificato come motore di ricerca da Adobe. Il dominio di riferimento è un motore di ricerca valido *e l&#39;URL di provenienza contiene* un parametro di stringa di query per parole chiave.
* **Domini del motore di ricerca nel valore** della dimensione &quot;Altri siti Web&quot;: L&#39;URL di provenienza non soddisfa tutti i criteri per la classificazione come motore di ricerca. Esempi comuni includono sottodomini dedicati ad altre funzioni oltre alla ricerca. Ad esempio, `mail.google.com` o `autos.yahoo.com` non sono motori di ricerca, ma risiedono in un dominio di primo livello comunemente associato alla ricerca. Questi sottodomini non includono una stringa di query per parole chiave, pertanto sono inclusi in &#39;Altri siti Web&#39; invece di &#39;Motori di ricerca&#39;.
