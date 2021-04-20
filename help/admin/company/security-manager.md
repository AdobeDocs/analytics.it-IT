---
description: Consente di controllare l’accesso ai dati di reporting. Le opzioni includono password complesse, scadenza password, restrizioni di accesso IP e restrizioni del dominio e-mail.
title: Sicurezza Manager
feature: Admin Tools
uuid: b3fbdba0-e2bf-4d67-92e3-ef05711141d4
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 1%

---

# Sicurezza Manager

Gestione sicurezza consente di controllare l&#39;accesso ai dati di reporting. Le opzioni includono password complesse, scadenza password, restrizioni di accesso IP e restrizioni del dominio e-mail.

## Impostazioni

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Company Settings]** > **[!UICONTROL Security]**

| Impostazione | Descrizione |
|--- |--- |
| Richiedi password forti | Impone agli utenti di creare password più sicure conformi alle seguenti regole: <ul><li>La lunghezza deve essere di almeno otto caratteri.</li><li>Deve essere presente almeno un simbolo/numero tra il primo e l&#39;ultimo carattere.</li><li>Deve avere almeno un carattere alfa.</li><li>Impossibile trovare in un dizionario o contenere parole di un dizionario (inglese).</li><li>Non possono includere tre (3) caratteri consecutivi dal nome utente di accesso.</li><li>Deve essere diverso dalle 10 password precedenti.</li></ul>**Nota**: Questa funzione viene applicata alle nuove password in corso. Non controlla le password esistenti o obbliga gli utenti a modificare le password esistenti. Per questo motivo, considera l&#39;abilitazione della scadenza della password per obbligare gli utenti a modificare le loro password e rispettare le regole per la password sicura. |
| Scadenza password | Impone agli utenti di modificare regolarmente la password del loro account utente. È possibile specificare l&#39;intervallo in cui si desidera che le password scadano e forzare la scadenza immediata delle password. |
| Applica restrizioni di accesso IP | (Questa funzionalità non può essere utilizzata insieme all’accesso di Experience Cloud. Questa funzionalità non sarà più disponibile a partire da ottobre 2020. [Altro...](/help/admin/company/login-restrictions-eol.md))<br> Limita l’accesso ai rapporti a specifici indirizzi IP o intervalli di indirizzi IP. È possibile aggiungere fino a 100 voci nell’elenco Filtro indirizzi IP e ogni voce può essere un indirizzo specifico o un intervallo di indirizzi. Applica restrizioni di accesso IP non viene applicato finché non è presente almeno una voce nell’elenco Filtro indirizzi IP. Indirizzo IP accettato: Per specificare un intervallo di indirizzi IP, racchiudi l’intervallo tra parentesi (ad esempio, `192.168.10.[20-240]`). Puoi inoltre utilizzare i caratteri jolly per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, `192.168.[10-14].*8) Gli accessi non riusciti vengono registrati e visualizzabili dal [Registro utilizzo e accesso](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/logs.html#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Applica restrizioni al dominio e-mail | Filtra gli indirizzi e-mail e i domini in cui Analytics invia segnalibri, rapporti scaricabili e avvisi. L’elenco dei filtri e-mail supporta fino a 100 voci e ogni voce può essere un indirizzo e-mail o un intero dominio e-mail. Se un report pianificato ha una destinazione e-mail non approvata, Analytics invia una notifica e-mail del problema e un collegamento per annullare la pianificazione del report. **[!UICONTROL Enforce Email Domain Restrictions]** non viene applicato finché non è presente almeno una voce nell’elenco Filtro dominio e-mail accettato. **[!UICONTROL Accepted Email Address and Domains]**: Per specificare un intervallo di indirizzi IP, racchiudi l’intervallo tra parentesi (ad esempio, 192.168.10.[20-240]). È inoltre possibile utilizzare i caratteri jolly per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, 192.168.[10-14].*) |
| Notifica di recupero password | Notifica agli amministratori specificati quando un utente tenta di reimpostare la password di un account utente. **[!UICONTROL Available Admins]**: Visualizza tutti gli amministratori. Per selezionare più amministratori, è possibile premere Ctrl e Maiusc e fare clic. **[!UICONTROL Email Members]**: Visualizza il gruppo e-mail attualmente definito. |
