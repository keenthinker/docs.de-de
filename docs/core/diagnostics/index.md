---
title: Übersicht über Diagnosetools – .NET Core
description: Eine Übersicht über die Tools und Techniken, die zur Diagnose von .NET Core-Anwendungen zur Verfügung stehen.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: ae3b9a1961f331c9cdea786bd5fe06b7bfa10927
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558113"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a>Welche Diagnosetools sind in .NET Core verfügbar?

Software verhält sich nicht immer erwartungsgemäß, .NET Core verfügt jedoch über Tools und APIs, mit denen Sie diese Probleme schnell und effektiv diagnostizieren können.

Dieser Artikel hilft Ihnen bei der Suche nach den verschiedenen Tools, die Sie benötigen.

## <a name="managed-debuggers"></a>Verwaltete Debugger

[Verwaltete Debugger](managed-debuggers.md) ermöglichen Ihnen die Interaktion mit dem Programm. Durch Anhalten, das inkrementelle Ausführen, Untersuchen und Fortsetzen erhalten Sie Erkenntnisse über das Verhalten Ihres Codes. Ein Debugger ist die erste Wahl für die Diagnose funktionaler Probleme, die leicht reproduziert werden können.

## <a name="logging-and-tracing"></a>Protokollierung und Ablaufverfolgung

Die [Protokollierung und Ablaufverfolgung](logging-tracing.md) sind verwandte Techniken. Sie beziehen sich auf das Instrumentieren von Code zum Erstellen von Protokolldateien. In den Dateien werden die Details eines Programms aufgezeichnet. Diese Details können zur Diagnose der kompliziertesten Probleme verwendet werden. In Kombination mit Zeitstempeln sind diese Techniken auch für Leistungsuntersuchungen von Bedeutung.

## <a name="unit-testing"></a>Komponententest

[Komponententests](../testing/index.md) sind eine wichtige Komponente von Continuous Integration und der Bereitstellung hochwertiger Software. Komponententests sollen Sie früh warnen, wenn Sie etwas unterbrechen.

## <a name="net-core-dotnet-diagnostic-global-tools"></a>Globale .NET Core-dotnet-Diagnosetools

### <a name="dotnet-counters"></a>dotnet-counters

[dotnet-counters](dotnet-counters.md) ist ein Tool zur Leistungsüberwachung der Integrität auf erster Ebene und zur Leistungsuntersuchung. Es überwacht die Werte des Leistungsindikators, die über die <xref:System.Diagnostics.Tracing.EventCounter>-API veröffentlicht wurden. Sie können beispielsweise den CPU-Verbrauch oder die Anzahl ausgelöster Ausnahmen in Ihrer .NET Core-Anwendung überwachen.

### <a name="dotnet-dump"></a>dotnet-dump

Mit dem Tool [dotnet-dump](dotnet-dump.md) können Sie Windows- und Linux-Kernspeicherabbilder ohne nativen Debugger erfassen und analysieren.

### <a name="dotnet-gcdump"></a>dotnet-gcdump

Mit dem Tool [dotnet-gcdump](dotnet-gcdump.md) können Sie GC-Speicherabbilder (Garbage Collector) aus .NET-Liveprozessen erfassen.

### <a name="dotnet-trace"></a>dotnet-trace

.NET Core schließt `EventPipe` ein, worüber Diagnosedaten bereitgestellt werden. Mit dem Tool [dotnet-trace](dotnet-trace.md) können Sie relevante Daten für die Profilerstellung in Ihrer App nutzen. Diese können hilfreich sein, wenn Sie die Ursache für langsame Apps ermitteln müssen.

## <a name="net-core-diagnostics-tutorials"></a>Tutorials zur .NET Core-Diagnose

### <a name="debug-a-memory-leak"></a>Debuggen eines Speicherverlusts

[Tutorial: Debuggen eines Speicherverlusts](debug-memory-leak.md). Hier wird erläutert, wie ein Speicherverlust gefunden wird. Das [dotnet-counters](dotnet-counters.md)-Tool wird zum Bestätigen des Verlusts und das [dotnet-dump](dotnet-dump.md)-Tool zur Diagnose des Verlusts verwendet.

### <a name="debug-high-cpu-usage"></a>Debuggen einer hohen CPU-Auslastung

[Tutorial: Debuggen einer hohen CPU-Auslastung](debug-highcpu.md). Hier lernen Sie, wie Sie eine hohe CPU-Auslastung untersuchen. In diesem Tutorial wird das Tool [dotnet-counters](dotnet-counters.md) verwendet, um eine solche Auslastung zu bestätigen. Danach erfahren Sie, wie Sie das [`dotnet-trace`-Hilfsprogramm für Leistungsanalysen](dotnet-trace.md) oder `perf` in Linux verwenden, um das CPU-Auslastungsprofil zu erfassen und anzuzeigen.

### <a name="debug-deadlock"></a>Debuggen eines Deadlocks

[Tutorial: Debuggen eines Deadlocks](debug-deadlock.md). Hier erfahren Sie, wie Sie das Tool [dotnet-dump](dotnet-dump.md) verwenden, um Threads und Sperren zu untersuchen.
