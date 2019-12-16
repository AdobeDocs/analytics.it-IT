---
description: Consente di controllare l'accesso ai dati di reporting. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail.
title: Sicurezza Manager
topic: Admin tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Sicurezza Manager

Security Manager consente di controllare l'accesso ai dati di reporting. Le opzioni disponibili includono password complesse, scadenza password, restrizioni di accesso IP e limitazioni del dominio e-mail.

## Impostazioni

**[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Company Settings]** &gt; **[!UICONTROL Security]**

| Impostazione | Descrizione |
|--- |--- |
| Richiedi password complesse | Impone agli utenti di creare password più sicure che rispettino le seguenti regole: <ul><li>Deve contenere almeno otto caratteri.</li><li>Deve contenere almeno un simbolo/numero di carattere tra il primo e l'ultimo carattere.</li><li>Deve avere almeno un carattere alfa.</li><li>Impossibile trovare in un dizionario o contenere parole da un dizionario (inglese).</li><li>Potrebbe non includere tre (3) caratteri consecutivi dal nome utente di accesso.</li><li>Deve essere diversa dalle 10 password precedenti.</li></ul>**Nota**:  Questa funzione viene applicata anche alle nuove password. Non controlla le password esistenti o obbliga gli utenti a cambiare quelle esistenti. Per questo motivo, è consigliabile abilitare la scadenza della password per obbligare gli utenti a cambiare la password e ad aderire alle regole per la password complessa. |
|  Scadenza password | Impone agli utenti di cambiare regolarmente la password dell'account utente. È possibile specificare l'intervallo di scadenza delle password e forzare la scadenza immediata delle password. |
|  Applica limitazioni di accesso IP | (Questa funzionalità non può essere utilizzata insieme all'accesso a Experience Cloud. Questa funzionalità non sarà più disponibile a partire da ottobre 2020. [Altro...](/help/admin/company/login-restrictions-eol.md))<br> Limita l'accesso al report a indirizzi IP o intervalli di indirizzi IP specifici. È possibile aggiungere fino a 100 voci nell'elenco Filtro indirizzi IP e ogni voce può essere un indirizzo specifico o un intervallo di indirizzi. Applica restrizioni di accesso IP non viene applicata fino a quando non è presente almeno una voce nell'elenco Filtro indirizzi IP. Indirizzo IP accettato: Per specificare un intervallo di indirizzi IP, racchiudere l'intervallo tra parentesi (ad esempio, `192.168.10.[20-240]`). Potete anche utilizzare i caratteri jolly per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, `192.168.[10-14].*8) Gli accessi non riusciti sono registrati e visibili dal registro [di](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232)utilizzo e accesso. |
|  Applica limitazioni dominio e-mail | Filtra gli indirizzi e-mail e i domini in cui Analytics invia segnalibri, rapporti scaricabili e avvisi. L'elenco dei filtri e-mail supporta fino a 100 voci e ogni voce può essere un indirizzo e-mail o un intero dominio e-mail. Se in un report pianificato è presente una destinazione e-mail non approvata, Analytics invia una notifica e-mail del problema e un collegamento per annullare la pianificazione del report. **[!UICONTROL Enforce Email Domain Restrictions]** non viene applicata finché non è presente almeno una voce nell'elenco Filtro dominio e-mail accettato. **[!UICONTROL Accepted Email Address and Domains]**: Per specificare un intervallo di indirizzi IP, racchiudere l'intervallo tra parentesi (ad esempio, 192.168.10.[20-240]). Potete inoltre utilizzare i caratteri jolly per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, 192.168.[10-14].*) |
|  Notifica recupero password | Notifica agli amministratori specificati quando un utente tenta di reimpostare la password di un account utente. **[!UICONTROL Available Admins]**: Visualizza tutti gli amministratori. Per selezionare più amministratori, tenete premuto Ctrl e Maiusc e fate clic. **[!UICONTROL Email Members]**: Visualizza il gruppo di e-mail attualmente definito. |
