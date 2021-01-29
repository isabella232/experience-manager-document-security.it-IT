---
title: Introduzione a AEM Document Security Extension for Microsoft Office
description: Document Security Extension for Microsoft Office vi consente di applicare ai file di Microsoft Office impostazioni predefinite per la salvaguardia della riservatezza.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
translation-type: tm+mt
source-git-commit: 19de0b62ac493c7507581abb607b008c64f77597
workflow-type: tm+mt
source-wordcount: '1304'
ht-degree: 0%

---


# Introduzione a AEM Document Security Extension for Microsoft Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

 Adobe®  Experience Manager Document Security Extension for Microsoft® Office garantisce che i file Word, Excel e PowerPoint contenenti materiale protetto da diritti di proprietà intellettuale vengano utilizzati solo dalle persone autorizzate. Document Security Extension for Microsoft Office vi consente di applicare ai file impostazioni predefinite per la salvaguardia della riservatezza.

Document Security Extension for Microsoft Office estende il componente aggiuntivo di LiveCycle e Document Security per  Adobe Experience Manager Forms per proteggere i file Word, Excel e PowerPoint e consentire agli utenti autorizzati che hanno installato questo software di utilizzare i file protetti tramite criterio in base alle impostazioni di riservatezza definite nel criterio.

## Come Document Security protegge la proprietà intellettuale {#how-document-security-protects-intellectual-property}

Document Security garantisce che solo le persone autorizzate utilizzino i file contenenti materiale protetto dai diritti di proprietà intellettuale. Document Security vi consente di proteggere i file utilizzando criteri per la salvaguardia della riservatezza. Una *policy* è una raccolta di informazioni che include impostazioni per la salvaguardia della riservatezza e un elenco di utenti autorizzati. Le impostazioni specificate in un criterio determinano in che modo il destinatario può utilizzare un file al quale si applica il criterio. Ad esempio, potete specificare se i destinatari possono stampare o copiare il testo o salvare le modifiche.

Gli amministratori e gli utenti di Document Security creano i criteri. Gli amministratori creano criteri organizzativi disponibili per tutti gli utenti autorizzati. Gli amministratori o i coordinatori di set di criteri possono anche creare gruppi di criteri denominati *set di criteri* che possono essere resi disponibili a un sottoinsieme di utenti. Gli utenti possono creare criteri personalizzati, che possono essere utilizzati solo da loro. Gli amministratori, i coordinatori di set di criteri e gli utenti creano i criteri tramite le pagine Web di Document Security.

Sebbene siano memorizzati in Document Security, i criteri vengono applicati ai file tramite Word, Excel o PowerPoint. Quando applicate un criterio a un file, le informazioni contenute nel file vengono protette dalle impostazioni di riservatezza specificate nel criterio. Quando distribuite il file protetto tramite criterio, solo i destinatari autorizzati dal criterio possono accedere al contenuto del file.

L&#39;utilizzo di un criterio per proteggere un file consente di controllare costantemente tale file, anche dopo averlo distribuito. È possibile controllare gli eventi per tenere traccia di quando e come i destinatari utilizzano il file, apportare modifiche al criterio, impedire agli utenti di continuare ad accedere al file e modificare il criterio associato al file.

## Funzionamento dei criteri {#how-policies-work}

I criteri contengono informazioni sugli utenti autorizzati e le impostazioni di riservatezza da applicare alla proprietà intellettuale. Gli utenti possono essere qualsiasi utente riconosciuto da Document Security tramite l&#39;inclusione in un elenco LDAP o Active Directory collegato. Possono essere utenti anche le persone invitate a registrarsi in Document Security o per le quali l&#39;amministratore ha creato un account.

Le impostazioni di riservatezza in un criterio determinano in che modo i destinatari possono utilizzare i file protetti dal criterio. Ad esempio, i criteri specificano se i destinatari possono stampare i file, copiare il contenuto in altri file o salvare le modifiche apportate ai file protetti. I criteri possono anche specificare impostazioni di riservatezza diverse per i vari utenti.

Quando applicate un criterio a un file, le informazioni contenute nel file vengono protette dalle impostazioni di riservatezza specificate nel criterio. Quando distribuite il file, Document Security autentica i destinatari che cercano di aprirlo e ne autorizza l&#39;accesso in base ai privilegi specificati nel criterio.

Dopo che un criterio è stato applicato a un file, le impostazioni di riservatezza del criterio possono essere modificate in qualsiasi momento, consentendo di aggiungere o rimuovere utenti autorizzati o di modificare i privilegi per gli utenti dopo che hanno ricevuto il file. Il criterio applicato al file può essere modificato e l&#39;accesso al file può essere revocato in modo che chiunque abbia una copia del file non possa più aprirlo.

Se il criterio consente l&#39;accesso offline, i destinatari possono anche utilizzare i file protetti tramite criterio offline (senza una connessione Internet o di rete attiva) per il periodo di tempo specificato nel criterio.

## Funzionamento dei file protetti tramite criterio {#how-policy-protected-files-work}

Per poter aprire e utilizzare i file Word, Excel e PowerPoint protetti tramite criterio, l&#39;utente deve avere installato Document Security Extension for Microsoft Office ed essere incluso come destinatario nel criterio oppure il criterio deve consentire l&#39;accesso anonimo. Se desiderate dare un file protetto tramite criterio a un utente che non possiede Document Security Extension for Microsoft Office, fornitegli una copia del software o informatelo su come scaricarlo dal vostro sito Web. Se non disponete del programma di installazione, potete scaricarlo dalla [pagina di download](https://www.adobe.com/products/livecycle/rightsmanagement/extension/downloads.html).

Quando un utente tenta di aprire un file protetto tramite criterio, Document Security Extension for Microsoft Office si connette a Document Security per autenticare l&#39;utente. Se Document Security è configurato per il controllo dell&#39;utilizzo del file, l&#39;utente riceve una notifica per informarlo che l&#39;utilizzo del file è sottoposto a controllo. Document Security determina le autorizzazioni sui file da concedere all&#39;utente, che può quindi utilizzare il file in base alle impostazioni del criterio, alle seguenti condizioni:

* Per il periodo di validità specificato nel criterio.
* Fino a quando un amministratore o la persona che ha applicato il criterio revoca l&#39;accesso al file o cambia il criterio.

   Se la persona che ha applicato il criterio cambia il criterio o revoca l&#39;accesso al file, le autorizzazioni dell&#39;utente per il file vengono modificate o rimosse anche se l&#39;utente ha già il file. Se il file è stato revocato, è possibile fornire un URL all&#39;utente per ottenere una copia aggiornata.

   I file protetti tramite criterio possono essere aperti offline (senza una connessione Internet o di rete), se il criterio consente l&#39;accesso offline, per la durata del periodo di tempo consentito dal criterio. Al termine del periodo consentito per l&#39;utilizzo non in linea, l&#39;utente deve andare online e sincronizzarsi con Document Security, che dà inizio a un nuovo periodo consentito.

   Se il criterio consente il salvataggio del file e l&#39;utente ne salva una copia, il criterio viene applicato e imposto automaticamente al file salvato. Gli eventi, come i tentativi di aprire il nuovo file, vengono anche sottoposti a controllo e registrati come per il file originale.

## Utilizzo di Document Security per proteggere i file {#using-document-security-to-protect-your-files}

Potete utilizzare i criteri per proteggere i file in varie situazioni.

Ad esempio, un produttore accetta offerte da fornitori che forniranno componenti per un nuovo prodotto. Il fabbricante deve fornire agli offerenti le informazioni proprietarie necessarie per finalizzare le loro comunicazioni. Il produttore utilizza Document Security per proteggere i file con un criterio che consente agli offerenti di aprire i file e visualizzarne le informazioni. Tuttavia, agli offerenti non è consentito modificare, stampare o copiare i file e a chiunque non disponga dell&#39;autorizzazione non è consentito aprire i file.

Dopo aver accettato una delle offerte, il produttore aggiorna il criterio per concedere all&#39;offerente vincente le autorizzazioni per stampare, copiare e salvare localmente le modifiche e per rimuovere gli offerenti non vincenti in modo che non abbiano più l&#39;autorizzazione per aprire i file.

Mentre lavorate con l&#39;offerente vincente, gli ingegneri del produttore modificano alcune specifiche di progettazione nei file. Per pubblicare le nuove specifiche, il produttore revoca l&#39;accesso ad alcuni file e pubblica nuove versioni. Quando gli ingegneri dell&#39;offerente vincente tentano di aprire il file, viene visualizzato un messaggio che informa che l&#39;accesso al file è stato revocato. Il messaggio contiene un URL dal quale è possibile scaricare una nuova versione del file.

## Informazioni aggiuntive {#additional-information}

Le risorse riportate in questa tabella possono essere utili per ulteriori informazioni su AEM Document Security:

<table >
 <tbody>
  <tr>
   <th><p>Per informazioni su</p> </th>
   <th><p>Consulta</p> </th>
  </tr>
  <tr>
   <td><p>AEM moduli - Guida per l'amministratore</p> </td>
   <td><p><a href="http://www.adobe.com/go/learn_aemforms_admin_65">Administrator </a> Helpor, nelle pagine di amministrazione di Document Security, fate clic sul collegamento della guida in linea situato nell'angolo superiore destro di una pagina.</p> </td>
  </tr>
  <tr>
   <td><p>Aggiornamenti patch, note tecniche e informazioni aggiuntive su questa versione del prodotto</p> </td>
   <td><p><a href="https://helpx.adobe.com/it/marketing-cloud/contact-support.html">Supporto tecnico Marketing Cloud</a></p> </td>
  </tr>
 </tbody>
</table>

