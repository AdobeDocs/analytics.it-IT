---
description: 'null'
title: Mappatura di elementi dati su variabili Analytics
uuid: null
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# Mappa gli elementi dei dati di avvio sulle variabili di Analytics


Dopo aver [mappato gli oggetti del livello dati sugli elementi](https://docs.adobe.com/content/help/en/analytics/implementation/layer-to-elements.md)di dati di Launch, puoi mappare gli elementi dati sulle variabili [di](https://docs.adobe.com/content/help/en/analytics/implementation/vars/overview.html)Analytics.

Per mappare gli elementi dei dati di Launch alle variabili di Analytics:

1. Se applicabile, assegnare l’elemento dati a una variabile globale. Alcuni elementi di dati, come Nome ** pagina, si applicano a tutte le pagine di una proprietà. In casi come questo, potete impostare la variabile a livello globale effettuando le seguenti operazioni:

2. In Launch, scorri verso il basso e fai clic su **Extensions Catalog**.

   ![Catalogo delle estensioni](assets/extensions.png)

3. Fai clic su **Configura** in Analytics.

   ![Estensione Analytics](assets/configure.png)


4. In **eVar** in Variabili **** globali, selezionate la [eVar impostata](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) per essere associata alla variabile. Selezionate **Imposta come**, quindi fate clic sull&#39;icona a barre nel campo più a destra per specificare l&#39;elemento dati.

   ![Specifica eVar](assets/evars.png)

5. Nella finestra a comparsa **Seleziona elemento** dati, selezionare l&#39;elemento dati da applicare alla variabile.

6. Fai clic su **Salva.**


In alternativa, se l&#39;elemento dati non è associato a una variabile globale, è possibile [creare semplicemente una regola](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) che assegna gli elementi dati a prop o evar.
