---
title: Installazione e configurazione di AEM Document Security Extension for Microsoft Office
description: Questo documento illustra come installare e configurare Adobe Experience Manager Document Security Extension 6.2 for Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
exl-id: 88759737-d57f-4354-951e-ad9f62d0a872
source-git-commit: 13c487b13acb0d65f02301c881bfade512428bcd
workflow-type: ht
source-wordcount: '2764'
ht-degree: 100%

---

# Installazione e configurazione di AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Questo documento illustra come installare e configurare Adobe Experience Manager Document Security Extension for Microsoft Office.

Questo documento contiene informazioni sulle seguenti attività:

* Installazione di Document Security Extension for Microsoft Office
* Preconfigurazione del programma di installazione per selezionare LiveCycle Rights Management ES2 o versione successiva o il componente aggiuntivo Document Security per AEM 6.0 Forms o versione successiva.
* Configurazione dell’applicazione automatica della policy predefinita

## Prima dell’installazione {#before-you-install}

Prima di installare Document Security Extension for Microsoft Office, assicurati di:

* aver letto le [Note sulla versione](document-security-extension-release-notes.md);
* aver attivato Microsoft Office: la finestra di dialogo di attivazione non viene visualizzata all’apertura delle applicazioni Microsoft Office;
* aver installato i più recenti Service Pack per Microsoft Windows e Microsoft Office;
* aver aperto l’applicazione Office almeno una volta, se stai installando Document Security for Microsoft Office per una lingua non supportata.

>[!NOTE]
>
>Non installare il software in una cartella con un nome contenente caratteri a doppio byte. In caso contrario, in Microsoft Office non viene visualizzato il menu di AEM Document Security.

>[!NOTE]
>
>È supportata l’installazione di una versione a 32 bit dell’estensione Document Security su un sistema operativo a 64 bit, ma non il contrario. In altre parole, non è possibile installare la versione a 64 bit dell’estensione Document Security per Microsoft Office in un sistema operativo a 32 bit.

### Disattivare McAfee VirusScan {#disable-mcafee-virusscan}

Per garantire un avvio ottimale delle applicazioni Office nei computer in cui sono installati Document Security Extension e McAfee VirusScan con scansione all’accesso abilitata, disabilita l’opzione di protezione da overflow del buffer nella console di McAfee VirusScan.

### Disinstallare i plug-in di terze parti {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office non supporta plug-in di terze parti per applicazioni Microsoft Office. L’estensione va in conflitto con i plug-in di terze parti ed è quindi necessario disinstallare eventuali plug-in non Adobe per Microsoft Office prima di installare Document Security for Microsoft Office. Adobe non fornisce il supporto per applicazioni Document Security for Microsoft Office con plug-in di terze parti installati.

## Requisiti di sistema {#system-requirements}

### Client Document Security Extension {#document-security-extension-client}

Verifica di disporre delle seguenti configurazioni minime in cui installare Document Security Extension:

* Versioni a 32 bit o 64 bit di Microsoft Windows 7 o Windows 10 in inglese, francese, tedesco, giapponese, italiano, spagnolo, portoghese brasiliano, coreano, cinese semplificato o cinese tradizionale.
   **Nota:** *l’estensione Document Security for Microsoft Office è stata progettata per essere utilizzata anche sui dispositivi Microsoft Surface.*

* Versioni a 32 bit o 64 bit di Microsoft Office 2013, 2016, 2019 e di applicazioni desktop Microsoft Office installate nell’ambito di Office 365 in inglese, francese, tedesco, giapponese, italiano, spagnolo, portoghese brasiliano, coreano, cinese semplificato o cinese tradizionale.

   **Nota**: *AEM Document Security Extension for Microsoft Office non supporta plug-in di terze parti per applicazioni Microsoft Office. Questa estensione può entrare in conflitto con plug-in di terze parti ed è quindi necessario disinstallare eventuali plug-in non Adobe per applicazioni Microsoft Office prima di installare Document Security Extension for Microsoft Office. Adobe non fornisce il supporto per applicazioni Document Security Extensions for Microsoft Office con plug-in di terze parti installati.*

* Processore da 1,3 GHz o superiore
* 2 GB di RAM
* 100 MB di spazio disponibile su disco rigido

### Document Security {#document-security}

Prima di utilizzare Document Security Extension, accertati di essere in grado di stabilire una connessione con Adobe LiveCycle Rights Management ES2 o versione successiva o con il componente aggiuntivo Document Security per AEM Forms 6.0 o versione successiva.

## Installazione di Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

È possibile scaricare il file di installazione dalla [pagina di download](download-installer.md). Non è possibile personalizzare direttamente il file eseguibile del programma di installazione, ma è possibile installarlo in modo interattivo o in modalità silenziosa. Per installare il software, accedi a Windows come amministratore.

Sono disponibili file di installazione separati per le versioni a 32 bit e 64 bit di Microsoft Office. Per la versione a 32 bit di Microsoft Office, scarica DocumentSecurityExtensionforMicrosoftOffice.exe. Per la versione a 64 bit di Microsoft Office, scarica DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>Per illustrare i comandi e le opzioni disponibili, in questo documento viene utilizzato il file di installazione a 32 bit (DocumentSecurityExtensionforMicrosoftOffice.exe). Se è in uso una versione a 64 bit di Microsoft Office, sarà necessario utilizzare il file di installazione a 64 bit (DocumentSecurityExtensionforMicrosoftOffice64.exe) per eseguire le operazioni elencate in questo documento.

### Eseguire l’installazione in modalità silenziosa {#install-in-silent-mode}

Utilizza un’utility di estrazione file, come WinZip, per estrarre `DocumentSecurityExtensionforMicrosoftOffice.exe` dal file di installazione. Apri il prompt dei comandi, accedi alla cartella contenente il file di installazione e digita il testo seguente:

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

Il file di installazione è disponibile anche come file MSI, che può essere utilizzato per la personalizzazione.

### Installare un file MSI in modalità silenziosa {#install-an-msi-file-in-silent-mode}

1. Utilizza un’utility di estrazione file, come WinZip, per estrarre `DocumentSecurityExtensionforMicrosoftOffice.msi` dal file ZIP.

1. Apri il prompt dei comandi, accedi alla cartella contenente il file MSI e digita il testo seguente:

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Preconfigurazione del programma di installazione per la connessione a Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

È possibile preconfigurare il programma di installazione di Document Security Extension for Microsoft Office in modo da selezionare un server LiveCycle o AEM e consentire agli utenti che installano Document Security Extension for Microsoft Office di utilizzare le funzioni senza dover configurare una connessione. Gli utenti possono quindi aprire documenti protetti anche senza una specifica configurazione, ma non possono proteggere nuovi documenti finché non configurano il client per l’utilizzo di un server specifico.

Nei passaggi seguenti viene descritto come creare e configurare un file MSI. Il file MSI contiene i valori del Registro di sistema necessari per preconfigurare il programma di installazione di Document Security Extension for Microsoft Office sul server LiveCycle o AEM presente in azienda.

### Prerequisiti per personalizzare il programma di installazione {#prerequisites-for-customizing-the-installer}

Puoi personalizzare il programma di installazione utilizzando l’editor di database Orca. Nei passaggi seguenti viene descritto come creare un file MSI personalizzato modificando una copia del file di installazione MSI con l’editor di database Orca. Orca è disponibile come parte di Windows SDK per Windows Server 2008 e .NET Framework 3.5.

<!--

For more information about how to edit Microsoft Windows® Installer files using Orca, see [Microsoft Support](http://support.microsoft.com/kb/255905/EN-US/).

-->

>[!NOTE]
>
>Si consiglia di eseguire un backup completo di tutti i file di installazione prima di creare il file MSI personalizzato.

#### Installare Orca {#install-orca}

1. Scarica Windows SDK per Windows Server 2008 e .NET Framework 3.5.
1. Fai doppio clic sul file Orca.msi nella cartella \Microsoft SDK\bin.

   È necessaria anche la variante MSI del file di installazione. Contatta il supporto Adobe per ricevere la versione più recente del file di installazione MSI.

   >[!NOTE]
   >
   >Chiudi sempre il file DocumentSecurityExtensionforMicrosoftOffice.msi prima di eseguire il file di installazione. Non è infatti possibile eseguire il file di installazione se il file MSI è in uso in Orca.

### Creare e configurare il file MSI {#create-and-configure-the-msi-file}

1. Fai clic su **[!UICONTROL Start > Programmi > Orca]**.

1. Fai clic su **[!UICONTROL File > Apri]**, quindi individua il file `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Seleziona Proprietà dall’elenco di tabelle (a sinistra).

1. Modifica i seguenti valori del Nome chiave in base all’installazione aziendale di Rights Management o Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nome </strong><strong></strong><strong> chiave</strong></p> </td>
   <td><p><strong>Descrizione</strong></p> </td>
   <td><p><strong>Valore </strong><strong></strong><strong>chiave predefinito</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_NAME</code></p> </td>
   <td><p>Nome visualizzato.</p> </td>
   <td><p>Server predefinito</p> </td>
  </tr>
  <tr>
   <td><p><code>APS_SERVER_URL</code></p> </td>
   <td><p>URL server host.</p> </td>
   <td><p>https://default.corp.com:1234</p> </td>
  </tr>
 </tbody>
</table>

1. Seleziona Registro di sistema dall’elenco di tabelle (a sinistra).

1. Modifica il seguente valore del Nome chiave.

   | **Nome chiave** | **Descrizione** | **Valore chiave predefinito** |
   |---|---|---|
   | `IsDefault` | Server APS predefinito. | Server predefinito |

1. Salva il file modificato nella stessa directory contenente il file di installazione MSI originale.

   >[!NOTE]
   >
   >In genere, si utilizza lo stesso nome del file MSI originale (ad esempio, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Configurazione dell’applicazione automatica di una policy predefinita {#configuring-automatic-application-of-a-default-policy}

Nell’ambito del processo di configurazione, è possibile configurare l’applicazione automatica di una policy predefinita in modo che Document Security Extension for Microsoft Office protegga tutti i documenti salvati.

È possibile specificare una delle opzioni seguenti:

* Proteggi tutti i documenti con una policy predefinita.
* Consenti agli utenti di salvare un file in un formato non protetto quando non possono connettersi al server. Questa flessibilità consente di supportare anche gli utenti che devono creare nuovi documenti mentre non sono connessi in rete (ad esempio, quando si trovano su un aereo).

Dopo aver attivato la funzione di applicazione automatica della policy, il documento viene protetto con la policy predefinita nei seguenti casi:

* quando l’utente modifica e salva un documento appena creato;
* quando l’utente modifica e salva un documento non protetto;
* quando l’utente apre un’applicazione che si apre con un documento predefinito, modifica e quindi salva il documento.

### Configurare la funzione di applicazione automatica della policy nel file MSI  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Prima di iniziare, preconfigura il programma di installazione in modo da selezionare il server LiveCycle o AEM Forms, come descritto in precedenza in questo articolo.

1. Fai clic su **[!UICONTROL Start > Programmi > Orca]**.

1. Fai clic su **[!UICONTROL File > Apri]**, quindi individua il file `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Seleziona Proprietà dall’elenco di tabelle (a sinistra).

1. Modifica i seguenti valori del Nome chiave in base all’installazione aziendale di Rights Management o Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nome chiave</strong></p> </td>
   <td><p><strong>Descrizione</strong></p> </td>
   <td><p><strong>Valore </strong><strong></strong><strong>chiave predefinito</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Attiva o disattiva la funzione di applicazione automatica della policy.</p> <p><code>1</code>: Attiva</p> <p>0: Disattiva</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>GUID della policy da utilizzare per il salvataggio di nuovi documenti. Viene applicato alla funzione di applicazione automatica della policy.</p> </td>
   <td><p>ID policy esadecimale come risulta visibile sul server RM</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>URL del server.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Numero della porta del server.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Determina se è possibile creare documenti senza la protezione di Document Security nel caso in cui il client non sia in grado di contattare il server per proteggere il documento al primo salvataggio.</p> <p>1: Consenti salvataggi non protetti </p> <p>0: Impedisci la creazione di nuovi documenti quando il client non è in grado di contattare il server per salvare il documento.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>L’opzione `AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` è utile quando si desidera ricordare ai clienti di proteggere tutti i documenti senza obbligarli a farlo. È utile anche quando si è certi che gli utenti hanno l’esigenza di creare nuovi documenti mentre sono disconnessi dalla rete e non si vuole impedire loro di creare e salvare i documenti.

1. Salva il file modificato nella stessa directory contenente il file MSI originale.

   >[!NOTE]
   >
   >In genere, si utilizza lo stesso nome del file MSI originale (ad esempio, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Abilitazione della protezione automatica di nuovi documenti {#enabling-automatic-protection-of-new-documents}

L’amministratore può abilitare la funzione di protezione automatica dei documenti salvati da un utente. In questo caso, l’amministratore configura la funzione di applicazione automatica della policy nel programma di installazione di Document Security Extension for Microsoft Office.

Se è abilitata questa funzione, tutti i documenti salvati dall’utente vengono protetti con la policy predefinita. Questa azione viene eseguita nelle situazioni seguenti:

* Quando un utente crea un nuovo documento, lo modifica e lo salva.
* Quando un utente apre un documento non protetto, lo modifica e lo salva.

Per informazioni sulla configurazione della funzione di applicazione automatica della policy, consulta [Configurazione dell’applicazione automatica della policy predefinita](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Abilitare l’interfaccia utente senza barra multifunzione {#enable-ribbon-less-user-interface}

È possibile abilitare o disabilitare l’interfaccia utente senza barra multifunzione modificando le impostazioni nel Registro di sistema di Windows. Per aggiornare il Registro di sistema e abilitare l’interfaccia utente senza barra multifunzione, effettua le seguenti operazioni:

1. Crea una copia di backup del Registro di sistema di Windows prima di modificarlo. Per istruzioni dettagliate, consulta [Come modificare il Registro di sistema di Windows](https://support.microsoft.com/it-it/kb/136393).
1. Nell’editor del Registro di sistema, passa a HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 oppure HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Crea un nuovo valore Dword (32 bit) denominato **HidePluginUI**.

1. Imposta il valore della proprietà **HidePluginUI** su 1 per abilitare l’interfaccia utente senza barra multifunzione.

1. Chiudi l’editor del Registro di sistema.

## Abilitare la filigrana per la stampa in Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

È possibile modificare le impostazioni del Registro di sistema di Windows in modo da far coesistere la filigrana dinamica con le intestazioni e i piè di pagina esistenti. Le impostazioni del Registro di sistema rendono disponibile la filigrana solo durante la stampa. Per aggiornare il Registro di sistema e abilitare le filigrane durante la stampa, effettua le seguenti operazioni:

1. Crea una copia di backup del Registro di sistema di Windows prima di modificarlo. Per istruzioni dettagliate, consulta [Come modificare il Registro di sistema di Windows](https://support.microsoft.com/it-it/kb/136393).
1. Nell’editor del Registro di sistema, passa a HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 oppure HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Crea una nuova chiave del Registro di sistema **WatermarkMode**.
1. Nella chiave del Registro di sistema WatermarkMode, crea un valore DWORD **WatermarkMode** e imposta il valore DWORD **WatermarkMode** su **1**.

1. Chiudi l’editor del Registro di sistema.

>[!NOTE]
>
>In Esplora risorse puoi utilizzare il menu File o il menu di scelta rapida per creare un documento Microsoft Excel. Per i documenti creati con metodi dichiarati, non è possibile recuperare o modificare la data di stampa. Si tratta di una limitazione di Microsoft Excel. Le filigrane di AEM Document Security si basano sulla data di stampa del documento. Per questi documenti, quindi, la filigrana viene ripristinata a una data precedente e le intestazioni e i piè di pagina non vengono conservati.

## Aggiungere una pagina di copertina personalizzata a un documento {#coverpage}

È possibile che un utente tenti di aprire il documento protetto su un computer in cui non è installato il plug-in di AEM Document Security for Microsoft Office. Questi computer non possono aprire il documento ma possono mostrare una pagina di copertina contenente le istruzioni per scaricare il plug-in di AEM Document Security for Microsoft Office e altre informazioni.

### Prima di configurare una pagina di copertina {#before-you-configure-a-cover-page}

* Crea una copia di backup del file CommonResources.dll. Il percorso predefinito è:

   * **(per Office a 32 bit su computer a 32 bit)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(per Office a 32 bit su computer a 64 bit)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(per Office a 64 bit su computer a 64 bit)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Verifica che sia installato Microsoft Visual Studio 2008 o versione successiva. È possibile utilizzare anche un’altra utility per modificare i file DLL.
* Estrai l’archivio templates.zip, contenente i modelli .xlsx, .docx e .pptx per la pagina di copertina. Utilizza solo i modelli forniti per i tipi di file .xlsx, .docx e .pptx. Per gli altri tipi di file, invece, puoi utilizzare anche altri modelli, contenenti istruzioni e messaggi personalizzati. Puoi trovare l’archivio template.zip in:

[Ottieni file](assets/templates.zip)

### Struttura del file CommonResources.dll {#structure-of-the-commonresources-dll-file}

Il file CommonResources.dll contiene informazioni sui modelli di risorse. Include due identificatori di nome: TEMPLATE_FILE e RT_MANIFEST. Per abilitare una pagina di copertina personalizzata, deve essere modificato l’identificatore di nome TEMPLATE_FILE. L’identificatore di nome TEMPLATE_FILE ha sei risorse:

<table>
 <tbody>
  <tr>
   <td><p><strong>Risorsa</strong></p> </td>
   <td><p><strong>Rappresenta </strong></p> </td>
  </tr>
  <tr>
   <td><p>101 </p> </td>
   <td><p>.xls</p> </td>
  </tr>
  <tr>
   <td><p>102</p> </td>
   <td><p>.doc</p> </td>
  </tr>
  <tr>
   <td><p>103 </p> </td>
   <td><p>.ppt</p> </td>
  </tr>
  <tr>
   <td><p>104 </p> </td>
   <td><p>.xlsx</p> </td>
  </tr>
  <tr>
   <td><p>105</p> </td>
   <td><p>.docx</p> </td>
  </tr>
  <tr>
   <td><p>106</p> </td>
   <td><p>.pptx</p> </td>
  </tr>
 </tbody>
</table>

#### Configurare il modello come pagina di copertina {#configure-the-template-as-a-cover-page}

1. Apri Microsoft Visual Studio. Sfoglia e apri il file CommonResources.dll per la modifica.

   >[!NOTE]
   >
   >Se il file non viene visualizzato nella finestra Esplora soluzioni, riaprilo mediante l’opzione Apri con. Seleziona Editor risorse come editor.

1. Nella finestra Esplora soluzioni, espandi la directory TEMPLATE_FILE ed elimina le risorse 101.

1. Aggiungi le risorse:

   1. Con un progetto selezionato in Esplora soluzioni, scegli Proprietà dal menu Progetto.
   1. Seleziona la scheda Risorse.
   1. Nella barra degli strumenti di Progettazione risorse, cerca Aggiungi risorsa e fai clic sulla freccia. Per il tipo di risorsa, seleziona TEMPLATE_FILE e fai clic su Importa.
   1. Nella finestra di dialogo Aggiungi il file esistente alle risorse, individua il file Resource.xlsx e fai clic su Apri. Il file viene aggiunto alla directory TEMPLATE_FILE.

   >[!NOTE]
   >
   >Verifica che le impostazioni della lingua siano corrette. Elimina la risorsa con lingua neutra.

1. Ripeti i passaggi 2 e 3 per tutti i tipi di risorse.

   >[!NOTE]
   >
   >Non eliminare o aggiungere tipi di risorse in ordine casuale. Dopo 101, configura 102 e così via.

### Creare un pacchetto personalizzato del file CommonResources.dll con il programma di installazione di AEM Document Security Extension for Microsoft Office  {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

Il file CommonResources.dll può essere personalizzato con una pagina di copertina personalizzata. Dopo aver personalizzato il file, puoi sostituire manualmente il file originale con il file personalizzato su tutte le workstation, oppure puoi ricorrere a un metodo automatizzato.

In un ambiente di grandi dimensioni, infatti, può risultare difficile e laborioso sostituire manualmente il file `CommonResources.dll file` predefinito con un file `CommonResources.dll` personalizzato. È possibile quindi utilizzare uno strumento di estrazione automatica e creazione pacchetti (ad esempio, WinZip Self-Extractor) per creare un pacchetto del file CommonResources.dll personalizzato con il programma di installazione di AEM Document Security Extension for Microsoft Office. In futuro, sarà quindi possibile distribuire il programma di installazione personalizzato su tutte le workstation. Questo metodo riduce il tempo necessario per sostituire il file `CommonResources.dll` predefinito con un file personalizzato. Inoltre garantisce che in tutte le workstation sia presente il file CommonResources.dll necessario. L’utilizzo di uno strumento di estrazione automatica e creazione pacchetti è solo uno dei numerosi metodi possibili per sostituire automaticamente un file. Ciascuno può scegliere il metodo più adatto al proprio ambiente.

Per creare un pacchetto del file `CommonResources.dll` personalizzato con il programma di installazione di AEM Document Security Extension for Microsoft Office, è possibile effettuare le seguenti operazioni:

1. Installa uno strumento di estrazione automatica e creazione pacchetti, ad esempio WinZip Self-Extractor.
1. Crea una nuova cartella, ad esempio YOUR_FOLDER_NAME
1. Inserisci il programma di installazione originale di AEM Document Security Extension e il file CommonResources.dll personalizzato nella cartella appena creata.
1. Crea un file batch nella cartella, ad esempio YOUR_FOLDER_NAME\Installer.bat
1. Apri il file batch per la modifica e aggiungi al file il codice seguente:

   ```shell
    @echo off
   
    setlocal EnableDelayedExpansion
   
    msiexec /i YOUR_FOLDER_NAME\MSI_NAME.exe
   
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\HARDWARE\DESCRIPTION\System\CentralProcessor\0" /v "Identifier"') DO set "IDENTIFIER=%%B"
   
    set IDENTIFIER= %IDENTIFIER: =%
   
    if not %IDENTIFIER:x86=%==%IDENTIFIER% (
   
    REM Fetching install path for 32 bit machine.
   
    FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
    ) else (
   
        REM Fetching install path for 64 bit machine.
   
            FOR /F "tokens=2,*" %%A IN ('REG query "HKLM\SOFTWARE\Wow6432Node\Adobe\LiveCycle Rights Management ES4\11.0.0" /v "InstallPath"') DO set "INSTALLPATH=%%B"
   
        )
   
    COPY "YOUR_FOLDER_NAME\CommonResources.dll" "%INSTALLPATH%"
   
    endlocal
   ```

   Se utilizzi una versione di LiveCycle e di AEM Forms su JEE diversa da LiveCycle Rights Management ES4 e dalla versione 11.0.0, sostituisci il percorso della chiave di registro come segue:

   * (Livecycle Rights Management ES2 e versione 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (Livecycle Rights Management ES3 e versione 10.0)
   * (Livecycle Rights Management ES4 e versione 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms su JEE e versioni successive) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. Nel codice sopra riportato, sostituisci tutte le istanze di YOUR_FOLDER_NAME con il nome della cartella creata al passaggio 2.
1. **(Solo per il file di installazione di AEM Document Security Extension for Microsoft Office con estensione .exe)** Sostituisci la seguente riga di codice:

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
con

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Salva e chiudi il file batch.
1. Con uno strumento di estrazione automatica e creazione pacchetti, crea un pacchetto della cartella contenente il file CommonResources.dll personalizzato, il programma di installazione originale di AEM Document Security Extension for Microsoft Office e il file batch.

   >[!NOTE]
   >
   >Verifica che il pacchetto di estrazione automatica sia impostato per essere eseguito come amministratore ed
   >esegua automaticamente il file batch al termine dell’estrazione.

Il file di installazione autoestraente di AEM Document Security Extension for Microsoft Office è ora incluso in un pacchetto con il file CommonResources.dll personalizzato ed è pronto per la distribuzione.
