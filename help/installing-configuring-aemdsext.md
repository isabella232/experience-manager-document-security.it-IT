---
title: Installazione e configurazione AEM Document Security Extension for Microsoft Office
description: Questo documento illustra come installare e configurare Adobe Experience Manager Document Security Extension 6.2 per Microsoft Office.
uuid: 9d7eb6bb-4780-4d82-8657-7c6c6d523af0
content-type: reference
topic-tags: installing
discoiquuid: f1cdf344-efe4-4cb5-9fc3-47ee4ba5faf4
translation-type: tm+mt
source-git-commit: ac385c538cdd7d3bb4772b92ee7a94b003595f56
workflow-type: tm+mt
source-wordcount: '2796'
ht-degree: 0%

---


# Installazione e configurazione AEM Document Security Extension for Microsoft Office{#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Questo documento illustra come installare e configurare Adobe Experience Manager Document Security Extension for Microsoft Office.

Questo documento contiene informazioni sulle seguenti attività:

* Installazione di Document Security Extension for Microsoft Office
* Preconfigurazione del programma di installazione per indirizzare l&#39;LiveCycle Rights Management ES2 o una versione successiva o il componente aggiuntivo di Document Security per AEM 6.0 Forms o versione successiva.
* Configurazione dell&#39;applicazione automatica del criterio predefinito

## Prima dell’installazione {#before-you-install}

Prima di installare Document Security Extension for Microsoft Office, accertatevi che:

* Sono state lette le [Note sulla versione](document-security-extension-release-notes.md).
* Microsoft Office è attivato. La finestra di dialogo di attivazione non viene visualizzata all&#39;apertura delle applicazioni di Microsoft Office.
* Sono installati gli ultimi Service Pack per Microsoft Windows e Microsoft Office.
* Se state installando Document Security for Microsoft Office per una lingua non supportata, aprite l&#39;applicazione Office almeno una volta.

>[!NOTE]
>
>Non installate il software in una cartella il cui nome contiene caratteri a doppio byte. In questo caso, il menu AEM Document Security non viene visualizzato in Microsoft Office.

>[!NOTE]
>
>L&#39;installazione di una versione a 32 bit dell&#39;estensione Document Security su un sistema operativo a 64 bit è supportata, ma non è supportata la modalità opposta. Non è possibile installare la versione a 64 bit dell&#39;estensione Document Security per Microsoft Office in un sistema operativo a 32 bit.

### Disattiva McAfee VirusScan&amp; {#disable-mcafee-virusscan}

Per fare in modo che le applicazioni Office vengano avviate senza problemi nei computer in cui sono installati Document Security Extension e McAfee VirusScan con l&#39;opzione per la scansione all&#39;accesso abilitata, disabilitate l&#39;opzione relativa alla protezione dell&#39;overflow del buffer nella console di McAfee VirusScan.

### Disinstallazione dei plug-in di terze parti {#uninstall-third-party-plug-ins}

AEM Document Security Extension for Microsoft Office non supporta i plug-in di terze parti per le applicazioni di Microsoft Office. Poiché l&#39;estensione è in conflitto con i plug-in di terze parti, disinstallate i plug-in non  Adobe per Microsoft Office prima di installare Document Security for Microsoft Office.  Adobe non fornisce supporto per le applicazioni di Document Security for Microsoft Office con plug-in di terze parti installati.

## Requisiti di sistema {#system-requirements}

### Client di Document Security Extension {#document-security-extension-client}

Assicuratevi di disporre delle seguenti configurazioni minime in cui installare Document Security Extension:

* Versioni a 32 bit o a 64 bit di Microsoft Windows 7 o Windows 10 in inglese, francese, tedesco, giapponese, italiano, spagnolo, portoghese brasiliano, coreano, cinese semplificato o cinese tradizionale.
   **Nota:** *Document Security extension for Microsoft Office deve funzionare anche sui dispositivi Microsoft Surface.*

* Versioni a 32 bit o a 64 bit di Microsoft Office 2013, 2016, 2019 e Microsoft Office desktop installati come parte di Office 365 in inglese, francese, tedesco, giapponese, italiano, spagnolo, portoghese brasiliano, coreano, cinese semplificato o cinese tradizionale.

   **Nota**:  *AEM Document Security Extension for Microsoft Office non supporta i plug-in di terze parti per le applicazioni di Microsoft Office. Poiché questa estensione può entrare in conflitto con i plug-in di terze parti, tutti i plug-in non  Adobe per le applicazioni di Microsoft Office devono essere disinstallati prima di installare Document Security Extension for Microsoft Office.  Adobe non supporta le applicazioni di Document Security Extensions for Microsoft Office con plug-in di terze parti installati.*

* Processore da 1,3 GHz o superiore
* 2 GB di RAM
* 100 MB di spazio disponibile su disco rigido

### Sicurezza dei documenti {#document-security}

Per utilizzare Document Security Extension, accertatevi di essere in grado di connettersi a  Adobe LiveCycle Rights Management ES2 e versioni successive o al componente aggiuntivo Document Security per moduli AEM 6.0 o versioni successive.

## Installazione di Document Security Extension for Microsoft Office {#installing-document-security-extension-for-microsoft-office}

È possibile scaricare il programma di installazione dalla [pagina di download](download-installer.md). Non potete personalizzare direttamente il file eseguibile del programma di installazione, ma può essere installato in modo interattivo o in modalità silenziosa. Per installare il software, accedete a Windows come amministratore.

Sono disponibili programmi di installazione separati per le versioni a 32 bit e a 64 bit di Microsoft Office. Per la versione a 32 bit di Microsoft Office, scaricate DocumentSecurityExtensionforMicrosoftOffice.exe. Per la versione a 64 bit di Microsoft Office, scaricate DocumentSecurityExtensionforMicrosoftOffice64.exe.

>[!NOTE]
>
>In questo documento viene utilizzato il file del programma di installazione a 32 bit (DocumentSecurityExtensionforMicrosoftOffice.exe) per illustrare i vari comandi e opzioni. Se utilizzate una versione a 64 bit di Microsoft Office, utilizzate il file del programma di installazione a 64 bit (DocumentSecurityExtensionforMicrosoftOffice64.exe) per eseguire le operazioni elencate in questo documento.

### Installazione in modalità silenziosa {#install-in-silent-mode}

Utilizzate un&#39;utilità di estrazione file, come WinZip, per estrarre `DocumentSecurityExtensionforMicrosoftOffice.exe` dal file del programma di installazione. Aprite il prompt dei comandi, accedete alla cartella che contiene il file di installazione e digitate il testo seguente:

`DocumentSecurityExtensionforMicrosoftOffice.exe -s -a -s -v" /qn"`

Il programma di installazione è disponibile anche come file MSI, che può essere utilizzato per la personalizzazione.

### Installare un file MSI in modalità silenziosa {#install-an-msi-file-in-silent-mode}

1. Utilizzate un&#39;utilità di estrazione file, come WinZip, per estrarre il file `DocumentSecurityExtensionforMicrosoftOffice.msi` dal file ZIP.

1. Aprite il prompt dei comandi, accedete alla cartella che contiene il file MSI e digitate il testo seguente:

   `msiexec /I DocumentSecurityExtensionforMicrosoftOffice.msi /qn`

## Preconfigurazione del programma di installazione per la connessione a Document Security {#preconfiguring-the-installer-to-connect-to-document-security}

Potete preconfigurare il programma di installazione di Document Security Extension for Microsoft Office in modo che punti a un server di LiveCycle o AEM in modo che gli utenti che installano Document Security Extension for Microsoft Office possano utilizzare le funzioni senza configurare una connessione. Pertanto, gli utenti possono aprire documenti protetti senza bisogno di alcuna configurazione. Tuttavia, non possono proteggere nuovi documenti finché non configurano il client per l&#39;utilizzo di un server specifico.

Nei passaggi seguenti viene descritto come creare e configurare un file MSI. Questo file MSI contiene i valori del Registro di sistema necessari per preconfigurare il programma di installazione di Document Security Extension for Microsoft Office sul server di LiveCycle o AEM installato nell&#39;azienda.

### Prerequisiti per la personalizzazione del programma di installazione {#prerequisites-for-customizing-the-installer}

Utilizzate l&#39;editor di database Orca per personalizzare il programma di installazione. Nei passaggi seguenti viene descritto come creare un file MSI personalizzato modificando una copia del file di installazione MSI utilizzando l&#39;editor di database Orca. Orca è disponibile come parte di Windows SDK per Windows Server 2008 e .NET Framework 3.5. Per ulteriori informazioni su come modificare i file di Microsoft Windows® Installer utilizzando Orca, vedere [Supporto Microsoft](http://support.microsoft.com/kb/255905/EN-US/).

>[!NOTE]
>
>Si consiglia di eseguire un backup completo di tutti i file del programma di installazione prima di creare il file MSI personalizzato.

#### Installazione di Orca {#install-orca}

1. Scaricate Windows SDK per Windows Server 2008 e .NET Framework 3.5 da [Microsoft Download Center](http://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=11310).
1. Fate doppio clic sul file Orca.msi nella cartella \Microsoft SDK\bin.

   È inoltre necessaria la variante MSI del file del programma di installazione. Contattate  Adobe per ricevere la versione più recente del programma di installazione MSI.

   >[!NOTE]
   >
   >Chiudete sempre il file DocumentSecurityExtensionforMicrosoftOffice.msi prima di eseguire il programma di installazione. Non potete eseguire il programma di installazione se Orca sta utilizzando il file MSI.

### Creare e configurare il file MSI {#create-and-configure-the-msi-file}

1. Fare clic su **[!UICONTROL Start > Programmi > Orca]**.

1. Fare clic su **[!UICONTROL File > Apri]**, quindi individuare il file `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Selezionare Proprietà dall&#39;elenco delle tabelle (sul lato sinistro).

1. Modificate i seguenti valori del nome chiave in base all&#39;installazione aziendale di Rights Management o Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nome </strong><strong></strong><strong>chiave</strong></p> </td>
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

1. Selezionare Registry dall&#39;elenco delle tabelle (sul lato sinistro).

1. Modificate il seguente valore del nome chiave.

   | **Nome chiave** | **Descrizione** | **Valore chiave predefinito** |
   |---|---|---|
   | `IsDefault` | Il server APS predefinito. | Server predefinito |

1. Salvate il file modificato nella stessa directory che contiene il programma di installazione MSI originale.

   >[!NOTE]
   >
   >È pratica comune utilizzare lo stesso nome file del file MSI originale (ad esempio, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Configurazione dell&#39;applicazione automatica di un criterio predefinito {#configuring-automatic-application-of-a-default-policy}

Come parte della configurazione, potete configurare l&#39;applicazione automatica di un criterio predefinito in modo che Document Security Extension for Microsoft Office protegga tutti i documenti salvati.

Potete specificare una delle seguenti opzioni:

* Protect tutti i documenti con un criterio predefinito.
* Consentire agli utenti di salvare un file in un formato non protetto quando non possono connettersi al server. Questa flessibilità consente di tenere conto dei casi in cui gli utenti creano documenti mentre sono disconnessi dalla rete (ad esempio, mentre si trovano su un aereo).

Dopo aver attivato la funzione di applicazione automatica del criterio, il documento viene protetto con il criterio predefinito nei seguenti casi:

* L&#39;utente modifica e salva un documento appena creato
* L&#39;utente modifica e salva un documento non protetto
* L&#39;utente apre un&#39;applicazione che si apre con un documento predefinito, modifica e quindi salva il documento

### Configurare la funzione di applicazione automatica del criterio nel file MSI  {#configure-the-auto-apply-policy-feature-in-the-msi-file}

Prima di iniziare, preconfigurate il programma di installazione in modo da indirizzarlo al server dei moduli di LiveCycle o AEM, come descritto in precedenza in questo articolo.

1. Fare clic su **[!UICONTROL Start > Programmi > Orca]**.

1. Fare clic su **[!UICONTROL File > Apri]**, quindi individuare il file `DocumentSecurityExtensionforMicrosoftOffice.msi`.

1. Selezionare Proprietà dall&#39;elenco delle tabelle (sul lato sinistro).

1. Modificate i seguenti valori del nome chiave in base all&#39;installazione aziendale di Rights Management o Document Security.

<table>
 <tbody>
  <tr>
   <td><p><strong>Nome chiave</strong></p> </td>
   <td><p><strong>Descrizione</strong></p> </td>
   <td><p><strong>Valore </strong><strong></strong><strong>chiave predefinito</strong></p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_IS_AUTO_ APPLY</code></p> </td>
   <td><p>Abilitare o disabilitare la funzione di applicazione automatica del criterio.</p> <p><code>1</code>: Abilita</p> <p>0: Disattiva</p> </td>
   <td><p>0</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_POLICY_I D</code></p> </td>
   <td><p>GUID del criterio da utilizzare per il salvataggio di nuovi documenti. Si applica alla funzione di applicazione automatica del criterio.</p> </td>
   <td><p>ID criterio esadecimale come visibile sul server RM</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_U RL</code></p> </td>
   <td><p>URL server.</p> </td>
   <td><p>default.corp.com</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_SERVER_P ORT_NO</code></p> </td>
   <td><p>Numero porta del server.</p> </td>
   <td><p>1234</p> </td>
  </tr>
  <tr>
   <td><p><code>AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE</code></p> </td>
   <td><p>Stabilisce se è possibile creare documenti senza protezione Document Security se il client non è in grado di contattare il server per proteggere il documento al primo salvataggio.</p> <p>1: Consenti salvataggi non protetti </p> <p>0: Impedisci la creazione di nuovi documenti quando il client non è in grado di contattare il server per salvare il documento.</p> </td>
   <td><p>0</p> </td>
  </tr>
 </tbody>
</table>

>[!NOTE]
>
>`AUTO_APPLY_POLICY_ALLOW_UN PROTECTED_SAVE` Questa opzione è utile se desiderate ricordare ai clienti di proteggere tutti i documenti senza obbligarli a farlo. È inoltre utile quando si è certi che gli utenti creano documenti mentre sono disconnessi dalla rete. Non si desidera impedire loro di creare e salvare documenti.

1. Salvate il file modificato nella stessa directory che contiene il file MSI originale.

   >[!NOTE]
   >
   >È pratica comune utilizzare lo stesso nome file del file MSI originale (ad esempio, `DocumentSecurityExtensionforMicrosoftOffice.msi`).

## Abilitazione della protezione automatica dei nuovi documenti {#enabling-automatic-protection-of-new-documents}

L&#39;amministratore può abilitare la possibilità di proteggere automaticamente i documenti salvati da un utente. L&#39;amministratore configura la funzione di applicazione automatica del criterio nel programma di installazione di Document Security Extension for Microsoft Office.

Se questa funzione è abilitata, tutti i documenti salvati dall&#39;utente sono protetti tramite il criterio predefinito. Questa azione si applica alle situazioni seguenti:

* Quando un utente crea un nuovo documento, lo modifica e lo salva.
* Quando un utente apre un documento non protetto, lo modifica e lo salva.

Per informazioni sulla configurazione della funzione di applicazione automatica del criterio, vedere [Configurare un&#39;applicazione automatica del criterio predefinito](installing-configuring-aemdsext.md#p-configuring-automatic-application-of-a-default-policy-p).

## Abilita interfaccia utente senza nastro {#enable-ribbon-less-user-interface}

È possibile abilitare o disabilitare l&#39;interfaccia utente senza nastro modificando le impostazioni nel Registro di sistema di Windows. Per aggiornare il Registro di sistema e abilitare l&#39;interfaccia utente per ridurre la barra multifunzione, eseguire i seguenti passaggi:

1. Eseguire un backup del Registro di sistema di Windows prima di apportare modifiche. Per istruzioni dettagliate, vedere [Come modificare il Registro di sistema di Windows](https://support.microsoft.com/en-us/kb/136393).
1. Nell&#39;Editor del Registro di sistema, andate a HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 o HKEY_LOCAL_MACHINE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Create un nuovo valore Dword (32 bit) denominato **HidePluginUI**.

1. Impostare il valore della proprietà **HidePluginUI **su 1 per abilitare l&#39;interfaccia utente senza nastro.

1. Chiudere l&#39;Editor del Registro di sistema.

## Abilita filigrana per la stampa in Microsoft Excel {#enable-watermark-for-printing-in-microsoft-excel}

È possibile modificare le impostazioni del Registro di sistema di Windows in modo da creare una filigrana dinamica coesistente con le intestazioni e i piè di pagina esistenti. Le impostazioni del Registro di sistema rendono disponibile la filigrana solo durante la stampa. Per aggiornare il Registro di sistema e abilitare le filigrane durante la stampa, effettuare le operazioni seguenti:

1. Eseguire un backup del Registro di sistema di Windows prima di apportare modifiche. Per istruzioni dettagliate, vedere [Come modificare il Registro di sistema di Windows](https://support.microsoft.com/en-us/kb/136393).
1. Nell&#39;Editor del Registro di sistema, andate a HKEY_CURRENT_USER\Software\Adobe\LiveCycle Rights Management ES4\11.0.0 o HKEY_LOCAL_MACHINE\WOW6432NODE\Software\Adobe\LiveCycle Rights Management ES4\11.0.0
1. Create una nuova chiave del Registro di sistema **WatermarkMode**.
1. Nella chiave del Registro di sistema WatermarkMode, creare un DWORD **WatermarkMode** e impostare il valore di DWORD **WatermarkMode** su **1**.

1. Chiudere l&#39;editor del Registro di sistema.

>[!NOTE]
>
>In Esplora risorse è possibile utilizzare il menu File o il menu di scelta rapida per creare un documento di Microsoft Excel. Per i documenti creati con metodi dichiarati, la data di stampa non può essere recuperata o modificata. È una limitazione di Microsoft Excel. AEM filigrane di Document Security dipendono dalla data di stampa del documento. Pertanto, per tali documenti, la filigrana viene ripristinata a una data precedente. Inoltre, le intestazioni e i piè di pagina non vengono conservati.

## Aggiungere una copertina personalizzata a un documento {#coverpage}

Un utente può tentare di aprire il documento protetto su un computer in cui non è installato AEM plug-in Document Security for Microsoft Office. Tali computer non possono aprire il documento. Su tali computer, potete visualizzare una pagina di copertina contenente le istruzioni per scaricare AEM plug-in di Document Security for Microsoft Office e altre informazioni.

### Prima di configurare una copertina {#before-you-configure-a-cover-page}

* Eseguire il backup del file CommonResources.dll. Il percorso predefinito è:

   * **(per uffici a 32 bit su computer a 32 bit)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(Per uffici a 32 bit su computer a 64 bit)** C:\Program Files (x86)\Adobe\Adobe Experience Manager Forms\Document Security Extension

   * **(per uffici a 64 bit su computer a 64 bit)** C:\Program Files\Adobe\Adobe Experience Manager Forms\Document Security Extension

* Verificare che Microsoft Visual Studio 2008 o versione successiva sia installato. È inoltre possibile utilizzare qualsiasi altra utility per modificare i file DLL.
* Estrarre l&#39;archivio templates.zip. L&#39;archivio contiene i modelli .xlsx, .docx e .pptx per la pagina di copertina. Utilizzate solo i modelli forniti per i tipi di file .xlsx, .docx e .pptx. Potete creare modelli personalizzati per altri tipi di file. Personalizzare i modelli per includere messaggi e istruzioni personalizzati. Potete trovare template.zip in:

[Ottieni file](assets/templates.zip)

### Struttura del file CommonResources.dll {#structure-of-the-commonresources-dll-file}

Il file CommonResources.dll contiene informazioni sui modelli di risorse. Contiene due identificatori di nome TEMPLATE_FILE e RT_MANIFEST. Per abilitare una copertina personalizzata, viene modificato l&#39;identificatore del nome TEMPLATE_FILE. L&#39;identificatore del nome TEMPLATE_FILE ha sei risorse:

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

#### Configurare il modello come copertina {#configure-the-template-as-a-cover-page}

1. Aprire Microsoft Visual Studio. Sfogliate e aprite il file CommonResources.dll per la modifica.

   >[!NOTE]
   >
   >Se il file non viene visualizzato nella finestra Esplora soluzioni, riaprire il file utilizzando l&#39;opzione Apri con. Selezionare l&#39;editor delle risorse come editor.

1. Nella finestra Esplora soluzioni, espandere la directory TEMPLATE_FILE ed eliminare le risorse 101.

1. Aggiungete le risorse:

   1. Con un progetto selezionato in Esplora soluzioni, scegliere Proprietà dal menu Progetto.
   1. Selezionate la scheda Risorse.
   1. Nella barra degli strumenti di Progettazione risorse, scegliere Aggiungi risorsa, fare clic sulla freccia. Per il tipo di risorsa, selezionate TEMPLATE_FILE e fate clic su Importa.
   1. Nella finestra di dialogo Aggiungi file esistente a risorse, individuare il file Resource.xlsx e fare clic su Apri. Il file viene aggiunto alla directory TEMPLATE_FILE.

   >[!NOTE]
   >
   >Verificate che le impostazioni della lingua siano corrette. Eliminate la risorsa con una lingua neutra.

1. Ripetere i passaggi 2 e 3 per tutti i tipi di risorse.

   >[!NOTE]
   >
   >Non eliminare e aggiungere tipi di risorse in ordine casuale. Dopo 101, configurare 102 e così via.

### Creare un pacchetto personalizzato del file CommonResources.dll con il programma di installazione di AEM&#39;estensione Document Security per Microsoft Office {#package-custom-commonresources-dll-file-with-the-installer-of-aem-document-security-extension-for-microsoft-office}

Puoi personalizzare il file CommonResources.dll per includere l&#39;aggiunta di una copertina personalizzata. Dopo aver personalizzato il file, è possibile sostituire manualmente il file originale con il file personalizzato su tutte le workstation oppure scegliere un metodo automatizzato per sostituire il file.

In un ambiente di grandi dimensioni, è difficile e noioso sostituire manualmente il file `CommonResources.dll file` predefinito con un file `CommonResources.dll` personalizzato. È possibile utilizzare uno strumento di autoestrazione e creazione di pacchetti (ad esempio WinZip Self-Extrait) per creare un pacchetto del file CommonResources.dll personalizzato con AEM programma di installazione di Document Security Extension for Microsoft Office. In seguito, potrete distribuire il programma di installazione personalizzato a tutta la workstation. Questo metodo riduce il tempo necessario per sostituire il file `CommonResources.dll` predefinito con un file personalizzato. Inoltre assicura che tutta la workstation abbia il file CommonResources.dll richiesto. Lo strumento di autoestrazione e imballaggio è solo uno dei molti metodi possibili per sostituire automaticamente un file. Potete scegliere qualsiasi metodo adatto al vostro ambiente.

Per creare un pacchetto di file `CommonResources.dll`personalizzato con il programma di installazione di AEM&#39;estensione Document Security per Microsoft Office, potete effettuare le seguenti operazioni:

1. Installare uno strumento autoestraente e packager. Ad esempio, WinZip Self-Extrait.
1. Create una nuova cartella. Ad esempio, YOUR_FOLDER_NAME
1. Inserire il programma di installazione originale dell&#39;estensione AEM Document Security e il file CommonResources.dll personalizzati nella cartella appena creata.
1. Create un file batch nella cartella. Ad esempio, YOUR_FOLDER_NAME\Installer.bat
1. Aprite il file batch per la modifica e aggiungete il seguente codice al file batch:

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

   Se utilizzate un&#39;altra versione di LiveCycle o AEM Forms  su JEE oltre a LiveCycle Rights Management ES4 e alla versione 11.0.0, sostituite il percorso della chiave di registro come segue:

   * (Livecycle Rights Management ES2 e versione 9.0): *HKLM\SOFTWARE\Adobe/LiveCycle* *Rights Management ES2\9.0 *
   * (Livecycle Rights Management ES3 e versione 10.0)
   * (Livecycle Rights Management ES4 e versione 11.0) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0
   * (AEM 6.0 Forms su JEE e versioni successive) HKLM\SOFTWARE\Adobe\LiveCycle Rights Management ES4\11.0.0

1. Nel codice riportato sopra, sostituite tutte le istanze di YOUR_FOLDER_NAME con il nome della cartella creata al punto 2.
1. **(Per AEM estensione Document Security per il programma di installazione di Microsoft Office con estensione .exe solo)** Sostituite la seguente riga di codice:

   `msiexec /i YOUR_FOLDER_NAME\MSI_NAME.msi`
con

   `START /w YOUR_FOLDER_NAME\APPLICATION_NAME.exe`

1. Salvate e chiudete il file batch.
1. Utilizzate uno strumento di autoestrazione e packager per creare un pacchetto della cartella contenente il file CommonResources.dll personalizzato, il programma di installazione originale AEM&#39;estensione Document Security per Microsoft Office e il file batch.

   >[!NOTE]
   >
   >Verificate che il pacchetto autoestraente sia impostato per essere eseguito come amministratore e automaticamente
   >esegue il file batch al completamento dell&#39;estrazione.

Il programma di installazione autoestraente di AEM&#39;estensione Document Security per Microsoft Office crea un pacchetto con il file CommonResources.dll personalizzato ed è pronto per la distribuzione.
