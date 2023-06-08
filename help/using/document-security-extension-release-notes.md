---
title: AEM Document Security for Microsoft Office - Note sulla versione
description: Prima di installare AEM Document Security 6.2 Extension for Microsoft Office, leggi le note sulla versione.
uuid: f6ab73d4-ac4e-4fff-9bb8-917b75401653
content-type: reference
topic-tags: installing
discoiquuid: c9342c28-8289-4831-a613-4bc03431f557
exl-id: 582f10bb-60d2-46ed-b81d-5818a040edc6
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: tm+mt
source-wordcount: '1030'
ht-degree: 100%

---

# AEM Document Security for Microsoft Office - Note sulla versione{#aem-document-security-for-microsoft-office-release-notes}

## Novità di AEM Document Security for Microsoft Office {#whats-new-in-aem-document-security-for-microsoft-office}

* **Supporto per Office 2019**: in Document Security Extension for Microsoft Office è stato aggiunto il supporto per Microsoft Office 2019. È stato progettato per essere utilizzato anche con le applicazioni desktop di Microsoft Office 2019 installate nell’ambito di Office 365.

>[!NOTE]
>
>In questo documento i termini Adobe Experience Manager Document Security for Microsoft Office, Adobe Experience Manager Document Security Extension for Microsoft Office e Document Security Extension for Microsoft Office vengono utilizzati in modo intercambiabile.

## Installazione e configurazione di AEM Document Security Extension for Microsoft Office {#installing-and-configuring-aem-document-security-extension-for-microsoft-office}

Questa versione di Document Security Extension for Microsoft Office è compatibile con Adobe LiveCycle Rights Management ES2 e versioni successive, e con il componente aggiuntivo Document Security per AEM Forms.

Prima di installare AEM Document Security Extension for Microsoft Office, leggi attentamente le informazioni presenti in questo documento. Per istruzioni di installazione dettagliate, consulta l’articolo [Installazione e configurazione di AEM Document Security Extension for Microsoft Office](installing-configuring-aemdsext.md).

## Problemi risolti {#fixed-issues}

* Le stringhe vengono visualizzate in verticale e al contenuto vengono aggiunte interruzioni di riga errate. (Rif. CQ-4201054)

## Problemi noti {#known-issues}

### Plug-in di terze parti non supportati {#third-party-plug-ins-not-supported}

AEM Document Security Extension for Microsoft Office non può essere utilizzato con plug-in di terze parti. Disinstalla eventuali plug-in di terze parti per Microsoft Office prima di installare Document Security Extension for Microsoft Office.

### Opzioni di menu disattivate in Microsoft Word, Excel e PowerPoint {#disabled-menu-options-in-microsoft-word-excel-and-powerpoint}

AEM Document Security Extension for Microsoft Office utilizza funzioni di protezione integrate per proteggere documenti, fogli di lavoro e presentazioni. Disattiva alcune opzioni di menu di Excel, Word e PowerPoint.

### Limitazioni per Microsoft Office 2013, 2016 e 2019 {#restrictions-for-microsoft-office}

In Microsoft Office, durante una sessione protetta non sono disponibili le seguenti opzioni:

* Microsoft Office 2016 o Microsoft Office 2019

   * File > Salva con nome
   * File > Cronologia
   * File > Condividi
   * File > Esporta
   * File > Pubblica
   * File > Account
   * File > Informazioni > Proteggi documento/cartella di lavoro/presentazione > Crittografa con password
   * File > Informazioni > Proteggi documento > Aggiungi firma digitale
   * File > Informazioni > Proteggi documento > Contrassegna come finale
   * Opzione di condivisione in alto a destra

* Microsoft Office 2013

   * File > Salva con nome
   * File > Condividi
   * File > Esporta
   * File > Account
   * File > Informazioni > Proteggi documento/cartella di lavoro/presentazione > Crittografa con password
   * File > Informazioni > Proteggi documento > Aggiungi firma digitale
   * File > Informazioni > Proteggi documento > Contrassegna come finale

### Apertura di un documento protetto da SharePoint Server {#opening-a-protected-document-from-sharepoint-server}

Apertura del documento protetto: se provi ad aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server senza prima aver aperto il programma Microsoft Office associato al tipo di file, ad esempio Microsoft Word, Microsoft Excel o Microsoft PowerPoint, è possibile che il documento non si apra. Viene visualizzato un messaggio di errore in cui si richiede l’installazione del plug-in applicabile. È quindi consigliabile aprire il programma Microsoft Office associato prima di aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server.

(Facoltativo) Si consiglia di svuotare la cartella della cache prima di aprire un documento protetto in Document Security Extension for Microsoft Office da SharePoint Server.

Quando si apre un documento protetto da SharePoint Server, vengono disattivate tutte le autorizzazioni sul documento, indipendentemente dalle policy applicate.

### Applicare una policy con filigrana dinamica a file Microsoft Excel 2013, Microsoft Excel 2016 e Microsoft Excel 2019 senza stampante installata {#apply-a-policy-with-a-dynamic-watermark-to-microsoft-excel-microsoft-excel-and-microsoft-excel-file-with-no-printer-installed}

Se applichi una policy con filigrana dinamica a un file Microsoft Excel 2013, Microsoft Excel 2016 o Microsoft Excel 2019 su un computer in cui non è installata alcuna stampante e quindi salvi il file, viene visualizzato il seguente errore: “Errore interno durante l’applicazione della filigrana dinamica.” Questo errore viene visualizzato anche se riapri il file protetto. La filigrana non viene applicata e non è visibile da Visualizza > Layout pagina.

### Disattivare Protezione esecuzione programmi di Windows per le applicazioni Office supportate {#disable-windows-data-execution-prevention-for-supported-office-applications}

Quando utilizzi Document Security Extension for Microsoft Office, è consigliabile disattivare l’impostazione Protezione esecuzione programmi di Windows.

### I file Microsoft Office condivisi non possono essere protetti con Document Security Extension {#shared-microsoft-office-files-cannot-be-protected-using-document-security-extension}

Se proteggi un file Microsoft Office condiviso con Document Security Extension, si verifica un errore e il file condiviso non è protetto.

### Avvio delle applicazioni Office in un computer contenente Document Security Extension for Microsoft Office e McAfee VirusScan {#starting-office-applications-on-a-machine-containing-document-security-extension-for-microsoft-office-and-mcafee-virusscan}

Per garantire un avvio ottimale delle applicazioni Office nei computer in cui sono installati Document Security e McAfee VirusScan con scansione all’accesso abilitata, disabilita l’opzione di protezione da overflow del buffer nella console di McAfee VirusScan.

### Installazione di Document Security Extension for Microsoft Office in un computer con una lingua di Microsoft Office non supportata {#installing-document-security-extension-for-microsoft-office-on-a-machine-with-an-unsupported-microsoft-office-language}

Prima di installare Document Security Extension for Microsoft Office in un computer in cui è presente un’applicazione Microsoft Office con una lingua non supportata, apri l’applicazione Office almeno una volta.

### Il pulsante di sincronizzazione offline è abilitato anche se un utente non dispone di autorizzazioni offline {#synchronize-offline-button-is-enabled-even-when-a-user-does-not-have-offline-permissions}

Il pulsante di sincronizzazione offline è disponibile anche se l’utente non dispone di autorizzazioni offline sul documento. Se selezioni il pulsante, tuttavia, non viene eseguita alcuna operazione.

### Versioni di prova di Microsoft Office non supportate {#no-support-for-trial-versions-of-microsoft-office}

L’estensione Document Security for Microsoft Office non supporta le versioni di prova di Microsoft Office. Prima di installare l’estensione, accertati di aver installato una copia con licenza di Microsoft Office e di averla attivata.

### Impossibile aprire un file Microsoft Office protetto {#unable-to-open-a-protected-microsoft-office-files}

Se è abilitata la visualizzazione protetta di Microsoft Office, Right Management Extension non è in grado di aprire file Microsoft Excel (XLS, XLSX) o Microsoft PowerPoint (PPT) protetti da una posizione remota.

### Le celle di un documento Microsoft Excel contenenti un’immagine o un colore di sfondo vengono visualizzate sopra la filigrana {#cells-of-microsoft-excel-document-containing-an-image-or-background-color-appear-on-top-of-watermark}

Se una cella di un documento Microsoft Excel contiene un’immagine o un colore di sfondo e al documento viene applicata una policy di filigrana dinamica, l’immagine o il colore di sfondo contenuto nella cella viene visualizzato sopra la filigrana e la copre.

### Problema di usabilità con più certificati {#usability-issue-with-multiple-certificates}

Se nel computer client sono presenti più certificati e l’utente annulla la finestra di dialogo di selezione del certificato, la finestra di dialogo viene visualizzata nuovamente e l’utente deve annullarla una seconda volta.

### Microsoft PowerPoint consente la modifica di documenti protetti {#microsoft-powerpoint-allows-editing-protected-documents}

Se si tenta di modificare un documento protetto, in Microsoft PowerPoint viene visualizzato il messaggio di tipo: “L’utente non dispone delle autorizzazioni per modificare il documento. Le modifiche non verranno salvate.” Dopo aver chiuso il messaggio, l’utente può continuare ad aggiungere testo o modificare il documento. Le modifiche apportate ai documenti protetti, tuttavia, non vengono salvate.

Questo comportamento corrisponde al comportamento previsto in PowerPoint 2013, PowerPoint 2016 e PowerPoint 2019.
