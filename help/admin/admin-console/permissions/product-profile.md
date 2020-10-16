---
source-git-commit: 78d9346ec82d802136cbaf2bfed31b6d25af207e
workflow-type: tm+mt
translation-type: tm+mt
source-wordcount: '644'
ht-degree: 2%

---
# Profili di prodotto in  Adobe Analytics

I profili di prodotto sono un predefinito di autorizzazione che gli amministratori di prodotto possono assegnare agli utenti all’interno di un’organizzazione. Se create un profilo di prodotto e assegnate un utente  Experience Cloud a tale profilo di prodotto, questi eredita gli elementi di autorizzazione contenuti nel profilo di prodotto.

Consultate [Gestione di prodotti e profili](https://helpx.adobe.com/it/enterprise/using/manage-products-and-profiles.html) nella guida utente di Enterprise per informazioni generali sui profili di prodotto.

## Amministratori del profilo di prodotto

Gli amministratori dei profili di prodotto sono un gruppo facoltativo che può aggiungere o rimuovere utenti a tale profilo di prodotto. Un amministratore del profilo di prodotto non equivale a un amministratore di prodotto:

* Gli amministratori dei profili di prodotto non dispongono dell&#39;accesso completo a  Adobe Analytics. L&#39;accesso completo a  Adobe Analytics è riservato agli amministratori dei prodotti.
* Gli amministratori dei profili di prodotto possono regolare gli elementi delle autorizzazioni nel loro profilo di prodotto.
* Gli amministratori dei profili di prodotto possono assegnare o rimuovere i profili di prodotto ai gruppi di utenti.
* Gli amministratori dei profili di prodotto sono ideali per i responsabili dei team o per i manager che devono concedere e gestire l&#39;accesso a  Adobe Analytics per il proprio team. Gli individui non dovrebbero disturbare gli amministratori di sistema o di prodotto a concedere l&#39;accesso a  Adobe Analytics.

##  le autorizzazioni di Adobe Analytics

Le autorizzazioni minime richieste in un profilo di prodotto per accedere  Adobe Analytics sono le seguenti:

* Il profilo di prodotto deve avere accesso ad almeno una suite di rapporti
* Il profilo di prodotto deve appartenere all’elemento di autorizzazione Strumenti di Analytics **Analysis Workspace Access** (o Accesso **a** Reporting e analisi)

### Suite di rapporti

Consente l&#39;accesso alle suite di rapporti che appartengono alla tua organizzazione Analytics. Per poter utilizzare  Adobe Analytics, un utente deve appartenere ad almeno una suite di rapporti.

### Metriche

Consente l&#39;accesso alle metriche nella suite di rapporti. Le metriche sono elencate come rispettivo componente in  Analysis Workspace, o se la metrica è disponibile in Reporting e analisi, disponibile come voce di menu in Metriche del sito.

Le metriche personalizzate sono etichettate &#39;Evento personalizzato 1-1000&#39; per mantenerle indipendenti dalle suite di rapporti. Se &#39;Custom Event 1&#39; è un elemento di autorizzazione abilitato, l&#39;utente ha accesso a event1 in tutte le suite di rapporti nel profilo di prodotto.

### Dimensioni

Consente l&#39;accesso alle dimensioni nella suite di rapporti. Gli Dimension sono elencati come rispettivi componenti in  Analysis Workspace, oppure se la dimensione è disponibile in Reporting e analisi, disponibile come voce di menu.

Le variabili personalizzate, come le eVar, sono etichettate &#39;Conversione personalizzata 1-250&#39; per mantenerle indipendenti dalle suite di rapporti. Se &quot;Conversione personalizzata 1&quot; è un elemento di autorizzazione abilitato, tale utente ha accesso a  eVar 1 in tutte le suite di rapporti nel profilo di prodotto.

### Strumenti delle suite di rapporti

Gli strumenti delle autorizzazioni della suite di rapporti concedono l&#39;accesso alle funzionalità specifiche delle suite di rapporti a cui l&#39;utente ha accesso. Consulta Strumenti [suite di](report-suite-tools.md) rapporti per un elenco completo delle autorizzazioni e delle descrizioni.

### Strumenti di Analytics

Gli strumenti di analisi concedono l&#39;accesso alle funzioni che sono indipendenti dalle impostazioni della suite di rapporti. Consulta Strumenti [di](analytics-tools.md) Analytics per un elenco completo delle autorizzazioni e delle descrizioni.

## Sviluppatori di profili di prodotto

Gli sviluppatori sono simili agli utenti, tranne per il fatto che possono utilizzare l&#39;API del Experience Cloud  nell&#39;I/O  Adobe. Per ulteriori informazioni, consulta [Gestione sviluppatori](https://helpx.adobe.com/enterprise/using/manage-developers.html) nella guida utente di Enterprise. Se a un utente viene concesso l&#39;accesso Developer per qualsiasi profilo, può accedere a Dev Console (console.adobe.io) e modificare  integrazioni Adobe Analytics. Le chiamate API di Analytics e le risposte autorizzate per l&#39;utente dipenderanno dalle autorizzazioni di rete di tutti i profili in cui l&#39;utente dispone di Developer Access.

Ad esempio, con le autorizzazioni di  Analysis Workspace Access, tutte le metriche, tutte le dimensioni e una suite di rapporti, l&#39;utente potrebbe effettuare chiamate API corrette all&#39;endpoint /reporting per qualsiasi rapporto all&#39;interno della suite. Con l&#39;aggiunta del rilevamento delle anomalie, i rapporti possono includere risposte più complete, aggiunte nei dati delle anomalie. Di regola, se un profilo concede l&#39;accesso a uno scenario all&#39;interno dell&#39;interfaccia Adobe Analytics , Developer Access sullo stesso profilo attiverà le chiamate e le risposte API corrispondenti.
