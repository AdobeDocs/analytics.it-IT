---
description: Dopo aver apportato tutti gli aggiornamenti necessari al sito Web, potete utilizzare un visualizzatore del traffico di rete, come Charles *, Chrome Developer Tools o Firebug *, per confermare che DFA stia comunicando con i server di raccolta Adobe.
keywords: DFA
seo-description: Dopo aver apportato tutti gli aggiornamenti necessari al sito Web, potete utilizzare un visualizzatore del traffico di rete, come Charles *, Chrome Developer Tools o Firebug *, per confermare che DFA stia comunicando con i server di raccolta Adobe.
seo-title: Conferma di un'integrazione DFA con esito positivo
solution: Analytics
title: Conferma di un'integrazione DFA con esito positivo
topic: Connettori dati
uuid: d 658 cd 7 c -6377-439 a -850 c-ecea 8 c 41 f 970
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Confirming a Successful DFA Integration{#confirming-a-successful-dfa-integration}

Dopo aver apportato tutti gli aggiornamenti necessari al sito Web, potete utilizzare un visualizzatore del traffico di rete, come Charles *, Chrome Developer Tools o Firebug *, per confermare che DFA stia comunicando con i server di raccolta Adobe.

After you have deployed the DFA-enabled `s_code.js` file, use the network traffic viewer to view the requests between DFA and Adobe data collection servers, looking for the following:

* A request to DFA's `fls.doubleclick.net/json` service. Questo servizio può rispondere in modo diverso a seconda della versione di DFA in uso. Con la versione Integrazione DFA 1.5:

   * An HTTP 302 redirect to [!DNL ad.doubleclick.net]. Viene inviato un percorso: nella risposta che contiene le informazioni relative al visitatore.
   * This Location tag causes a redirect to [!DNL integrate.112.2o7.net/dfa_echo]. Questo servizio traduce le informazioni relative al visitatore in una stringa codificata JSON (Notati oggetto javascript). Questi dati vengono restituiti con una risposta HTTP 200 OK.

* Con la versione Integrazione DFA 2.0 (Advanced Ad Serving enabled):

   * [!DNL fls.doubleclick.net] risponderà direttamente a un 200 OK.

In entrambi i casi, una richiesta corretta darà luogo a una richiesta ai server di raccolta dati Adobe che contengono il parametro vx, dove X è il numero evar View-through. Questo valore di parametro prende il modulo: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Questa stringa contiene dati sull'ultimo clic e l'ultima impression per il visitatore corrente.
