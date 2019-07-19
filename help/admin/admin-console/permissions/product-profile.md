---
source-git-commit: d8f2458e7bae596dbabc8dab33ea5d2881047566
translation-type: tm+mt

---
# Profili di prodotto in Adobe Analytics

I profili di prodotto sono un predefinito di autorizzazione che gli amministratori di prodotti possono assegnare agli utenti all'interno di un'organizzazione. Se crei un profilo di prodotto e assegna un utente Experience Cloud a quel profilo di prodotto, eredita le autorizzazioni contenute nel profilo di prodotto.

See [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) in the Enterprise user guide for general information on product profiles.

## Amministratori di profilo di prodotto

Gli amministratori di profili di prodotto sono un gruppo facoltativo che può aggiungere o rimuovere utenti a tale profilo. Un amministratore di profilo di prodotto non è lo stesso di un amministratore di prodotto:

* Gli amministratori di profili di prodotto sono semplicemente responsabili dell'elenco di utenti di un profilo di prodotto.
* Gli amministratori di profili di prodotto non hanno accesso completo ad Adobe Analytics. L'accesso completo ad Adobe Analytics è riservato agli amministratori di prodotti.
* Gli amministratori di profili di prodotto non possono regolare le autorizzazioni nel proprio profilo di prodotto, un amministratore di prodotto deve effettuare regolazioni degli elementi delle autorizzazioni.
* Gli amministratori del profilo di prodotto sono ideali per i lead del team o per i manager che devono semplicemente concedere e gestire l'accesso ad Adobe Analytics per il team. Gli utenti non dovranno disturbare gli amministratori di sistema o gli amministratori di prodotti per concedere l'accesso ad Adobe Analytics.

## Autorizzazioni di Adobe Analytics

Le autorizzazioni minime necessarie in un profilo di prodotto per accedere ad Adobe Analytics sono le seguenti:

* Il profilo di prodotto deve avere accesso ad almeno una suite di rapporti
* The product profile must belong to the Analytics Tools permission item **Analysis Workspace Access** (or **Reports &amp; Analytics Access**)

### Suite di rapporti

Consente di accedere alle suite di rapporti che appartengono alla tua organizzazione Analytics. Un utente deve appartenere ad almeno una suite di rapporti per poter accedere ad Adobe Analytics.

### Metrics (Metriche)

Consente di accedere alle metriche nella suite di rapporti. Le metriche sono elencate come il rispettivo componente in Analysis Workspace, oppure se la metrica è disponibile in Reporting e analisi, disponibile come voce di menu in Metriche del sito.

Le metriche personalizzate sono etichettate'Custom Event 1-1000 '(Evento personalizzato) per mantenerle indipendenti dalle suite di rapporti. Se'Custom Event 1 'è un elemento di autorizzazione abilitato, tale utente può accedere all'evento 1 in tutte le suite di rapporti del profilo di prodotto.

### Dimensioni

Consente di accedere alle dimensioni nella suite di rapporti. Le dimensioni sono elencate come il rispettivo componente in Analysis Workspace, oppure se la dimensione è disponibile in Reporting e analisi, disponibile come voce di menu.

Le variabili personalizzate, come evar, sono etichettate'Conversione personalizzata 1-250 'per mantenerle indipendenti dalle suite di rapporti. Se'Custom Conversion 1 'è un'autorizzazione abilitata, tale utente può accedere a evar 1 in tutte le suite di rapporti del profilo di prodotto.

### Strumenti delle suite di rapporti

Gli elementi delle autorizzazioni degli strumenti delle suite di rapporti concedono l'accesso alle funzionalità specifiche delle suite di rapporti a cui l'utente ha accesso. See [Report Suite Tools](report-suite-tools.md) for a full list of permission items and descriptions.

### Strumenti Analytics

Gli elementi delle autorizzazioni degli strumenti di Analytics concedono l'accesso alle funzionalità indipendenti dalle impostazioni della suite di rapporti. See [Analytics Tools](analytics-tools.md) for a full list of permission items and descriptions.

## Sviluppatori di profili di prodotto

Developers are similar to users, except they are granted the ability to use the Experience Cloud API on Adobe I/O. See [Manage Developers](https://helpx.adobe.com/enterprise/using/manage-developers.html) in the Enterprise user guide for more information.
