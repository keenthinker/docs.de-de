---
title: ETW-Stapelereignis
description: Informieren Sie sich über das ETW-Stapel Ereignis, das zusammen mit anderen Ereignissen verwendet werden sollte, um Stapel Überwachungen zu generieren, nachdem ein Ereignis ausgelöst wurde.
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
ms.openlocfilehash: cab496615c4ef17831895b72c8987917e3c06e77
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474136"
---
# <a name="stack-etw-event"></a>ETW-Stapelereignis
Das Stapelereignis sollte in Verbindung mit anderen Ereignissen verwendet werden, um Stapelüberwachungen zu generieren, nachdem ein Ereignis ausgelöst wird. Es wird protokolliert, wann der Laufzeitanbieter aktiviert ist. Dieses Ereignis hat eine hohe Frequenz, da es ausgelöst wird, wenn ein anderes Laufzeitereignis ausgelöst wird. Aus diesem Grund wird empfohlen, dass Sie dieses Ereignis mit Vorsicht verwenden.  
  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`StackKeyword` (0x40000000)|LogAlways(0)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|82|In Verbindung mit anderen Ereignissen zum Generieren von Stapelüberwachungen nach einem Ereignis.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|BESCHREIBUNG|  
|----------------|---------------|-----------------|  
|ClrInstanceID|win:UInt16|URI.|  
|Reserved1|win:UInt8|Reserviert.|  
|Reserved2|win:UInt8|Reserviert.|  
|FrameCount|win:UInt32|Die Anzahl von Frames in der Stapelüberwachung.|  
|Stapel|win:Pointer|Anweisungszeigerspalten.|  
  
## <a name="see-also"></a>Weitere Informationen

- [CLR-ETW-Ereignisse](clr-etw-events.md)
