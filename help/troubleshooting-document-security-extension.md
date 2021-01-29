---
title: Risoluzione dei problemi AEM Document Security Extension for Microsoft Office
description: In caso di problemi durante l'installazione, la configurazione o l'utilizzo di AEM Document Security Extension for Microsoft Office, seguite le istruzioni riportate in questo documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
translation-type: tm+mt
source-git-commit: ac26ec61f62d7a3db2429c8a9d3f68b82ba8f77a
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# Risoluzione dei problemi AEM Document Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Risoluzione dei problemi di installazione e configurazione {#troubleshootinginstallationandconfiguration}

In caso di problemi durante l&#39;installazione e la configurazione AEM Document Security Extension for Microsoft Office, accertatevi di aver seguito attentamente le istruzioni elencate nella sezione - prima dell&#39;installazione - dell&#39;articolo [install](installing-configuring-aemdsext.md).

Se avete installato e configurato tutto in base alla documentazione, controllate le sezioni seguenti per verificare se sono presenti problemi simili a quelli riscontrati.

### Impossibile caricare Document Security Extension per le applicazioni di Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La proprietà LoadBehavior nel Registro di sistema di Windows specifica il funzionamento in fase di esecuzione del plug-in per la protezione dei documenti. Se la proprietà LoadBehavior è impostata su 3, tutti i plug-in vengono caricati automaticamente. Prima di installare Document Security Extension for Microsoft Office, verificate che il valore della proprietà LoadBehavior sia impostato su 3.

1. Eseguire un backup del Registro di sistema di Windows prima di apportare modifiche. Per istruzioni dettagliate, vedere [Come modificare il Registro di sistema di Windows](https://support.microsoft.com/en-us/kb/136393).
1. Nell’Editor del Registro di sistema, andate toHKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin o HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Impostare il valore della proprietà **LoadBehavior** su 3.

1. Chiudere l&#39;Editor del Registro di sistema.

Per informazioni dettagliate su LoadBehavior, vedere l&#39;articolo [Voci del Registro di sistema per i componenti aggiuntivi VSTO](https://msdn.microsoft.com/en-us/library/bb386106.aspx#LoadBehavior).

## Risoluzione dei problemi delle attività amministrative {#admintasks}

In questa sezione vengono descritti i possibili problemi con l&#39;installazione AEM Document Security Extension.

### Le applicazioni di Microsoft Office non si avviano senza problemi durante l&#39;installazione di Document Security Extension {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Per fare in modo che le applicazioni Office vengano avviate senza problemi nei computer in cui sono installati Document Security Extension e McAfee VirusScan con l&#39;opzione per la scansione all&#39;accesso abilitata, disabilitate l&#39;opzione relativa alla protezione dell&#39;overflow del buffer nella console di McAfee VirusScan.
