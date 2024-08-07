---
title: Profili di prodotto per Adobe Analytics
description: Scopri come i profili di prodotto possono essere utilizzati come predefiniti di autorizzazioni che gli amministratori di prodotto possono assegnare agli utenti all’interno di un’organizzazione.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
feature: Admin Tools
role: Admin
source-git-commit: 938795c7378cb1f0537ff84eddeab3feddf8d073
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 80%

---

# Profili di prodotto per Adobe Analytics

I profili di prodotto sono predefiniti di autorizzazione che gli amministratori di prodotto possono assegnare agli utenti all’interno di un’organizzazione. Se crei un profilo di prodotto e assegni un utente di Experience Cloud a tale profilo di prodotto, questi ereditano gli elementi di autorizzazione contenuti nel profilo di prodotto.

Per informazioni generali sui profili di prodotto, tra cui la creazione di profili di prodotto e l&#39;assegnazione di utenti, consulta [Gestione dei profili di prodotto per gli utenti Enterprise](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) nella guida utente Enterprise.

## Amministratori del profilo di prodotto

Gli amministratori dei profili di prodotto sono un gruppo facoltativo che può aggiungere o rimuovere utenti a tale profilo di prodotto. Un amministratore del profilo di prodotto non è lo stesso di un amministratore di prodotto:

* Gli amministratori dei profili di prodotto non hanno accesso completo ad Adobe Analytics. L’accesso completo ad Adobe Analytics è riservato agli amministratori dei prodotti.
* Gli amministratori dei profili di prodotto non possono regolare gli elementi delle autorizzazioni nel loro profilo di prodotto.
* Gli amministratori dei profili di prodotto possono assegnare o rimuovere i profili di prodotto ai gruppi di utenti.
* Gli amministratori dei profili di prodotto sono ideali per i lead o i manager dei team che devono concedere e gestire l’accesso ad Adobe Analytics per il proprio team. Gli utenti singoli non dovranno più preoccuparsi degli amministratori di sistema o dei prodotti per concedere l’accesso ad Adobe Analytics.

Per informazioni su come assegnare gli amministratori dei profili di prodotto, consulta la sezione &quot;Gestire gli amministratori dei profili di prodotto&quot; nell&#39;articolo [Gestire i profili di prodotto per gli utenti Enterprise](https://helpx.adobe.com/it/enterprise/using/manage-product-profiles.html) nella guida utente Enterprise.

## Autorizzazioni Adobe Analytics

Le autorizzazioni minime necessarie in un profilo di prodotto per accedere ad Adobe Analytics sono le seguenti:

* Il profilo di prodotto deve avere accesso ad almeno una suite di rapporti
* Il profilo di prodotto deve appartenere all&#39;elemento di autorizzazione Strumenti di Analytics **Accesso ad Analysis Workspace**.

### Suite di rapporti

Consente di accedere alle suite di rapporti che appartengono alla tua organizzazione Analytics. Per poter accedere all’utilizzo di Adobe Analytics, un utente deve appartenere ad almeno una suite di rapporti.

### Metriche

Consente di accedere alle metriche nella suite di rapporti. Le metriche sono elencate come rispettivi componenti in Analysis Workspace.

Le metriche personalizzate sono etichettate “Evento personalizzato 1-1000” per mantenerle indipendenti dalle suite di rapporti. Se “Evento personalizzato 1” è un elemento di autorizzazione abilitato, l’utente ha accesso a evento 1 in tutte le suite di rapporti nel profilo di prodotto.

### Dimensioni

Consente di accedere alle dimensioni nella suite di rapporti. I Dimension sono elencati come rispettivi componenti in Analysis Workspace.

Le variabili personalizzate, come le eVar, sono etichettate “Conversione personalizzata 1-250” per mantenerle indipendenti dalle suite di rapporti. Se “Conversione personalizzata 1” è un elemento di autorizzazione abilitato, l’utente ha accesso a eVar1 in tutte le suite di rapporti nel profilo di prodotto.

### Strumenti delle suite di rapporti

Gli elementi di autorizzazione degli strumenti della suite di rapporti consentono l’accesso alle funzioni specifiche delle suite di rapporti a cui l’utente ha accesso. Consulta [Strumenti delle suite di rapporti](report-suite-tools.md) per un elenco completo delle autorizzazioni e delle descrizioni.

### Strumenti di Analytics

Gli elementi di autorizzazione degli strumenti di Analytics concedono l’accesso alle funzioni indipendenti dalle impostazioni della suite di rapporti. Per un elenco completo delle autorizzazioni e delle descrizioni, consulta [Autorizzazioni del profilo di prodotto per gli strumenti di Analytics](analytics-tools.md).

## Sviluppatori di profili di prodotto

Gli sviluppatori sono simili agli utenti, tranne per il fatto che possono utilizzare l’API Experience Cloud per gli sviluppatori Adobe. Per ulteriori informazioni, consulta [Gestione sviluppatori](https://helpx.adobe.com/it/enterprise/using/manage-developers.html) nella guida utente Enterprise. Se a un utente viene concesso l’accesso per sviluppatori per qualsiasi profilo, può accedere alla Console per sviluppatori (console.adobe.io) e modificare le integrazioni Adobe Analytics. Le chiamate e le risposte API di Analytics autorizzate per l’utente dipenderanno dalle autorizzazioni nette di tutti i profili in cui l’utente dispone di Accesso per sviluppatori.

Ad esempio, con le autorizzazioni di profilo che includono tutte le metriche, tutte le dimensioni e una suite di rapporti, un membro di Developer Access del profilo potrebbe effettuare chiamate API rilevanti per qualsiasi componente della suite pertinente. Aggiungendo la funzione Rilevamento anomalie, i rapporti potrebbero includere risposte più complete, che verranno aggiunte nei dati delle anomalie. Di regola, se un profilo concede l’accesso a uno scenario all’interno dell’interfaccia di Adobe Analytics, Accesso per sviluppatori su un profilo definito in modo simile attiverebbe le chiamate e le risposte API corrispondenti.
