---
title: AEM Document Security for Microsoft Office - Note sulla versione
description: Prima di installare AEM Document Security 6.2 Extension for Microsoft Office, leggete le note sulla versione.
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
translation-type: tm+mt
source-git-commit: 403b800eab086d131beb65a496836158778954ee
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 0%

---


# AEM Document Security for Microsoft Office - Note sulla versione{#aem-document-security-for-microsoft-office-release-notes}

## Novità di AEM Document Security for Microsoft Office {#whats-new-in-aem-document-security-for-microsoft-office}

* **Supporto per Office 2019**: Document Security Extension for Microsoft Office ha aggiunto il supporto per Microsoft Office 2019. È inoltre previsto che funzioni con le applicazioni desktop Microsoft Office 2019 installate come parte di Office 365.

>[!NOTE]
>
>Il documento utilizza in modo intercambiabile i termini Adobe Experience Manager Document Security for Microsoft Office, Adobe Experience Manager Document Security Extension for Microsoft Office e Document Security Extension for Microsoft Office.

## Installazione e configurazione AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Questa versione di Document Security Extension for Microsoft Office è compatibile con  Adobe LiveCycle Rights Management ES2 e versioni successive e con il componente aggiuntivo Document Security per AEM moduli.

Prima di installare AEM Document Security Extension for Microsoft Office, rivedete le informazioni presenti in questo documento. Per istruzioni di installazione dettagliate, consultate l&#39;articolo [Installazione e configurazione AEM Document Security Extension for Microsoft Office](installing-configuring-aemdsext.md).

## Problemi risolti {#fixed-issues}

* Le stringhe vengono visualizzate in verticale e al contenuto vengono aggiunte interruzioni di riga errate. (Ref. CQ-4201054)

## Problemi noti {#known-issues}

### Plug-in di terze parti non supportati {#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office non funziona con plug-in di terze parti. Disinstallate eventuali plug-in di terze parti per Microsoft Office prima di installare Document Security Extension for Microsoft Office.

### Opzioni menu disattivate in Microsoft Word, Excel e PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office utilizza funzioni di protezione integrate per proteggere documenti, fogli di lavoro e presentazioni. Disattiva alcune opzioni di menu di Excel, Word e PowerPoint.

### Restrizioni per Microsoft Office 2013, 2016 e 2019 {#restrictions-for-microsoft-office}

In Microsoft Office, durante una sessione protetta non sono disponibili le seguenti opzioni:

* Microsoft Office 2016 o Microsoft Office 2019

   * File > Salva con nome
   * File > Cronologia
   * File > Condividi
   * File > Esporta
   * File > Pubblica
   * File > Account
   * File > Informazioni > Documento/Cartella di lavoro/Presentazione di Protect > Crittografa con password
   * File > Informazioni > Documento Protect > Aggiungi firma digitale
   * File > Informazioni > Documento Protect > Segna come finale
   * Opzione Condividi in alto a destra

* Microsoft Office 2013

   * File > Salva con nome
   * File > Condividi
   * File > Esporta
   * File > Account
   * File > Informazioni > Documento/Cartella di lavoro/Presentazione di Protect > Crittografa con password
   * File > Informazioni > Documento Protect > Aggiungi firma digitale
   * File > Informazioni > Documento Protect > Segna come finale

### Apertura di un documento protetto da SharePoint Server {#opening-a-protected-document-from-sharepoint-server}

Apertura del documento protetto: Se provate ad aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server senza prima aprire il programma di Microsoft Office associato al tipo di file, ad esempio Microsoft Word, Microsoft Excel o Microsoft PowerPoint, il documento potrebbe non venire aperto. Viene visualizzato un messaggio di errore che indica l&#39;installazione del plug-in applicabile. Pertanto, è consigliabile aprire il programma Microsoft Office associato prima di aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server.

(Facoltativo) Si consiglia di svuotare la cartella della cache prima di aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server.

Quando si apre un documento protetto da SharePoint Server, tutte le autorizzazioni sul documento vengono disattivate, indipendentemente dal criterio applicato.

### Applicare un criterio con una filigrana dinamica a file di Microsoft Excel 2013, Microsoft Excel 2016 e Microsoft Excel 2019 senza stampante installata {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

Quando applicate un criterio con filigrana dinamica al file Microsoft Excel 2013, Microsoft Excel 2016 e Microsoft Excel 2019 su un computer in cui non è installata alcuna stampante e quindi salvate il file, viene visualizzato il seguente errore: &quot;Errore interno durante l&#39;applicazione della filigrana dinamica.&quot; Questo errore viene visualizzato anche quando si riapre il file protetto. La filigrana non viene applicata e non è visibile da Visualizza > Layout pagina.

### Disattivazione della prevenzione dell&#39;esecuzione dei dati di Windows per le applicazioni Office supportate {#disable-windows-data-execution-prevention-for-supported-office-applications}

È consigliabile disattivare l&#39;impostazione Protezione esecuzione programmi di Windows quando si utilizza Document Security Extension for Microsoft Office.

### I file Microsoft Office condivisi non possono essere protetti utilizzando Document Security Extension {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

Quando proteggete un file di Microsoft Office condiviso utilizzando Document Security Extension, si verifica un errore e il file condiviso non è protetto.

### Avvio delle applicazioni Office in un computer contenente Document Security Extension for Microsoft Office e McAfee VirusScan {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Per fare in modo che le applicazioni Office vengano avviate senza problemi nei computer in cui sono installati Document Security e McAfee VirusScan con l&#39;opzione per la scansione all&#39;accesso abilitata, disabilitate l&#39;opzione relativa alla protezione dell&#39;overflow del buffer nella console di McAfee VirusScan.

### Installazione di Document Security Extension for Microsoft Office in un computer con una lingua di Microsoft Office non supportata {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

Prima di installare Document Security Extension for Microsoft Office in un computer con un&#39;applicazione Microsoft Office con una lingua non supportata, aprite l&#39;applicazione Office almeno una volta.

### Il pulsante Sincronizza offline è attivato anche quando un utente non dispone delle autorizzazioni per la sincronizzazione offline {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

Il pulsante Sincronizza non in linea è disponibile anche se l&#39;utente non dispone delle autorizzazioni per la sincronizzazione offline del documento. Tuttavia, se si seleziona il pulsante non viene eseguita alcuna operazione.

### Nessun supporto per le versioni di prova di Microsoft Office {#no-support-for-trial-versions-of-microsoft-office}

L&#39;estensione Document Security per Microsoft Office non supporta le versioni trail di Microsoft Office. Prima di installare l’estensione, accertatevi di aver installato una copia con licenza di Microsoft Office e di averla attivata.

### Impossibile aprire i file di Microsoft Office protetti {#unable-to-open-a-protected-microsoft-office-files}

Se la visualizzazione protetta di Microsoft Office è attivata, Right Management Extension non è in grado di aprire i file Microsoft Excel (XLS, XLSX) e Microsoft PowerPoint (PPT) protetti da una posizione remota.

### Le celle di un documento Microsoft Excel contenente un&#39;immagine o un colore di sfondo vengono visualizzate sulla filigrana {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Se una cella di un documento di Microsoft Excel contiene un&#39;immagine o è riempita con un colore di sfondo e al documento viene applicato un criterio di filigrana dinamica, l&#39;immagine o il colore di sfondo riempito nella cella vengono visualizzati sopra alla filigrana e coprono la filigrana.

### Problema di usabilità con più certificati {#usability-issue-with-multiple-certificates}

Se nel computer client sono presenti più certificati e l&#39;utente annulla la finestra di dialogo di selezione del certificato, la finestra di dialogo viene nuovamente visualizzata e l&#39;utente deve annullare due volte la finestra di dialogo.

### Microsoft PowerPoint consente la modifica di documenti protetti {#microsoft-powerpoint-allows-editing-protected-documents}

Durante il tentativo di modifica di un documento protetto, in Microsoft PowerPoint viene visualizzato un messaggio &quot;Non è consentito modificare il documento. Non potrai salvare le modifiche.&quot; Dopo aver chiuso il messaggio, gli utenti possono continuare ad aggiungere testo o a modificare il documento. Tuttavia, le modifiche apportate ai documenti protetti non vengono salvate.

Il comportamento di cui sopra è come previsto in PowerPoint 2013, PowerPoint 2016 e PowerPoint 2019.
