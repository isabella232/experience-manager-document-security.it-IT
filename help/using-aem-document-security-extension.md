---
title: Utilizzo di AEM Document Security Extension for Microsoft Office
description: Potete controllare in che modo i destinatari utilizzano i file protetti tramite criterio, indipendentemente dalla loro estensione. Il documento spiega come proteggere i file e come lavorare con i file protetti.
uuid: db4abbc8-eb21-4f4a-9950-224ada95ce66
content-type: reference
topic-tags: using
discoiquuid: f4c2460c-174f-4e4d-b804-1eb051d2781e
translation-type: tm+mt
source-git-commit: 21288f7f1c8f786d3c4c363986226038bdb03e26
workflow-type: tm+mt
source-wordcount: '6270'
ht-degree: 0%

---


# Utilizzo di AEM Document Security Extension for Microsoft Office{#using-aem-document-security-extension-for-microsoft-office}

## File Protect che utilizzano AEM Document Security Extension {#usingaemdocumentsecurityextensiontoprotectfiles}

Potete controllare in che modo i destinatari utilizzano i file protetti tramite criterio, indipendentemente dalla loro estensione.

Document Security Extension for Microsoft Office vi consente di effettuare le seguenti operazioni:

* Configurare la connessione a Document Security
* Applicazione di un criterio a un file
* Aprire le pagine Web di Document Security per creare e gestire i criteri utente
* Rimozione della protezione tramite criterio di un file
* Modificare il criterio applicato a un file
* Aprire le pagine Web di Document Security per revocare l&#39;accesso ai file o modificare il criterio del file
* Aprire le pagine Web di Document Security per visualizzare la cronologia del controllo del file

### Connessione a un server di Document Security {#connect-to-a-document-security-server}

Se intendete applicare criteri ai file, dovete configurare le impostazioni di connessione per Document Security. A seconda di come è stato installato Document Security Extension for Microsoft Office, potrebbero essere già presenti impostazioni di connessione predefinite. Potete aggiungere le impostazioni di connessione per una o più istanze di Document Security. Potete ottenere informazioni sul server dall&#39;amministratore di Document Security.

È necessario impostare come server predefinito il server che si desidera utilizzare per proteggere i file o gestire i file protetti. Quando applicate un criterio a un nuovo file o aprite le pagine Web di Document Security, Document Security Extension for Microsoft Office si connette al server predefinito. Se proteggete i file utilizzando più di un&#39;istanza di Document Security, dovete modificare l&#39;impostazione del server predefinito quando passate da un server all&#39;altro. Potete aprire i file protetti da qualsiasi istanza di Document Security a condizione che disponiate dell&#39;autorizzazione per aprire il file.

Se il server Document Security utilizza l&#39;autenticazione basata sui certificati, dovrete installare il certificato ricevuto nel computer locale. Vi verrà richiesto di scegliere l&#39;autenticazione tramite certificato e fornire il certificato da utilizzare per l&#39;autenticazione.

Dopo aver configurato le impostazioni di connessione per un&#39;istanza di Document Security in un&#39;applicazione Microsoft Office, questa viene configurata per Word, Excel e PowerPoint.

#### Installare il certificato lato client {#install-the-client-side-certificate}

Se dovete accedere alle pagine Web di Document Security tramite l&#39;autenticazione tramite certificato o l&#39;autenticazione a due vie, riceverete il certificato da installare nel computer locale. Riceverete un file di certificato (file .PFX o .P12) e la relativa password.

1. Salvate il file del certificato nel computer locale.
1. Fare doppio clic sul file del certificato per aprire l&#39;Importazione guidata certificati e fare clic su **Avanti**.
1. Fare clic su **Next** se il file del certificato è elencato nella casella del nome del file. Fare clic su **Sfoglia** per individuare un altro certificato.
1. Immettere la password ricevuta e fare clic su **Avanti**.
1. Nella finestra di dialogo Archivio certificati, selezionare Inserisci tutti i certificati nel seguente archivio, quindi fare clic su **Sfoglia**.
1. Nella finestra di dialogo Seleziona archivio certificati, selezionare Personale, fare clic su **OK**, fare clic su **Avanti**, quindi fare clic su **Fine**.

#### Configurare le impostazioni di connessione {#configure-connection-settings}

1. In Document Security Extension for Microsoft Office 2010 e Office 2013, nella scheda **Document Security**, selezionate **Scegli server**.
1. Fare clic su **Nuovo** per creare nuove impostazioni di connessione, oppure selezionare una connessione esistente e fare clic su **Modifica**.
1. Digitare un nome per la connessione nella casella **Nome**. Potete usare qualsiasi nome.
1. Digitare l&#39;indirizzo del server nella casella **Indirizzo server**.
1. Digitare la porta del server nella casella **Porta**.
1. (Facoltativo) Se desiderate ricordare il nome utente e la password, selezionate **Ricorda password su questo computer** e digitate il nome utente e la password nelle caselle corrispondenti. Si consiglia di non selezionare questa opzione se altri utenti possono accedere al computer.
1. Fare clic su **Connetti a questo server**. Document Security Extension for Microsoft Office cerca di connettersi al server specificato. A seconda del tipo di autenticazione specificato, effettuare una delle seguenti operazioni:

   **Nome utente e password**

   Immettete il nome utente e la password che avete ricevuto dall&#39;amministratore di Document Security.

   **Autenticazione certificato**

   Scegliete questa opzione per selezionare il certificato ricevuto e installato nell&#39;archivio certificati personale.

   Se in Document Security è configurato un solo tipo di autenticazione, viene visualizzata solo tale opzione.

>[!NOTE]
>
>Se non riuscite a connettervi al server, provate ad aprire le pagine Web di Document Security in Internet Explorer. Se non riuscite a connettervi al server utilizzando Internet Explorer o se viene visualizzato un avviso relativo al certificato del server, Document Security Extension for Microsoft Office non è in grado di connettersi al server. Per assistenza, contattare l&#39;amministratore del server.

>[!NOTE]
>
>Se non riuscite a connettervi a Document Security, viene visualizzato un messaggio che indica che &quot;Il nome utente e la password non sono corretti. Controllare le impostazioni di configurazione e riprovare&quot;. Questo messaggio potrebbe essere visualizzato se non riuscite a connettervi per un altro motivo. Se vi state connettendo al server per la prima volta, verificate di aver impostato correttamente il nome del server e la porta.

#### Specificare il server predefinito {#specify-the-default-server}

1. Effettua le seguenti operazioni:

   * In Document Security Extension for Microsoft Office 2010 e Office 2013, nella scheda **Document Security**, selezionate **Scegli server**.

1. Selezionare un server da specificare come predefinito e fare clic su **Imposta come predefinito**. Accanto al server predefinito viene visualizzata una stella.

### Utilizzo di provider di autenticazione di terze parti {#using-third-party-authentication-providers}

Potete utilizzare provider di autenticazione di terze parti con  AEM Forms Document Security. Questi provider di autenticazione consentono di aggiungere un ulteriore livello di accesso ai documenti protetti.  AEM Forms Document Security supporta i seguenti flussi di lavoro di autenticazione estesa:

* Autenticazione estesa tramite URL AEM Forms  predefinito
* Autenticazione estesa mediante un URL personalizzato
* Flusso di lavoro di autenticazione estesa predefinito con provider di identità di terze parti configurati su  AEM Forms sul server JEE
* Flusso di lavoro di autenticazione estesa personalizzato con provider di identità di terze parti configurati su  AEM Forms sul server JEE
* Autenticazione estesa mediante pagina personalizzata per l&#39;elenco delle autenticazioni SAML

#### Autenticazione estesa mediante l&#39;URL AEM Forms predefinito  {#extended-authentication-using-default-aem-forms-url}

Potete utilizzare  URL AEM Forms predefinito per l&#39;autenticazione estesa. La pagina di destinazione predefinita contiene  marchio di Adobe. Inoltre,  impostazioni AEM Forms predefinite vengono utilizzate per l&#39;utilizzo  URL AEM Forms predefinito per l&#39;autenticazione estesa.

Effettuate le seguenti operazioni per abilitare l&#39;autenticazione estesa con l&#39;URL di destinazione  Adobe predefinito:

1. Aprite &#39;interfaccia utente di amministrazione di AEM Forms.
1. Passa a Servizi > Document Security > Configuration > Server Configuration (Configurazione server).
1. Abilitate l&#39;opzione Consenti autenticazione estesa.
1. Specificate l&#39;URL di destinazione per l&#39;autenticazione estesa dell&#39;URL predefinito. L’URL predefinito è http://localhost:8080/edc/extendedauthentication/welcome.jsp.

   Fai clic su **[!UICONTROL Salva]**.

   >[!NOTE]
   >
   >Utilizzate un nome host completo nell&#39;URL. Si consiglia di utilizzare il protocollo HTTPS.

   Ora,  protezione dei documenti AEM Forms è configurata per utilizzare l&#39;autenticazione estesa con l&#39;URL di destinazione AEM Forms  predefinito.

   ![](assets/third-party-authentication.png)

#### Autenticazione estesa con URL di destinazione personalizzato {#extended-authentication-with-a-custom-landing-url}

Potete utilizzare un URL personalizzato per l&#39;autenticazione estesa. Offre la flessibilità necessaria per visualizzare una pagina di autenticazione personalizzata con un marchio personalizzato. Ad esempio, il branding per l’organizzazione.

È possibile creare un pacchetto della pagina di autenticazione personalizzata in un file di guerra e distribuire il file di guerra  server AEM Forms. Il file di guerra contiene una logica completa per accettare le credenziali utente e autenticarsi sul server AEM Forms .  AEM Forms Document Security dispone dei seguenti requisiti per la pagina di autenticazione personalizzata:

* La pagina di autenticazione deve inviare nome utente come j_username e password come j_password. La pagina deve inoltre inviare source_url e login_url come parametri nascosti.
* Se l’autenticazione ha esito positivo, la pagina deve essere chiusa automaticamente.

Per abilitare l&#39;autenticazione estesa con un URL di destinazione personalizzato, effettuate le seguenti operazioni:

1. Distribuire il file di guerra di autenticazione personalizzato  server AEM Forms.
1. Aprite &#39;interfaccia utente di amministrazione di AEM Forms.
1. Passa a Servizi > Document Security > Configuration > Server Configuration (Configurazione server).
1. Abilitate l&#39;opzione Consenti autenticazione estesa e specificate l&#39;URL di destinazione autenticazione estesa personalizzato.
1. Aggiungete le seguenti voci al file config.xml sotto il nodo SSO dopo la voce *&lt;node name=&quot;AllowedUrls&quot;>*:

   >[!NOTE]
   >
   >&lt;entry>!discoiqbr!!&lt;entry>!discoiqbr!!&lt;entry>!discoiqbr!!

   Per informazioni dettagliate sull&#39;aggiornamento del file config.xml, vedere [Modifica manuale del file di configurazione della protezione del documento](https://helpx.adobe.com/aem-forms/6-3/admin-help/configuring-client-server-options.html#manually_editing_the_document_security_configuration_file).

   Ora  protezione dei documenti AEM Forms è configurata per l&#39;utilizzo dell&#39;autenticazione estesa con un URL di destinazione personalizzato

#### Flusso di lavoro di autenticazione estesa predefinito con provider di identità di terze parti configurati  server AEM Forms {#default-extended-authentication-workflow-with-third-party-identity-providers-configured-on-aem-forms-server}

L&#39;autenticazione estesa può utilizzare tipi diversi di autenticazione disponibili  server AEM Forms. Ad esempio, SAML, [Ulteriori esempi].

Nota: Se i fornitori SAML sono configurati  server AEM Forms, prima di visualizzare l&#39;URL di destinazione viene visualizzata una pagina contenente tutti i provider di identità configurati per le autenticazioni SAML.

Quando un documento protetto viene aperto in  Acrobat, viene visualizzata la schermata seguente.

#### Flusso di lavoro di autenticazione estesa personalizzato quando i fornitori SAML sono configurati  server AEM Forms {#custom-extended-authentication-workflow-when-saml-providers-are-configured-on-aem-forms-server}

Se i fornitori SAML sono configurati  server AEM Forms, prima di visualizzare l&#39;URL di destinazione viene visualizzata una pagina contenente tutti i provider di identità configurati per le autenticazioni SAML.

Possibilità di configurare un flusso di lavoro di autenticazione estesa personalizzato quando i fornitori SAML sono configurati  server AEM Forms sono:

* Le autenticazioni SAML sono configurate  server AEM Forms
* La guerra personalizzata, contenente una pagina di autenticazione personalizzata e la logica completa per accettare le credenziali utente e autenticarsi sul server AEM Forms , viene distribuita  server AEM Forms.

#### Utilizzo di una pagina personalizzata per l&#39;elenco delle autenticazioni SAML {#using-custom-page-for-listing-saml-authentications}

Potete inoltre visualizzare una pagina personalizzata per includere tutti i provider di autenticazione configurati  server AEM Forms. Per creare una pagina di questo tipo, effettuate le seguenti operazioni:

1. Creare un pacchetto della pagina di autenticazione personalizzata in un file di guerra e distribuire il file di guerra  server AEM Forms. Il file di guerra contiene una logica completa per accettare le credenziali utente e autenticarsi sul server AEM Forms .
1. Aprite  interfaccia utente amministratore AEM Forms e andate a **[!UICONTROL Impostazioni]**> **[!UICONTROL Gestione utente]** > **[!UICONTROL Configurazione]** > **[!UICONTROL Impostazioni provider di servizi SAML]**.
1. Aggiungere quanto segue al campo Proprietà personalizzate e fare clic su **[!UICONTROL Salva]**.

   *saml.sp.di.url=/demoJSP/saml_discovery.jsp*

   Ora,  protezione dei documenti AEM Forms è configurata per visualizzare una pagina personalizzata contenente tutti i provider di autenticazione configurati.

### Ottenere un account utente {#obtaining-a-user-account}

Se non disponete già di un account Document Security, Document Security potrebbe avviare il processo di registrazione al verificarsi di tali eventi:

* Un utente di Document Security che desidera inviarvi un file protetto tramite criterio vi aggiunge a un criterio.
* L&#39;amministratore di Document Security crea un account per voi.

Dopo aver registrato e attivato l&#39;account, potete utilizzare i file protetti tramite criterio che vi sono stati concessi l&#39;autorizzazione a utilizzare tramite un criterio.

>[!NOTE]
Se ricevete un file protetto tramite criterio e non disponete di un account Document Security o se ricevete un invito a registrarvi, rivolgetevi alla persona che vi ha inviato il file per assistenza.

Se ricevete un invito per la registrazione tramite e-mail da Document Security, potete registrarvi utilizzando l&#39;URL contenuto nel messaggio e-mail per aprire la pagina di registrazione online. Dopo la registrazione, riceverete un secondo avviso sull&#39;attivazione dell&#39;account.

#### Ottenere un account utente esterno {#obtain-an-external-user-account}

1. Aprite il messaggio di posta elettronica di registrazione a Document Security. L&#39;URL contenuto nel messaggio contiene un collegamento alla pagina di registrazione degli utenti esterni di Document Security. Se non ricevete un messaggio di registrazione, rivolgetevi alla persona che vi ha inviato il file per assistenza.
1. Fate clic sull’URL o copiatelo e incollatelo nel browser.
1. Digitate il vostro nome, la vostra organizzazione e la vostra password nelle caselle corrispondenti. La password può contenere una combinazione qualsiasi di otto caratteri.

   >[!NOTE]
   Accertatevi di scegliere una password facile da ricordare; non è disponibile alcun metodo per la ricerca di password dimenticate.

1. Fare clic su **Register**. Viene visualizzato un messaggio per informarvi di controllare l’indirizzo e-mail relativo a un messaggio e-mail di attivazione.
1. Aprite il messaggio e-mail di conferma della registrazione a Document Security.
1. Fate clic sull’URL che appare nel messaggio.
1. Fate clic sul collegamento alla pagina di accesso.
1. Nella casella **Nome utente**, digitate l&#39;indirizzo e-mail con cui vi siete registrati in Document Security. Questo indirizzo e-mail è il vostro nome utente predefinito di Document Security.
1. Nella casella **Password**, digitare la password creata al momento della registrazione.
1. Fare clic su **Login**.

### Creazione e gestione di criteri {#creating-and-managing-policies}

Se disponete dell&#39;autorizzazione dell&#39;amministratore di Document Security, potete creare criteri da applicare ai vostri file nella pagina Web Criteri di Document Security.

Alcune delle impostazioni dei criteri disponibili per la creazione dei criteri nelle pagine Web di Document Security non sono supportate per i file Word, Excel e PowerPoint. Le tabelle seguenti descrivono il mapping delle autorizzazioni dei criteri alle funzioni Word, Excel e PowerPoint.

<table>
 <thead>
  <tr>
   <th><p>Autorizzazioni </p></th>
   <th><p>Supporto per Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Stampa &gt; Non consentita</p></td>
   <td><p>La stampa del file non è consentita.</p></td>
  </tr>
  <tr>
   <td><p>Stampa &gt; Consentita</p></td>
   <td><p>La stampa del file è consentita.</p><p><strong>Nota</strong>:  <i>Se un criterio fornisce l'autorizzazione Copia ma non l'autorizzazione Stampa, è possibile stampare il contenuto copiato in un altro file.</i></p></td>
  </tr>
  <tr>
   <td><p>Stampa &gt; A Basso Prezzo Solo</p></td>
   <td><p>Non applicabile.</p></td>
  </tr>
  <tr>
   <td><p>Modifica &gt; Qualsiasi</p></td>
   <td><p>Il file può essere modificato.</p><p>Se questa autorizzazione non viene concessa, non potete modificare i file Word ed Excel protetti. Potete modificare i file PowerPoint ma non salvare le modifiche o visualizzare le presentazioni per i file modificati.</p></td>
  </tr>
  <tr>
   <td><p>Modifica &gt; Non consentita</p></td>
   <td><p>Gli utenti non possono modificare i file protetti.</p></td>
  </tr>
  <tr>
   <td><p>Modifica &gt; Modifica pagine</p></td>
   <td><p>Non applicabile.</p><p>Include inserimento, eliminazione e rotazione delle pagine.</p></td>
  </tr>
  <tr>
   <td><p>Modifica &gt; Fill &amp; Sign</p></td>
   <td><p>Non applicabile.</p></td>
  </tr>
  <tr>
   <td><p>Offline</p></td>
   <td><p>Il file può essere aperto offline.</p></td>
  </tr>
  <tr>
   <td><p>Copia</p></td>
   <td><p>Il contenuto del file può essere copiato in altri file.</p></td>
  </tr>
  <tr>
   <td><p>Reader </p></td>
   <td><p>Gli assistenti vocali (dispositivi per gli utenti con problemi di vista) possono leggere il contenuto del file.</p></td>
  </tr>
  <tr>
   <td><p>Validità autorizzazione</p></td>
   <td><p>Supportato.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Impostazioni generali</p></th>
   <th><p>Supporto per Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Periodo di validità</p></td>
   <td><p>Supportato.</p></td>
  </tr>
  <tr>
   <td><p>Controllo documento</p></td>
   <td><p>Supportato.</p></td>
  </tr>
  <tr>
   <td><p>Periodo di tempo consentito per l'utilizzo automatico offline</p></td>
   <td><p>Supportato.</p></td>
  </tr>
  <tr>
   <td><p>Provider di autorizzazioni esterni</p></td>
   <td><p>Supportato.</p></td>
  </tr>
 </tbody>
</table>

<table>
 <thead>
  <tr>
   <th><p>Impostazioni avanzate</p></th>
   <th><p>Supporto per Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Filigrane dinamiche</p></td>
   <td><p>Supportato.</p></td>
  </tr>
  <tr>
   <td><p>Plug-in di certificazione</p></td>
   <td><p>Non applicabile.</p></td>
  </tr>
  <tr>
   <td><p>Algoritmo di cifratura e lunghezza della chiave </p></td>
   <td><p>Sono supportate tutte le opzioni.</p></td>
  </tr>
  <tr>
   <td><p>Limitazione documento</p></td>
   <td><p>Tutto il contenuto del file viene sempre cifrato, indipendentemente dall'impostazione del criterio.</p></td>
  </tr>
  <tr>
   <td><p>Messaggio di errore di accesso negato</p></td>
   <td><p>Supportato.</p></td>
  </tr>
 </tbody>
</table>

Per ulteriori informazioni sulla creazione e la gestione dei criteri, vedere [Guida per l&#39;utente finale di Document Security](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

### Applica criteri {#applying-policies}

Potete applicare a un file qualsiasi criterio disponibile, inclusi i criteri creati e quelli che fanno parte di set a cui avete accesso. Prima di applicare un criterio, è necessario salvare il file.

Dopo aver applicato un criterio, questo viene aggiunto all&#39;elenco dei criteri utilizzati di recente nel menu AEM Document Security per facilitare l&#39;applicazione dei criteri utilizzati più di frequente. Se utilizzate più di un&#39;istanza di Document Security, nell&#39;elenco dei criteri utilizzati di recente vengono visualizzati solo quelli del server a cui siete attualmente connessi o del server predefinito, se non avete ancora eseguito l&#39;accesso a un&#39;istanza di Document Security.

>[!NOTE]
È possibile applicare i criteri solo ai file di documenti di Word (.doc, .docx e .docm in Microsoft Office 2010 e 2013), ai file di cartelle di lavoro di Excel (.xls, .xlsx e .xlsm in Microsoft Office 2010 e 2013) e ai file di presentazione di PowerPoint (.ppt, .pptx, e .pptm in Microsoft Office 2010 e 2013). Non è possibile applicare criteri ai file di modelli Word (.dot), di modelli Excel (.xlt) e di modelli di struttura PowerPoint (.pot).

#### Applicare un criterio {#apply-a-policy}

1. In Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Proteggi > Scegli criterio**.

   Se scegliete nome utente e password come metodo di autenticazione sul server e non avete ancora fornito le informazioni di accesso a Document Security, viene visualizzata una finestra di dialogo in cui immettere il nome utente e la password.

1. Selezionate un criterio dall&#39;elenco e fate clic su **Applica**.
1. Salvate il file.

#### Applicare un criterio utilizzato di recente {#apply-a-recently-used-policy}

1. In Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Secure > ***[Policy Name]*.
1. Salvate il file.

## Operazioni con i file protetti tramite criterio {#usingaemdocumentsecurityextensionpolicyprotectedfiles}

I file protetti tramite criterio contengono materiale protetto da diritti di proprietà intellettuale di proprietà dell&#39;autore e protetto tramite Document Security.

Potete utilizzare i file protetti tramite criterio sia che siate interni o esterni all&#39;organizzazione di pubblicazione dei file. Per aprire i file protetti tramite criterio, è necessario essere riconosciuti da Document Security, sia tramite l&#39;inclusione in un elenco LDAP o Active Directory collegato, l&#39;aggiunta come utente locale per i moduli di LiveCycle o AEM in JEE, sia mediante la registrazione in Document Security dopo essere stati invitati come utenti.

Se ricevete un file protetto tramite criterio e non disponete di un account Document Security o se ricevete un invito a registrarvi, rivolgetevi alla persona che vi ha inviato il file per assistenza.

### Utilizzo dei file protetti tramite criterio in Microsoft Office {#working-with-policy-protected-files-in-microsoft-office}

Document Security Extension for Microsoft Office limita alcune funzionalità di Word, Excel e PowerPoint per proteggere la proprietà intellettuale dell&#39;autore del file. Se non disponete dell&#39;autorizzazione per modificare il file, non potete salvare le modifiche apportate.

Se state lavorando con un file protetto tramite criterio, alcune funzioni del prodotto potrebbero non essere disponibili o non funzionare normalmente. Se disponete anche di un file non protetto aperto, la maggior parte delle funzioni sono abilitate per il file non protetto, ad eccezione di quelle che consentono di importare o copiare contenuto da un file protetto tramite criterio per il quale non disponete delle autorizzazioni di copia o esportazione.

>[!NOTE]
Quando utilizzate le applicazioni Office supportate da Document Security Extension, si consiglia di disabilitare Protezione esecuzione programmi di Windows. Inoltre, per fare in modo che le applicazioni Office vengano avviate senza problemi nei computer in cui sono installati Document Security Extension e McAfee VirusScan con l&#39;opzione per la scansione all&#39;accesso abilitata, disattivate l&#39;opzione relativa alla protezione dell&#39;overflow del buffer nella console di McAfee VirusScan.

Se una funzione non è disponibile, il nome del comando nel menu e il pulsante della barra degli strumenti correlati non sono disponibili. In Document Security Extension for Microsoft Office, quando passate il puntatore del mouse sul comando o sul pulsante, una descrizione comandi indica che Document Security ha reso il comando non disponibile.

### Apertura di file protetti tramite criterio {#opening-policy-protected-files}

Potete aprire i file protetti tramite criterio usando gli stessi metodi utilizzati per aprire qualsiasi altro file. Se non avete ancora eseguito l&#39;accesso a Document Security, vi verrà richiesto di farlo, a meno che non siate connessi a Internet e possiate aprire il file offline. Se annullate la procedura di accesso, l&#39;accesso viene negato.

Se non disponete dell&#39;autorizzazione per aprire il file, vi verrà comunicato che l&#39;accesso è stato negato. Se i privilegi di accesso al file sono stati revocati, è possibile che venga indirizzato a una versione aggiornata del file, se disponibile. Per ulteriore assistenza, se non riuscite ad aprire un file protetto tramite criterio, contattate l&#39;autore del file.

Quando un file protetto viene aperto, nella barra del titolo, dopo il nome del file viene visualizzato del testo che informa che il file è protetto tramite AEM Document Security.

Quando aprite un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server, verificate che il programma di Microsoft Office associato al tipo di file, ad esempio Microsoft Word, Microsoft Excel o Microsoft PowerPoint, sia aperto. Se provate ad aprire il file senza aprire l&#39;applicazione associata, il documento potrebbe non venire aperto e verrà visualizzato un messaggio di errore che indica che è necessario installare il plug-in appropriato. Oltre ad avviare l&#39;applicazione richiesta, si consiglia di svuotare la cartella della cache prima di aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server. Inoltre, quando si apre un documento protetto da SharePoint Server, tutte le autorizzazioni sul documento vengono disattivate, indipendentemente dal criterio applicato.

A seconda del metodo di autenticazione implementato in Document Security, all&#39;apertura di un documento protetto potrebbe essere richiesto di scegliere il metodo di autenticazione. Se Document Security supporta più di un metodo di autenticazione, le opzioni di autenticazione vengono presentate all&#39;utente. Ad esempio, se il server di Document Security fornisce l&#39;autenticazione tramite nome utente/password e tramite certificato, potete scegliere il metodo di autenticazione appropriato. Se l&#39;autenticazione basata sui certificati è abilitata, viene richiesto di utilizzare il certificato ricevuto e installato.

L&#39;esperienza utente all&#39;apertura dei file protetti dipende dalla configurazione dell&#39;autenticazione reciproca sul server. Se è installato un solo certificato client valido, non viene visualizzata alcuna finestra di dialogo di autenticazione e i file vengono aperti correttamente. Tuttavia, se in un computer sono installati più certificati client, viene visualizzata una finestra di dialogo di autenticazione. L&#39;utente deve scegliere un certificato valido per aprire il file protetto.

### Rimozione della protezione tramite criterio da un file {#removing-policy-protection-from-a-file}

Se siete autorizzati, potete rimuovere la protezione tramite criterio dai file che avete protetto. In questo caso, il file non sarà più protetto tramite Document Security.

1. In Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Rimuovi**.

   Se non avete ancora fornito le informazioni di accesso a Document Security, viene visualizzata una finestra di dialogo in cui immettere il nome utente e la password.

>[!NOTE]
Se non riuscite a rimuovere un criterio da un file che avete protetto, contattate un amministratore di Document Security.

### Visualizzazione delle impostazioni di protezione {#viewing-security-settings}

È possibile visualizzare le autorizzazioni di cui si dispone per il file corrente per la stampa, la copia, la modifica e l&#39;accesso offline, insieme al periodo di validità del file.

In Document Security Extension for Microsoft Office 2010, le autorizzazioni per il file vengono visualizzate nel gruppo Stato protezione della scheda Document Security.

Effettua le seguenti operazioni:

* In Document Security Extension for Microsoft Office 2010 e 2013, nella **scheda Document Security**, nel gruppo **Stato protezione**, fate clic su un elemento qualsiasi.

### Salvataggio di documenti quando viene abilitata l&#39;applicazione automatica del criterio {#saving-documents-when-auto-apply-policy-is-enabled}

Se l&#39;amministratore ha attivato la funzionalità di applicazione automatica del criterio, tutti i documenti creati o modificati verranno protetti automaticamente al momento del salvataggio del documento.

Se questa funzione è abilitata, Document Security Extension for Microsoft Office vi richiede di accedere al server di Document Security. Per essere autenticati dal server, dovete fornire il vostro nome utente e la vostra password. Se avete fornito le credenziali di accesso corrette, il documento verrà salvato e protetto.

>[!NOTE]
Se non riuscite ad accedere a Document Security, il documento potrebbe non essere salvato. Ciò dipende dalla configurazione del criterio di applicazione automatica da parte dell&#39;amministratore. Consultate l’amministratore per informazioni su come vengono gestiti i documenti in questa situazione.

### Sincronizzazione per l&#39;accesso offline {#synchronizing-for-offline-access}

I criteri possono consentirvi di aprire i file mentre siete offline e non connessi a Document Security. Prima di poter lavorare offline, dovete avere eseguito l&#39;accesso a Document Security per stabilire le credenziali con il server. Se intendete lavorare con i file offline, prima di disconnettervi vi vi consigliamo di effettuare la sincronizzazione con Document Security per essere certi che le impostazioni dei criteri per i file siano aggiornate con il server. Si consiglia inoltre di aprire il file online una volta prima di aprirlo offline. Se non aprite il file una volta in linea o non effettuate la sincronizzazione con il server, potete comunque utilizzare i file protetti tramite criterio mentre siete offline. Tuttavia, il periodo di tempo consentito per l&#39;utilizzo non in linea non deve essere scaduto e le impostazioni del criterio per il file non devono essere state modificate dall&#39;ultima volta che avete eseguito la sincronizzazione con il server manualmente o automaticamente.

Effettua le seguenti operazioni:

* In Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Sincronizza non in linea**.

   ***nota**: Il pulsante Sincronizza non in linea è disponibile anche se l&#39;utente non dispone dell&#39;autorizzazione per la sincronizzazione offline del documento. Tuttavia, se si seleziona il pulsante non viene eseguita alcuna operazione. *

### Utilizzo delle filigrane dinamiche {#working-with-dynamic-watermarks}

Document Security Extension for Microsoft Office supporta l&#39;inclusione di filigrane dinamiche basate su testo nei documenti protetti tramite criterio. Una filigrana dinamica può includere informazioni che possono essere modificate, ad esempio data, ora, nome utente o nome del criterio. Se un utente stampa un file protetto tramite criterio e tale file contiene una filigrana dinamica e l&#39;autorizzazione a stampare, la filigrana viene visualizzata nell&#39;output.

Document Security Extension non supporta funzioni rich watermark quali filigrane basate su PDF, filigrane con più elementi, opzioni di formattazione del testo e intervallo di pagine.

Potete creare una filigrana dinamica utilizzando le pagine Web di Document Security. Per ulteriori informazioni sulla creazione e l&#39;inclusione di filigrane dinamiche in un documento protetto tramite criterio, vedere [Guida per l&#39;utente finale di Document Security](http://www.adobe.com/go/learn_lc_euRightsMgmt_11).

Document Security Extension for Microsoft Office supporta le seguenti funzionalità delle filigrane:

<table>
 <thead>
  <tr>
   <th><p>Opzioni filigrana di Document Security</p></th>
   <th><p>Supporto per Word, Excel e PowerPoint</p></th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td><p>Nome criterio</p></td>
   <td><p>Supportato.</p></td>
  </tr>
  <tr>
   <td><p>Nome filigrana</p></td>
   <td><p>Supportato.</p></td>
  </tr>
  <tr>
   <td><p>Usa come sfondo</p></td>
   <td><p>Il comportamento di visualizzazione di una filigrana dinamica è lo stesso, indipendentemente dal fatto che sia stato selezionato Usa come sfondo.</p><p>Per Word 2010 e 2013 la filigrana dinamica viene visualizzata solo nelle visualizzazioni Layout di stampa e Anteprima di stampa. </p><p>In Excel 2010 e 2013 appaiono anche nelle visualizzazioni Anteprima di stampa e Layout di pagina.</p></td>
  </tr>
  <tr>
   <td><p>Posizione verticale</p></td>
   <td><p>Supportato</p></td>
  </tr>
  <tr>
   <td><p>Posizione orizzontale</p></td>
   <td><p>Supportato</p><p>In Excel 2010 e 2013 il posizionamento orizzontale delle filigrane tramite l'utilizzo di punti non è supportato.</p></td>
  </tr>
  <tr>
   <td><p>Scala</p></td>
   <td><p>Supportato</p></td>
  </tr>
  <tr>
   <td><p>Posizione</p></td>
   <td><p>Supportato</p></td>
  </tr>
  <tr>
   <td><p>Opacità</p></td>
   <td><p>Supportato</p></td>
  </tr>
 </tbody>
</table>

### Apertura delle pagine Web di Document Security {#opening-the-document-security-web-pages}

Potete aprire le pagine Web di Document Security per creare e aggiornare i criteri utente e per visualizzare lo stato e le informazioni sul controllo dei file protetti tramite criterio. Potete inoltre utilizzare le pagine Web di Document Security per cambiare criteri o revocare l&#39;accesso a un file protetto tramite criterio.

Per aprire le pagine Web di Document Security, in Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Crea e gestisci criteri**. Se non avete ancora fornito le informazioni di accesso, il browser apre la pagina di accesso al server.

### Modifica dei criteri {#changing-policies}

Se disponete delle autorizzazioni, in genere come amministratore di Document Security o autore del file, potete applicare in un secondo momento un altro criterio a un file o modificare le impostazioni del criterio attualmente applicato.

Per modificare le impostazioni di un criterio, utilizzate le pagine Web di Document Security.

1. Effettua le seguenti operazioni:

   * In Document Security Extension for Microsoft Office 2010 o 2013, nella scheda **Document Security**, selezionate **Proteggi > Modifica protezione**.

1. Selezionate un criterio dall&#39;elenco e fate clic su **Applica**.

### Revoca dei privilegi di accesso ai file {#revoking-file-access-privileges}

Potete revocare la possibilità di aprire i file protetti. Quando revocate i privilegi di accesso a un file, potete anche specificare il messaggio che viene visualizzato a chiunque tenti di aprire il file e l’URL di una versione aggiornata del file, se lo sostituite con una copia rivista.

1. Effettua le seguenti operazioni:

   * In Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Revoca**.

   Viene aperta la pagina Web Revoca documenti di Document Security.

1. Specificate un messaggio da visualizzare e, se disponibile, un URL per la versione aggiornata, quindi fate clic su **OK**.

Per ulteriori informazioni sulla revoca dei privilegi di accesso ai file, vedere [Guida dell&#39;utente finale di Document Security](http://help.adobe.com/en_US/AEMForms/6.1/RMHelp/).

I privilegi di accesso possono essere ripristinati tramite le pagine Web di Document Security.

### Visualizzazione della cronologia del controllo file {#viewing-the-file-audit-history}

Document Security consente di salvare la cronologia del controllo dei file protetti tramite criterio per controllare le azioni eseguite dagli utenti sui file.

Gli eventi controllati per i file Word, Excel e PowerPoint includono:

**Proteggere un nuovo** DocumentPolicy applicato a un file

**Visualizza** file documento aperto

**Chiudi file** documento chiuso

**Revoca privilegi** DocumentAccess rimossi per il file

**Annullamento della revoca dei privilegi** DocumentAccess restituiti al file

**Modifica file** documento modificato e salvato localmente

**Stampa file ad alta** risoluzione

**Modifica protezione** HandlerPolicy rimossa dal file

**Cambiare il criterio in** DocumentNuovo criterio applicato al file dalle pagine Web di Document Security

### Visualizzare la cronologia del controllo di un file {#view-the-audit-history-for-a-file}

In Document Security Extension for Microsoft Office 2010 e 2013, nella scheda **Document Security**, selezionate **Cronologia controllo**.

Viene aperta la pagina Web Eventi di Document Security in cui sono visualizzati gli eventi sottoposti a controllo per il file corrente.

### Funzioni limitate di Microsoft Office {#microsoft-office-restricted-features}

Per proteggere la proprietà intellettuale, alcune funzioni di Microsoft Office non sono disponibili quando si apre un file protetto tramite criterio. L&#39;elenco delle funzioni non disponibili dipende dalle autorizzazioni concesse all&#39;utente corrente. Alcune funzioni non sono disponibili solo per un file protetto e altre non sono disponibili per tutti i file durante una sessione protetta. In genere, la sessione protetta inizia dal momento in cui aprite un file protetto tramite criterio fino alla chiusura dell&#39;applicazione o alla scadenza della sessione.

La maggior parte dei criteri concedono autorizzazioni complete all&#39;autore del file. Altri utenti potrebbero rilevare ulteriori limitazioni delle funzioni.

Se un comando non è disponibile, il nome del comando nel menu e il pulsante della barra degli strumenti correlati sono disabilitati.

>[!NOTE]
L&#39;applicazione di un criterio a un file contenente un collegamento a un file incorporato non applica il criterio al file collegato. Document Security for Microsoft Office non estende la protezione ai file collegati.

* I file Word, Excel e PowerPoint protetti tramite criterio non possono essere aperti in una finestra del browser Internet Explorer.
* Gli utenti ai quali è stata concessa solo l&#39;autorizzazione Modifica non possono copiare il contenuto in un file da un&#39;altra applicazione utilizzando Appunti di Windows. Gli utenti possono copiare il contenuto nei file abilitando l&#39;opzione Appunti di Microsoft Office.
* Se si apre un file protetto tramite criterio in Microsoft Office, il tasto Stampa schermo non è disponibile fino a quando l&#39;applicazione non viene chiusa o scade la sessione.
* Document Security for Microsoft Office non supporta Web-based Distributed Authoring and Versioning (WebDAV). Nella maggior parte dei casi, non è possibile aprire un file protetto tramite criterio da una cartella WebDAV. Se potete aprire un file protetto tramite criterio, non disponete delle autorizzazioni necessarie per salvare, stampare, modificare o copiare il file dal file.

La protezione generale applicata ai file protetti tramite criterio include le seguenti limitazioni:

Molte funzioni comuni potrebbero essere limitate in Word, Excel e PowerPoint durante una sessione protetta.

Se viene aperto un file protetto tramite criterio che non consente all&#39;utente di apportare modifiche, i comandi che modificano il file in qualsiasi modo non sono disponibili. Sono disponibili solo i comandi che aprono o creano nuovi documenti e modificano le preferenze dell’applicazione.

#### Limitazioni per Word 2010 e Word 2013 {#word-2010-and-word-2013-restrictions}

L&#39;apertura di un file protetto tramite criterio in Word rende il salvataggio delle informazioni di recupero automatico dei file non disponibile fino a quando non si chiude e si riavvia Word. Inoltre, le funzioni elencate di seguito sono limitate nelle situazioni descritte:

**File > Nuovo > Nuovo da** esistenteDisponibile, ma non è possibile salvare i file creati con questo comando mentre è aperto un file protetto tramite criterio. Il contenuto del nuovo file non può essere copiato in un altro file.

**File >** SaveRestricted dall&#39;autorizzazione Modifica.

**Opzioni File > Salva** con nomeTutte limitate dall&#39;autorizzazione Modifica.

**Opzioni File >** StampaTutte limitate dall&#39;autorizzazione Stampa. Disponibile solo se il criterio consente la stampa ad alta risoluzione.

**Opzioni File > Salva e** InviaTutte non disponibili durante una sessione protetta.

**File > Informazioni > Documento Protect > Crittografa con password, Aggiungi firma digitale, Segna come finale, Limita le autorizzazioni per** gli utenti non disponibili durante una sessione protetta.

**File >** Flussi di lavoroNon disponibile durante una sessione protetta.

***nota **: La possibilità di avviare un flusso di lavoro dalle versioni di Word, Excel e PowerPoint del sistema Microsoft Office 2010 è disponibile solo nelle suite Office Professional Plus 2010, Office Enterprise 2010 e Office Ultimate 2010, nonché nelle versioni standalone di tali programmi per Office 2010.*

**Post di blog >** PublishUnavailable durante una sessione protetta.

**File > Server >** Menu attività file serverNon disponibile durante una sessione protetta.

**Home > Appunti >** CopiaLimitata dall&#39;autorizzazione Copia. Se la copia non è consentita, il contenuto copiato non può essere incollato in nessun altro file o negli Appunti di Office. Il contenuto può essere copiato all&#39;interno del file protetto se l&#39;utente dispone dell&#39;autorizzazione di modifica.

**Home > Appunti >** IncollaLimitato dall&#39;autorizzazione Modifica.

**Home > Appunti > Incolla** specialeLimitato dall&#39;autorizzazione Modifica.

**Inserisci > Testo >** OggettoNon disponibile durante una sessione protetta. I file protetti tramite criterio non possono essere inseriti in alcun momento.

**** MessaggiLa maggior parte delle opzioni presenti in questa scheda non sono disponibili durante una sessione protetta.

**Rivedi > Strumenti di correzione >** RicercheLimitate dall&#39;autorizzazione Copia. Non disponibile se la copia non è consentita.

**Rivedi > Strumenti di correzione >** ThesaurusRestricted dall&#39;autorizzazione Copia. Non disponibile se la copia non è consentita.

**Rivedi > Lingua > Traduci > Traduci** documento abilitato con l&#39;autorizzazione Copia.

**Rivedi > Lingua > Traduci > Traduci** testo selezionato abilitato con l&#39;autorizzazione Copia.

**Rivedi > Lingua > Traduci > Mini** TranslatorEnabled con l&#39;autorizzazione Copia.

**Rivedi > Confronta >** ConfrontaNon disponibile durante una sessione protetta. Non è mai possibile confrontare i file protetti tramite criterio.

**Rivedi > Protect > Blocca** autoriNon disponibile durante una sessione protetta.

**Rivedi > Protect > Limita** modificaNon disponibile durante una sessione protetta.

**Visualizza >** MacroAlcune macro sono limitate dall&#39;autorizzazione Copia e non sono disponibili a meno che non sia consentita la copia.

**Impossibile aggiungere o** rimuovere componenti aggiuntivi durante una sessione protetta.

**Online** CollaborationNon disponibile durante una sessione protetta.

**Documenti master e** secondariI documenti secondari sono gestiti dal criterio dei documenti master quando vengono aperti all&#39;interno del documento master. Se aperti separatamente, i documenti secondari non possono essere stampati, copiati o modificati.

**** ResummaryNon disponibile durante una sessione protetta.

**Frame (e tutti i comandi correlati)** Non disponibili durante una sessione protetta.

**Document** PanelNon disponibile durante una sessione protetta.

**Sviluppatore >** Modello del documentoNon disponibile durante una sessione protetta. Per accedere a questo comando, selezionare File > Opzioni > Personalizza > scheda Sviluppatore > Modelli > Modello del documento.

**Struttura > Documento master > Crea documento secondario, Inserisci documento** secondarioNon disponibile durante una sessione protetta.

#### Limitazioni per Excel 2010 ed Excel 2013 {#excel-2010-and-excel-2013-restrictions}

Le funzioni elencate di seguito sono limitate nelle situazioni descritte:

**File > Nuovo > Nuovo da** esistenteDisponibile, ma non è possibile salvare i file creati con questo comando durante una sessione protetta. Il contenuto del nuovo file non può essere copiato in un altro file.

**File > Salva, Salva con** nome con autorizzazione Modifica.

**File > Salva con nome >** PDFU disponibile durante una sessione protetta.

**File >** StampaLimitato dall&#39;autorizzazione Stampa. Disponibile solo se il criterio consente la stampa ad alta risoluzione.

**File > Informazioni > Protect** DocumentUnavailable durante una sessione protetta.

**File > Informazioni > Protect** WorkbookNon disponibile durante una sessione protetta.

**File > Salva e** inviaNon disponibile durante una sessione protetta.

**File > Opzioni >** Componenti aggiuntiviImpossibile aggiungere o rimuovere durante una sessione protetta.

**File >** Flussi di lavoroNon disponibile durante una sessione protetta.

***nota **: La possibilità di avviare un flusso di lavoro dalle versioni di Word, Excel e PowerPoint del sistema Microsoft Office 2010 è disponibile solo nelle suite Office Professional Plus 2010, Office Enterprise 2010 e Office Ultimate 2010, nonché nelle versioni standalone di tali programmi per Office 2010.*

**File > Server >** Menu attività file serverNon disponibile durante una sessione protetta.

**Home > Appunti >** CopiaLimitata dall&#39;autorizzazione Copia. Se la copia non è consentita, il contenuto copiato non può essere incollato in nessun altro file o negli Appunti di Microsoft Office. Il contenuto può essere copiato all&#39;interno del file protetto se l&#39;utente dispone dell&#39;autorizzazione di modifica.

**Home > Appunti >** IncollaLimitato dall&#39;autorizzazione Modifica.

**Home > Appunti > Incolla** specialeLimitato dall&#39;autorizzazione Modifica.

**Home > Celle > Formato > Sposta o Copia** foglioNon disponibile durante una sessione protetta.

**Home > Celle > Inserisci > Inserisci** foglioNon disponibile durante una sessione protetta.

**Home > Celle > Elimina > Elimina** foglioNon disponibile durante una sessione protetta.

**Home > Modifica > Riempimento > Tra** fogli di lavoroLimitati dall&#39;autorizzazione Modifica.

**Inserisci > Tabelle >** TabellaLimitata dall&#39;autorizzazione Modifica.

**Impossibile selezionare nella Creazione guidata i file protetti da** PivotTablePolicy > Tabelle >.

**Inserisci > Testo >** OggettoNon disponibile durante una sessione protetta. I file protetti tramite criterio non possono essere inseriti in alcun momento.

**Inserisci > Testo > Intestazione e** piè di paginaLimitato dall&#39;autorizzazione Modifica. Non disponibile per un documento protetto tramite criterio.

**Non è possibile importare dati > Recupera** dati esterni da file protetti tramite criterio.

**Dati > Struttura >** SubtotaliLimitati dall&#39;autorizzazione Modifica.

**Dati > Strumenti dati >** Convalida datiLimitata dall&#39;autorizzazione Modifica.

**Rivedi > Strumenti di correzione >** RicercheLimitate dall&#39;autorizzazione Copia.

**Rivedi > Strumenti di correzione >** ThesaurusRestricted dall&#39;autorizzazione Copia.

**Rivedi > Lingua >** TraduciLimitato dall&#39;autorizzazione Copia.

**Rivedi > Modifiche > Protect** SheetNon disponibile durante una sessione protetta.

**Rivedi > Modifiche > Protect** WorkbookNon disponibile durante una sessione protetta.

**Rivedi > Modifiche > Condivisione** cartella di lavoroNon disponibile durante una sessione protetta.

**Rivedi > Modifiche > Protect e Condivisione** cartella di lavoroNon disponibile durante una sessione protetta.

**Rivedi > Modifiche > Consenti agli utenti di modificare** gli intervalliNon disponibile durante una sessione protetta.

**Rivedi > Modifiche > Rileva modifiche > Evidenzia** modificheNon disponibile per un file protetto tramite criterio contenente una filigrana dinamica.

**Visualizza >** MacrosLimitato dall&#39;autorizzazione Modifica.

**Visualizza > Salva** WorkspaceCommand non funziona.

**Sviluppatore > XML >** Pacchetti di espansioneAlcune macro sono limitate dall&#39;autorizzazione Copia e non sono disponibili a meno che non sia consentita la copia.

**Formule > Verifica formule >** Controllo erroriLimitato dall&#39;autorizzazione Modifica. Disponibile solo se è consentita la modifica.

**Online** CollaborationNon disponibile durante una sessione protetta.

**Salvataggio automatico** InfoNon disponibile durante una sessione protetta.

***Nota **: Se si tenta di modificare una cella in un file protetto tramite criterio per il quale non si dispone delle autorizzazioni necessarie per apportare modifiche, Excel visualizza un messaggio di avviso non corretto che indica che è necessario rimuovere la protezione dal file utilizzando il comando Rimuovi protezione foglio. L&#39;utilizzo del comando Rimuovi protezione foglio non rimuove la protezione tramite criterio dal file.*

#### Limitazioni per PowerPoint 2010 e PowerPoint 2013 {#powerpoint-2010-and-powerpoint-2013-restrictions}

Le funzioni elencate di seguito sono limitate nelle situazioni descritte:

**File > Nuovo > Nuovo da** esistenteDisponibile, ma non è possibile salvare i file creati con questo comando durante una sessione protetta. Il contenuto del nuovo file non può essere copiato in un altro file.

**File >** SaveRestricted dall&#39;autorizzazione Modifica.

**Opzioni File > Salva** con nomeTutte limitate dall&#39;autorizzazione Modifica.

**Opzioni File >** StampaTutte limitate dall&#39;autorizzazione Stampa. Disponibile solo se il criterio consente la stampa ad alta risoluzione.

**File > Salva e** inviaNon disponibile durante una sessione protetta.

**File > Informazioni > Presentazione Protect > Crittografa con password, Aggiungi firma digitale, Segna come finale, Limita le autorizzazioni per** gli utenti non disponibili durante una sessione protetta.

**File > Opzioni di PowerPoint > Salva** informazioni di salvataggio automatico non disponibili durante una sessione protetta.

**File > Server >** Menu attività file serverNon disponibile durante una sessione protetta.

**Home > Appunti >** CopiaLimitata dall&#39;autorizzazione Copia. Se la copia non è consentita, il contenuto copiato non può essere incollato nel documento, in nessun altro file o negli Appunti di Office. Il contenuto può essere copiato all&#39;interno del file protetto se l&#39;utente dispone dell&#39;autorizzazione di modifica.

**Home > Appunti >** IncollaLimitato dall&#39;autorizzazione Modifica. Se la copia non è consentita, il contenuto copiato non può essere incollato nel documento.

**Home > Appunti > Incolla** specialeLimitato dall&#39;autorizzazione Modifica.

**Home > Diapositive > Nuove diapositive > Diapositive dalla struttura, Riutilizza** diapositiveNon disponibile durante una sessione protetta.

**Inserisci > Testo >** OggettoNon disponibile durante una sessione protetta. I file protetti tramite criterio non possono essere inseriti in alcun momento.

**Progettazione > Sfondo > Stili di sfondo, Nascondi grafica di sfondo, Formato** sfondoNon disponibile per un file protetto tramite criterio contenente una filigrana dinamica.

**Presentazione > Impostazione > Registra** presentazioneLimitata dall&#39;autorizzazione di modifica.

**Rivedi > Strumenti di correzione >** ThesaurusRestricted dall&#39;autorizzazione Copia.

**Rivedi > Lingua >** TraduciLimitato dall&#39;autorizzazione Copia.

**Rivedi > Lingua > Traduci > Mini** TranslatorEnabled con l&#39;autorizzazione Copia.

**Visualizza > Visualizzazioni presentazione >** Presentazione limitata dall&#39;autorizzazione Modifica. Se le modifiche non sono consentite, non è possibile visualizzare le presentazioni se il file è stato modificato.

**Visualizza >** MacroAlcune macro sono limitate dall&#39;autorizzazione Copia e non sono disponibili a meno che non sia consentita la copia.

**Impossibile aggiungere o** rimuovere componenti aggiuntivi durante una sessione protetta.

**Online** CollaborationNon disponibile durante una sessione protetta.

## Utilizzare provider di autenticazione di terze parti {#use-third-party-authentication-providers}

Potete utilizzare provider di autenticazione di terze parti con  AEM Forms Document Security. Questi provider di autenticazione consentono di aggiungere un ulteriore livello di accesso ai documenti protetti.  AEM Forms Document Security supporta i seguenti flussi di lavoro di autenticazione estesa:

* Autenticazione estesa tramite URL AEM Forms  predefinito
* Autenticazione estesa mediante un URL personalizzato
* Flusso di lavoro di autenticazione estesa predefinito con provider di identità di terze parti configurati su  AEM Forms sul server JEE
* Flusso di lavoro di autenticazione estesa personalizzato con provider di identità di terze parti configurati su  AEM Forms sul server JEE
* Autenticazione estesa mediante pagina personalizzata per l&#39;elenco delle autenticazioni SAML

Per i passaggi dettagliati per configurare i flussi di lavoro di autenticazione estesa, consultate l&#39;articolo [Scenari di autenticazione estesa](http://blogs.adobe.com/livecycle/2011/12/extended-authentication-scenarios.html)

## Glossario {#glossary}

Per informazioni sui moduli di LiveCycle e AEM relativi alla terminologia JEE, vedere [Glossario](http://www.adobe.com/go/learn_aemforms_designer_65).
