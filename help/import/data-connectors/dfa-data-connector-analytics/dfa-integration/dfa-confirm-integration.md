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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# Conferma di un'integrazione DFA con esito positivo{#confirming-a-successful-dfa-integration}

Dopo aver apportato tutti gli aggiornamenti necessari al sito Web, potete utilizzare un visualizzatore del traffico di rete, come Charles *, Chrome Developer Tools o Firebug *, per confermare che DFA stia comunicando con i server di raccolta Adobe.

Dopo aver distribuito il `s_code.js` file abilitato per DFA, usa il visualizzatore del traffico di rete per visualizzare le richieste tra i server di raccolta dati DFA e Adobe, cercando i seguenti elementi:

* Una richiesta al `fls.doubleclick.net/json` servizio DFA. Questo servizio può rispondere in modo diverso a seconda della versione di DFA in uso. Con la versione Integrazione DFA 1.5:

   * Un reindirizzamento HTTP 302 a [!DNL ad.doubleclick.net]. Viene inviato un percorso: nella risposta che contiene le informazioni relative al visitatore.
   * Questo tag Posizione causa il reindirizzamento [!DNL integrate.112.2o7.net/dfa_echo]a. Questo servizio traduce le informazioni relative al visitatore in una stringa codificata JSON (Notati oggetto javascript). Questi dati vengono restituiti con una risposta HTTP 200 OK.

* Con la versione Integrazione DFA 2.0 (Advanced Ad Serving enabled):

   * [!DNL fls.doubleclick.net] risponderà direttamente a un 200 OK.

In entrambi i casi, una richiesta corretta darà luogo a una richiesta ai server di raccolta dati Adobe che contengono il parametro vx, dove X è il numero evar View-through. Questo valore di parametro prende il modulo: DFA-XXXX-XXXX- XXXX-XXXX-XXXX-XXXX-XXXX-XXXX. Questa stringa contiene dati sull'ultimo clic e l'ultima impression per il visitatore corrente.
