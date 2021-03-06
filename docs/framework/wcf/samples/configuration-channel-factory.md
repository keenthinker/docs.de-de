---
title: Konfigurationskanalfactory
ms.date: 03/30/2017
ms.assetid: 3b749493-bd8a-4ccb-893e-5948901a1486
ms.openlocfilehash: 0f00ba5e217420fe416100071d380e413c3df118
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183946"
---
# <a name="configuration-channel-factory"></a>Konfigurationskanalfactory
In diesem Beispiel wird die Verwendung von <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> behandelt. Die <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> ermöglicht die zentrale Verwaltung der WCF-Clientkonfiguration. Dies kann auch in Szenarien nützlich sein, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.

## <a name="demonstrates"></a>Zeigt
 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601>

## <a name="discussion"></a>Diskussion
 In diesem Beispiel wird gezeigt, wie eine bestimmte Konfigurationsdatei mit <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zu einer Clientanwendung hinzugefügt wird, ohne die standardmäßige Anwendungskonfigurationsdatei verwenden zu müssen.

 Das Beispiel umfasst zwei Projekte. Das erste Projekt ist ein einfacher Dienst, der auf Nachrichten von den Clients antwortet. Das zweite Projekt ist eine Clientanwendung, die für die Konfigurationsdatei Test.config mithilfe einer <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> zwei <xref:System.Configuration.ExeConfigurationFileMap>-Objekte erstellt und diese für die Kommunikation mit dem Dienst verwendet. Beide Clients verwenden die in Test.config angegebene Konfiguration für die Kommunikation mit dem Dienst.

 Der folgende Code fügt einer Clientanwendung eine benutzerdefinierte Konfigurationsdatei hinzu.

```csharp
ExeConfigurationFileMap fileMap = new ExeConfigurationFileMap();
fileMap.ExeConfigFilename = "Test.config";
Configuration newConfiguration = ConfigurationManager.OpenMappedExeConfiguration(fileMap, ConfigurationUserLevel.None);

ConfigurationChannelFactory<ICalculatorChannel> factory1 = new ConfigurationChannelFactory<ICalculatorChannel>("endpoint1", newConfiguration, new EndpointAddress("http://localhost:8000/servicemodelsamples/service"));
ICalculatorChannel client1 = factory1.CreateChannel();
```

#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen

1. Öffnen Sie Visual Studio 2012 mit Administratorrechten.

2. Klicken Sie mit der rechten Maustaste auf die ConfigurationChannelFactory-Projektmappe (2 Projekte) und wählen Sie dann **Eigenschaften**aus.

3. Wählen Sie unter **Allgemeine Eigenschaften**die Option **Projekt starten**aus, und klicken Sie dann auf **Mehrere Startprojekte**.

4. Verschieben Sie das **Serviceprojekt** mit der **Aktion 'Start'** an den Anfang der Liste, und verschieben Sie dann das **Clientprojekt** nach dem **Serviceprojekt,** ebenfalls mit der **Aktion 'Start',** damit das **Clientprojekt** nach dem **Serviceprojekt** ausgeführt wird.

5. Klicken Sie auf **OK**, und drücken Sie dann F5 (oder STRG+F5), um das Beispiel auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigurationChannelFactory`
