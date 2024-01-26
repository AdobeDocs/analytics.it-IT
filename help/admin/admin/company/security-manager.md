---
description: Consente di controllare l’accesso ai dati di reporting. Le opzioni includono password sicure, scadenza password, restrizioni di accesso IP e restrizioni del dominio e-mail.
title: Security Manager
feature: Company Settings
exl-id: 6dcf0354-4b4a-4bd5-ba6c-ae42c7b9e4df
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 100%

---

# Security Manager

Security Manager consente di controllare l’accesso ai dati di reporting. Le opzioni includono password sicure, scadenza password, restrizioni di accesso IP e restrizioni del dominio e-mail.

## Impostazioni

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Company settings]** > **[!UICONTROL Security]**

| Impostazione | Descrizione |
| --- | --- |
| Require Strong Passwords (Richiedi password sicure) | Impone l’utilizzo di una password più sicura, conforme alle seguenti regole: <ul><li>Deve contenere almeno otto caratteri.</li><li>Deve essere presente almeno un simbolo o numero tra il primo e l’ultimo carattere.</li><li>Deve essere presente almeno un carattere alfabetico.</li><li>Non può essere trovata in un dizionario né contenere parole di un dizionario (inglese).</li><li>Non può includere tre (3) caratteri consecutivi dal nome utente di accesso.</li><li>Deve essere diversa dalle 10 password precedenti.</li></ul>**Nota**: questa funzione viene applicata alle nuove password che vengono create. Non controlla le password esistenti né obbliga gli utenti a modificare le password esistenti. Per questo motivo, ti consigliamo di impostare la scadenza della password: gli utenti dovranno così modificare le loro password esistenti, impostandone una nuova che rispetti questi regole. |
| Password Expiration (Scadenza password) | Impone agli utenti di modificare regolarmente la password dell’account utente. È possibile specificare ogni quanto tempo scadono le password, nonché forzare la scadenza immediata delle password. |
| Enforce IP Login Restrictions (Applica restrizioni di accesso IP) | Questa funzione non è più disponibile da gennaio 2021.<br> Limita l’accesso ai rapporti a specifici indirizzi IP o intervalli di indirizzi IP. È possibile aggiungere fino a 100 voci nell’elenco Filtro indirizzi IP e ogni voce può essere un indirizzo specifico o un intervallo di indirizzi. “Applica restrizioni di accesso IP” non viene applicato finché non è presente almeno una voce nell’elenco Filtro indirizzi IP. Indirizzo IP accettato: per specificare un intervallo di indirizzi IP, racchiudi l’intervallo tra parentesi (ad esempio, `192.168.10.[20-240]`). È inoltre possibile utilizzare i caratteri jolly per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, `192.168.[10-14].*8`) Gli accessi non riusciti vengono registrati e sono visualizzabili dal [Registro di utilizzo e accesso](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/logs.html?lang=it#section_6FBAF92D9EA244809C45A78A2F0A7232). |
| Applicare restrizioni al dominio e-mail | Questa funzione filtra gli indirizzi e i domini e-mail a cui Analytics invia segnalibri, rapporti scaricabili e avvisi. L’elenco dei filtri e-mail supporta fino a 100 voci e ogni voce può essere un indirizzo e-mail o un intero dominio e-mail. Se un report pianificato ha una destinazione e-mail non approvata, Analytics invia una notifica e-mail del problema e un collegamento per annullare la pianificazione del report. **[!UICONTROL Enforce Email Domain Restrictions]** non viene applicato finché non è presente almeno una voce nell’elenco Accepted Email Domain Filter (Filtro domini e-mail accettati). **[!UICONTROL Accepted Email Address and Domains]**: per specificare un intervallo di indirizzi IP, racchiudi l’intervallo tra parentesi (ad esempio, `192.168.10.[20-240]`). È inoltre possibile utilizzare i caratteri jolly per specificare un numero qualsiasi compreso tra 0 e 255 (ad esempio, `192.168.[10-14].*`) |
| Notifica di recupero password | Avvisa gli amministratori specificati quando un utente tenta di reimpostare la password di un account utente. **[!UICONTROL Available Admins]**: visualizza tutti gli amministratori. Per selezionare più amministratori, premi Ctrl+clic o Maiusc+clic. **[!UICONTROL Email Members]**: visualizza il gruppo e-mail attualmente definito. |
