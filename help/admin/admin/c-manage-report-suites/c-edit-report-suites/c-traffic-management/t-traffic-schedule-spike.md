---
title: Pianificare un picco di traffico
description: Collabora con Adobe per assicurarti che gli eventi a traffico elevato non subiscano latenza.
feature: Traffic Management
exl-id: a6bbd975-6d31-40f5-8f80-491ec3a5c5f5
source-git-commit: c13e39e7bfe3d7fef07ea9ccda76255d28dde1c3
workflow-type: tm+mt
source-wordcount: '703'
ht-degree: 72%

---

# Pianificare un picco di traffico

Adobe tenta di collaborare con i client per garantire il successo di un evento con traffico elevato. La pianificazione dei picchi di traffico è il punto di partenza del processo di collaborazione. La sezione di pianificazione di un picco consente di avvisare Adobe di picchi di traffico temporanei, in modo da allocare le risorse appropriate per gestirli. È possibile stimare le chiamate server passate per ottenere un&#39;idea migliore delle dimensioni del picco di traffico che è necessario pianificare.

Il bilanciamento avanzato dei dati lato server con più personale dedicato viene utilizzato per garantire che tutti i clienti dispongano di rapporti il più possibile aggiornati. Quando la tua organizzazione notifica ad Adobe i picchi di traffico, Adobe può verificare se l’aumento improvviso del traffico è un’esperienza positiva. La mancata notifica ad Adobe degli aumenti del traffico può aumentare la latenza durante i periodi critici di reporting.

{{$include /help/_includes/traffic-lead-time.md}}

## Pianificare un picco di traffico

Per pianificare un picco di traffico:

1. Fai clic su **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Report suites]**.
1. Seleziona una suite di rapporti.
1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Traffic Management]** > **[!UICONTROL Schedule Spike]**.
1. (Facoltativo) Puoi stimare le chiamate server passate per ottenere un&#39;idea migliore delle dimensioni del picco di traffico da pianificare.

   Ad esempio, è possibile ottenere la media giornaliera delle chiamate al server dell&#39;anno scorso durante un intervallo di tempo specifico, più un aumento previsto del volume delle chiamate al server per quest&#39;anno. Puoi quindi pianificare i picchi di traffico in base a questo fattore di moltiplicazione.

   1. In **[!UICONTROL Past Server Calls]** seleziona una data di inizio e una data di fine per le suite di rapporti selezionate.

      L&#39;importo [!UICONTROL **Giorno del picco**], [!UICONTROL **Chiamate server giornaliere di picco**] e [!UICONTROL **Media giornaliera delle chiamate server**] viene generato.

   1. Inserisci un valore per il fattore di moltiplicazione, quindi seleziona **[!UICONTROL Click to multiply and set]**.

      Il valore di ciascuna colonna viene moltiplicato per ogni suite di rapporti.
1. In [!UICONTROL **Impostare i parametri del picco**] nella zona **[!UICONTROL Spike Start Date]** Specifica la data in cui si prevede che inizi il picco di traffico.
1. Nel campo **[!UICONTROL Spike End Date]**, specifica la data in cui prevedi la fine del picco di traffico.
1. In **[!UICONTROL Peak Day Server Calls]** Specifica il totale previsto di visualizzazioni di picco della pagina al giorno durante il periodo di picco del traffico.
1. In **[!UICONTROL Peak Hour Server Calls]** Specifica il totale previsto di visualizzazioni della pagina di picco all’ora durante il periodo di picco del traffico.
1. Seleziona **[!UICONTROL Submit]**.

   Assicurati di specificare il totale delle visualizzazioni di pagina previste, non solo le visualizzazioni di pagina aggiuntive.

   >[!NOTE]
   >
   >Per pianificare un picco di traffico, includi un numero di telefono nelle tue informazioni di contatto dell’utente in modo che Adobe possa contattarti, se necessario, per eventuali domande.

## Perché è importante pianificare sempre i picchi di traffico

Quando i clienti segnalano ad Adobe i picchi di traffico per ogni suite di rapporti, Adobe fa tutto il possibile per garantire che questo abbia un impatto minimo sul reporting.

* Le organizzazioni con picchi di traffico pianificati ricevono la priorità se i dati iniziano a diventare latenti. L’importanza di questo concetto è particolarmente critico durante le festività, poiché molte organizzazioni pianificano picchi di traffico.
* Se Adobe nota che il traffico previsto è significativamente sovrastimato/sottostimato rispetto agli anni precedenti, può contattarti per verificare la precisione.
* È importante pianificare un picco di traffico ogni anno, anche se l’organizzazione riceve lo stesso picco ogni anno. Molte organizzazioni rilasciano nuove app, combinano suite di rapporti e migrano/ritirano suite di rapporti durante l’anno. Per Adobe non è possibile sapere con certezza quali suite di rapporti ricevono ulteriore traffico, a meno che l’organizzazione non pianifichi ogni volta un picco di traffico. Sebbene Adobe utilizzi i dati storici per ottenere una stima, è importante che tutte le risorse aggiuntive siano inserite nella suite di rapporti corretta.

## Azioni che la tua organizzazione può intraprendere

Adobe vuole assicurarsi che la tua esperienza con la creazione di rapporti aggiornati sia coerente. Per svolgere questa attività nel modo più efficace, Adobe consiglia vivamente quanto segue:

* Pianifica il lead time per tutti i picchi di traffico. **È particolarmente importante che qualsiasi picco di traffico anticipato nei mesi di novembre e dicembre sia programmato entro il 15 settembre**. Se non rispetti la scadenza, pianifica il picco il prima possibile. Un lead time ridotto è meglio che niente e Adobe lavora con le risorse correnti per adattarsi alle suite di rapporti nel modo migliore.
* Se Adobe ti contatta in relazione a un picco di traffico pianificato, assicurati di comunicare se è più importante generare rapporti in tempo reale o rapporti con elaborazione completa. Alcune organizzazioni si affidano al reporting in tempo reale più di altre. Sapere quale tipo di reporting utilizzi può aiutare Adobe ad assegnare le priorità di conseguenza.
* Comunicare al tuo account manager quali sono i report più importanti e quando li richiami può essere utile per avere il suo sostegno.
