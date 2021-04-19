---
title: Profili di prodotto per Adobe Analytics
description: Scopri come i profili di prodotto possono essere utilizzati come predefiniti di autorizzazioni che gli amministratori di prodotto possono assegnare agli utenti all’interno di un’organizzazione.
exl-id: 834e4cf1-20b0-4c9d-939a-19e00494c8dd
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 3%

---

# Profili di prodotto per Adobe Analytics

I profili di prodotto sono predefiniti di autorizzazione che gli amministratori di prodotto possono assegnare agli utenti all’interno di un’organizzazione. Se crei un profilo di prodotto e assegni un utente di Experience Cloud a tale profilo di prodotto, questi eredita gli elementi di autorizzazione contenuti nel profilo di prodotto.

Per informazioni generali sui profili di prodotto, consulta [Gestione di prodotti e profili](https://helpx.adobe.com/it/enterprise/using/manage-products-and-profiles.html) nella guida utente Enterprise .

## Amministratori del profilo di prodotto

Gli amministratori dei profili di prodotto sono un gruppo facoltativo che può aggiungere o rimuovere utenti a tale profilo di prodotto. Un amministratore del profilo di prodotto non è lo stesso di un amministratore di prodotto:

* Gli amministratori dei profili di prodotto non hanno accesso completo ad Adobe Analytics. L’accesso completo ad Adobe Analytics è riservato agli amministratori dei prodotti.
* Gli amministratori dei profili di prodotto possono regolare gli elementi delle autorizzazioni nel loro profilo di prodotto.
* Gli amministratori dei profili di prodotto possono assegnare o rimuovere i profili di prodotto ai gruppi di utenti.
* Gli amministratori dei profili di prodotto sono ideali per i lead o i manager dei team che devono concedere e gestire l’accesso ad Adobe Analytics per il proprio team. Gli utenti singoli non dovranno più preoccuparsi degli amministratori di sistema o dei prodotti per concedere l’accesso ad Adobe Analytics.

## Autorizzazioni Adobe Analytics

Le autorizzazioni minime necessarie in un profilo di prodotto per accedere ad Adobe Analytics sono le seguenti:

* Il profilo di prodotto deve avere accesso ad almeno una suite di rapporti
* Il profilo di prodotto deve appartenere alla voce di autorizzazione Strumenti di Analytics **Accesso ad Analysis Workspace** (o **Accesso a Reports &amp; Analytics**)

### Suite di rapporti

Consente di accedere alle suite di rapporti che appartengono alla tua organizzazione Analytics. Per poter accedere all’utilizzo di Adobe Analytics, un utente deve appartenere ad almeno una suite di rapporti.

### Metriche

Consente di accedere alle metriche nella suite di rapporti. Le metriche sono elencate come rispettivo componente in Analysis Workspace, o se la metrica è disponibile in Reports &amp; Analytics, disponibile come voce di menu in Metriche del sito.

Le metriche personalizzate sono etichettate &quot;Custom Event 1-1000&quot; per mantenerle indipendenti dalle suite di rapporti. Se &#39;Custom Event 1&#39; è un elemento di autorizzazione abilitato, l&#39;utente ha accesso a event1 in tutte le suite di rapporti nel profilo di prodotto.

### Dimensioni

Consente di accedere alle dimensioni nella suite di rapporti. I Dimension sono elencati come rispettivi componenti in Analysis Workspace, o se la dimensione è disponibile in Reports &amp; Analytics, disponibile come voce di menu.

Le variabili personalizzate, come le eVar, sono etichettate &quot;Conversione personalizzata 1-250&quot; per mantenerle indipendenti dalle suite di rapporti. Se &quot;Conversione personalizzata 1&quot; è un elemento di autorizzazione abilitato, l’utente ha accesso ad eVar1 in tutte le suite di rapporti nel profilo di prodotto.

### Strumenti delle suite di rapporti

Gli elementi di autorizzazione degli strumenti della suite di rapporti consentono l’accesso alle funzioni specifiche delle suite di rapporti a cui l’utente ha accesso. Per un elenco completo degli elementi e delle descrizioni delle autorizzazioni, consulta [Strumenti delle suite di rapporti](report-suite-tools.md) .

### Strumenti di Analytics

Gli elementi di autorizzazione degli strumenti di Analytics concedono l’accesso alle funzioni indipendenti dalle impostazioni della suite di rapporti. Per un elenco completo delle autorizzazioni e delle descrizioni, consulta [Autorizzazioni del profilo di prodotto per gli strumenti di Analytics](analytics-tools.md) .

## Sviluppatori di profili di prodotto

Gli sviluppatori sono simili agli utenti, tranne per il fatto che possono utilizzare l’API Experience Cloud ad Adobe I/O. Per ulteriori informazioni, consulta [Gestione sviluppatori](https://helpx.adobe.com/enterprise/using/manage-developers.html) nella guida utente Enterprise . Se a un utente viene concesso l’accesso per sviluppatori per qualsiasi profilo, può accedere alla Console per sviluppatori (console.adobe.io) e modificare le integrazioni Adobe Analytics. Le chiamate e le risposte API di Analytics autorizzate per l’utente dipenderanno dalle autorizzazioni nette di tutti i profili in cui l’utente dispone di Accesso per sviluppatori.

Ad esempio, con le autorizzazioni di profilo che includono tutte le metriche, tutte le dimensioni e una suite di rapporti, un membro di Developer Access del profilo potrebbe effettuare chiamate API rilevanti per qualsiasi componente della suite pertinente. Aggiungendo la funzione Rilevamento anomalie, i rapporti potrebbero includere risposte più complete, che verranno aggiunte nei dati delle anomalie. Di regola, se un profilo concede l’accesso a uno scenario all’interno dell’interfaccia di Adobe Analytics, Developer Access su un profilo definito in modo simile attiverebbe le chiamate e le risposte API corrispondenti.
