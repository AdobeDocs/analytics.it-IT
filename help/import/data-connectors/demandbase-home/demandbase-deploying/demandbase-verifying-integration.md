---
description: Convalidare che l'integrazione acquisisca correttamente i dati controllando il monitoraggio live e i rapporti.
seo-description: Convalidare che l'integrazione acquisisca correttamente i dati controllando il monitoraggio live e i rapporti.
seo-title: Verifica dell'integrazione
title: Verifica dell'integrazione
uuid: a 9 a 0746 a -4845-41 ae -919 e-e 85 d 95 c 305 be
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Verifica dell'integrazione{#verifying-the-integration}

Convalidare che l'integrazione acquisisca correttamente i dati controllando il monitoraggio live e i rapporti.

## Tracciamento live {#section-9c20e8ff6b404ae09387ee07d675c9e2}

Utilizzate lo strumento di debugger digitalpulse per verificare che i dati della dimensione Demandbase vengano inviati ad Adobe Analytics. Dopo aver eliminato i cookie, ricaricate una pagina sul sito Web in cui è stato distribuito il codice di integrazione. Presupponendo che il IP corrente venga mappato su un'organizzazione riconosciuta da Demandbase, dovreste vedere risultati simili a quelli seguenti.

**Reporting e analisi (già sitecatalyst) include le due variabili di dati Contestuali Demandbase:**

![](assets/debugger1.png)

** La mbox di Target include i parametri di profilo Demandbase: **

Ciò verrà visualizzato solo se Target è stato implementato sulla pagina e hai già configurato questa integrazione per Adobe Target; vedete il passaggio 4 nella procedura guidata di integrazione Adobe.

![](assets/debugger2.png)

## Generazione di rapporti  {#section-1792fe75dc3249d0ad063dfd87a89162}

Controllate i report Demandbase in Adobe Analytics utilizzando il Dashboard creato automaticamente per voi utilizzando la procedura guidata Integrazione Adobe (Passaggio 7).

In alternativa, potete accedere al rapporto Demandbase nella struttura del menu di Adobe Analytics, consultando le videate di seguito.

>[!NOTE]
>
>Questi dati devono essere visualizzati entro 24-48 ore dalla riuscita della distribuzione.

![](assets/reporting1.png)

![](assets/reporting2.png)

## Domanda frequente {#section-d926b160a2ef4f07b43ea1bc67ac2a0a}

**Cosa significa «[n/d]»?**

Il Connettore dati Demandbase indica quando un attributo è «Non disponibile» impostando questo valore predefinito. Esistono due scenari comuni in cui il valore predefinito è:

* Demandbase rileva che il visitatore proviene da un indirizzo IP che non appartiene a una società.
* Viene utilizzato un attributo Watch Watch (che inizia con «watch_ list»), ma la società non si trova nell'elenco Watch Watch (Watch Watch).

** Perché «[n/d]» viene visualizzato più spesso per alcuni attributi? **

Demandbase classifica tutti gli indirizzi IP e fornisce gli attributi audience e audience_ segment anche quando il visitatore non proviene da un IP della società. Quando l'audience restituisce valori quali «Residenziale», «Wireless» e «Ospitalità», gli altri attributi potrebbero non essere disponibili.

A volte, il pubblico di un visitatore sarà «SMB», ma altri attributi mostreranno «[n/d]». Questo significa che Demandbase è in grado di classificare il visitatore come piccolo business, ma il profilo azienda completo non è disponibile. Ciò avviene generalmente per le società più piccole, quando più di una piccola azienda utilizza lo stesso provider di servizi o un blocco di indirizzi IP.

## Considerazioni per sviluppatori {#section-d33fff55bc4b4db99f82dee418ef1bc2}

Se devi regolare il valore predefinito nella tua implementazione, aggiorna la riga:

```
_db._nonOrgMatchLabel = "[n/a]";
```

