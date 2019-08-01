---
description: Per attivare l'integrazione è necessario completare la procedura guidata di integrazione di Qualtrics nell'interfaccia dei Connettori dati
seo-description: Per attivare l'integrazione è necessario completare la procedura guidata di integrazione di Qualtrics nell'interfaccia dei Connettori dati
seo-title: Completamento della procedura guidata Integrazione Adobe
solution: Analytics
subtopic: Qualificazioni
title: Completamento della procedura guidata Integrazione Adobe
topic: Connettori dati
uuid: e 065 fba 4-1 fe 1-4 e 25-9 c 45-6 c 52 dc 20 f 81 e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

Per attivare l'integrazione è necessario completare la procedura guidata di integrazione di Qualtrics nell'interfaccia dei Connettori dati

1. Passa ai connettori dati e avvia la procedura guidata di integrazione di Qualtrics. ([Data Connectors Help](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. Selezionate la suite di rapporti che desiderate utilizzare per questa integrazione e fornite un nome.

   Completate la procedura guidata di integrazione, fornendo le informazioni descritte nei passaggi seguenti. 1. **Wizard Step 1**

   | Email Address | L'indirizzo e-mail principale del contatto. |
   |---|---|
   | Descrizione | (Facoltativo) Descrizione per questa configurazione dell'integrazione. |
   | ID organizzazione di Qualtrics | [Ricerca dell'ID organizzazione di Qualtrics](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Token di Adobe sitecatalyst | [Generazione del token di Adobe Analytics ICS](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. ** Procedura guidata Passo 2 - Mappature variabili**

   | Elenco risposte qualificate | Seleziona una variabile di elenco disponibile dalla suite di rapporti. (Potrebbe essere necessario abilitare una nuova listvar all'interno della suite di rapporti.) |
   |---|---|
   | ID risposta di qualtrics | Seleziona un evar o prop disponibile dalla suite di rapporti. (Potrebbe essere necessario abilitare una nuova listvar all'interno della suite di rapporti.) |
   | Server di monitoraggio | Fornite l'impostazione del server di tracciamento (dominio) che utilizzate per tenere traccia dei dati di Adobe Analytics. Use the `trackingServerSecure` tracking server if it differs from your standard tracking server setting. |
   | Submissions Survey Ics Submissions | Selezionate un evento disponibile dalla suite di rapporti (potrebbe essere necessario abilitare un nuovo evento dall'interno del Gestore suite di rapporti). |

1. **Procedura guidata 3**: Niente obbligatorio, informativo.

   Risultato 1. ** Procedura guidata Passo 4 - Impostazioni di esportazione**

   | eVar | Seleziona fino a cinque evar da esporre per l'esportazione in Qualificazioni |
   |---|---|
   | Eventi | Selezionate fino a cinque eventi personalizzati da esporre per l'esportazione in Qualtrics (Qualificazioni) |
   | Proprietà | Seleziona fino a cinque dei tuoi Prop da esporre per l'esportazione in Analytrics |
   | Richieste di accesso | Seleziona la casella per le metriche standard e le dimensioni da esportare in Qualtrics. The `visitor_id` is required to allow the export to function properly. |

1. **Procedura guidata 5**: Esaminate la configurazione e fate clic **[!UICONTROL Activate Now]** su.
