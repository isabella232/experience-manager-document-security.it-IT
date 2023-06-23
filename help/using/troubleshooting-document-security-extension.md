---
title: Risoluzione dei problemi di AEM Document Security Extension for Microsoft Office
description: In caso di problemi durante l’installazione, la configurazione o l’utilizzo di AEM Document Security Extension for Microsoft Office, segui le istruzioni riportate in questo documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
source-git-commit: 28137f26afc024d411857d44887bf69fe1ee2b81
workflow-type: ht
source-wordcount: '294'
ht-degree: 100%

---

# Risoluzione dei problemi di AEM Document Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Risoluzione dei problemi di installazione e configurazione {#troubleshootinginstallationandconfiguration}

In caso di problemi durante l’installazione e la configurazione di AEM Document Security Extension for Microsoft Office, accertati di aver seguito attentamente le istruzioni elencate nella sezione “Prima dell’installazione” dell’articolo [Installazione](installing-configuring-aemdsext.md).

Se hai eseguito le procedure di installazione e configurazione secondo quanto descritto nella documentazione, consulta le sezioni seguenti per verificare se sono presenti problemi simili a quelli riscontrati.

### Impossibile caricare Document Security Extension per le applicazioni di Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La proprietà LoadBehavior nel Registro di sistema di Windows specifica il funzionamento in fase di esecuzione del plug-in di protezione dei documenti. Se la proprietà LoadBehavior è impostata su 3, tutti i plug-in vengono caricati automaticamente. Prima di installare Document Security Extension for Microsoft Office, verifica che il valore della proprietà LoadBehavior sia impostato su 3.

1. Crea una copia di backup del Registro di sistema di Windows prima di modificarlo. Per istruzioni dettagliate, consulta [Come modificare il Registro di sistema di Windows](https://support.microsoft.com/it-it/kb/136393).
1. Nell’editor del Registro di sistema, passa a HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin oppure HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Imposta il valore della proprietà **LoadBehavior** su 3.

1. Chiudi l’editor del Registro di sistema.

Per informazioni dettagliate su LoadBehavior, consulta l’articolo sulle [voci del registro di sistema per i componenti aggiuntivi VSTO](https://msdn.microsoft.com/it-it/library/bb386106.aspx#LoadBehavior).

## Risoluzione dei problemi relativi ad attività amministrative {#admintasks}

In questa sezione vengono descritti i possibili problemi con la versione di AEM Document Security Extension installata.

### Con l’installazione di Document Security Extension, le applicazioni di Microsoft Office presentano problemi di avvio {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Per garantire un avvio ottimale delle applicazioni Office nei computer in cui sono installati Document Security Extension e McAfee VirusScan con scansione all’accesso abilitata, disabilita l’opzione di protezione da overflow del buffer nella console di McAfee VirusScan.
