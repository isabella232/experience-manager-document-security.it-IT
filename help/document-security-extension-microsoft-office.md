---
title: Introduzione a AEM Document Security Extension for Microsoft Office
description: Document Security Extension for Microsoft Office consente di applicare impostazioni di riservatezza ai file di Microsoft Office.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
translation-type: ht
source-git-commit: 19de0b62ac493c7507581abb607b008c64f77597
workflow-type: ht
source-wordcount: '1304'
ht-degree: 100%

---


# Introduzione a AEM Document Security Extension for Microsoft Office {#introduction-to-aem-document-security-extension-for-microsoft-office}

L’estensione Adobe® Experience Manager Document Security Extension for Microsoft® Office garantisce che solo le persone autorizzate possano utilizzare file Word, Excel e PowerPoint con contenuti protetti dai diritti di proprietà intellettuale dell’autore. Document Security Extension for Microsoft Office consente di applicare impostazioni di riservatezza ai file di Microsoft Office.

Document Security Extension for Microsoft Office estende i componenti aggiuntivi LiveCycle Rights Management e Document Security ad Adobe Experience Manager Forms per proteggere file Word, Excel e PowerPoint e consentire agli utenti autorizzati che dispongono di questo software di utilizzare file protetti tramite policy in base alle impostazioni di riservatezza definite nella policy.

## Come Document Security protegge la proprietà intellettuale {#how-document-security-protects-intellectual-property}

Document Security garantisce che solo le persone autorizzate possano utilizzare file protetti da diritti di proprietà intellettuale. Document Security consente infatti di proteggere i file tramite policy (o criteri) di riservatezza. Una *policy* è una raccolta di informazioni che comprendono impostazioni di riservatezza e un elenco di utenti autorizzati. Le impostazioni specificate in una policy determinano il modo in cui un destinatario può utilizzare i file a cui è associata la policy. Consentono di specificare, ad esempio, se i destinatari possono stampare o copiare il testo o salvare le modifiche.

Sia gli amministratori che gli utenti di Document Security possono creare policy. Gli amministratori creano policy organizzative disponibili per tutti gli utenti autorizzati. Gli amministratori e i coordinatori di set di policy possono anche creare gruppi o *set di policy* disponibili per un sottoinsieme di utenti. Gli utenti possono creare policy proprie, che possono essere utilizzate solo dall’utente che le ha create. Per creare le policy, gli amministratori, i coordinatori di set di policy e gli utenti possono utilizzare le pagine web di Document Security.

Sebbene siano memorizzate in Document Security, le policy vengono applicate ai file tramite Word, Excel o PowerPoint. Quando si applica una policy a un file, le informazioni contenute nel file vengono protette dalle impostazioni di riservatezza specificate nella policy. Quando si distribuisce un file protetto tramite policy, solo i destinatari autorizzati dalla policy possono accedere al contenuto del file.

Se si protegge un file mediante una policy, si ha un controllo costante del file, anche dopo averlo distribuito. È possibile verificare gli eventi per tenere traccia di come e quando i destinatari utilizzano il file, apportare modifiche alla policy, impedire ad altri utenti di continuare ad accedere al file e modificare la policy associata al file.

## Funzionamento delle policy {#how-policies-work}

Le policy contengono informazioni sugli utenti autorizzati e impostazioni di riservatezza da applicare alla proprietà intellettuale. Gli utenti possono essere costituiti da qualsiasi utente riconosciuto da Document Security tramite un elenco LDAP o Active Directory collegato. Possono essere anche persone invitate a registrarsi in Document Security o per le quali l’amministratore ha creato un account.

Le impostazioni di riservatezza di una policy determinano il modo in cui i destinatari possono utilizzare i file protetti dalla policy. Le policy consentono ad esempio di specificare se i destinatari possono stampare i file, copiarne i contenuti in altri file o salvare le modifiche apportate ai file protetti. Con le policy è possibile anche specificare impostazioni di riservatezza diverse per i vari utenti.

Quando si applica una policy a un file, le informazioni contenute nel file vengono protette dalle impostazioni di riservatezza specificate nella policy. Quando si distribuisce il file, Document Security autentica i destinatari che tentano di aprirlo e ne autorizza l’accesso in base ai privilegi specificati nella policy.

È possibile modificare in qualsiasi momento le impostazioni di riservatezza di una policy anche dopo che questa è stata applicata a un file; ad esempio, è possibile aggiungere o rimuovere utenti autorizzati o modificare i privilegi degli utenti dopo che hanno ricevuto il file. È possibile modificare la policy applicata al file, nonché revocare l’accesso al file in modo che chiunque abbia una copia del file non possa più aprirlo.

Se la policy consente l’accesso offline, i destinatari possono utilizzare i file protetti tramite policy anche in modalità offline (senza una connessione Internet o di rete attiva) per il periodo di tempo specificato nella policy.

## Funzionamento dei file protetti tramite policy {#how-policy-protected-files-work}

Per poter aprire e utilizzare file Word, Excel e PowerPoint protetti tramite policy, deve essere consentito l’accesso anonimo e l’utente deve essere incluso tra i destinatari della policy e aver installato Document Security Extension for Microsoft Office. Per mettere a disposizione un file protetto tramite policy a un utente che non dispone di Document Security Extension for Microsoft Office, è possibile fornirgli una copia del software o informarlo su come scaricare il file dal proprio sito web. Se necessario, il programma di installazione può essere scaricato dalla [pagina di download](https://www.adobe.com/it/products/livecycle/rightsmanagement/extension/downloads.html).

Quando un utente tenta di aprire un file protetto tramite policy, Document Security Extension for Microsoft Office si connette a Document Security per autenticare l’utente. Se Document Security è configurato per controllare le modalità di utilizzo del file, l’utente riceve una notifica con cui viene informato che l’utilizzo del file è sotto controllo. Document Security determina le autorizzazioni sui file da concedere all’utente, che potrà quindi utilizzare il file in base alle impostazioni della policy, alle seguenti condizioni:

* Per il periodo di validità specificato nella policy.
* Fino a quando un amministratore o la persona che ha applicato la policy non revoca l’accesso al file o modifica la policy.

   Se la persona che ha applicato la policy la modifica o revoca l’accesso al file, le autorizzazioni di cui dispone l’utente sul file vengono modificate o rimosse, anche se il file è già in suo possesso. Se il file è stato revocato, è possibile fornire all’utente un URL da cui scaricare una copia aggiornata.

   Se la policy prevede l’accesso offline, i file protetti tramite policy possono essere aperti offline (senza una connessione Internet o di rete) per la durata del periodo di lease specificato nella policy. Al termine di questo intervallo di tempo, l’utente deve tornare online ed effettuare la sincronizzazione con Document Security, che avvia un nuovo periodo di lease.

   Se la policy consente di salvare il file e l’utente salva una copia del file protetto dalla policy, questa viene automaticamente applicata e imposta al file salvato. Come per il file originale, vengono controllati e registrati anche gli eventi correlati, ad esempio i tentativi di aprire il nuovo file.

## Utilizzo di Document Security per proteggere i file {#using-document-security-to-protect-your-files}

È possibile utilizzare le policy per proteggere i file in varie situazioni.

Supponiamo ad esempio che un produttore debba ricevere le offerte di vari fornitori di componenti per un nuovo prodotto. Il produttore deve necessariamente fornire ai candidati le informazioni proprietarie necessarie per finalizzare le loro offerte. Utilizza quindi Document Security per proteggere i file con una policy che consenta ai candidati di aprire i file e visualizzarne le informazioni, senza tuttavia poter modificare, stampare o copiare i file. Chiunque non disponga delle necessarie autorizzazioni, inoltre, non potrà aprire i file.

Dopo aver selezionato l’offerta preferita, il produttore aggiorna la policy per concedere al candidato vincitore l’autorizzazione a stampare, copiare e salvare le modifiche in locale, e per rimuovere gli altri candidati che non potranno quindi più aprire i file.

Supponiamo inoltre che, in collaborazione con il candidato vincitore, gli ingegneri del produttore modifichino alcune specifiche di progettazione nei file. Per pubblicare le nuove specifiche, il produttore revoca l’accesso ad alcuni file e pubblica le nuove versioni. Quando gli ingegneri del candidato vincitore tentano di aprire il file, viene visualizzato un messaggio con cui vengono informati che l’accesso al file è stato revocato. Il messaggio contiene inoltre un URL da cui possono scaricare la nuova versione del file.

## Informazioni aggiuntive {#additional-information}

Le risorse elencate in questa tabella consentono di acquisire maggiore familiarità con AEM Document Security:

<table >
 <tbody>
  <tr>
   <th><p>Per informazioni su</p> </th>
   <th><p>Consulta</p> </th>
  </tr>
  <tr>
   <td><p>Guida per gli amministratori di AEM Forms</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65_it">Guida per gli amministratori</a> o, nelle pagine di amministrazione di Document Security, fai clic sul collegamento Help, in alto a destra.</p> </td>
  </tr>
  <tr>
   <td><p>Aggiornamenti patch, note tecniche e informazioni aggiuntive su questa versione del prodotto</p> </td>
   <td><p><a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html">Supporto tecnico per Experience Cloud</a></p> </td>
  </tr>
 </tbody>
</table>

